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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Japonya ikamet kartı numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 512a20f00dd2ff77d2f88950d83b227a717c309e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948869"
---
# <a name="japan-residence-card-number"></a>Japonya konut kartı numarası

## <a name="format"></a>Biçim

12 harf ve rakam

## <a name="pattern"></a>Desen

12 harf ve rakam:

- iki harf (büyük/küçük harfe duyarlı değil)
- sekiz basamak
- iki harf (büyük/küçük harfe duyarlı değil)

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade `Regex_jp_residence_card_number` , desenle eşleşen içeriği bulur.
- 'den `Keyword_jp_residence_card_number` bir anahtar sözcük bulunur.

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