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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Estonya Kişisel Kimlik Kodu hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 866c78a871f0d402cab49783b43e770328b32b1d
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948402"
---
# <a name="estonia-personal-identification-code"></a>Estonya kişisel kimlik kodu

Bu hassas bilgi türü yalnızca şu durumlarda kullanılabilir:

- veri kaybı önleme ilkeleri
- iletişim uyumluluk ilkeleri
- veri yaşam döngüsü yönetimi
- kayıt yönetimi
- Bulut Uygulamaları için Microsoft Defender

## <a name="format"></a>Biçim

Boşluk ve sınırlayıcı içermeyen 11 basamak

## <a name="pattern"></a>Desen

11 basamak:

- cinsiyete ve doğum yüzyılına karşılık gelen bir basamak (tek sayı erkek, hatta kadın sayısı; 1-2: 19. yüzyıl; 3-4: 20. yüzyıl; 5-6: 21. yüzyıl)
- doğum tarihine karşılık gelen altı basamak (YYMMDD)
- aynı tarihte doğan kişileri ayıran seri numarasına karşılık gelen üç basamak
- bir denetim basamalı

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_estonia_eu_national_id_card` , desenle eşleşen içeriği bulur.
- 'den `Keywords_estonia_eu_national_id_card` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_estonia_eu_national_id_card` , desenle eşleşen içeriği bulur.

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