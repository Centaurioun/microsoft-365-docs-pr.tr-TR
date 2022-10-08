---
title: ABD / BK pasaport numarası varlık tanımı
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
description: ABD / BK pasaport numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 96e3f270cfa49cc63a263b54960afb19c27aa3df
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68471892"
---
# <a name="usuk-passport-number"></a>ABD / BK pasaport numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

dokuz basamak

## <a name="pattern"></a>Desen

- bir harf veya rakam
- sekiz basamak

## <a name="checksum"></a>Sağlama Toplamı

Hayır

### <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_usa_uk_passport`, desenle eşleşen içeriği bulur.
- veya `Keywords_uk_eu_passport_number` anahtar `Keywords_eu_passport_number` sözcüğü bulunur.
- 'den `Keywords_eu_passport_date` bir anahtar sözcük bulundu

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_usa_uk_passport`, desenle eşleşen içeriği bulur.
- veya `Keywords_uk_eu_passport_number` anahtar `Keywords_eu_passport_number` sözcüğü bulunur.

```xml
    <!-- U.S. / U.K. Passport Number -->
    <Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
       <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
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

### <a name="keywords_uk_eu_passport_number"></a>Keywords_uk_eu_passport_number

- İngiliz pasaportu
- uk passport
