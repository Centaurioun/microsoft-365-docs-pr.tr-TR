---
title: Almanya pasaport numarası varlık tanımı
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
description: Almanya pasaport numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 3e58ded04d1507903c890598a7f2c7d892ac45e7
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948597"
---
# <a name="germany-passport-number"></a>Almanya pasaport numarası

## <a name="format"></a>Biçim

9 - 11 karakter

## <a name="pattern"></a>Desen

- C, F, G, H, J, K dilinde bir harf (büyük/küçük harfe duyarsız)
- C, F, G, H, J, K, L, M, N, P, R, T, V, W, X, Y ve Z'de sekiz basamak veya harf (büyük/küçük harfe duyarsız)
- isteğe bağlı denetim basamalı
- İsteğe bağlı d/D

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_german_passport_checksum` , desenle eşleşen içeriği bulur.
- veya `Keywords_eu_passport_number_common` anahtar `Keyword_german_passport` sözcüğü bulunur.
- Sağlama toplamı geçer.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_german_passport` dokuz karakter deseni ile eşleşen içerik bulur (denetim basamalı ve isteğe bağlı d/D olmadan).
- veya `Keywords_eu_passport_number_common` anahtar `Keyword_german_passport` sözcüğü bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- İşlev `Func_german_passport_checksum` , desenle eşleşen içeriği bulur.
- Sağlama toplamı geçer.

```xml
    <!-- German Passport Number -->
    <Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keywords_eu_passport_number_common" />
        </Any>
      </Pattern>
      <Version minEngineVersion="15.20.4570.0">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_german_passport_checksum" />
          <Any minMatches="1">
            <Match idRef="Keyword_german_passport" />
            <Match idRef="Keywords_eu_passport_number_common" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_german_passport_checksum" />
        </Pattern>
      </Version>
    </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_german_passport"></a>Keyword_german_passport

- reisepasse
- reisepassnummer
- No-Reisepass
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisepässe
- passport no.
- passport no

### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- Pasaport #
- Pasaport #
- passportid
- Pasaport
- passportno
- pasaport no
- passportnumber
- pasaport numarası
- passportnumbers
- pasaport numaraları