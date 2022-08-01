---
title: Danimarka kişisel kimlik numarası varlık tanımı
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
description: Danimarka kişisel kimlik numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 8fbdd3fc2bd273b34fcf3625fa9f021d1f948358
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948613"
---
# <a name="denmark-personal-identification-number"></a>Danimarka kişisel kimlik numarası

## <a name="format"></a>Biçim

Kısa çizgi içeren 10 basamak

## <a name="pattern"></a>Desen

10 basamak:

- doğum tarihi olan DDMMYY biçiminde altı basamak
- isteğe bağlı bir boşluk veya kısa çizgi
- son basamağın bir denetim basamağı olduğu dört basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade `Func_denmark_eu_tax_file_number` , desenle eşleşen içeriği bulur.
- 'den `Keyword_denmark_id` bir anahtar sözcük bulunur.
- Sağlama toplamı geçer.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- Normal ifade `Func_denmark_eu_tax_file_number` , desenle eşleşen içeriği bulur.
- Sağlama toplamı geçer.

```xml
<!-- Denmark Personal Identification Number -->
    <!-- Denmark Personal Identification Number -->
      <Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keyword_denmark_id" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_denmark_id"></a>Keyword_denmark_id

- centrale personregister
- civilt registreringssystem
- Cpr
- Cpr #
- gesundheitskarte nummer
- gesundheitsversicherungkarte nummer
- sistem durumu kartı
- sağlık sigortası kart numarası
- sağlık sigortası numarası
- kimlik numarası
- identifikationsnummer
- identifikationsnummer #
- kimlik numarası
- krankenkassennummer
- nationalid #
- nationalnumber #
- ulusal sayı
- personalidnumber #
- personalidentityno #
- kişisel kimlik numarası
- personnummer
- personnummer #
- reisekrankenversicherungskartenummer
- rejsesygesikringskort
- ssn
- ssn #
- skat kimliği
- skat kode
- skat nummer
- skattenummer
- sosyal güvenlik numarası
- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhedskort
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- vergi kodu
- seyahat sağlık sigortası kartı
- uniqueidentityno #
- vergi numarası
- vergi kayıt numarası
- vergi kimliği
- vergi kimlik numarası
- taksiye bindi #
- vergi numarası #
- vergi no
- taxno #
- vergi numarası
- vergi tanımlama no
- Teneke #
- taxidno #
- taxidnumber #
- vergi no #
- teneke kimlik
- tin no
- cpr.nr
- cprnr
- cprnummer
- kişi
- personregister
- sygesikringsbevis
- sygesikringsbevisnr
- sygesikringsbevisnummer
- sygesikringskort
- sygesikringskortnr
- sygesikringskortnummer
- sygesikringsnr
- sygesikringsnummer