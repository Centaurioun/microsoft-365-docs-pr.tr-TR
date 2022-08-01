---
title: Hindistan benzersiz tanımlaması (Aadhaar) sayı varlığı tanımı
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
description: Hindistan benzersiz tanımlama (Aadhaar) numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 37f0182050e4602ebeda9d9e5376df18b7971571
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948693"
---
# <a name="india-unique-identification-aadhaar-number"></a>Hindistan benzersiz tanımlama (Aadhaar) numarası

## <a name="format"></a>Biçim

İsteğe bağlı boşluklar veya tireler içeren 12 basamak

## <a name="pattern"></a>Desen

12 basamak:

- 0 veya 1 olmayan bir basamak
- Üç basamak
- İsteğe bağlı bir boşluk veya tire
- Dört basamak
- İsteğe bağlı bir boşluk veya tire
- Denetim basamalı olan son basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_india_aadhaar` , desenle eşleşen içeriği bulur.
- 'den `Keyword_india_aadhar` bir anahtar sözcük bulunur.
- Sağlama toplamı geçer.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_india_aadhaar` , desenle eşleşen içeriği bulur.
- Sağlama toplamı geçer.

```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_india_aadhar"></a>Keyword_india_aadhar

- aadhaar
- Acar
- Acar #
- Uıd
- आधार
- uidai