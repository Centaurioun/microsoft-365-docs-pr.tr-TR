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
- tier3
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Tayvan pasaport numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: ab4284b88be490c7c56c058fa9b73ce337516b7a
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472002"
---
# <a name="taiwan-passport-number"></a>Tayvan pasaport numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

- biyometrik pasaport numarası: dokuz basamak
- biyometrik olmayan pasaport numarası: dokuz basamak

## <a name="pattern"></a>Desen

biyometrik pasaport numarası:

- "3" karakteri
- sekiz basamak

biyometrik olmayan pasaport numarası:

- dokuz basamak

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- Normal ifade `Regex_taiwan_passport` , desenle eşleşen içeriği bulur.
- `Keyword_taiwan_passport` içinden bir anahtar sözcük bulundu.

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
