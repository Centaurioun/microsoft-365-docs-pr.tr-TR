---
title: Estonya Kişisel Kimlik Kodu varlık tanımı
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
- tier3
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Estonya Kişisel Kimlik Kodu hassas bilgi türü varlık tanımı.
ms.openlocfilehash: d14d5cade3a714cdae5983470960dd0144d2082e
ms.sourcegitcommit: 2ff545246fec060ea7829da5afbc1cdc698d51ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68361675"
---
# <a name="estonia-personal-identification-code"></a>Estonya kişisel kimlik kodu

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

Boşluk ve sınırlayıcı içermeyen 11 basamak

## <a name="pattern"></a>Desen

11 basamak:

- cinsiyete ve doğum yüzyılına karşılık gelen bir basamak (tek sayı erkek, hatta kadın sayısı; 1-2: 19. yüzyıl; 3-4: 20. yüzyıl; 5-6: 21. yüzyıl)
- doğum tarihine karşılık gelen altı basamak (YYMMDD)
- aynı tarihte doğan kişileri ayıran seri numarasına karşılık gelen üç basamak
- bir denetim basamalı

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_estonia_eu_national_id_card`, desenle eşleşen içeriği bulur.
- `Keywords_estonia_eu_national_id_card` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_estonia_eu_national_id_card`, desenle eşleşen içeriği bulur.

```xml
      <!-- Estonia Personal Identification Code -->
      <Entity id="bfb26de6-dad5-4d48-ab72-4789cdd0654c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_estonia_eu_telephone_number" />
            <Match idRef="Keywords_estonia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_estonia_eu_national_id_card"></a>Keywords_estonia_eu_national_id_card

- id-kaart
- ık
- isikukood #
- isikukood
- maksu kimliği
- maksukohustuslase identifitseerimisnumber
- maksunumber
- ulusal kimlik numarası
- ulusal sayı
- kişisel kod
- kişisel kimlik numarası
- kişisel kimlik kodu
- kişisel kimlik numarası
- personalidnumber #
- vergi kimliği
- vergi tanımlama no
- vergi kimlik numarası
- vergi no #
- vergi no
- vergi numarası
- vergi kayıt numarası
- taksiye bindi #
- taxidno #
- taxidnumber #
- taxno #
- vergi numarası #
- vergi numarası
- teneke kimlik
- tin no
- Teneke #
