---
title: Fransa sağlık sigortası numarası varlık tanımı
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
description: Fransa sağlık sigortası numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 59fed01945647b483601a1917fe50f2b37732ac2
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68380018"
---
# <a name="france-health-insurance-number"></a>Fransa sağlık sigortası numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

21 basamaklı sayı

## <a name="pattern"></a>Desen

21 basamaklı sayı:

- 10 basamak
- isteğe bağlı bir alan
- 10 basamak
- isteğe bağlı bir alan
- basamak

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- regex `Regex_France_Health_Insurance_Number` desenle eşleşen içeriği bulur.
- anahtar sözcüğü `Keyword_France_Health_Insurance_Number` bulunur.

```xml
      <!-- France Health Insurance Number -->
      <Entity id="9bc2069e-76df-4ff9-ac02-2f519469e236" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_France_Health_Insurance_Number"/>
          <Match idRef="Keyword_France_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_france_health_insurance_number"></a>Keyword_France_health_insurance_number

- sigorta kartı
- carte vitale
- carte d'assuré social
