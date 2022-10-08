---
title: İspanya sosyal güvenlik numarası (SSN) varlık tanımı
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
description: İspanya sosyal güvenlik numarası (SSN) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 8a87fcc82af413e074e7e37302bb72de0f9a501a
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68470574"
---
# <a name="spain-social-security-number-ssn"></a>İspanya sosyal güvenlik numarası (SSN)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

11-12 basamak

## <a name="pattern"></a>Desen

11-12 basamak:

- iki basamak
- eğik çizgi (isteğe bağlı)
- yedi ila sekiz basamak
- eğik çizgi (isteğe bağlı)
- iki basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_spanish_social_security_number`, desenle eşleşen içeriği bulur.
- Sağlama toplamı başarılı.
    - `Keywords_spain_eu_ssn_or_equivalent` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_spanish_social_security_number`, desenle eşleşen içeriği bulur.
- Sağlama toplamı başarılı.

```xml
    <!-- Spain SSN -->
    <Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85" relaxProximity="true" >
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spanish_social_security_number" />
          <Match idRef="Keywords_spain_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spanish_social_security_number" />
        </Pattern>
    </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- ssn
- ssn #
- socialsecurityno
- sosyal güvenlik hayır
- sosyal güvenlik numarası
- número de la seguridad social
