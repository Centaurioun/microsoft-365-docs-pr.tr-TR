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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Yunanistan ulusal kimlik kartı hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 731adcfee8c2464bd45e9324e8305a4cc813d7eb
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948339"
---
# <a name="greece-national-id-card"></a>Yunanistan ulusal kimlik kartı

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

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- Normal ifade `Regex_greece_id_card` , desenle eşleşen içeriği bulur.
- 'den `Keyword_greece_id_card` bir anahtar sözcük bulunur.

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