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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Hindistan kalıcı hesap numarası (PAN) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: bf712e0949bba5f1e5396d61ff70f41b70ba579d
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948397"
---
# <a name="india-permanent-account-number-pan"></a>Hindistan kalıcı hesap numarası (PAN)

## <a name="format"></a>Biçim

10 harf veya rakam

## <a name="pattern"></a>Desen

10 harf veya rakam:

- Üç harf (büyük/küçük harfe duyarlı değil)
- C, P, H, F, A, T, B, L, J, G harfi (büyük/küçük harfe duyarlı değildir)
- Bir mektup
- Dört basamak
- Alfabetik denetim basamakları olan bir harf

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- Normal ifade `Regex_india_permanent_account_number` , desenle eşleşen içeriği bulur.
- 'den `Keyword_india_permanent_account_number` bir anahtar sözcük bulunur.

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
- PAN