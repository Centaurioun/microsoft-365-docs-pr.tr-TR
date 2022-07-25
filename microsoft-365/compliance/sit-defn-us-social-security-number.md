---
title: ABD sosyal güvenlik numarası (SSN) varlık tanımı
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
description: ABD sosyal güvenlik numarası (SSN) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 2644ff5be51d8316007d20ec3c8918ce0e2003c1
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66989357"
---
# <a name="us-social-security-number-ssn"></a>ABD sosyal güvenlik numarası (SSN)

## <a name="format"></a>Biçim

dokuz basamak, biçimlendirilmiş veya biçimlendirilmemiş bir desende olabilir

> [!NOTE]
> 2011'in ortasından önce verilirse, SSN'nin geçerli olması için sayının belirli bölümlerinin belirli aralıklar içinde yer alması gereken güçlü biçimlendirmesi vardır (ancak sağlama toplamı yoktur).

## <a name="pattern"></a>Desen

dört işlev, SSN'leri dört farklı desende arar:

- `Func_ssn` tire veya boşluklarla biçimlendirilmiş 2011 öncesi güçlü biçimlendirmeye sahip SSN'leri bulur (ddd-dd-dddd VEYA ddd dd d)
- `Func_unformatted_ssn` 2011 öncesi güçlü biçimlendirmesi olan ve ardışık dokuz basamak (dddd) olarak biçimlendirilmemiş SSN'leri bulur
- `Func_randomized_formatted_ssn` tire veya boşluklarla biçimlendirilmiş 2011 sonrası SSN'leri bulur (ddd-dd-dddd VEYA ddd dd dd)
- `Func_randomized_unformatted_ssn` ardışık dokuz basamak (ddddd) olarak biçimlendirilmemiş 2011 sonrası SSN'leri bulur

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_ssn` , desenle eşleşen içeriği bulur.
- 'den `Keyword_ssn` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_unformatted_ssn` , desenle eşleşen içeriği bulur.
- 'den `Keyword_ssn` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- İşlev `Func_randomized_formatted_ssn` veya `Func_randomized_unformatted_ssn` desenle eşleşen içeriği bulur.
- 'den `Keyword_ssn` bir anahtar sözcük bulunur.

```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
  </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_ssn"></a>Keyword_ssn

- SSA Numarası
- sosyal güvenlik numarası
- sosyal güvenlik #
- sosyal güvenlik #
- sosyal güvenlik hayır
- Sosyal Güvenlik #
- Soc Sn
- SSN
- SSN'ler
- SSN #
- SS #
- SSID