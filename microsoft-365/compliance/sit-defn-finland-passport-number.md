---
title: Finlandiya pasaport numarası varlık tanımı
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
description: Finlandiya pasaport numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: d8994d4af43d391a800b33b16b18e8521b53e6a6
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948326"
---
# <a name="finland-passport-number"></a>Finlandiya pasaport numarası

Bu varlık AB Pasaport Numarası hassas bilgi türünde kullanılabilir ve tek başına hassas bilgi türü varlığı olarak kullanılabilir.

## <a name="format"></a>Biçim

dokuz harf ve rakamın birleşimi

## <a name="pattern"></a>Desen

dokuz harf ve rakamın birleşimi:

- iki harf (büyük/küçük harfe duyarlı değil)
- yedi basamak

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- Normal ifade `Regex_finland_passport_number` , desenle eşleşen içeriği bulur.
- veya `Keyword_finland_passport_number` anahtar `Keywords_eu_passport_number` sözcüğü bulunur.
- Normal ifade `Regex_eu_passport_date1` tarihi DD.AA.YYYY biçiminde bulur veya bir `Keywords_eu_passport_date` anahtar sözcük bulunur

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade `Regex_finland_passport_number` , desenle eşleşen içeriği bulur.
- veya `Keyword_finland_passport_number` anahtar `Keywords_eu_passport_number` sözcüğü bulunur.

```xml
      <!-- Finland Passport Number -->
      <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- Pasaport #
- Pasaport #
- passportid
- Pasaport
- passportno
- pasaport no
- passportnumber
- pasaport numarası
- passportnumbers
- pasaport numaraları

### <a name="keyword_finland_passport_number"></a>Keyword_finland_passport_number

- suomalainen passi
- passin numero
- çok sayıda geçiş. #
- passin numero #
- çok sayıda geçiş.
- passi #
- passi numarası

### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- sorun tarihi
- süre sonu tarihi