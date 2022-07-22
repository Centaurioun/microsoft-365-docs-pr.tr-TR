---
title: ABD bireysel vergi mükellefi kimlik numarası (ITIN) varlık tanımı
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
description: ABD bireysel vergi mükellefi kimlik numarası (ITIN) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: c99635c29bb5b720ecc2d70577fe66d508ce9d9c
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948845"
---
# <a name="us-individual-taxpayer-identification-number-itin"></a>ABD bireysel vergi mükellefi kimlik numarası (ITIN)

## <a name="format"></a>Biçim

"9" ile başlayan ve dördüncü basamak olarak "7" veya "8" içeren dokuz basamak, isteğe bağlı olarak boşluk veya tirelerle biçimlendirilmiş

## <a name="pattern"></a>Desen

Biçimlendirilmiş:

- "9" rakamı
- iki basamak
- boşluk veya tire
- "7" veya "8"
- basamak
- boşluk veya tire
- dört basamak

Biçimlendir -ilmemiş:

- "9" rakamı
- iki basamak
- "7" veya "8"
- beş basamak

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_formatted_itin` , desenle eşleşen içeriği bulur.
- 'den `Keyword_itin` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_unformatted_itin` , desenle eşleşen içeriği bulur.
- 'den `Keyword_itin` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- İşlev `Func_formatted_itin` veya `Func_unformatted_itin` desenle eşleşen içeriği bulur.

```xml
    <!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
    <Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_formatted_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_unformatted_itin" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_itin"></a>Keyword_itin

- Vergi mükellefi
- vergi kimliği
- vergi belirleme
- bu
- i.t.i.n.
- ssn
- Teneke
- sosyal güvenlik
- vergi ödeyen
- itins
- taksiye bindi
- bireysel vergi mükellefi