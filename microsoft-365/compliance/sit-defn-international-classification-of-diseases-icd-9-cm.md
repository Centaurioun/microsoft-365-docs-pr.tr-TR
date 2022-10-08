---
title: Uluslararası hastalık sınıflandırması (ICD-9-CM) varlık tanımı
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
description: Uluslararası hastalık sınıflandırması (ICD-9-CM) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: f2f482eb951066c0d3bdae084d9082cd8992da8f
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68378302"
---
# <a name="international-classification-of-diseases-icd-9-cm"></a>Uluslararası hastalık sınıflandırması (ICD-9-CM)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

Sözlük

## <a name="pattern"></a>Desen

Anahtar kelime

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- `Dictionary_icd_9_updated` içinden bir anahtar sözcük bulundu.
- `Dictionary_icd_9_codes` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- `Dictionary_icd_9_updated` içinden bir anahtar sözcük bulundu.

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

Uluslararası [Hastalık Sınıflandırması, Dokuzuncu Düzeltme, Klinik Modifikasyon (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605) temelinde anahtar sözcük sözlüğünden `Dictionary_icd_9_updated` herhangi bir terim. Bu tür yalnızca terimi arar, sigorta kodlarını aramaz.

Uluslararası [Hastalık Sınıflandırması, Dokuzuncu Düzeltme, Klinik Modifikasyon (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605) temelinde anahtar sözcük sözlüğünden `Dictionary_icd_9_codes` herhangi bir terim. Bu tür yalnızca sigorta kodlarını arar, açıklamayı aramaz.
