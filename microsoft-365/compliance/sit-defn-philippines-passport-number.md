---
title: Filipinler pasaport numarası varlık tanımı
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
description: Filipinler pasaport numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 676e68a03d4b51c5b7461f8db82323c72c295407
ms.sourcegitcommit: cd044e28516c5e024700f89fb15b92c1ea5269b0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2022
ms.locfileid: "67361544"
---
# <a name="philippines-passport-number"></a>Filipinler pasaport numarası

## <a name="format"></a>Biçim

yedi veya sekiz veya dokuz alfasayısal karakter

## <a name="pattern"></a>Desen

Yedi veya sekiz veya dokuz alfasayısal karakter:

- bir harf ve ardından altı basamak veya
- iki harf ve ardından altı basamak veya
- iki harf ve ardından yedi basamak veya
- bir harf ve ardından yedi basamak ve ardından bir harf.

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir: 

- Normal ifade Regex_philippines_passport_number desenle eşleşen içeriği bulur. 
- Keyword_philippines_passport_number anahtar sözcüğü bulunur. 

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür: 

- Normal ifade Regex_philippines_passport_number desenle eşleşen içeriği bulur. 

```xml
     <!-- Philippines Passport Number -->
     <Entity id="6fa57f91-314a-4561-8248-7ab921957448" patternsProximity="300" recommendedConfidence="85" relaxProximity="true" filters="philippines_passport_filter">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_philippines_passport_number" />
          <Match idRef="Keyword_philippines_passport_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_philippines_passport_number" />
        </Pattern>
     </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_philippines_passport_number"></a>Keyword_philippines_passport_number 

- Pasaport 
- pasaport no 
- pasaport numarası 
- Pasaport # 
- passportno 
- pasaport no. 
- passportno # 
- pasaport defteri 
- passportbook # 
- pasaporte 
- çok sayıda ng pasaporte 
- libro ng pasaporte 
