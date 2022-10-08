---
title: Yeni Zelanda sosyal yardım numarası varlık tanımı
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
description: Yeni Zelanda sosyal yardım numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 6bd9a61fd5e54d83fedf941afc7a97653f8bef7e
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68382567"
---
# <a name="new-zealand-social-welfare-number"></a>Yeni Zelanda sosyal yardım numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

dokuz basamak

## <a name="pattern"></a>Desen

dokuz basamak

- üç basamak
- isteğe bağlı kısa çizgi
- üç basamak
- isteğe bağlı kısa çizgi
- üç basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

### <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_newzealand_social_welfare_number`, desenle eşleşen içeriği bulur.
- `Keywords_newzealand_social_welfare_number` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- İşlev `Func_newzealand_social_welfare_number`, desenle eşleşen içeriği bulur.

```xml
      <!-- Newzealand Social Welfare Number -->
      <Entity id="20f3c48d-4ac1-4cd2-86bd-34ecc1826e9d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
          <Match idRef="Keywords_newzealand_social_welfare_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
        </Pattern>
      </Entity>
    </Version>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_new_zealand_social_welfare_number"></a>Keyword_new_zealand_social_welfare_number

- sosyal yardım #
- sosyal yardım #
- sosyal yardım no.
- sosyal yardım numarası
- swn #
