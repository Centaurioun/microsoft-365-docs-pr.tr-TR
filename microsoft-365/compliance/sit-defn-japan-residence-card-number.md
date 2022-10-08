---
title: Japonya konut kartı numarası varlık tanımı
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
description: Japonya ikamet kartı numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: a4e9c090515f25ffcf22504e171f94e1ceaee7b3
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68381709"
---
# <a name="japan-residence-card-number"></a>Japonya konut kartı numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

12 harf ve rakam

## <a name="pattern"></a>Desen

12 harf ve rakam:

- iki harf (büyük/küçük harfe duyarlı değil)
- sekiz basamak
- iki harf (büyük/küçük harfe duyarlı değil)

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- Normal ifade `Regex_jp_residence_card_number` , desenle eşleşen içeriği bulur.
- `Keyword_jp_residence_card_number` içinden bir anahtar sözcük bulundu.

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_jp_residence_card_number"></a>Keyword_jp_residence_card_number

- İkamet kartı numarası
- İkamet kartı no
- İkamet kartı #
- 在留カード番号
- 在留カード
- 在留番号
