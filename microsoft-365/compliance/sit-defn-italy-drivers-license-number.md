---
title: İtalya sürücü lisans numarası varlık tanımı
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
description: İtalya sürücü lisans numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: a2a64aa45ff974ca085174961d955ed5a0e16229
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948954"
---
# <a name="italy-drivers-license-number"></a>İtalya sürücü lisans numarası

Bu tür varlık, AB Sürücü Lisans Numarası hassas bilgi türüne dahil edilir. Tek başına hassas bilgi türü varlığı olarak da kullanılabilir.

## <a name="format"></a>Biçim

10 harf ve rakamın birleşimi

## <a name="pattern"></a>Desen

10 harf ve rakamın birleşimi:

- bir harf (büyük/küçük harfe duyarlı değil)
- "A" veya "V" harfi (büyük/küçük harfe duyarlı değil)
- yedi basamak
- bir harf (büyük/küçük harfe duyarlı değil)

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade `Regex_italy_drivers_license_number` , desenle eşleşen içeriği bulur.
- veya `Keyword_italy_drivers_license_number` anahtar `Keywords_eu_driver's_license_number` sözcüğü bulunur.

```xml
    <!-- Italy Driver's license Number -->
    <Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keyword_italy_drivers_license_number" />
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

### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- numero di patente
- patente di guida
- patent guida
- patenti di guida
- patenti guida