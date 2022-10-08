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
- tier3
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Danimarka kişisel kimlik numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: a9e47db57f98ab2ad06ba34dee3bc73d3b558863
ms.sourcegitcommit: 2ff545246fec060ea7829da5afbc1cdc698d51ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68363133"
---
# <a name="denmark-personal-identification-number"></a>Danimarka kişisel kimlik numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

Kısa çizgi içeren 10 basamak

## <a name="pattern"></a>Desen

10 basamak:

- doğum tarihi olan DDMMYY biçiminde altı basamak
- isteğe bağlı bir boşluk veya kısa çizgi
- son basamağın bir denetim basamağı olduğu dört basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- Normal ifade `Func_denmark_eu_tax_file_number` , desenle eşleşen içeriği bulur.
- `Keyword_denmark_id` içinden bir anahtar sözcük bulundu.
- Sağlama toplamı başarılı.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- Normal ifade `Func_denmark_eu_tax_file_number` , desenle eşleşen içeriği bulur.
- Sağlama toplamı başarılı.

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
