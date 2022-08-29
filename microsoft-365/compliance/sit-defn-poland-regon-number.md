---
title: Polonya REGON numarası varlık tanımı
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
description: Polonya REGON numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 7dbdd18de1f00383b3731c4715f4aec8d3c869ad
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67369042"
---
# <a name="poland-regon-number"></a>Polonya REGON numarası

## <a name="format"></a>Biçim

9 basamaklı veya 14 basamaklı sayı

## <a name="pattern"></a>Desen

dokuz basamaklı veya 14 basamaklı sayı:

- dokuz basamak veya
- dokuz basamak
- Tire
- beş basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_polish_regon_number`, desenle eşleşen içeriği bulur.
- `Keywords_polish_regon_number` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- İşlev `Func_polish_regon_number`, desenle eşleşen içeriği bulur.

```xml
      <!-- Polish REGON Number  -->
      <Entity id="fc87b421-f437-4f8b-b739-29a735ead0d9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_regon_number" />
          <Match idRef="Keywords_polish_regon_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_regon_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_poland_regon_number"></a>Keywords_poland_regon_number

- regon id
- istatistiksel sayı
- istatistiksel kimlik
- istatistiksel hayır
- regon sayısı
- regonid #
- regonno #
- şirket kimliği
- şirket kimliği #
- companyidno #
- sayı statystyczny
- numeru regon
- numerstatystyczny #
- numeruregon #