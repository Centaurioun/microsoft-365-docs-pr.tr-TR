---
title: Siber güvenlik araçlarına yönetici erişimini sınırlamak için Office 365 için Microsoft Defender'da Azure Privileged Identity Management (PIM) kullanın.
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 09/03/2021
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: high
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- m365-security
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Azure PIM'i tümleştirerek kullanıcılara Office 365 için Microsoft Defender'da yükseltilmiş ayrıcalık görevleri gerçekleştirmeleri için tam zamanında ve sınırlı erişim vermek ve verilerinize yönelik riski azaltmayı öğrenin.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: da1e105a218fe7885daf8e6e6059a5436695189e
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68633118"
---
<!--A-->
# <a name="privileged-identity-management-pim-and-why-to-use-it-with-microsoft-defender-for-office-365"></a>Privileged Identity Management (PIM) ve neden Office 365 için Microsoft Defender

Privileged Identity Management (PIM), ayarlandıktan sonra belirli bir görevin yapılabilmesi için kullanıcılara sınırlı bir süre boyunca (zaman kutulu zaman aralığı olarak da adlandırılır) verilere erişim sağlayan bir Azure özelliğidir. Bu erişim, gerekli eylemi gerçekleştirmek için "tam zamanında" verilir ve ardından iptal edilir. PIM, verilere ve diğer ayarlara uzun süreli erişimi olan ayrıcalıklı yönetim hesaplarıyla karşılaştırıldığında, kullanıcının hassas verilere erişimi ve süresini sınırlayarak açığa çıkarma riskini azaltır. Peki bu özelliği (PIM) Office 365 için Microsoft Defender ile birlikte nasıl kullanabiliriz?

> [!TIP]
> PIM erişiminin kapsamı rol ve kimlik düzeyine göre belirlenir ve birden çok görev tamamlanmasını sağlar. Görev düzeyinde kapsamı belirlenmiş Privileged Access Management (PAM) ile karıştırılmamalıdır.

## <a name="steps-to-use-pim-to-grant-just-in-time-access-to-defender-for-office-365-related-tasks"></a>İlgili Office 365 için Defender görevlere tam zamanında erişim vermek için PIM kullanma adımları

Yöneticiler, PIM'i Office 365 için Defender ile çalışacak şekilde ayarlayarak kullanıcının ihtiyaç duyduğu eylemleri gerçekleştirmesi için erişim istemesi için bir işlem oluşturur. Kullanıcı ayrıcalıklarının yükseltilmesi gereksinimini *haklı çıkarmalıdır* .

Bu örnekte güvenlik ekibimizin bir üyesi olan ve Office 365 içinde sıfır erişime sahip olacak ancak [tehdit avcılığı](threat-hunting-in-threat-explorer.md) gibi normal günlük işlemler için gerekli olan bir role hem de [kötü amaçlı teslim edilen e-postayı düzeltme](remediate-malicious-email-delivered-office-365.md) gibi daha az sık ama hassas işlemler gerektiğinde daha yüksek bir ayrıcalık düzeyine yükseltebilen "Alex" öğesini yapılandıracağız.

> [!NOTE]
> Bu, Office 365 için Microsoft Defender'de Tehdit Gezgini'ni kullanarak e-postaları temizleme olanağı gerektiren bir Güvenlik Analisti için PIM'i ayarlamak için gereken adımlarda size yol gösterir, ancak aynı adımlar Güvenlik ve Uyumluluk portalındaki diğer RBAC rolleri için de kullanılabilir. Örneğin bu işlem, eBulma'da arama ve olay çalışması gerçekleştirmek için gündelik erişim gerektiren ancak kiracıdan verileri dışarı aktarmak için yalnızca zaman zaman yükseltilmiş haklara ihtiyaç duyan bir bilgi çalışanı için kullanılabilir.

***1. Adım***. Aboneliğinizin Azure PIM konsolunda kullanıcıyı (Alex) Azure Güvenlik Okuyucusu rolüne ekleyin ve etkinleştirmeyle ilgili güvenlik ayarlarını yapılandırın.

1. [Azure AD Yönetici Merkezi'nde](https://aad.portal.azure.com/) oturum açın ve **Azure Active Directory** > **Rolleri ve yöneticileri'ni** seçin.
2. Rol **listesinden Güvenlik Okuyucusu'na** ve ardından **Ayarlar** > **Düzenle'ye tıklayın**
3. **Azure MFA** **gerektirmek için 'Etkinleştirme maksimum süresi (saat)**' değerini normal bir çalışma gününe ve 'Etkinleştirme açık' olarak ayarlayın.
4. Bu Alex'in günlük işlemler için normal ayrıcalık düzeyi olduğundan Etkinleştirme için **gerekçe gerektir'in** > **Güncelleştirme** seçeneğini kaldıracağız.
5. **Ödev** >  Ekle **Üye seçilmedi'yi** seçin > doğru üyeyi aramak için adı seçin veya yazın.
6. PIM ayrıcalıkları için eklemeniz gereken üyeyi seçmek için **Seç** düğmesine tıklayın > Atama Ekle sayfasında değişiklik > **İleri'ye** tıklayın (hem atama türü *Uygun* hem de *Süre Kalıcı Olarak Uygun* varsayılanlar) ve **Ata'ya tıklayın**.

Kullanıcınızın adı (burada 'Alex'), sonraki sayfada Uygun atamalar altında görünür; bu, daha önce yapılandırılan ayarlarla rolde PIM yapabilecekleri anlamına gelir.

> [!NOTE]
> Privileged Identity Management hızlı bir şekilde gözden geçirmek için [bu videoya](https://www.youtube.com/watch?v=VQMAg0sa_lE) bakın.

:::image type="content" source="../../media/pim-mdo-role-setting-details-for-security-reader-show-8-hr-duration.png" alt-text="Rol ayarı ayrıntıları - Güvenlik Okuyucusu sayfası" lightbox="../../media/pim-mdo-role-setting-details-for-security-reader-show-8-hr-duration.png":::

***2. Adım***. Ek görevler için gerekli ikinci (yükseltilmiş) izin grubunu oluşturun ve uygunluk atayın.

[Privileged Access gruplarını](/azure/active-directory/privileged-identity-management/groups-features) kullanarak artık kendi özel gruplarımızı oluşturabilir, izinleri birleştirebilir veya kuruluş uygulamalarınızı ve gereksinimlerinizi karşılamak için gereken yerlerde ayrıntı düzeyini artırabiliriz.

### <a name="create-a-role-group-requiring-the-permissions-we-need"></a>İhtiyacımız olan izinleri gerektiren bir rol grubu oluşturma

Microsoft 365 Defender portalında, istediğimiz izinleri içeren özel bir rol grubu oluşturun.

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**İzinler & Roller'e** gidin ve **Email ve İşbirliği** altında **Roller'i** seçin. **doğrudan İzinler** sayfasına gitmek için kullanın<https://security.microsoft.com/emailandcollabpermissions>.
2. **İzinler** sayfasında Oluştur simgesine tıklayın![.](../../media/m365-cc-sc-create-icon.png) **Oluştur'u seçin**.
3. Grubunuzu amacını yansıtacak şekilde adlandırarak 'PIM'i Ara ve Temizle' gibi bir ad verin.
4. Üye eklemeyin, grubu kaydedin ve bir sonraki bölüme geçin!

### <a name="create-the-security-group-in-azure-ad-for-elevated-permissions"></a>Yükseltilmiş izinler için Azure AD'de güvenlik grubunu oluşturma

1. [Azure AD Yönetici Merkezi'ne](https://aad.portal.azure.com/) geri gidin ve **Azure AD** >  **Groups** > **Yeni Grubu'na** gidin.
2. Azure AD grubunuzu amacını yansıtacak şekilde adlandır, şu anda **sahip veya üye gerekmez**.
3. **Azure AD rolleri gruba** **Evet** olarak atayabilirsiniz.
4. Hiçbir rol, üye veya sahip eklemeyin, grubu oluşturun.
5. Yeni oluşturduğunuz gruba Geri dön ve **Ayrıcalıklı Erişim Ayrıcalıklı Erişimi** > **Etkinleştir'i** seçin.
6. Grubun içinde **Uygun atamalar** > **Atama ekle'yi** seçin > Arama & Temizleme'ye ihtiyacı olan kullanıcıyı **Üye** rolü olarak ekleyin.
7. Grubun Ayrıcalıklı Erişim **bölmesindeki Ayarlar'ı** yapılandırın. **Üye** rolünün ayarlarını **düzenle'yi** seçin.
8. Etkinleştirme süresini kuruluşunuza uyacak şekilde değiştirin. Bu örnekte **Güncelleştir'i** seçmeden önce *Azure MFA*, *gerekçe* ve *bilet bilgileri* gerekir.

### <a name="nest-the-newly-created-security-group-into-the-role-group"></a>Yeni oluşturulan güvenlik grubunu rol grubuna iç içe yerleştirme

1. [Güvenlik & Uyumluluğu PowerShell'e bağlanın](/powershell/exchange/connect-to-scc-powershell) ve aşağıdaki komutu çalıştırın:

   ```powershell
   Add-RoleGroupMember "<<Role Group Name>>" -Member "<<Azure Security Group>>"`
   ```

## <a name="test-your-configuration-of-pim-with-defender-for-office-365"></a>Office 365 için Defender ile PIM yapılandırmanızı test edin

1. Bu noktada [Microsoft 365 Defender portalında](/microsoft-365/security/defender/overview-security-center) yönetici erişimi olmaması gereken test kullanıcısı (Alex) ile oturum açın.
2. Kullanıcının günlük güvenlik okuyucusu rolünü etkinleştirebileceği PIM'e gidin.
3. Tehdit Gezgini'yi kullanarak bir e-postayı temizlemeye çalışırsanız ek izinlere ihtiyacınız olduğunu belirten bir hata alırsınız.
4. PIM, daha yükseltilmiş role ikinci kez girer ve kısa bir gecikmeden sonra artık e-postaları sorunsuz bir şekilde temizleyebilirsiniz.

   :::image type="content" source="../../media/pim-mdo-add-the-search-and-purge-role-assignment-to-this-pim-role.PNG" alt-text="Email sekmesinin altındaki Eylemler bölmesi" lightbox="../../media/pim-mdo-add-the-search-and-purge-role-assignment-to-this-pim-role.PNG":::

Arama ve Temizleme Rolü gibi yönetim rollerinin ve izinlerinin kalıcı olarak atanması Sıfır Güven güvenlik girişiminde yer almaz, ancak gördüğünüz gibi PIM, gerekli araç kümesine tam zamanında erişim vermek için kullanılabilir.

*Bu içerik için kullanılan blog gönderisine ve kaynaklara erişim için Müşteri Mühendisi Ben Harris'e teşekkür ederiz.*

<!--A-->
