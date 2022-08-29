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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Fransa katma değer vergi numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 0bec456bdfb4c41f4ab9c3cf4b33e99d7a91b9d4
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367257"
---
# <a name="france-value-added-tax-number"></a>Fransa katma değer vergi numarası

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