---
title: İsveç ulusal kimliği varlık tanımı
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
description: İsveç ulusal kimliği hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 9cc223e2e1f135ed1237a3f9f142ca46e51566af
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68471793"
---
# <a name="sweden-national-id"></a>İsveç ulusal kimliği

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

10 veya 12 basamak ve isteğe bağlı sınırlayıcı

## <a name="pattern"></a>Desen

10 veya 12 basamak ve isteğe bağlı sınırlayıcı:

- iki basamak (isteğe bağlı)
- YYMMDD tarih biçiminde altı basamak
- "-" veya "+" sınırlayıcısı (isteğe bağlı)
- dört basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_swedish_national_identifier`, desenle eşleşen içeriği bulur.
- 'den `Keywords_swedish_national_identifier` bir anahtar sözcük bulundu
- Sağlama toplamı başarılı.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_swedish_national_identifier`, desenle eşleşen içeriği bulur.
- Sağlama toplamı başarılı.

```xml
    <!-- Sweden National ID -->
    <Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
        <Match idRef="Keywords_swedish_national_identifier" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_swedish_national_identifier" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_swedish_national_identifier"></a>Keywords_swedish_national_identifier

- kimlik no
- kimlik numarası
- Kimliği #
- tanımlama no
- kimlik numarası
- identifikationsnumret #
- identifikationsnumret
- identitetshandling
- kimlik belgesi
- kimlik no
- kimlik numarası
- id-nummer
- kişisel kimlik
- personnummer #
- personnummer
- skatteidentifikationsnummer
