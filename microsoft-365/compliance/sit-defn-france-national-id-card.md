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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Fransa ulusal kimlik kartı (CNI) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 35a6481e657d20a83ed1b80a6d06ad8ebf1c9cdf
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66989579"
---
# <a name="france-national-id-card-cni"></a>Fransa ulusal kimlik kartı (CNI)

## <a name="format"></a>Biçim

12 basamak

## <a name="pattern"></a>Desen

12 basamak

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- Normal ifade `Regex_france_cni` , desenle eşleşen içeriği bulur.
- 'den `Keywords_france_eu_national_id_card` bir anahtar sözcük bulunur.

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