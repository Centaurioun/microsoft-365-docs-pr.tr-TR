---
title: Suudi Arabistan Ulusal Kimliği varlık tanımı
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
description: Suudi Arabistan Ulusal Kimliği hassas bilgi türü varlık tanımı.
ms.openlocfilehash: c5bfa2560959caa0aa6115f4e25e8d09c8dffb5e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948511"
---
# <a name="saudi-arabia-national-id"></a>Suudi Arabistan Ulusal Kimliği

## <a name="format"></a>Biçim

10 basamak

## <a name="pattern"></a>Desen

Ardışık 10 basamak

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade `Regex_saudi_arabia_national_id` , desenle eşleşen içeriği bulur.
- 'den `Keyword_saudi_arabia_national_id` bir anahtar sözcük bulunur.

```xml
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_saudi_arabia_national_id"></a>Keyword_saudi_arabia_national_id

- Kimlik Kartı
- I kart numarası
- Kimlik numarası
- الوطنية الهوية بطاقة رقم