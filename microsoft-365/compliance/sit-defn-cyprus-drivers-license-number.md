---
title: Kıbrıs sürücü lisans numarası varlık tanımı
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
- tier3
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Kıbrıs ehliyet numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: d4b442a9ce8b0233e24e88d9e20a46a030a5ec99
ms.sourcegitcommit: 2ff545246fec060ea7829da5afbc1cdc698d51ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68363419"
---
# <a name="cyprus-drivers-license-number"></a>Kıbrıs ehliyet numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

Boşluk ve sınırlayıcı içermeyen 12 basamak

## <a name="pattern"></a>Desen

12 basamak

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- Normal ifade `Regex_cyprus_eu_driver's_license_number` , desenle eşleşen içeriği bulur.
- veya `Keywords_cyprus_eu_driver's_license_number` anahtar `Keywords_eu_driver's_license_number` sözcüğü bulunur.

```xml
      <!-- Cyprus Driver's License Number -->
      <Entity id="356fa104-f9ac-4aff-a0e4-2e6e65ea06c4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- sürücü
- driverlics
- driverlicense
- sürücü lisansları
- sürücülik
- driverlicences
- sürücü lic
- sürücü lisansları
- sürücü lisansı
- sürücü lisansları
- sürücü lisansı
- sürücü lisansları
- sürücüler
- sürücüler
- sürücüler
- sürücüler
- driverslicense
- sürücü lisansları
- sürücüler lic
- sürücüler lics
- sürücü lisansı
- sürücü lisansları
- sürücü lisansı
- sürücü lisansları
- driver'lic
- driver'lics
- sürücü lisansı
- sürücü lisansları
- sürücü belgesi
- sürücü lisansları
- driver'lic
- sürücü lisansları
- sürücü lisansı
- sürücü lisansları
- sürücü belgesi
- sürücü lisansları
- driver'slic
- sürücü dilimleri
- driver'slicense
- driver'slicenses
- sürücü dilimi
- sürücü dilimleri
- sürücü lic
- sürücü lics
- sürücü belgesi
- sürücü lisansları
- sürücü belgesi
- sürücü lisansları
- Dl #
- Dls #
- sürücü #
- driverlics #
- driverlicense #
- sürücü lisansları #
- sürücülik #
- driverlicences #
- sürücü lic #
- sürücü lisansları #
- sürücü lisansı #
- sürücü lisansları #
- sürücü lisansları #
- sürücüler #
- sürücüler #
- driverslicense #
- sürücü lisansları #
- sürücüler #
- sürücüler #
- sürücüler lic #
- sürücüler lics #
- sürücü lisansı #
- sürücü lisansları #
- sürücü lisansı #
- sürücü lisansları #
- driver'lic #
- driver'lics #
- sürücü lisansı #
- sürücü lisansları #
- sürücü belgesi #
- sürücü lisansları #
- driver'lic #
- sürücü lisansları #
- sürücü lisansı #
- sürücü lisansları #
- sürücü belgesi #
- sürücü lisansları #
- driver'slic #
- sürücü dilimleri #
- driver'slicense #
- driver'slicenses #
- sürücü dilimi #
- sürücü dilimleri #
- sürücü lic #
- sürücü lics #
- sürücü belgesi #
- sürücü lisansları #
- sürücü belgesi #
- sürücü lisansları #
- Ehliyet
- Ehliyet
- dlno #
- driv lic
- driv licen
- driv lisansı
- driv lisansları
- driv lisansı
- driv lisansları
- sürücü lisans
- sürücüler lisans
- sürücü lisans
- sürüş lic
- sürüş licen
- sürücü lisansları
- Ehliyet
- ehliyetler
- sürüş izni
- dl no
- dlno
- dl numarası

### <a name="keywords_cyprus_eu_drivers_license_number"></a>Keywords_cyprus_eu_driver s_license_number

- άδεια οδήγησης
- αριθμό άδειας οδήγησης
- άδειες οδήγησης
