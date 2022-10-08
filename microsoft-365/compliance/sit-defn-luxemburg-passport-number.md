---
title: Luxemburg pasaport numarası varlık tanımı
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
description: Luxemburg pasaport numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: d13296b0eab1663caac1f711dfa3ce8ea72ea7db
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68381621"
---
# <a name="luxemburg-passport-number"></a>Lüksemburg pasaport numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

boşluk veya sınırlayıcı içermeyen sekiz basamak veya harf

## <a name="pattern"></a>Desen

sekiz basamak veya harf (büyük/küçük harfe duyarlı değil)

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- Normal ifade `Regex_luxemburg_eu_passport_number` , desenle eşleşen içeriği bulur.
- veya `Keywords_luxemburg_eu_passport_number` anahtar `Keywords_eu_passport_number` sözcüğü bulunur.
- Normal ifade `Regex_eu_passport_date3` tarihi DD AA YYYY biçiminde bulur veya bir anahtar sözcük `Keywords_eu_passport_date` bulunur

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- Normal ifade `Regex_luxemburg_eu_passport_number` , desenle eşleşen içeriği bulur.
- veya `Keywords_luxemburg_eu_passport_number` anahtar `Keywords_eu_passport_number` sözcüğü bulunur.

```xml
      <!-- Luxemburg Passport Number -->
      <Entity id="81d5c027-bed9-4421-91a0-3b2e55b3eb85" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
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

### <a name="keywords_luxemburg_eu_passport_number"></a>Keywords_luxemburg_eu_passport_number
- ausweisnummer
- lüksemburg geçişi
- lüksemburg passport
- lüksemburg pasaportu
- geçiş yok
- no-reisepass
- nr-reisepass
- numéro de passport
- net geçirme
- nr'ı geç
- passnummer
- passport nombre
- reisepässe
- reisepass-nr
- reisepassnummer

### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- sorun tarihi
- süre sonu tarihi
