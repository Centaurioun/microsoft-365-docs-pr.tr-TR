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
ms.openlocfilehash: 6a42b833ecfc59d96f69d5061a0e6fe64746a8c6
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806173"
---
# <a name="step-3-cross-tenant-onedrive-migration---verifying-trust"></a>3. Adım: Kiracılar arası OneDrive geçişi - Güveni doğrulama

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