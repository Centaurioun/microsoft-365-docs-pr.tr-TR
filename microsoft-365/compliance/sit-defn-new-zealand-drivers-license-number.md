---
title: Yeni Zelanda sürücü lisans numarası varlık tanımı
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Yeni Zelanda ehliyet numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 6e136663fa6a47b2da8a7742f4ac73603efac3b1
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67368619"
---
# <a name="new-zealand-drivers-license-number"></a>Yeni Zelanda ehliyet numarası

## <a name="format"></a>Biçim

sekiz karakterli alfasayısal desen

## <a name="pattern"></a>Desen

sekiz karakterli alfasayısal desen

- iki harf
- altı basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_newzealand_driver_license_number`, desenle eşleşen içeriği bulur.
- `Keywords_newzealand_driver_license_number` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- İşlev `Func_newzealand_driver_license_number`, desenle eşleşen içeriği bulur.

```xml
      <!-- New Zealand Driver License Number -->
      <Entity id="1924b377-d287-49c9-a737-cfe7a8a2615a" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
          <Match idRef="Keywords_newzealand_driver_license_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_new_zealand_drivers_license_number"></a>Keyword_new_zealand_drivers_license_number

- sürücülik
- driverlicences
- sürücü lic
- sürücü lisansı
- sürücü lisansları
- sürücüler
- sürücüler
- sürücüler
- sürücüler lic
- sürücüler lics
- sürücü lisansı
- sürücü lisansları
- driver'lic
- driver'lics
- sürücü belgesi
- sürücü lisansları
- driver'lic
- sürücü lisansları
- sürücü belgesi
- sürücü lisansları
- driver'slic
- sürücü dilimleri
- sürücü dilimi
- sürücü dilimleri
- sürücü lic
- sürücü lics
- sürücü belgesi
- sürücü lisansları
- sürücü #
- driverlics #
- sürücülik #
- driverlicences #
- sürücü lic #
- sürücü lisansları #
- sürücü lisansı #
- sürücü lisansları #
- sürücüler #
- sürücüler #
- sürücüler #
- sürücüler #
- sürücüler lic #
- sürücüler lics #
- sürücü lisansı #
- sürücü lisansları #
- driver'lic #
- driver'lics #
- sürücü belgesi #
- sürücü lisansları #
- driver'lic #
- sürücü lisansları #
- sürücü belgesi #
- sürücü lisansları #
- driver'slic #
- sürücü dilimleri #
- sürücü dilimi #
- sürücü dilimleri #
- sürücü lic #
- sürücü lics #
- sürücü belgesi #
- sürücü lisansları #
- uluslararası sürüş izni
- uluslararası sürüş izinleri
- nz automobile association
- new zealand automobile association