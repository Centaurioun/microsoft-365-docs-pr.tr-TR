---
title: Yunanistan ulusal kimlik kartı varlık tanımı
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
description: Yunanistan ulusal kimlik kartı hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 9f4ae0728138a33640a4afddfb73ed04692e1723
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68379732"
---
# <a name="greece-national-id-card"></a>Yunanistan ulusal kimlik kartı

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

7-8 harf ve sayı ile tire birleşimi

## <a name="pattern"></a>Desen

Yedi harf ve sayı (eski biçim):

- Bir harf (Yunan alfabesinin herhangi bir harfi)
- Kısa çizgi
- Altı basamak

Sekiz harf ve sayı (yeni biçim):

- Büyük harf karakteri hem Yunanca hem de Latin alfabelerinde (ABEZHIKMNOPTYX) oluşan iki harf
- Kısa çizgi
- Altı basamak

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- Normal ifade `Regex_greece_id_card` , desenle eşleşen içeriği bulur.
- `Keyword_greece_id_card` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- Normal ifade `Regex_greece_id_card` , desenle eşleşen içeriği bulur.

```xml
      <!-- Greece National ID Card -->
      <Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_id_card" />
          <Match idRef="Keyword_greece_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_greece_id_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_greece_id_card"></a>Keyword_greece_id_card

- yunanca kimlik
- yunan uyruklu kimlik
- yunan kişisel kimlik kartı
- yunan polis kimliği
- kimlik kartı
- tautotita
- ταυτότητα
- ταυτότητας
