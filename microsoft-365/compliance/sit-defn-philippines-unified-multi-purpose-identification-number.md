---
title: Filipinler birleşik çok amaçlı kimlik numarası varlık tanımı
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
description: Filipinler birleşik çok amaçlı tanımlama numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: d5e880ff8c021cdcee195077f419f3b7ab87ed36
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948902"
---
# <a name="philippines-unified-multi-purpose-identification-number"></a>Filipinler birleşik çok amaçlı kimlik numarası

## <a name="format"></a>Biçim

Kısa çizgilerle ayrılmış 12 basamak

## <a name="pattern"></a>Desen

12 basamak:

- dört basamak
- kısa çizgi
- yedi basamak
- kısa çizgi
- bir basamak

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade `Regex_philippines_unified_id` , desenle eşleşen içeriği bulur.
- 'den `Keyword_philippines_id` bir anahtar sözcük bulunur.

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_philippines_id"></a>Keyword_philippines_id

- Birleşik Çok Amaçlı Kimlik
- UMID
- Kimlik Kartı
- Pinag-isang Multi-Layunin Kimliği