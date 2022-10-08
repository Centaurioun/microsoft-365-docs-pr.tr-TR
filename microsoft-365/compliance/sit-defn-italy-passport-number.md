---
title: İtalya pasaport numarası varlık tanımı
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
description: İtalya pasaport numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 57817ff2e6865215109829e6cdb6e2256d991dbe
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68382281"
---
# <a name="italy-passport-number"></a>İtalya pasaport numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

iki harf veya basamak ve ardından boşluk veya sınırlayıcı içermeyen yedi basamak

## <a name="pattern"></a>Desen

iki harf veya rakam ve ardından yedi basamak:

- iki basamak veya harf (büyük/küçük harfe duyarlı değil)
- yedi basamak

## <a name="checksum"></a>Sağlama Toplamı

geçerli değil

### <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- Normal ifade `Regex_italy_eu_passport_number` , desenle eşleşen içeriği bulur.
- veya `Keywords_italy_eu_passport_number` anahtar `Keywords_eu_passport_number` sözcüğü bulunur.
- Normal ifade `Regex_italy_eu_passport_date` tarihi DD AAA/AAA YYYY biçiminde bulur (Örnek - 01 GEN/JAN 1988) veya anahtar sözcüğü `Keywords_eu_passport_date` bulunur

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- Normal ifade `Regex_italy_eu_passport_number` , desenle eşleşen içeriği bulur.
- veya `Keywords_italy_eu_passport_number` anahtar `Keywords_eu_passport_number` sözcüğü bulunur.

```xml
      <!-- Italy Passport Number -->
      <Entity id="39811019-4750-445f-b26d-4c0e6c431544" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_italy_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

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

### <a name="keywords_italy_eu_passport_number"></a>Keywords_italy_eu_passport_number

- italiana passaporto
- passaporto italiana
- passaporto numero
- numéro passport
- numero di passaporto
- numeri del passaporto
- passport italien

### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- sorun tarihi
- süre sonu tarihi
