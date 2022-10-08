---
title: Suudi Arabistan Ulusal Kimliği varlık tanımı
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
description: Suudi Arabistan Ulusal Kimliği hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 864e175c4d1b8410e26bbd1c39a2f588cce07f2e
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68470266"
---
# <a name="saudi-arabia-national-id"></a>Suudi Arabistan Ulusal Kimliği

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

10 basamak

## <a name="pattern"></a>Desen

Ardışık 10 basamak

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- Normal ifade `Regex_saudi_arabia_national_id` , desenle eşleşen içeriği bulur.
- `Keyword_saudi_arabia_national_id` içinden bir anahtar sözcük bulundu.

```xml
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_saudi_arabia_national_id"></a>Keyword_saudi_arabia_national_id

- Kimlik Kartı
- I kart numarası
- Kimlik numarası
- الوطنية الهوية بطاقة رقم
