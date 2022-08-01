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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: İspanya sosyal güvenlik numarası (SSN) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 4a531f0548aba2caa330423d493cf8e524c4ed73
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948629"
---
# <a name="spain-social-security-number-ssn"></a>İspanya sosyal güvenlik numarası (SSN)

## <a name="format"></a>Biçim

11-12 basamak

## <a name="pattern"></a>Desen

11-12 basamak:

- iki basamak
- eğik çizgi (isteğe bağlı)
- yedi ila sekiz basamak
- eğik çizgi (isteğe bağlı)
- iki basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_spanish_social_security_number` , desenle eşleşen içeriği bulur.
- Sağlama toplamı geçer.
    - 'den `Keywords_spain_eu_ssn_or_equivalent` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_spanish_social_security_number` , desenle eşleşen içeriği bulur.
- Sağlama toplamı geçer.

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