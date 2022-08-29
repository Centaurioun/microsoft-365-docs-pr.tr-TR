---
title: İtalya katma değer vergi numarası varlık tanımı
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
description: İtalya katma değer vergi numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 9e45fda7fe698e4059ec1f3af79ef7625f8f81a8
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67369925"
---
# <a name="italy-value-added-tax-number"></a>İtalya katma değer vergi numarası

## <a name="format"></a>Biçim

İsteğe bağlı sınırlayıcılarla 13 karakterli alfasayısal desen

## <a name="pattern"></a>Desen

İsteğe bağlı sınırlayıcılarla 13 karakterlik alfasayısal desen:

- Ben veya ben
- T veya t
- isteğe bağlı boşluk, nokta, kısa çizgi veya virgül
- 11 basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_italy_value_added_tax_number`, desenle eşleşen içeriği bulur.
- `Keywords_italy_value_added_tax_number` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_italy_value_added_tax_number`, desenle eşleşen içeriği bulur.

```xml
      <!-- Italy Value Added Tax -->
      <Entity id="26a8cc07-2283-4a2a-ab1d-4ab643c4c67f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
          <Match idRef="Keywords_italy_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_italy_value_added_tax_number"></a>Keyword_italy_value_added_tax_number

- kdv numarası
- kdv no
- Kdv #
- ıva
- ıva #