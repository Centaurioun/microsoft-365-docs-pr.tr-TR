---
title: Almanya katma değer vergi numarası varlık tanımı
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
description: Almanya katma değer vergi numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 67522ff0fe1e18b878624f151cc7fcf9e4f346d2
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67368553"
---
# <a name="germany-value-added-tax-number"></a>Almanya katma değer vergi numarası

## <a name="format"></a>Biçim

11 karakter alfasayısal desen

## <a name="pattern"></a>Desen

11 karakterli alfasayısal desen:

- D veya d harfi
- E veya e harfi
- isteğe bağlı bir alan
- üç basamak
- isteğe bağlı bir alan veya virgül
- üç basamak
- isteğe bağlı bir alan veya virgül
- üç basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_germany_value_added_tax_number`, desenle eşleşen içeriği bulur.
- `Keywords_germany_value_added_tax_number` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_germany_value_added_tax_number`, desenle eşleşen içeriği bulur.

```xml
      <!-- Germany Value Added Tax Number -->
      <Entity id="db177eb2-8811-4842-bffc-128c14aa219f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
          <Match idRef="Keywords_germany_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
        </Pattern>
      </Entity>
```
## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_germany_value_added_tax_number"></a>Keyword_germany_value_added_tax_number

- kdv numarası
- kdv no
- Kdv #
- vat# mehrwertsteuer
- mwst
- mehrwertsteuer identifikationsnummer
- mehrwertsteuer nummer