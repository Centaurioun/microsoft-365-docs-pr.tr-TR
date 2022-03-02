---
title: Etki alanına katılmış Windows 10 cihazları işletmeler için Kurumsal tarafından yönetil Microsoft 365 etkinleştirme
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
description: Yalnızca birkaç adımda Microsoft 365 Active-Directory'ye katılmış yerel Windows 10 cihazlarını korumayı öğrenin.
ms.openlocfilehash: f0af270bc46d09de84e57ffb63c3b72e351c5bfa
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2021
ms.locfileid: "62973583"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Etki alanına katılmış Windows 10 cihazları başka bir kullanıcı tarafından yönetil Microsoft 365 İş Ekstra

Kuruluşta şirket Windows Server Active Directory kullanıyorsa, Windows 10 cihazlarınızı korumak için Microsoft 365 İş Ekstra'i kurabilirsiniz ve bu sırada yerel kimlik doğrulaması gerektiren şirket içi kaynaklara erişimi de koruyabilirsiniz.
Bu korumayı ayarlamak için Azure **AD'ye katılan Karma cihazları kullanabilirsiniz**. Bu cihazlar hem şirket içi Active Directory'nize hem de kullanıcılarınıza Azure Active Directory.

## <a name="watch-configure-hybrid-azure-active-directory-join"></a>İzle: Karma kimlik Azure Active Directory yapılandırma

Bu videoda, bunu en yaygın senaryo için ayarlama adımları açıklanan ve aşağıdaki adımlarda da ayrıntılı olarak açıklanan bir anlatı yer almaktadır.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="before-you-begin"></a>Başlamadan önce

- Azure AD hizmetleriyle kullanıcıları Azure AD'ye Bağlan.
- Azure AD Kurumsal Bağlan (OU) eşitlemeyi tamamlama.
- Eşitle hesabı olan tüm etki alanı kullanıcılarının lisanslarının olduğundan Microsoft 365 İş Ekstra.

Adımlar [için bkz. Etki alanı kullanıcılarını Microsoft](manage-domain-users.md) ile eşitleme.

## <a name="1-verify-mdm-authority-in-intune"></a>1. Intune'da MDM Yetkilisini doğrulama

Genel [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) gidin ve Microsoft Intune Cihaz kaydı'na **tıklayın, ardından** Genel Bakış sayfasında **MDM yetkilisinin** **Intune olduğundan emin olun**.

- **MDM yetkilisi Yok** **ise**, **MDM yetkilisini** tıklatın ve bunu **Intune olarak ayarlayın**.
- **MDM** yetkilisi **Microsoft Office 365** ise **DevicesEnroll**  >  cihazlar'a gidin ve **intune MDM** yetkilisini eklemek için sağlarda yer alan **MDM** yetkili ekle iletişim kutusunu kullanın (**MDM** Yetkili Ekle iletişim kutusu yalnızca **MDM** Yetkilisi Ekle seçeneği Microsoft Office 365).

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Bilgisayarları birleştirme için Azure AD'nin etkinleştirildiğinden emin olun

- Yönetim merkezi'ne gidin ve <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> Yönetim **Azure Active Directory** listesinden Genel Azure Active Directory'ı seçin (**Azure Active Directory'ı** seçin). 
- Uygulama Azure Active Directory **gidin, Cihazlar'ı** ve **Azure Active Directory** **Ayarlar'ı seçin**.
- **VerifyUsers may join devices to Azure AD** is enabled 
    1. Tüm kullanıcıları etkinleştirmek için, Herkes olarak **ayarlayın**.
    2. Belirli kullanıcıları etkinleştirmek için, belirli bir **kullanıcı** grubunu etkinleştirmek üzere Seçili olarak ayarlayın.
        - Azure AD'de eşitlenen istenen etki alanı kullanıcılarını bir güvenlik [grubuna ekleyin](../../admin/create-groups/create-groups.md).
        - Bu **güvenlik grubu için** MDM kullanıcı kapsamını etkinleştirmek için Grupları seç'i seçin.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. MDM için Azure AD'nin etkinleştirildiğinden emin olun

- Yönetim merkezine gidip Uç Nokta Yönetimi'ni <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **seçin** (Uç nokta görünmüyorsa  **Endpoint Manager'i** seçin)
- Genel **Microsoft Endpoint Manager, Cihazlar,Windows** >  >  **Windows Yazdırma** >  **Kaydı'na gidin**.
- MDM kullanıcı kapsamının etkinleştirildiğinden emin olun.

    1. Tüm bilgisayarları kaydetmek için, Azure AD'ye katılmış tüm kullanıcı bilgisayarlarını ve kullanıcılar Windows'e iş hesabı ekleyeni yeni bilgisayarlara otomatik olarak kaydeden Tüm Windows.
    2. Belirli bir **kullanıcı** grubunun bilgisayarlarını kaydetmek için Bazıları olarak ayarlayın.
        -  Azure AD'de eşitlenen istenen etki alanı kullanıcılarını bir güvenlik [grubuna ekleyin](../create-groups/create-groups.md).
        -  Bu **güvenlik grubu için** MDM kullanıcı kapsamını etkinleştirmek için Grupları seç'i seçin.

## <a name="4-create-the-required-resources"></a>4. Gerekli kaynakları oluşturma 

Karma [Azure AD](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) birleştirmesini yapılandırmak için gereken görevlerin gerçekleştirilip[, SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell modülünde bulunan [Initialize-SecMtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet'i kullanımı basitleştirildi. Bu cmdlet'i çağırıldığında, gerekli hizmet bağlantı noktası ve grup ilkesi oluşturulacak ve yapılandırılır.

Bu modülü, bir PowerShell örneğinden aşağıdakini faturalamaya göre yükleyebilirsiniz:

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> Bu modülü, Azure AD Bağlan çalıştıran Windows Server'a yüklemeniz önerilir.

Gerekli hizmet bağlantı noktası ve grup ilkesi oluşturmak için  [, Başlat-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet'ini çağırmış olursunuz. Bu görevi yerine Microsoft 365 İş Ekstra yönetici kimlik bilgileriniz gerekir. Kaynakları oluşturmak için hazır olduğunda, aşağıdakini çağırın:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

İlk komut Microsoft bulut ile bağlantı kuracak ve sizden istendiğinde genel yönetici Microsoft 365 İş Ekstra belirtecek.

## <a name="5-link-the-group-policy"></a>5. Grup İlkesini Bağlama

1. Grup İlkesi Yönetim Konsolu'nda (GPMC), ilkeyi bağlamayı istediğiniz konuma sağ tıklayın ve bağlam menüsünde Var olan *bir GPO'ya bağlantı...* öğesini seçin.
2. Yukarıdaki adımda oluşturulan ilkeyi seçin ve Tamam'a **tıklayın**.

## <a name="get-the-latest-administrative-templates"></a>En son Yönetim Şablonlarını Al

Otomatik **MDM kaydı varsayılan Azure AD** kimlik bilgilerini kullanarak etkinleştir ayarını görmüyorsanız, bunun nedeni Windows 10, sürüm 1803 veya sonraki sürümlerde ADMX'in yüklü olması olabilir. Sorunu düzeltmek için şu adımları izleyin (Not: en son MDM.admx geriye dönük uyumlu):

1. İndir: [Ekim 2020 Güncelleştirmesi'Windows 10 Yönetim Şablonları (.admx)](https://www.microsoft.com/download/102157)
2. Paketi Etki Alanı Denetleyicisi'ne yükleyin.
3. Yönetim Şablonları sürümüne bağlı olarak şu klasöre gidin: **C:\Program Files (x86)\Microsoft Grup İlkesi\Windows 10 Ekim 2020 Güncelleştirmesi (20H2)**.
4. Yukarıdaki yolda **İlke Tanımları** klasörünü **PolicyDefinitions olarak yeniden adlandırabilirsiniz**.
5. **SysVOL paylaşımınıza PolicyDefinitions** klasörünü kopyalayın; varsayılan olarak **C:\Windows\SYSVOL\domain\Policies konumundadır**.
   - Tüm etki alanınız için merkezi bir ilke deposu kullanmayı planlıyorsanız, PolicyDefinitions içeriğini oraya ekleyin.
6. Birden fazla Etki Alanı Denetleyicisi olması durumunda, ilkelerin kullanılabilir olması için SYSVOL'nin çoğaltmasını bekleyin. Bu yordam, Yönetim Şablonlarının gelecek tüm sürümü için de kullanılabilir.

Bu noktada, Varsayılan Azure AD kimlik bilgilerini kullanarak otomatik **MDM kaydı etkinleştir'i görüyor olması** gerekir.

## <a name="related-content"></a>İlgili içerik

[Etki alanı kullanıcılarını yeni Microsoft 365](manage-domain-users.md) (makale)\
[Yönetim merkezinde grup oluşturma](../create-groups/create-groups.md) (makale)\
[Öğretici: Yönetilen etki Azure Active Directory için karma etki alanlarını yapılandırma](/azure/active-directory/devices/hybrid-azuread-join-managed-domains) (makale)