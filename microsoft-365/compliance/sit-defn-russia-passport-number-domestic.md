---
title: Rusya pasaport numarası yurt içi varlık tanımı
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
description: Rusya pasaport numarası yurt içi hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 186f5fc3e231a311ef8d9de4a87dd18c7b47972b
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67368862"
---
# <a name="russia-passport-number-domestic"></a>Rusya pasaport numarası yurt içi

## <a name="format"></a>Biçim

10 basamaklı sayı

## <a name="pattern"></a>Desen

10 basamaklı sayı:

- iki basamak
- isteğe bağlı bir boşluk veya kısa çizgi
- iki basamak
- isteğe bağlı bir alan
- altı basamak

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- Regex `Regex_Russian_Passport_Number_Domestic` , desenle eşleşen içeriği bulur.
- `Keyword_Russian_Passport_Number` içinden bir anahtar sözcük bulundu.

```xml
      <!-- Russian Passport Number Domestic -->
      <Entity id="76ec2f5d-cedb-48e1-8070-1998794af445" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_Domestic" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_russia_passport_number_domestic"></a>Keyword_russia_passport_number_domestic

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