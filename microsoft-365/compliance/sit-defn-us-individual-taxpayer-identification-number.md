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
- tier3
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: ABD bireysel vergi mükellefi kimlik numarası (ITIN) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 56f57421d3a35e32c1b86d93feb670a57484275e
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68469985"
---
# <a name="us-individual-taxpayer-identification-number-itin"></a>ABD bireysel vergi mükellefi kimlik numarası (ITIN)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

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

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_formatted_itin`, desenle eşleşen içeriği bulur.
- `Keyword_itin` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_unformatted_itin`, desenle eşleşen içeriği bulur.
- `Keyword_itin` içinden bir anahtar sözcük bulundu.

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
