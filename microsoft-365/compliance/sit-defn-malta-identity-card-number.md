---
title: Malta kimlik kartı numarası varlık tanımı
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
description: Malta kimlik kartı numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 55b029446f7152a208ca0c92ef11c6825dc364d6
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68382237"
---
# <a name="malta-identity-card-number"></a>Malta kimlik kartı numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

yedi basamak ve ardından bir harf

## <a name="pattern"></a>Desen

yedi basamak ve ardından bir harf:

- yedi basamak
- "M, G, A, P, L, H, B, Z" içinde bir harf (büyük/küçük harfe duyarsız)

## <a name="checksum"></a>Sağlama Toplamı

Geçerli değil

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- Normal ifade `Regex_malta_eu_national_id_card` , desenle eşleşen içeriği bulur.
- `Keywords_malta_eu_national_id_card` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- Normal ifade `Regex_malta_eu_national_id_card` , desenle eşleşen içeriği bulur.

```xml
      <!-- Malta Identity Card Number -->
      <Entity id="854b36b3-a388-4ac8-a4ec-677c2b5e4356" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_malta_eu_national_id_card"></a>Keywords_malta_eu_national_id_card

- vatandaş hizmet numarası
- id tat-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- kişisel sayısal kod
- benzersiz kimlik numarası
- benzersiz kimlik numarası
- uniqueidentityno #
