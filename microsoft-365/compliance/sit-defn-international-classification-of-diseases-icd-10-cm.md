---
title: Uluslararası hastalık sınıflandırması (ICD-10-CM) varlık tanımı
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
description: Uluslararası hastalık sınıflandırması (ICD-10-CM) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: d557d3830d7a7af179ce7896d757114262737f9a
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68380282"
---
# <a name="international-classification-of-diseases-icd-10-cm"></a>Uluslararası hastalık sınıflandırması (ICD-10-CM)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

Sözlük

## <a name="pattern"></a>Desen

Anahtar kelime

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- `Dictionary_icd_10_updated` içinden bir anahtar sözcük bulundu.
- `Dictionary_icd_10_codes` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- `Dictionary_icd_10_ updated` içinden bir anahtar sözcük bulundu.

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_updated" />
          <Match idRef="Dictionary_icd_10_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_10_updated" />
        </Pattern>

```

## <a name="keywords"></a>Anahtar Sözcükler

Uluslararası [Hastalık Sınıflandırması, Onuncu Düzeltme, Klinik Modifikasyon (ICD-10-CM)](https://icd10cmtool.cdc.gov/) temelinde anahtar sözcük sözlüğünden `Dictionary_icd_10_updated` herhangi bir terim. Bu tür yalnızca terimi arar, sigorta kodlarını aramaz.

Uluslararası [Hastalık Sınıflandırması, Onuncu Düzeltme, Klinik Modifikasyon (ICD-10-CM)](https://icd10cmtool.cdc.gov/) temelinde anahtar sözcük sözlüğünden `Dictionary_icd_10_codes` herhangi bir terim. Bu tür yalnızca sigorta kodlarını arar, açıklamayı aramaz.
