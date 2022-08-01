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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Uluslararası hastalık sınıflandırması (ICD-10-CM) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 414ad224f32a6eecb1fe244bdefde12afdc4b006
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948492"
---
# <a name="international-classification-of-diseases-icd-10-cm"></a>Uluslararası hastalık sınıflandırması (ICD-10-CM)

## <a name="format"></a>Biçim

Sözlük

## <a name="pattern"></a>Desen

Anahtar kelime

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- 'den `Dictionary_icd_10_updated` bir anahtar sözcük bulunur.
- 'den `Dictionary_icd_10_codes` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- 'den `Dictionary_icd_10_ updated` bir anahtar sözcük bulunur.

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