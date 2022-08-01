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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Güney Afrika kimlik numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 95fbf2baa8842f1654881d0435a0328b5593242a
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948571"
---
# <a name="south-africa-identification-number"></a>Güney Afrika kimlik numarası

### <a name="format"></a>Biçim

Boşluk içerebilen 13 basamak

## <a name="pattern"></a>Desen

13 basamak:

- doğum tarihi olan YYMMDD biçiminde altı basamak
- dört basamak
- tek basamaklı vatandaşlık göstergesi
- "8" veya "9" rakamı
- sağlama toplamı olan bir basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_south_africa_identification_number` , desenle eşleşen içeriği bulur.
- 'den `Keyword_south_africa_identification_number` bir anahtar sözcük bulunur.
- Sağlama toplamı geçer.

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