---
title: Hindistan kalıcı hesap numarası (PAN) varlık tanımı
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
description: Hindistan kalıcı hesap numarası (PAN) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: f997fa774b7fb85e083004d8c2f8296a70e11a40
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68380238"
---
# <a name="india-permanent-account-number-pan"></a>Hindistan kalıcı hesap numarası (PAN)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

10 harf veya rakam

## <a name="pattern"></a>Desen

10 harf veya rakam:

- Üç harf (büyük/küçük harfe duyarlı değil)
- C, P, H, F, A, T, B, L, J, G harfi (büyük/küçük harfe duyarlı değildir)
- Bir mektup
- Dört basamak
- Alfabetik denetim basamakları olan bir harf

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- Normal ifade `Regex_india_permanent_account_number` , desenle eşleşen içeriği bulur.
- `Keyword_india_permanent_account_number` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- Normal ifade `Regex_india_permanent_account_number` , desenle eşleşen içeriği bulur.

```xml
      <!-- India Permanent Account Number -->
      <Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_india_permanent_account_number" />
          <Match idRef="Keyword_india_permanent_account_number" />
        </Pattern>
        <Version minEngineVersion="15.20.3520.000">
          <Pattern confidenceLevel="65">
            <IdMatch idRef="Regex_india_permanent_account_number" />
          </Pattern>
        </Version>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_india_permanent_account_number"></a>Keyword_india_permanent_account_number

- Kalıcı Hesap Numarası
- Pan
