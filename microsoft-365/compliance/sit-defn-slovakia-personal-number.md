---
title: Slovakya kişisel numarası varlık tanımı
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
description: Slovakya kişisel numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 3783022b44917e8b2d14144db4b5f27f9cb8b4ec
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68471694"
---
# <a name="slovakia-personal-number"></a>Slovakya kişisel numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

isteğe bağlı ters eğik çizgi içeren dokuz veya 10 basamak

## <a name="pattern"></a>Desen

- doğum tarihini temsil eden altı basamak
- isteğe bağlı eğik çizgi (/)
- üç basamak
- isteğe bağlı bir denetim basamalı

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_slovakia_eu_national_id_card`, desenle eşleşen içeriği bulur.
- `Keywords_slovakia_eu_national_id_card` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- İşlev `Func_slovakia_eu_national_id_card`, desenle eşleşen içeriği bulur.

```xml
      <!-- Slovakia Personal Number -->
      <Entity id="951c26b7-3b35-4f73-924b-15dd599cb9ab" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
      </Entity>
    </Version>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

- azonosító szám
- doğum numarası
- číslo národnej identifikačnej karty
- číslo občianského preukazu
- daňové číslo
- kimlik numarası
- tanımlama no
- kimlik numarası
- identifikačná karta č
- identifikačné číslo
- kimlik kartı no
- kimlik kartı numarası
- národná identifikačná značka č
- ulusal sayı
- nationalnumber #
- nemzeti személyazonosító igazolvány
- personalidnumber #
- rč
- rodne cislo
- rodné číslo
- sosyal güvenlik numarası
- ssn #
- ssn
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
- vergi dosyası no
- vergi dosyası numarası
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
