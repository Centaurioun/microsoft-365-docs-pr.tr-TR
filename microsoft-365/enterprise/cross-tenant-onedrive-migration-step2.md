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
ms.openlocfilehash: 2f2a298178048eed82f4de4638ff94c19dfcfeda
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806276"
---
# <a name="step-2-cross-tenant-onedrive-migration---establishing-trust-between-the-source-and-target-tenants"></a>2. Adım: Kiracılar arası OneDrive geçişi - Kaynak ve hedef kiracılar arasında güven oluşturma

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