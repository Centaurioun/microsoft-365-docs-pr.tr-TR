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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Finlandiya Avrupa sağlık sigortası numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 799f664f03f91fa35c01cc87701046faddab5dde
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367389"
---
# <a name="finland-european-health-insurance-number"></a>Finlandiya Avrupa sağlık sigortası numarası

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
