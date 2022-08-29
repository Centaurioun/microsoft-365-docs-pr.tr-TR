---
title: Belçika katma değer vergi numarası varlık tanımı
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
description: Belçika katma değer vergi numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: c1099e69636f9b3dd0fdc5250df47f57506176fd
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367367"
---
# <a name="belgium-value-added-tax-number"></a>Belçika katma değer vergi numarası

## <a name="format"></a>Biçim

12 karakterli alfasayısal desen

## <a name="pattern"></a>Desen

12 karakterli alfasayısal desen:

- B veya b harfi
- E veya e harfi
- bir basamak 0
- 1'den 9'a kadar olan bir basamak
- isteğe bağlı nokta veya Kısa Çizgi veya boşluk
- dört basamak
- isteğe bağlı nokta veya Kısa Çizgi veya boşluk
- dört basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_belgium_value_added_tax_number`, desenle eşleşen içeriği bulur.
- `Keywords_belgium_value_added_tax_number` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_belgium_value_added_tax_number`, desenle eşleşen içeriği bulur.

```xml
      <!-- Belgium Value Added Tax Number -->
      <Entity id="85b5b3c3-f2de-4ae8-ac46-fd3cb38bf9ed" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
          <Match idRef="Keywords_belgium_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
        </Pattern>
      </Entity>
    </Version>
```
## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_belgium_value_added_tax_number"></a>Keyword_belgium_value_added_tax_number

- nº tva
- kdv numarası
- kdv no
- numéro t.v.a
- umsatzsteuer-identifikationsnummer
- umsatzsteuernummer
- Btw
- Btw #
- Kdv #
