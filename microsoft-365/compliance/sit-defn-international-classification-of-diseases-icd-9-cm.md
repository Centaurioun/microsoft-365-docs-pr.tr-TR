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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Uluslararası hastalık sınıflandırması (ICD-9-CM) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 1aceb3864638f2fa8658d4c88dc47812910dd588
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948610"
---
# <a name="international-classification-of-diseases-icd-9-cm"></a>Uluslararası hastalık sınıflandırması (ICD-9-CM)

## <a name="format"></a>Biçim

Sözlük

## <a name="pattern"></a>Desen

Anahtar kelime

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- 'den `Dictionary_icd_9_updated` bir anahtar sözcük bulunur.
- 'den `Dictionary_icd_9_codes` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- 'den `Dictionary_icd_9_updated` bir anahtar sözcük bulunur.

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