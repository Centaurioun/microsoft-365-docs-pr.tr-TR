---
title: Macaristan sürücüleri lisans numarası varlık tanımı
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
description: Macaristan sürücü lisans numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: b1e679c5a56092818807ba464603ac2742736c16
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68380590"
---
# <a name="hungary-drivers-license-number"></a>Macaristan ehliyet numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

İki harf ve ardından altı basamak

## <a name="pattern"></a>Desen

İki harf ve altı basamak:

- İki harf (büyük/küçük harfe duyarlı değil)
- Altı basamak

## <a name="checksum"></a>Sağlama Toplamı

Hayır

### <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- Normal ifade `Regex_hungary_eu_driver's_license_number` , desenle eşleşen içeriği bulur.
- veya `Keywords_hungary_eu_driver's_license_number` anahtar `Keywords_eu_driver's_license_number` sözcüğü bulunur.

```xml
      <Entity id="9d31c46b-6e6b-444c-aeb1-6dd7e604bb24" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_hungary_eu_driver's_license_number" />
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

### <a name="keywords_hungary_eu_drivers_license_number"></a>Keywords_hungary_eu_driver s_license_number

- vezetoi engedely
- vezetői engedély
- vezetői engedélyek
