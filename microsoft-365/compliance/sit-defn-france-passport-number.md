---
title: Fransa pasaport numarası varlık tanımı
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
description: Fransa pasaport numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 2b41095c897113bfd093b02fb1e787fae8cb7686
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68380392"
---
# <a name="france-passport-number"></a>Fransa pasaport numarası

Bu varlık, AB Pasaport Numarası hassas bilgi türünde kullanılabilir. Tek başına hassas bilgi türü varlığı olarak da kullanılabilir.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

dokuz basamak ve harf

## <a name="pattern"></a>Desen

dokuz basamak ve harf:

- iki basamak
- iki harf (büyük/küçük harfe duyarlı değil)
- beş basamak

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_fr_passport`, desenle eşleşen içeriği bulur.
- veya `Keywords_france_eu_passport_number` anahtar `Keywords_eu_passport_number` sözcüğü bulunur.
- Normal ifade `Regex_eu_passport_date3` tarihi DD AA YYYY biçiminde bulur veya bir anahtar sözcük `Keywords_eu_passport_date` bulunur

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_fr_passport`, desenle eşleşen içeriği bulur.
- veya `Keywords_france_eu_passport_number` anahtar `Keywords_eu_passport_number` sözcüğü bulunur.

```xml
    <!-- France Passport Number -->
    <Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
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

### <a name="keywords_france_eu_passport_number"></a>Keywords_france_eu_passport_number

- numéro de passport
- passport n °
- passport non
- passport #
- passport #
- passportnon
- passportn °
- passport français
- passport livre
- passport carte
- numéro passport
- passport n°
- n° du passport
- n° geçiş noktası

### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- sorun tarihi
- süre sonu tarihi
