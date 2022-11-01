---
title: OneDrive Kiracılar Arası Kullanıcı Verileri Geçişi 6. Adım
ms.author: jhendr
author: JoanneHendrickson
manager: serdars
recommendations: true
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
ms.subservice: sharepoint-migration
ms.localizationpriority: high
ms.collection:
- SPMigration
- M365-collaboration
- m365initiative-migratetom365
search.appverid: MET150
description: OneDrive Kiracılar arası geçiş özelliğinin 6. adımı
ms.openlocfilehash: b12ff8d9b1aebcfa0286f7c1bc291586cb9c0f91
ms.sourcegitcommit: b386eaa33e1e5cdea59916247082b6e6e6a3d99e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68807727"
---
# <a name="step-6-start-a-onedrive-cross-tenant-migration"></a>6. Adım: OneDrive kiracılar arası geçişi başlatma

Bu, Kiracılar Arası OneDrive geçişini tamamlamak için tasarlanmış bir çözümdeki 6. Adımdır. Daha fazla bilgi için bkz. [Kiracılar arası OneDrive geçişine genel bakış](cross-tenant-onedrive-migration.md).

- 1. Adım: [Kaynağa ve hedef kiracılara bağlanma](cross-tenant-onedrive-migration-step1.md)
- 2. Adım: [Kaynak ile hedef kiracı arasında güven oluşturma](cross-tenant-onedrive-migration-step2.md) 
- 3. Adım: [Güvenin kurulduğunu doğrulama](cross-tenant-onedrive-migration-step3.md) 
- 4. Adım: [Kullanıcıları ve grupları önceden oluşturma](cross-tenant-onedrive-migration-step4.md)  
- 5. Adım: [Kimlik eşlemesini hazırlama](cross-tenant-onedrive-migration-step5.md)
- **6. Adım: [Kiracılar arası OneDrive geçişi başlatma](cross-tenant-onedrive-migration-step6.md)**
- 7. Adım: [Geçiş sonrası adımları](cross-tenant-onedrive-migration-step7.md)

Artık OneDrive geçişinizi başlatmaya hazırsınız.  Kiracılar arası geçişe başlamadan önce aşağıdaki adımları uygulayın. 

1. Uyumluluk durumunu doğruladığınızdan emin olun. Kaynak kiracınızda uyumlu bir durum görürseniz devam edebilirsiniz. Çalıştırmak:

```powershell
Get-SPOCrossTenantCompatibilityStatus –PartnerCrossTenantHostURL [Target tenant hostname]
```

2. Geçişi başlatmak için, kaynak kiracının SharePoint Online Yönetici veya Microsoft 365 Genel Yönetici aşağıdaki komutu çalıştırması gerekir:

```PowerShell
Start-SPOCrossTenantUserContentMove  -SourceUserPrincipalName <…> -TargetUserPrincipalName <…> -TargetCrossTenantHostUrl <…>
```

|Parametre|Açıklama|
|:-----|:-----|
|SourceUserPrincipalName|Kaynak kiracıda OneDrive'a sahip olan kullanıcının kullanıcı asıl adı.|
|TargetUserPrincipalName|Hedef kiracıda OneDrive'a sahip olan kullanıcının asıl adı.|
|TargetCrossTenantHostUrl|Hedef kiracının Kiracılar Arası Ana Bilgisayar URL'si. TargetCrossTenantHostUrl öğesini bulmak için kiracıda *Get-SPOCrossTenantHostUrl* komutunu çalıştırın.|

Örneğin:

```Powershell

Start-SPOCrossTenantUserContentMove -SourceUserPrincipalName DiegoS@M365x016651.OnMicrosoft.com -TargetUserPrincipalName
        Test-Diego@M365x946316.OnMicrosoft.com -TargetCrossTenantHostUrl https://m365x946316-my.sharepoint.com/ 

```

Geçişi daha sonraki bir zaman için zamanlamak için yukarıdaki komutu kullanabilir ve aşağıdaki parametrelerden biriyle ekleyebilirsiniz. 

Bu komutlar, OneDrive geçişlerinin toplu toplu işlemlerini planlarken yararlı olabilir.  Toplu iş başına en fazla 4.000 OneDrive geçişini kuyruğa alabilir/geçirebilirsiniz.  Kullanıcı sayınız 4.000'i aşarsa, ayrı toplu işlemler oluşturun ve geçerli toplu işlem tamamlanmaya yaklaştığında bunları çalışacak şekilde zamanlayın.

|Parametre|Açıklama|
|:-----|:-----|
|PreferredMoveBeginDate|Geçiş büyük olasılıkla belirtilen zamanda başlayacaktır. Saat Eşgüdümlü Evrensel Saat (UTC) içinde belirtilmelidir.|
|PreferredMoveEndDate|Geçiş büyük olasılıkla belirtilen zamana kadar en iyi çaba temelinde tamamlanacaktır. Saat Eşgüdümlü Evrensel Saat (UTC) içinde belirtilmelidir.|


## <a name="onedrive-status-pre-migration"></a>OneDrive durumu geçiş öncesi

Geçişe başlamadan önce, kullanıcıların geçerli kaynak OneDrive durumu aşağıdaki örneğe benzer olacaktır.  Bu örnek, geçerli dosya ve klasörlerini gösteren kullanıcı kaynak kiracısından alınıp verilmiştir.


:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-status-premigration.png" alt-text="geçiş öncesi durumu":::

## <a name="cancelling-a-onedrive-migration"></a>OneDrive geçişini iptal etme

Kullanıcının OneDrive'ının kiracılar arası geçişini durdurmak için aşağıdaki komutu kullanabilirsiniz; geçiş Sürüyor veya Başarı durumu değilse.

```powershell

Stop-SPOCrossTenantUserContentMove – SourceUserPrincipalName [UPN name of user who you wish to stop]

Stop-SPOCrossTenantUserContentMove – SourceUserPrincipalName DiegoS@M365x016651.OnMicrosoft.com
```

## <a name="determining-current-status-of-a-migration"></a>Geçişin geçerli durumunu belirleme

Geçişinizi başlattıktan sonra, kaynak VEYA hedef kiracıda aşağıdaki komutu kullanarak durumunu de kontrol edebilirsiniz:

**Kaynak komut biçimi**
```powershell

Get-SPOCrossTenantUserContentMoveState -PartnerCrossTenantHostURL [Target URL]
```
Örneğin:

```Powershell
Get-SPOCrossTenantUserContentMoveState -PartnerCrossTenantHostURL  https://m365x946316-my.sharepoint.com/

```

**Hedef komutu:** 

```powershell

Get-SPOCrossTenantUserContentMoveState -PartnerCrossTenantHostURL [Source URL]
Get-SPOCrossTenantUserContentMoveState -PartnerCrossTenantHostURL  https://m365x016551-my.sharepoint.com/
```

Belirli bir kullanıcının geçiş durumunu bulmak için *UserPrincipalName* parametresini kullanın:

```powershell

Get-SPOCrossTenantUserContentMoveState -PartnerCrossTenantHostURL <PartnerCrossTenantHostURL> -SourceUserPrincipalName <UPN>
Get-SPOUserAndContentMoveState -PartnerCrossTenantHostURL https://m365x946316-my.sharepoint.com -SourceUserPrincipalName DiegoS@M365x016651.OnMicrosoft.com
```

Taşıma işleminin durumunu belirli bir kullanıcının UPN'sine göre ancak daha fazla bilgiyle almak için *-Verbose* parametresini kullanın.

Örneğin:

```PowerShell

Get-SPOCrossTenantUserContentMoveState -PartnerCrossTenantHostURL https://ttesttenant-my.sharepoint.com -SourceUserPrincipalName User3@stesttenant.onmicrosoft.com -Verbose 

```


## <a name="migration-states"></a>Geçiş Durumları


|Durum|Açıklama|
|:-----|:-----|
|Başlamadı|Geçiş henüz başlamadı.|
|Planlanan|Geçiş artık kuyruktadır ve bir yuva kullanılabilir olduğunda çalışacak şekilde zamanlanır.|
|ReadytoTrigger|Geçiş, uçuş öncesi aşamasındadır ve kısa süre içinde Geçiş işlemini başlatacaktır.|
|InProgress|Geçiş işlemi aşağıdaki durumlardan birinde devam ediyor: </br>-Doğrulama </br>-Yedekleme </br>-Geri yükleme </br>-Temizleme|
|Başarı|Geçiş başarıyla tamamlandı.|
|Yeniden Zamanlandı|Geçiş tamamlanmamış olabilir ve başka bir geçiş için yeniden sorgulanmış olabilir.|
|Başarısız |Geçiş tamamlanamadı.|


 
## <a name="post-migration-status-checks"></a>Geçiş sonrası durum denetimleri

**Hedef kiracı:** Geçiş başarıyla tamamlandıktan sonra, yeni OneDrive hesabında oturum açarak hedef kiracıdaki kullanıcının durumunu denetleyin. 

**Kaynak kiracı:** Kullanıcı hedef kiracıya başarıyla geçiş yapmış olduğundan, artık kaynakta etkin bir OneDrive hesabı yoktur.


## <a name="step-7-post-migration-steps"></a>7. Adım: [Geçiş sonrası adımları](cross-tenant-onedrive-migration-step7.md)