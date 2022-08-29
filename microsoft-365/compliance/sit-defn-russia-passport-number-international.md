---
title: Rusya pasaport numarası uluslararası varlık tanımı
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
description: Rusya pasaport numarası uluslararası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 4f8c581dccac25d3c7f402e2d273037918c05868
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367433"
---
# <a name="russia-passport-number-international"></a>Rusya pasaport numarası uluslararası

## <a name="format"></a>Biçim

dokuz basamaklı sayı

## <a name="pattern"></a>Desen

dokuz basamaklı sayı:

- iki basamak
- isteğe bağlı bir boşluk veya kısa çizgi
- yedi basamak

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- Regex `Regex_Russian_Passport_Number_International` , desenle eşleşen içeriği bulur.
- `Keyword_Russian_Passport_Number` içinden bir anahtar sözcük bulundu.

```xml
      <!-- Russian Passport Number International -->
      <Entity id="ac5f4878-75e4-4b82-af2d-02e13ea9f411" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_International" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_russia_passport_number_international"></a>Keywords_russia_passport_number_international

- pasaport numarası
- pasaport no
- Pasaport #
- pasaport kimliği
- passportno #
- passportnumber #
- паспорт нет
- паспорт id
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- паспортid #
- номер паспорта
- номерпаспорта #