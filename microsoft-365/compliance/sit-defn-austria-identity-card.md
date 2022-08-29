---
title: Avusturya kimlik kartı varlık tanımı
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
description: Avusturya kimlik kartına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: d180c3e46c3810997bfe54a3521c840f833aff02
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367631"
---
# <a name="austria-identity-card"></a>Avusturya kimlik kartı

## <a name="format"></a>Biçim

Harflerin, basamakların ve özel karakterlerin 24 karakterlik birleşimi

## <a name="pattern"></a>Desen

24 karakter:

- 22 harf (büyük/küçük harfe duyarlı değil), basamaklar, ters eğik çizgi, eğik çizgi veya artı işareti

- iki harf (büyük/küçük harfe duyarlı değil), basamaklar, ters eğik çizgi, eğik çizgi, artı işareti veya eşittir işareti

## <a name="checksum"></a>Sağlama Toplamı

Geçerli değil

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- Normal ifade `Regex_austria_eu_national_id_card` , desenle eşleşen içeriği bulur.
- `Keywords_austria_eu_national_id_card` içinden bir anahtar sözcük bulundu.

```xml
      <!-- Austria Identity Card -->
      <Entity id="5ec06c3b-007e-4820-8343-7ff73b889735" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

- kimlik numarası
- ulusal kimlik
- personalausweis republik österreich