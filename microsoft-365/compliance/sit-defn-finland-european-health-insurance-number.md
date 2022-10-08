---
title: Finlandiya Avrupa sağlık sigortası numarası varlık tanımı
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
description: Finlandiya Avrupa sağlık sigortası numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: d2a1a509bc2a466d504eb9cd9766ed1c998498db
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68379886"
---
# <a name="finland-european-health-insurance-number"></a>Finlandiya Avrupa sağlık sigortası numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

20 basamaklı sayı

## <a name="pattern"></a>Desen

20 basamaklı sayı:

- 10 basamak - 8024680246
- isteğe bağlı bir boşluk veya kısa çizgi
- 10 basamak

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- Regex `Regex_Finland_European_Health_Insurance_Number` , desenle eşleşen içeriği bulur.
- `Keyword_Finland_European_Health_Insurance_Number` içinden bir anahtar sözcük bulundu.

```xml
      <!-- Finland European Health Insurance Number -->
      <Entity id="60f75aed-81bf-4625-89b0-0846b9248ee7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Finland_European_Health_Insurance_Number"/>
          <Match idRef="Keyword_Finland_European_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_finland_european_health_insurance_number"></a>Keyword_finland_european_health_insurance_number

- ehic #
- ehic
- finlandiyaehicnumber #
- finska sjukförsäkringskort
- sistem durumu kartı
- sağlık sigortası kartı
- sağlık sigortası numarası
- hälsokort
- sairaanhoitokortin
- sairausvakuutuskortti
- sairausvakuutusnumero
- sjukförsäkring nummer
- sjukförsäkringskort
- suomen sairausvakuutuskortti
- terveyskortti
