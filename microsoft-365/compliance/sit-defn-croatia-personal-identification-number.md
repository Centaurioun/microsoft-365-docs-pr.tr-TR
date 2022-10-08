---
title: Hırvatistan kişisel kimlik (OIB) numarası varlık tanımı
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
description: Hırvatistan kişisel kimlik (OIB) numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 683ee32f3e12255583958766e1d94efd6eeedfb7
ms.sourcegitcommit: 2ff545246fec060ea7829da5afbc1cdc698d51ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68362980"
---
# <a name="croatia-personal-identification-oib-number"></a>Hırvatistan kişisel kimlik (OIB) numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

11 basamak

## <a name="pattern"></a>Desen

11 basamak:

- 10 basamak
- son basamak bir denetim basamadır

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_croatia_oib_number`, desenle eşleşen içeriği bulur.
- `Keywords_croatia_eu_tax_file_number` içinden bir anahtar sözcük bulundu.
- Sağlama toplamı başarılı.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_croatia_oib_number`, desenle eşleşen içeriği bulur.
- Sağlama toplamı başarılı.

```xml
      <!-- Croatia Personal Identification (OIB) Number -->
      <Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_oib_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_oib_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_croatia_oib_number"></a>Keyword_croatia_oib_number

- majstorski broj građana
- ana vatandaş numarası
- nacionalni identifikacijski broj
- ulusal kimlik numarası
- oib #
- oib
- osobna iskaznica
- osobni kimliği
- osobni identifikacijski broj
- kişisel kimlik numarası
- porezni broj
- porezni identifikacijski broj
- vergi kimliği
- vergi tanımlama no
- vergi kimlik numarası
- vergi no #
- vergi no
- vergi numarası
- vergi kayıt numarası
- taksiye bindi #
- taxidno #
- taxidnumber #
- taxno #
- vergi numarası #
- vergi numarası
- teneke kimlik
- tin no
- Teneke #
