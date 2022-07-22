---
title: Norveç kimlik numarası varlık tanımı
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
description: Norveç kimlik numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 9edce24b1fef475ce30b50d3703214d4388a1338
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948910"
---
# <a name="norway-identification-number"></a>Norveç kimlik numarası

## <a name="format"></a>Biçim

11 basamak

## <a name="pattern"></a>Desen

11 basamak:

- doğum tarihi olan DDMMYY biçiminde altı basamak
- üç basamaklı tek tek sayı
- iki denetim basamağı

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_norway_id_number` , desenle eşleşen içeriği bulur.
- 'den `Keyword_norway_id_number` bir anahtar sözcük bulunur.
- Sağlama toplamı geçer.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_norway_id_number` , desenle eşleşen içeriği bulur.
- Sağlama toplamı geçer.

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_norway_id_number"></a>Keyword_norway_id_number

- Kişisel kimlik numarası
- Norveç kimlik numarası
- Kimlik Numarası
- Kimlik
- Personnummer
- Fødselsnummer