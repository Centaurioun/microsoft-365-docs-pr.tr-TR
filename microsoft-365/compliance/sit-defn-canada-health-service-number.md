---
title: Kanada sağlık hizmeti numarası varlık tanımı
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
description: Kanada sağlık hizmeti numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: ea98e3861b1969506ecbd4f35f23d72b8f92a295
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948993"
---
# <a name="canada-health-service-number"></a>Kanada sağlık hizmeti numarası

## <a name="format"></a>Biçim

 10 basamak

## <a name="pattern"></a>Desen

10 basamak

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade `Regex_canada_health_service_number` , desenle eşleşen içeriği bulur.
- 'den `Keyword_canada_health_service_number` bir anahtar sözcük bulunur.

```xml
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_canada_health_service_number"></a>Keyword_canada_health_service_number

- kişisel sağlık numarası
- hasta bilgileri
- sağlık hizmetleri
- uzmanlık hizmetleri
- otomobil kazası
- hasta hastanesi
- Psikiyatrist
- işçi tazminatı
- Engelli