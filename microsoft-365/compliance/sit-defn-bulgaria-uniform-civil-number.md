---
title: Bulgaristan tek tip sivil sayı varlık tanımı
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
description: Bulgaristan tek tip sivil numara hassas bilgi türü varlık tanımı.
ms.openlocfilehash: f9e97c049cf20f3c804e0fbf0f12489e557ad9f1
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67369709"
---
# <a name="bulgaria-uniform-civil-number"></a>Bulgaristan üniforma sivil numarası

## <a name="format"></a>Biçim

Boşluk ve sınırlayıcı içermeyen 10 basamak

## <a name="pattern"></a>Desen

Boşluk ve sınırlayıcı içermeyen 10 basamak

- doğum tarihine karşılık gelen altı basamak (YYMMDD)
- doğum sırasına karşılık gelen iki basamak
- cinsiyete karşılık gelen bir basamak: Erkek için çift basamak ve kadın için tek bir basamak
- bir denetim basamalı

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_bulgaria_eu_national_id_card`, desenle eşleşen içeriği bulur.
- `Keywords_bulgaria_eu_national_id_card` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_bulgaria_eu_national_id_card`, desenle eşleşen içeriği bulur.

```xml
      <!-- Bulgaria Uniform Civil Number -->
      <Entity id="100d58b1-0a35-4fb1-aa89-e4a86fb53fcc" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Match idRef="Keywords_bulgaria_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_bulgaria_eu_telephone_number" />
            <Match idRef="Keywords_bulgaria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_bulgaria_eu_national_id_card"></a>Keywords_bulgaria_eu_national_id_card

- Bnn #
- Bnn
- bucn #
- bucn
- edinen grazhdanski nomer
- egn #
- egn
- kimlik numarası
- ulusal kimlik
- ulusal sayı
- nationalnumber #
- nationalnumber
- kişisel kimlik
- kişisel hayır
- kişisel numara
- personalidnumber #
- sosyal güvenlik numarası
- ssn #
- ssn
- tekdüzen sivil kimlik
- tek tip sivil hayır
- tek tip sivil numara
- uniformcivilno #
- uniformcivilno
- uniformcivilnumber #
- uniformcivilnumber
- benzersiz vatandaşlık numarası
- егн #
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- униформ id
- униформ граждански id
- униформ граждански не
- униформ граждански номер
- униформгражданскиid #
- униформгражданскине. #