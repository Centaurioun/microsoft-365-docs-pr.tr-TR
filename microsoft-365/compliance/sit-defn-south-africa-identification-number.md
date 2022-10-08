---
title: Güney Afrika kimlik numarası varlık tanımı
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
description: Güney Afrika kimlik numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: ca385d9255ce5906769307ad1b29b5c377cec4bf
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472046"
---
# <a name="south-africa-identification-number"></a>Güney Afrika kimlik numarası

### <a name="format"></a>Biçim

Boşluk içerebilen 13 basamak

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="pattern"></a>Desen

13 basamak:

- doğum tarihi olan YYMMDD biçiminde altı basamak
- dört basamak
- tek basamaklı vatandaşlık göstergesi
- "8" veya "9" rakamı
- sağlama toplamı olan bir basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_south_africa_identification_number`, desenle eşleşen içeriği bulur.
- `Keyword_south_africa_identification_number` içinden bir anahtar sözcük bulundu.
- Sağlama toplamı başarılı.

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_south_africa_identification_number"></a>Keyword_south_africa_identification_number

- Kimlik kartı
- Kimlik
- Kimlik
