---
title: Hollanda katma değer vergi numarası varlık tanımı
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
description: Hollanda katma değer vergi numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: eb1db00d5f34d7591cc7f9ff54cba917781d7884
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367675"
---
# <a name="netherlands-value-added-tax-number"></a>Hollanda katma değer vergi numarası

## <a name="format"></a>Biçim

14 karakterli alfasayısal desen

## <a name="pattern"></a>Desen

14 karakterli alfasayısal desen:

- N veya n
- L veya ben
- isteğe bağlı boşluk, nokta veya kısa çizgi
- dokuz basamak
- isteğe bağlı boşluk, nokta veya kısa çizgi
- B veya b
- iki basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_netherlands_value_added_tax_number`, desenle eşleşen içeriği bulur.
- `Keywords_netherlands_value_added_tax_number` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_netherlands_value_added_tax_number`, desenle eşleşen içeriği bulur.

```xml
      <!-- Netherlands Value Added Tax Number -->
      <Entity id="4f320d9b-4972-41ae-b337-88d499bb1ade" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
          <Match idRef="Keywords_netherlands_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_netherlands_value_added_tax_number"></a>Keyword_netherlands_value_added_tax_number

- kdv numarası
- kdv no
- Kdv #
- wearde tafoege tax getal
- btw nûmer
- btw-nummer