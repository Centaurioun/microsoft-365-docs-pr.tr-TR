---
title: Almanya kimlik kartı numarası varlık tanımı
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
description: Almanya kimlik kartı numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 961dec17e4f68a1650cd0c4360ccf5244bef0062
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948496"
---
# <a name="germany-identity-card-number"></a>Almanya kimlik kartı numarası

## <a name="format"></a>Biçim

1 Kasım 2010'dan bu yana: Dokuz - 11 harf ve rakam

1 Nisan 1987 ile 31 Ekim 2010 arasında: 10 basamak

## <a name="pattern"></a>Desen

1 Kasım 2010'dan bu yana: 9 - 11 karakter alfasayısal desen
- one L, M, N, P, R, T, V, W, X, Y (büyük/küçük harfe duyarsız)
- C, F, G, H, J, K, L, M, N, P, R, T, V, W, X, Y ve Z'de sekiz basamak veya harf (büyük/küçük harfe duyarsız)
- isteğe bağlı denetim basamalı
- İsteğe bağlı d/D

1 Nisan 1987 ile 31 Ekim 2010 arasında:

- 10 basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_german_id_card_with_check` , desenle eşleşen içeriği bulur.
- 'den `Keyword_germany_id_card` bir anahtar sözcük bulunur.
- Sağlama toplamı geçer.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade `Regex_germany_id_card` , desenle eşleşen içeriği bulur (2010 öncesi verilmiş onay basamağı olmayan 9 karakter veya 2010'da verilen 10 basamak deseni).
- 'den `Keyword_germany_id_card` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- İşlev `Func_german_id_card_with_check` , desenle eşleşen içeriği bulur.
- Sağlama toplamı geçer.

```xml
      <!-- Germany Identity Card Number -->
      <Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
         <IdMatch idRef="Regex_germany_id_card" />
         <Match idRef="Keyword_germany_id_card" />
        </Pattern>
        <Version minEngineVersion="15.20.4545.000">
          <Pattern confidenceLevel="85">
           <IdMatch idRef="Func_german_id_card_with_check" />
            <Match idRef="Keyword_germany_id_card" />
          </Pattern>
          <Pattern confidenceLevel="65">
           <IdMatch idRef="Func_german_id_card_with_check" />
          </Pattern>
        </Version>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_germany_id_card"></a>Keyword_germany_id_card

- ausweis
- gpid
- Kimlik
- identifikation
- identifizierungsnummer
- kimlik kartı
- kimlik numarası
- id-nummer
- kişisel kimlik
- personalausweis
- persönliche id nummer
- persönliche identifikationsnummer
- persönliche-id-nummer