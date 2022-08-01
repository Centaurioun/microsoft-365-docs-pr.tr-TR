---
title: Kanada sosyal sigorta numarası varlık tanımı
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
description: Kanada sosyal sigorta numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 9af5cc026da5ac6bd414ebd80ded934efb90effb
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948598"
---
# <a name="canada-social-insurance-number"></a>Kanada sosyal sigorta numarası

## <a name="format"></a>Biçim

isteğe bağlı kısa çizgi veya boşluk içeren dokuz basamak

## <a name="pattern"></a>Desen

Biçimlendirilmiş:

- üç basamak
- kısa çizgi veya boşluk
- üç basamak
- kısa çizgi veya boşluk
- üç basamak

Biçimlendirilmemiş: dokuz basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev Func_canadian_sin desenle eşleşen içeriği bulur.
- Aşağıdaki desenlerden en az ikisi:
    - 'den `Keyword_sin` bir anahtar sözcük bulunur.
    - 'den `Keyword_sin_collaborative` bir anahtar sözcük bulunur.
    - İşlev `Func_eu_date` doğru tarih biçiminde bir tarih bulur.
- Sağlama toplamı geçer.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev Func_unformatted_canadian_sin desenle eşleşen içeriği bulur.
- 'den `Keyword_sin` bir anahtar sözcük bulunur.
- Sağlama toplamı geçer.

```xml
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_sin"></a>Keyword_sin

- Günah
- sosyal sigorta
- numero d'assurance sociale
- Günah
- ssn
- ssns
- sosyal güvenlik
- numero d'assurance social
- ulusal kimlik numarası
- ulusal kimlik
- Günah #
- soc ins
- sosyal ins

### <a name="keyword_sin_collaborative"></a>Keyword_sin_collaborative

- sürücü belgesi
- sürücü lisansı
- sürücü belgesi
- sürücü lisansı
- DOB
- Doğum tarihi
- Doğum günü
- Doğum tarihi