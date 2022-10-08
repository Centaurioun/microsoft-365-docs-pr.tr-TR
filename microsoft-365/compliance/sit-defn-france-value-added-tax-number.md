---
title: Fransa katma değer vergi numarası varlık tanımı
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
description: Fransa katma değer vergi numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: c34426d3bcbb8d6ec9d86618232f6be2607f960b
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68378852"
---
# <a name="france-value-added-tax-number"></a>Fransa katma değer vergi numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

13 karakterli alfasayısal desen

## <a name="pattern"></a>Desen

13 karakter alfasayısal desen:

- iki harf - FR (büyük/küçük harfe duyarsız)
- isteğe bağlı bir boşluk veya kısa çizgi
- iki harf veya basamak
- isteğe bağlı boşluk, nokta, kısa çizgi veya virgül
- üç basamak
- isteğe bağlı boşluk, nokta, kısa çizgi veya virgül
- üç basamak
- isteğe bağlı boşluk, nokta, kısa çizgi veya virgül
- üç basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_france_value_added_tax_number`, desenle eşleşen içeriği bulur.
- `Keywords_france_value_added_tax_number` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_france_value_added_tax_number`, desenle eşleşen içeriği bulur.

```xml
      <!-- France Value Added Tax Number -->
      <Entity id="949121e6-ad9f-4379-8731-710342baea78" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_value_added_tax_number" />
          <Match idRef="Keywords_france_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_value_added_tax_number" />
        </Pattern>
      </Entity>
```
## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_france_value_added_tax_number"></a>Keyword_France_value_added_tax_number

- kdv numarası
- kdv no
- Kdv #
- katma değer vergisi
- siren kimliği no numéro d'identification taxe sur valeur ajoutée
- taxe valeur ajoutée
- taxe sur la valeur ajoutée
- n° tva
- numéro de tva
- numéro d'identification siren
