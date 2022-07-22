---
title: Polonya pasaport numarası varlık tanımı
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
description: Polonya pasaport numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 910084a1c4a2c97256a2045e25ac436c248899fd
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948890"
---
# <a name="poland-passport-number"></a>Polonya pasaport numarası

Bu hassas bilgi türü varlığı AB Pasaport Numarası hassas bilgi türüne dahil edilir. Tek başına hassas bilgi türü varlığı olarak da kullanılabilir.

## <a name="format"></a>Biçim

iki harf ve yedi basamak

## <a name="pattern"></a>Desen

İki harf (büyük/küçük harfe duyarlı değil) ve ardından yedi basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_polish_passport_number_v2` , desenle eşleşen içeriği bulur.
- Sağlama toplamı geçer.
- veya `Keyword_polish_national_passport_number` anahtar `Keywords_eu_passport_number` sözcüğü bulunur.
- 'den `Keywords_eu_passport_date` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_polish_passport_number_v2` , desenle eşleşen içeriği bulur.
- Sağlama toplamı geçer.
- veya `Keyword_polish_national_passport_number` anahtar `Keywords_eu_passport_number` sözcüğü bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- İşlev `Func_polish_passport_number_v2` , desenle eşleşen içeriği bulur.
- Sağlama toplamı geçer.

```xml
      <!-- Poland Passport Number -->
      <Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_passport_number_v2" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

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

### <a name="keyword_polish_national_passport_number"></a>Keyword_polish_national_passport_number

- numer paszportu
- numery paszportów
- numery paszportowe
- nr paszportu
- Nr. paszportu
- nr paszportów
- n° geçiş noktası
- passport n°

### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- sorun tarihi
- süre sonu tarihi