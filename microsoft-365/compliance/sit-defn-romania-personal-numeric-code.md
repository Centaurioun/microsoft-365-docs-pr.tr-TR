---
title: Romanya kişisel sayısal kodu (CNP) varlık tanımı
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
description: Romanya kişisel sayısal kodu (CNP) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: c1241d3bdd3035b053713137a4e64feb50a6dba0
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68470376"
---
# <a name="romania-personal-numeric-code-cnp"></a>Romanya kişisel sayısal kodu (CNP)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

Boşluk ve sınırlayıcı içermeyen 13 basamak

## <a name="pattern"></a>Desen

- 1-9 arasında bir basamak
- doğum tarihini temsil eden altı basamak (YYMMDD)
- 01-52 veya 99 olabilecek iki basamak
- dört basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_romania_eu_national_id_card`, desenle eşleşen içeriği bulur.
- `Keywords_romania_eu_national_id_card` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_romania_eu_national_id_card`, desenle eşleşen içeriği bulur.

```xml
      <!-- Romania Personal Numerical Code (CNP) -->
      <Entity id="eb5fa399-fe28-4c67-8188-d63a616ed89c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_romania_eu_national_id_card"></a>Keywords_romania_eu_national_id_card

- Cnp #
- Cnp
- cod identificare personal
- cod sayısal kişisel
- cod unic identificare
- codnumericpersonal #
- codul fiscal nr.
- identificarea fiscală nr #
- id-ul taxei
- sigorta numarası
- insurancenumber #
- ulusal kimlik #
- ulusal kimlik
- ulusal kimlik numarası
- număr identificare personal
- număr identitate
- număr kişisel unic
- număridentitate #
- număridentitate
- numărpersonalunic #
- numărpersonalunic
- număru de identificare fiscală
- numărul de identificare fiscală
- kişisel sayısal kod
- Pin #
- Pin
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
- benzersiz kimlik numarası
- benzersiz kimlik numarası
- uniqueidentityno #
- uniqueidentityno
