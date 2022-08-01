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
ms.openlocfilehash: 95bbe1368ca4d6d91d98d07f5cd1c48029fd8499
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948355"
---
# <a name="bulgaria-uniform-civil-number"></a>Bulgaristan üniforma sivil numarası

Bu hassas bilgi türü yalnızca şu durumlarda kullanılabilir:

- veri kaybı önleme ilkeleri
- iletişim uyumluluk ilkeleri
- veri yaşam döngüsü yönetimi
- kayıt yönetimi
- Bulut Uygulamaları için Microsoft Defender

## <a name="format"></a>Biçim

Boşluk ve sınırlayıcı içermeyen 10 basamak

## <a name="pattern"></a>Desen

Boşluk ve sınırlayıcı içermeyen 10 basamak

- doğum tarihine karşılık gelen altı basamak (YYMMDD)
- doğum sırasına karşılık gelen iki basamak
- cinsiyete karşılık gelen bir basamak: Erkek için çift basamak ve kadın için tek bir basamak
- bir denetim basamalı

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_bulgaria_eu_national_id_card` , desenle eşleşen içeriği bulur.
- 'den `Keywords_bulgaria_eu_national_id_card` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_bulgaria_eu_national_id_card` , desenle eşleşen içeriği bulur.

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