---
title: Avustralya pasaport numarası varlık tanımı
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
description: Avustralya pasaport numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 9f879dc2f071398f7c3ba49b7fcded8be220e07b
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948475"
---
# <a name="australia-passport-number"></a>Avustralya pasaport numarası

## <a name="format"></a>Biçim

sekiz veya dokuz alfasayısal karakter

## <a name="pattern"></a>Desen

- bir harf (N, E, D, F, A, C, U, X) ve ardından yedi basamak veya
- İki harf (PA, PB, PC, PD, PE, PF, PU, PW, PX, PZ) ve ardından yedi basamak.

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade `Regex_australia_passport_number` , desenle eşleşen içeriği bulur.
- 'den `Keyword_australia_passport_number` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- Normal ifade `Regex_australia_passport_number` , desenle eşleşen içeriği bulur.

```xml
    <!-- Australia Passport Number -->
    <Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Match idRef="Keyword_australia_passport_number" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_australia_passport_number" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

- Pasaport #
- Pasaport #
- passportid
- Pasaport
- passportno
- pasaport no
- passportnumber
- pasaport numarası
- passportnumbers
- pasaport numaraları
- pasaport ayrıntıları
- göçmenlik ve vatandaşlık
- avustralya birleşik topluluğu
- göç departmanı
- ulusal kimlik kartı
- seyahat belgesi
- veren yetkili