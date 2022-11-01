---
title: OneDrive Kiracılar Arası Kullanıcı Verileri Geçişi 2. Adım
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
description: OneDrive Kiracılar arası geçiş özelliğinin 2. adımı
ms.openlocfilehash: 424636e01b89420979752c7c9b0e61d778319725
ms.sourcegitcommit: b386eaa33e1e5cdea59916247082b6e6e6a3d99e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68807639"
---
# <a name="step-2-establishing-trust-between-the-source-and-target-tenants"></a>2. Adım: Kaynak ve hedef kiracılar arasında güven oluşturma

Bu, Kiracılar Arası OneDrive geçişini tamamlamak için tasarlanmış bir çözümdeki 2. Adımdır. Daha fazla bilgi için bkz. [Kiracılar arası OneDrive geçişine genel bakış](cross-tenant-onedrive-migration.md).

- 1. Adım: [Kaynağa ve hedef kiracılara bağlanma](cross-tenant-onedrive-migration-step1.md)
- **2. Adım: [Kaynak ile hedef kiracı arasında güven oluşturma](cross-tenant-onedrive-migration-step2.md)** 
- 3. Adım: [Güvenin kurulduğunu doğrulama](cross-tenant-onedrive-migration-step3.md) 
- 4. Adım: [Kullanıcıları ve grupları önceden oluşturma](cross-tenant-onedrive-migration-step4.md)  
- 5. Adım: [Kimlik eşlemesini hazırlama](cross-tenant-onedrive-migration-step5.md)
- 6. Adım: [Kiracılar arası OneDrive geçişi başlatma](cross-tenant-onedrive-migration-step6.md)
- 7. Adım: [Geçiş sonrası adımları](cross-tenant-onedrive-migration-step7.md)

Kaynak ve hedef kiracıya bağlandıktan sonra, kiracılar arası OneDrive geçişi gerçekleştirmenin bir sonraki adımı kiracılar arasında güven oluşturmaktır.

Güven oluşturmak için, her SharePoint Online kiracı yöneticisinin hem kaynak hem de hedef kiracılarda belirli komutları çalıştırması gerekir. Güven istendikten sonra hedef kiracının yöneticisi, başka bir kiracının güven ilişkisi kurmaya çalıştığını bildiren bir e-posta alır.

>[!Note]
>"trust" komutu SharePoint Online'a özgüdür. Yalnızca kaynak kiracıdaki SharePoint yöneticisine, tanımlanan hedef kiracıda OneDrive Geçişi işlemlerini yürütme izni verir. 
>
>*Güven vermek*, yöneticiye kaynak kiracı ile hedef kiracı arasında herhangi bir görünürlük, izin veya işbirliği yapma olanağı vermez. 

>[!Important]
>Microsoft 365 Multi-Geo müşterisiyseniz, geçiş projenizde yer alan her coğrafya arasında güven oluşturmanız gerekir.
>

## <a name="before-you-begin"></a>Başlamadan önce

Güven komutlarını çalıştırmadan önce hem kaynak hem de hedef kiracılar için kiracılar arası konak URL'lerini alın. Kaynaktan hedefe ve hedef kaynak arasında güven ilişkisi kurarken bu URL'lere ihtiyacınız olacaktır. 

**Kiracılar arası konak URL'lerini almak için:**

Hem kaynak hem de hedef kiracılarda şunu çalıştırın:

```powershell

Get-SPOCrossTenantHostURL
``` 

 
*Örnek:* Kaynak kiracıda komutunu çalıştırın:

 :::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-hosturl-source.png" alt-text="kaynak için ana bilgisayar URL'sini alma örneği":::

*Örnek:* Hedef kiracıda komutunu çalıştırın:

:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-hosturl-target.png" alt-text="hedef için ana bilgisayar URL'sini alma örneği":::
 


## <a name="run-the-trust-commands"></a>Güven komutlarını çalıştırma
Bu komutlar, güven oluşturmak istediğiniz kiracıya bir istek gönderir.

1. Kaynak kiracıda, hedef kiracıya bir güven isteği göndermek için şu komutu çalıştırın:

```powershell

Set-SPOCrossTenantRelationship -Scenario MnA -PartnerRole Target -PartnerCrossTenantHostUrl <TARGETCrossTenantHostUrl>
 
``` 

</br>

2. Hedef kiracıda, kaynak kiracıya bir güven isteği göndermek için şu komutu çalıştırın:

```powershell
Set-SPOCrossTenantRelationship -Scenario MnA -PartnerRole Source -PartnerCrossTenantHostUrl <SOURCECrossTenantHostUrl>
```

 
### <a name="parameter-definitions"></a>Parametre tanımları

|Parametre|Tanım|
|:-----|:-----|
|PartnerRole|Güven oluşturduğunuz iş ortağı kiracısının rolleri.  İş ortağı kiracısı OneDrive geçişlerinin kaynağıysa *kaynak* , *hedef* ise hedef olarak da iş ortağı kiracısını kullanın.
|PartnerCrossTenantHostURL|İş ortağı kiracısının kiracılar arası ana bilgisayar URL'si. İş ortağı kiracısı, kiracıların her birinde *Get-SPOCrossTenantHostURL* komutunu çalıştırarak bunu sizin için belirleyebilir.|

## <a name="sample-trust-email"></a>Örnek güven e-postası
Genel yöneticilere gönderilen e-posta örneğinde aşağıdakiler:


:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-trust-email.png" alt-text="güven e-postası örneği":::


**Konu:**  SPO Kiracısı [] [https://a830edad9050849mnaus093022-my.sharepoint.com/setuporupdate] Kuruluş İlişkisi [Scenario=MnA, Role=Source] bizimle

**İleti:**  SPO Kiracısı [] [https://a830edad9050849mnaus093022-my.sharepoint.com/setuporupdate] Kuruluş İlişkisi [Scenario=MnA, Role=Source] bizimle


## <a name="step-3-verify-that-trust-has-been-established"></a>3. Adım: [Güvenin kurulduğunu doğrulayın](cross-tenant-onedrive-migration-step3.md)