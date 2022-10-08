---
title: Hindistan Seçmen Kimliği Kartı varlık tanımı
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
description: Hindistan Seçmen Kimliği Kartı hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 168cf756e547f1b8090735cad22aeeaabb68d404
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68379776"
---
# <a name="india-voter-id-card"></a>Hindistan Seçmen Kimlik Kartı

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

10 karakterli alfasayısal desen

## <a name="pattern"></a>Desen

10 harf veya rakam:

- üç harf
- yedi basamak

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- Normal ifade `Regex_india_voter_id_card` , desenle eşleşen içeriği bulur.
- `Keyword_india_voter_id_card` içinden bir anahtar sözcük bulundu.

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
- Ecı
- seçim takdiri
