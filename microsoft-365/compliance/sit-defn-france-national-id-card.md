---
title: Fransa ulusal kimlik kartı (CNI) varlık tanımı
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
description: Fransa ulusal kimlik kartı (CNI) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: fae2db81a39de5ff583a363ce426484f54a52230
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68379600"
---
# <a name="france-national-id-card-cni"></a>Fransa ulusal kimlik kartı (CNI)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

12 basamak

## <a name="pattern"></a>Desen

12 basamak

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- Normal ifade `Regex_france_cni` , desenle eşleşen içeriği bulur.
- `Keywords_france_eu_national_id_card` içinden bir anahtar sözcük bulundu.

```xml
    <!-- France CNI -->
    <Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
        <Match idRef="Keywords_france_eu_national_id_card" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_france_eu_national_id_card"></a>Keywords_france_eu_national_id_card

- kart numarası
- carte nationale d'identité
- carte nationale d'idenite no
- cni #
- cni
- compte bancaire
- ulusal kimlik numarası
- ulusal kimlik
- nationalidno #
- numéro d'assurance maladie
- numéro de carte vitale
