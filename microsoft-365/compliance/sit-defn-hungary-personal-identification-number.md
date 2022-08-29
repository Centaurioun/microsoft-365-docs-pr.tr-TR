---
title: Macaristan kişisel kimlik numarası varlık tanımı
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
description: Macaristan kişisel kimlik numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: ee3a22ffccdf9110d36e49013bfed912b2d2319b
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367279"
---
# <a name="hungary-personal-identification-number"></a>Macaristan kişisel kimlik numarası

## <a name="format"></a>Biçim

11 basamak

## <a name="pattern"></a>Desen

11 basamak:

- Cinsiyete karşılık gelen bir basamak, erkek için 1, kadın için 2. 1900'lü yıllardan önce doğan veya çifte vatandaşlığa sahip vatandaşlar için de başka sayılar mümkündür.
- Doğum tarihine karşılık gelen altı basamak (YYMMDD)
- Seri numarasına karşılık gelen üç basamak
- Bir denetim basamalı

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_hungary_eu_national_id_card`, desenle eşleşen içeriği bulur.
- `Keywords_hungary_eu_national_id_card` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_hungary_eu_national_id_card`, desenle eşleşen içeriği bulur.

```xml
      <!-- Hungary Personal Identification Number -->
      <Entity id="7b5cc218-7046-47d9-80c9-f325b50896ca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

- kimlik numarası
- kimlik numarası
- sz ig
- Sz. ıg.
- sz.ig.
- személyazonosító igazolvány
- személyi igazolvány