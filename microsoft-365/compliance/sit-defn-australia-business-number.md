---
title: Avustralya iş numarası varlık tanımı
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
description: Avustralya iş numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 656dbc0315b0b7b09b112bdd7e423bcdec64a165
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67368487"
---
# <a name="australia-business-number"></a>Avustralya iş numarası

## <a name="format"></a>Biçim

İsteğe bağlı sınırlayıcılarla 11 basamak

## <a name="pattern"></a>Desen

İsteğe bağlı sınırlayıcıları olan 11 basamak:

- iki basamak
- isteğe bağlı kısa çizgi veya boşluk
- üç basamak
- isteğe bağlı kısa çizgi veya boşluk
- üç basamak
- isteğe bağlı kısa çizgi veya boşluk
- üç basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev Func_australian_business_number desenle eşleşen içeriği bulur.
- Keywords_australian_business_number anahtar sözcüğü bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev Func_australian_business_number desenle eşleşen içeriği bulur.

```xml
      <!-- Australia Business Number -->
      <Entity id="76e83b3b-01ee-4530-aced-e667a6609f49" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_australian_business_number" />
          <Match idRef="Keywords_australian_business_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_australian_business_number" />
        </Pattern>
      </Entity>
```
## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_australia_business_number"></a>Keyword_australia_business_number

- avustralya iş no
- iş numarası
- Abn #
- businessid #
- iş kimliği
- Abn
- businessno #