---
title: Kanada pasaport numarası varlık tanımı
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
description: Kanada pasaport numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 5a645a71bd9cdb27727fd493bcd09ceca7340c22
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66989310"
---
# <a name="canada-passport-number"></a>Kanada pasaport numarası

## <a name="format"></a>Biçim

iki büyük harf ve ardından altı basamak

## <a name="pattern"></a>Desen

iki büyük harf ve ardından altı basamak

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade `Regex_canada_passport_number` , desenle eşleşen içeriği bulur.
- veya `Keyword_passport` anahtar `Keyword_canada_passport_number` sözcüğü bulunur.

```xml
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_canada_passport_number"></a>Keyword_canada_passport_number

- kanada vatandaşlığı
- kanada pasaportu
- pasaport başvurusu
- pasaport fotoğrafları
- sertifikalı çevirmen
- kanada vatandaşları
- işlem süreleri
- yenileme uygulaması

### <a name="keyword_passport"></a>Keyword_passport

- Pasaport Numarası
- Pasaport No
- Pasaport #
- Pasaport #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート＃
- Numéro de passport
- Passport n °
- Passport Non
- Passport #
- Passport #
- PassportNon
- Passportn °