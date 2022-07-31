---
title: İsveç pasaport numarası varlık tanımı
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
description: İsveç pasaport numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 497965aea803a162fc97bb64fa456191f8788aab
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948327"
---
# <a name="sweden-passport-number"></a>İsveç pasaport numarası

## <a name="format"></a>Biçim

sekiz basamak

## <a name="pattern"></a>Desen

ardışık sekiz basamak

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- normal ifade Regex_sweden_passport_number desenle eşleşen içeriği bulur.
- veya `Keyword_sweden_passport` anahtar `Keywords_eu_passport_number` sözcüğü bulunur.
- normal ifade `Regex_sweden_eu_passport_date` DD MMM/AAA YY (01 OCA/JAN 12) biçiminde bir tarih bulur veya bir `Keywords_eu_passport_date` anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- normal ifade Regex_sweden_passport_number desenle eşleşen içeriği bulur.
- veya `Keyword_sweden_passport` anahtar `Keywords_eu_passport_number` sözcüğü bulunur.

```xml
    <!-- Sweden Passport Number -->
    <Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_sweden_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
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

### <a name="keyword_sweden_passport"></a>Keyword_sweden_passport

- yabancı kayıt kartı
- g3 işleme ücretleri
- birden çok giriş
- Numéro de passport
- passport n °
- passport non
- passport #
- passport #
- passportnon
- passportn °
- passnummer
- nr'ı geç
- schengen vizesi
- schengen vizeleri
- tek girdi
- sverige pass
- vize gereksinimleri
- vize işleme
- vize türü

### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- sorun tarihi
- süre sonu tarihi