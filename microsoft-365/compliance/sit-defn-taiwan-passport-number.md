---
title: Tayvan pasaport numarası varlık tanımı
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
description: Tayvan pasaport numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: b899fbe560ea6cba19c66bafea819c769ece2634
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948625"
---
# <a name="taiwan-passport-number"></a>Tayvan pasaport numarası

## <a name="format"></a>Biçim

- biyometrik pasaport numarası: dokuz basamak
- biyometrik olmayan pasaport numarası: dokuz basamak

## <a name="pattern"></a>Desen

biyometrik pasaport numarası:

- "3" karakteri
- sekiz basamak

biyometrik olmayan pasaport numarası:

- dokuz basamak

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade `Regex_taiwan_passport` , desenle eşleşen içeriği bulur.
- 'den `Keyword_taiwan_passport` bir anahtar sözcük bulunur.

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_taiwan_passport"></a>Keyword_taiwan_passport

- ROC pasaport numarası
- Pasaport numarası
- Pasaport no
- Passport Num
- Pasaport #
- 护照
- 中華民國護照
- Zhônghuá Mínguó hùzhào