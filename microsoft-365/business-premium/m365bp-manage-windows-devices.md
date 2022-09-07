---
title: İşletmeler için Microsoft 365 tarafından yönetilecek etki alanına katılmış Windows 10 cihazlarını etkinleştirme
f1.keywords:
- CSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-business
ms.subservice: business-premium
ms.localizationpriority: high
ms.date: 07/19/2022
ms.collection: ''
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
description: Yalnızca birkaç adımda Yerel Active Directory'ye katılmış Windows 10 cihazları korumak için Microsoft 365'i etkinleştirmeyi öğrenin.
ms.openlocfilehash: fd49bdd0ca866644c39e7e2a52d2061f6bee1b01
ms.sourcegitcommit: 651610ca73bfd1d008d97311b59782790df664fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2022
ms.locfileid: "67612691"
---
# <a name="manage-windows-devices-with-microsoft-365-business-premium"></a>windows cihazlarını Microsoft 365 İş Ekstra ile yönetme

Kuruluşunuz şirket içi Windows Server Active Directory kullanıyorsa, Yerel kimlik doğrulaması gerektiren şirket içi kaynaklara erişimi korurken Windows cihazlarınızı korumak için Microsoft 365 İş Ekstra ayarlayabilirsiniz.

Bunu ayarlamak için **Karma Azure AD birleştirilmiş cihazları** uygulayın. Bu cihazlar hem şirket içi Active Directory hem de Azure Active Directory'nize katılır.

> [!NOTE]
> İş için Microsoft Defender, 1 Mart 2022'de başlayarak Microsoft 365 İş Ekstra müşterilerine dağıtılıyor. Bu teklif, cihazlar için ek güvenlik özellikleri sağlar. [İş için Defender hakkında daha fazla bilgi edinin](../security/defender-business/mdb-overview.md).

## <a name="watch-configure-hybrid-azure-active-directory-join"></a>İzleyin: Hibrit Azure Active Directory katılımını yapılandırma

Bu videoda, bunu en yaygın senaryo için ayarlama adımları açıklanır ve bu adımlar da aşağıdaki adımlarda ayrıntılı olarak açıklanmıştır.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="before-you-begin"></a>Başlamadan önce

- kullanıcıları Azure AD Connect ile Azure AD eşitleyin.
- Connect Kuruluş Birimi (OU) eşitlemesini Azure AD tamamlayın.
- Eşitlediğiniz tüm etki alanı kullanıcılarının Microsoft 365 İş Ekstra lisanslarına sahip olduğundan emin olun.

Adımlar için bkz. [Etki alanı kullanıcılarını Microsoft 365'e eşitleme](../admin/setup/manage-domain-users.md) .

## <a name="possible-device-actions-and-statuses"></a>Olası cihaz eylemleri ve durumları
  
![In the Device actions list, you can see the Devices states.](./../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)

Cihazlar ve ilişkili eylemleri aşağıdaki durumlara sahip olabilir:
  
|**Durum**|**Açıklama**|
|:-----|:-----|
|Intune tarafından yönetilen  |Microsoft 365 İş Ekstra tarafından yönetilir.  |
|Devre dışı bırakma bekliyor  |Microsoft 365 İş Ekstra, şirket verilerini cihazdan kaldırmaya hazırlanıyor.  |
|Devre dışı bırakma sürüyor  |Microsoft 365 İş Ekstra şu anda cihazdan şirket verilerini kaldırıyor.  |
|Devre dışı bırakma başarısız  | Şirket verilerini kaldırma işlemi başarısız oldu.  |
|Devre dışı bırakma iptal edildi  |Devre dışı bırakma eylemi iptal edildi.  |
|Temizleme işlemi beklemede  |Fabrika sıfırlamasının başlatılması bekleniyor.  |
|Temizleme işlemi sürüyor  |Fabrika sıfırlaması gönderildi.  |
|Temizleme başarısız oldu  |Fabrika sıfırlaması yapılamaz.  |
|Silme iptal edildi  |Fabrika silme işlemi iptal edildi.  |
|Uygun olmayan durumda  |Bir eylem beklemede (veya devam ediyor) ancak cihaz 30 günden fazla süreyle iade edilmemiştir.  |
|Silme bekliyor  |Silme eylemi bekliyor.  |
|Bulundu  |Microsoft 365 İş Ekstra cihazı algılamıştır.  |

## <a name="1-verify-mdm-authority-in-intune"></a>1. Intune'da MDM Yetkilisini Doğrulama

Microsoft Endpoint Manager yönetim merkezine ([https://endpoint.microsoft.com](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview)) gidin ve **Cihaz kaydı'nı** seçin, ardından **Genel Bakış** sayfasında **MDM yetkilisinin** **Intune** emin olun.

- **MDM yetkilisi** **Yok** ise, **Intune** olarak ayarlamak için **MDM yetkilisine** tıklayın.
- **MDM yetkilisi** **Microsoft Office 365** ise **Cihazlar Cihazları** > **kaydet'e** gidin ve sağ taraftaki **MDM yetkilisi ekle** iletişim kutusunu kullanarak **Intune MDM** yetkilisi ekleyin (**MDM Yetkilisi Ekle** iletişim kutusu yalnızca **MDM Yetkilisi** Microsoft Office 365 olarak ayarlandıysa kullanılabilir).

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. bilgisayarlara katılmak için Azure AD etkinleştirildiğini doğrulayın

1. konumundaki Microsoft 365 yönetim merkezi gidin ve Yönetici <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **merkezleri** listesinde **Azure Active Directory'yi** (Azure Active Directory görünmüyorsa tümünü göster'i seçin) seçin. 

2. **Azure Active Directory yönetim merkezinde Azure Active Directory'ye** gidin, **Cihazlar'ı** ve ardından **Cihaz ayarları'nı** seçin.

3. **Kullanıcıların Azure AD cihazlara katılabileceğini** doğrulama 

    1. Tüm kullanıcıları etkinleştirmek için **Tümü** olarak ayarlayın.

    2. Belirli kullanıcıları etkinleştirmek için, belirli bir kullanıcı grubunu etkinleştirmek için **Seçili** olarak ayarlayın.

        - Azure AD eşitlenen istenen etki alanı kullanıcılarını bir [güvenlik grubuna](../admin/create-groups/create-groups.md) ekleyin.

        - Bu güvenlik grubu için MDM kullanıcı kapsamını etkinleştirmek için **Grupları seçin'i** seçin.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. MDM için Azure AD etkinleştirildiğini doğrulayın

1. konumundaki Microsoft 365 yönetim merkezi <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> gidin ve **Uç Nokta Yönetimi'ni** seçin (**Endpoint Manager** görünmüyorsa **Tümünü göster'i** seçin)

2. **Microsoft Endpoint Manager yönetim merkezinde** **Cihazlar** > **Windows** > **Kaydı** > **Otomatik Kayıt'a** gidin.

3. MDM kullanıcı kapsamının etkinleştirildiğini doğrulayın.

    1. Tüm bilgisayarları kaydetmek için, kullanıcılar Windows'a bir iş hesabı eklediğinde Azure AD ve yeni bilgisayarlara katılmış tüm kullanıcı bilgisayarlarını otomatik olarak kaydetmek için **Tümü** olarak ayarlayın.
  
    2. Belirli bir kullanıcı grubunun bilgisayarlarını kaydetmek için **Bazıları** olarak ayarlayın.
  
        -  Azure AD eşitlenen istenen etki alanı kullanıcılarını bir [güvenlik grubuna](/admin/create-groups/create-groups.md) ekleyin.
  
       -  Bu güvenlik grubu için MDM kullanıcı kapsamını etkinleştirmek için **Grupları seçin'i** seçin.

## <a name="4-create-the-required-resources"></a>4. Gerekli kaynakları oluşturma 

[Karma Azure AD birleştirmeyi yapılandırmak](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) için gerekli görevlerin gerçekleştirilmesi[,](https://www.powershellgallery.com/packages/SecMgmt) SecMgmt PowerShell modülünde bulunan [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet'inin kullanılmasıyla basitleştirildi. Bu cmdlet'i çağırdığınızda gerekli hizmet bağlantı noktası ve grup ilkesi oluşturulur ve yapılandırılır.

Bir PowerShell örneğinden aşağıdakileri çağırarak bu modülü yükleyebilirsiniz:

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> Bu modülü Azure AD Connect çalıştıran Windows Server'a yükleyin.

Gerekli hizmet bağlantı noktasını ve grup ilkesini oluşturmak için  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet'ini çağıracaksınız. Bu görevi gerçekleştirirken Microsoft 365 İş Ekstra genel yönetici kimlik bilgileriniz gerekir. Kaynakları oluşturmaya hazır olduğunuzda aşağıdakileri çağırın:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

İlk komut Microsoft bulutuyla bağlantı kurar ve istendiğinde Microsoft 365 İş Ekstra genel yönetici kimlik bilgilerinizi belirtin.

## <a name="5-link-the-group-policy"></a>5. Grup ilkesini bağlama

1. grup ilkesi Yönetim Konsolu'nda (GPMC), ilkeyi bağlamak istediğiniz konuma sağ tıklayın ve bağlam *menüsünden Var olan bir GPO'yu bağla...* öğesini seçin.

2. Yukarıdaki adımda oluşturulan ilkeyi seçin ve **tamam'a** tıklayın.

## <a name="get-the-latest-administrative-templates"></a>En son yönetim şablonlarını alma

**Varsayılan Azure AD kimlik bilgilerini kullanarak otomatik MDM kaydını etkinleştir** ilkesini görmüyorsanız, bunun nedeni Windows 10, sürüm 1803 veya üzeri için ADMX'in yüklü olmaması olabilir. Sorunu düzeltmek için şu adımları izleyin (Not: En son MDM.admx geriye dönük olarak uyumludur):

1. İndir: [ekim 2020 güncelleştirmesi (20H2) için Windows 10 Yönetim Şablonları (.admx).](https://www.microsoft.com/download/102157)

2. Paketi bir Etki Alanı Denetleyicisine yükleyin.

3. Yönetim Şablonları sürümüne bağlı olarak şu klasöre gidin: **C:\Program Files (x86)\Microsoft grup ilkesi\Windows 10 Ekim 2020 Güncelleştirmesi (20H2)**.

4. Yukarıdaki yoldaki **İlke Tanımları** klasörünü **PolicyDefinitions olarak yeniden adlandırın**.

5. **PolicyDefinitions** klasörünü varsayılan olarak konumunda `C:\Windows\SYSVOL\domain\Policies`bulunan SYSVOL paylaşımınıza kopyalayın.

   Etki alanınızın tamamı için merkezi bir ilke deposu kullanmayı planlıyorsanız, policyDefinitions içeriğini buraya ekleyin.

6. Birden fazla Etki Alanı Denetleyiciniz varsa, ilkelerin kullanılabilir olması için SYSVOL'un çoğaltılması için bekleyin. Bu yordam, Yönetim Şablonları'nın gelecekteki sürümleri için de çalışır.

Bu noktada **, varsayılan Azure AD kimlik bilgilerini kullanarak otomatik MDM kaydını etkinleştirme** ilkesini görebilmeniz gerekir.

## <a name="related-content"></a>İlgili içerik

- [Etki alanı kullanıcılarını Microsoft 365 ile eşitleme](../admin/setup/manage-domain-users.md)

- [Yönetim merkezinde grup oluşturma](../admin/create-groups/create-groups.md)

- [Öğretici: Yönetilen etki alanları için karma Azure Active Directory katılımını yapılandırma](/azure/active-directory/devices/hybrid-azuread-join-managed-domains)

- [Self servis parolaları ayarlama](../admin/add-users/let-users-reset-passwords.md)

- [Self servis grup yönetimini ayarlama](/azure/active-directory/enterprise-users/groups-self-service-management)

- [İş için Microsoft 365 planlarının güvenliğini sağlamaya yönelik en iyi yöntemler](../admin/security-and-compliance/secure-your-business-data.md)

## <a name="next-objective"></a>Sonraki hedef

[Office istemci dağıtımı hazırlığı](m365bp-prepare-for-office-client-deployment.md)