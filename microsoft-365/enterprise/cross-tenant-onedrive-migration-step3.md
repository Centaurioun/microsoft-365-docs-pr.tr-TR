---
title: OneDrive Kiracılar Arası Kullanıcı Verileri Geçişi 3. Adım
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
description: OneDrive Kiracılar arası geçiş özelliğinin 3. adımı
ms.openlocfilehash: c59706de4300f6c505582b74aef4ec7223fb3d08
ms.sourcegitcommit: b386eaa33e1e5cdea59916247082b6e6e6a3d99e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68807771"
---
# <a name="step-3-verifying-trust"></a>3. Adım: Güveni doğrulama

Bu, Kiracılar Arası OneDrive geçişini tamamlamak için tasarlanmış bir çözümdeki 3. Adımdır. Daha fazla bilgi için bkz. [Kiracılar arası OneDrive geçişine genel bakış](cross-tenant-onedrive-migration.md).

- 1. Adım: [Kaynağa ve hedef kiracılara bağlanma](cross-tenant-onedrive-migration-step1.md)
- 2. Adım: [Kaynak ile hedef kiracı arasında güven oluşturma](cross-tenant-onedrive-migration-step2.md) 
- **3. Adım: [Güvenin kurulduğunu doğrulama](cross-tenant-onedrive-migration-step3.md)** 
- 4. Adım: [Kullanıcıları ve grupları önceden oluşturma](cross-tenant-onedrive-migration-step4.md)  
- 5. Adım: [Kimlik eşlemesini hazırlama](cross-tenant-onedrive-migration-step5.md)
- 6. Adım: [Kiracılar arası OneDrive geçişi başlatma](cross-tenant-onedrive-migration-step6.md)
- 7. Adım: [Geçiş sonrası adımları](cross-tenant-onedrive-migration-step7.md)

Geçiş işlemine devam etmeden önce güvenin tamam olduğunu doğrulamanız gerekir. *GoodToProceed* durumu, güvenin doğrulandığını onaylar.

## <a name="to-verify-trust-has-been-established"></a>Güvenin kurulduğunu doğrulamak için

1. **Kaynak kiracıda** komutunu çalıştırın:
 
```powershell

Verify-SPOCrossTenantRelationship -Scenario MnA -PartnerRole Target -PartnerCrossTenantHostUrl <TARGETCrossTenantHostUrl>

```
2. **Hedef kiracıda** komutunu çalıştırın:

```powershell 

Verify-SPOCrossTenantRelationship -Scenario MnA -PartnerRole Source -PartnerCrossTenantHostUrl <SOURCECrossTenantHostUrl>
```

## <a name="troubleshooting-trust-issues"></a>Güven sorunlarını giderme

Güven doğrularken olası değerler

|Değer|Açıklama|
|:-----|:-----|
|NotEstablished|Yerel olarak güven istenmedi.|
|NotEstablishedByPartner|Güven iş ortağı tarafından istenmedi|
|DormantByPartner|İş ortağının istenen güveni oluşturulduktan sonraki yedi günlük bekleme süresi içindedir.|
|CouldNotContactPartner|Durumu belirlemek için iş ortağıyla iletişim kurulamadı.|
|GoodToProceed|Devam etmek için doğrulandı.|


## <a name="step-4-pre-create-users-and-groups"></a>4. Adım: [Kullanıcıları ve grupları önceden oluşturma](cross-tenant-onedrive-migration-step4.md)