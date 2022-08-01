---
title: Kıbrıs pasaport numarası varlık tanımı
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
description: Kıbrıs pasaport numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: abfb7b7ce3365b6f65c8e639250e4bebd7f02f48
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948761"
---
# <a name="cyprus-passport-number"></a>Kıbrıs pasaport numarası

## <a name="format"></a>Biçim

bir harf ve ardından boşluk veya sınırlayıcı içermeyen 6-8 basamak

## <a name="pattern"></a>Desen

bir harf ve ardından altı ila sekiz basamak

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- Normal ifade `Regex_cyprus_eu_passport_number` , desenle eşleşen içeriği bulur.
- veya `Keywords_cyprus_eu_passport_number` anahtar `Keywords_eu_passport_number` sözcüğü bulunur.
- Normal ifade `Regex_cyprus_eu_passport_date` tarihi DD/AA/YYYY biçiminde bulur veya bir anahtar sözcük `Keywords_cyprus_eu_passport_date` bulunur

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade `Regex_cyprus_eu_passport_number` , desenle eşleşen içeriği bulur.
- veya `Keywords_cyprus_eu_passport_number` anahtar `Keywords_eu_passport_number` sözcüğü bulunur.

```xml
      <!-- Cyprus Passport Number -->
      <Entity id="9193e2e8-7f8c-43c1-a274-ac40d651936f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_cyprus_eu_passport_date" />
            <Match idRef="Keywords_cyprus_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
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

### <a name="keywords_cyprus_eu_passport_number"></a>Keywords_cyprus_eu_passport_number

- αριθμό διαβατηρίου
- yeni bir şey
- Αριθμός Διαβατηρίου
- κυπριακό διαβατήριο
- διαβατήριο #
- διαβατήριο
- αριθμός διαβατηρίου
- PasaportKimlik
- pasaport akdi
- Pasaport no.
- Αρ. Διαβατηρίου

### <a name="keywords_cyprus_eu_passport_date"></a>Keywords_cyprus_eu_passport_date

- tarihinde sona eriyor
- yayım tarihi