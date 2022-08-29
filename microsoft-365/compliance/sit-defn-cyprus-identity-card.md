---
title: Kıbrıs kimlik kartı varlık tanımı
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
description: Kıbrıs kimlik kartı hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 9797776342161365643aa48add071faa5b00f310
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67368550"
---
# <a name="cyprus-identity-card"></a>Kıbrıs kimlik kartı

## <a name="format"></a>Biçim

Boşluk ve sınırlayıcı içermeyen 10 basamak

## <a name="pattern"></a>Desen

10 basamak

## <a name="checksum"></a>Sağlama Toplamı

geçerli değil

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- Normal ifade `Regex_cyprus_eu_national_id_card` , desenle eşleşen içeriği bulur.
- `Keywords_cyprus_eu_national_id_card` içinden bir anahtar sözcük bulundu.

```xml
      <!-- Cyprus Identity Card -->
      <Entity id="3ba8afe5-7a6c-4929-8247-0001b6878438" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

- kimlik kartı numarası
- kimlik kartı numarası
- kimlik kartı
- ulusal kimlik numarası
- kişisel kimlik numarası
- ταυτοτητασ