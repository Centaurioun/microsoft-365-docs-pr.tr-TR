---
title: Hindistan Seçmen Kimlik Kartı varlık tanımı
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
description: Hindistan Seçmen Kimliği Kartı hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 4556824999f44f6407e996fbca7c82e79fe2cafc
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948493"
---
# <a name="india-voter-id-card"></a>Hindistan Seçmen Kimlik Kartı

## <a name="format"></a>Biçim

10 karakterli alfasayısal desen

## <a name="pattern"></a>Desen

10 harf veya rakam:

- üç harf
- yedi basamak

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade `Regex_india_voter_id_card` , desenle eşleşen içeriği bulur.
- 'den `Keyword_india_voter_id_card` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- Normal ifade `Regex_india_voter_id_card` , desenle eşleşen içeriği bulur.

```xml
      <!-- India Voter Id Card  -->
        <Entity id="646d643f-5228-4408-acc8-f2e81a6df897" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
           <Pattern confidenceLevel="75">
             <IdMatch idRef="Regex_india_voter_id_card" />
             <Match idRef="Keyword_india_voter_id_card" />
            </Pattern>
           <Pattern confidenceLevel="65">
              <IdMatch idRef="Regex_india_voter_id_card" />
            </Pattern>
        </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_india_voter_id_card"></a>Keyword_india_voter_id_card

- Seçmen
- voterid
- oy kartı
- voteridcard
- seçim fotoğrafı kimlik kartı
- EPİK
- ECI
- seçim takdiri