---
title: Macaristan katma değer vergi numarası varlık tanımı
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
description: Macaristan katma değer vergi numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 7523bc370177884d058faad4b6313552e8ba3964
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367411"
---
# <a name="hungary-value-added-tax-number"></a>Macaristan katma değer vergi numarası

## <a name="format"></a>Biçim

10 karakterli alfasayısal desen

## <a name="pattern"></a>Desen

10 karakter alfasayısal desen:

- iki harf - HU veya hu
- isteğe bağlı alan
- sekiz basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_hungarian_value_added_tax_number`, desenle eşleşen içeriği bulur.
- `Keywords_hungarian_value_added_tax_number` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_hungarian_value_added_tax_number`, desenle eşleşen içeriği bulur.

```xml
      <!-- Hungarian Value Added Tax Number -->
      <Entity id="976349a0-683b-477a-90f8-ff0a220d5592" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
          <Match idRef="Keywords_hungarian_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_hungary_value_added_tax_number"></a>Keyword_Hungary_value_added_tax_number

- Kdv
- katma değer vergi numarası
- Kdv #
- vatno #
- macarvatno #
- vergi no
- katma değer vergisi áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám