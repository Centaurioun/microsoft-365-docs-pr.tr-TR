---
title: Arjantin ulusal kimliği (DNI) numarası varlık tanımı
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
description: Arjantin ulusal kimliği (DNI) numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: f7a74b4f92cc23acf4c71320c06455fffcff378f
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948718"
---
# <a name="argentina-national-identity-dni-number"></a>Arjantin ulusal kimlik (DNI) numarası

## <a name="format"></a>Biçim

Noktalı veya noktasız sekiz basamak

## <a name="pattern"></a>Desen

Sekiz basamak:

- iki basamak
- isteğe bağlı bir dönem
- üç basamak
- isteğe bağlı bir dönem
- üç basamak

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade Regex_argentina_national_id desenle eşleşen içeriği bulur.
- Keyword_argentina_national_id anahtar sözcüğü bulunur.

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Arjantin Ulusal Kimlik numarası
- cedula
- cédula
- dni
- documento nacional de identidad
- documento número
- documento numero
- registro nacional de las personas
- rnp