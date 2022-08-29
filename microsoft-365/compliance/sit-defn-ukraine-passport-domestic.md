---
title: Ukrayna pasaportu yurt içi varlık tanımı
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
description: Ukrayna pasaportu yurt içi hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 7a941d28dc92f54ceb1c2f00d910b0ba1722bfa0
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367323"
---
# <a name="ukraine-passport-domestic"></a>Ukrayna pasaportu yurt içi

## <a name="format"></a>Biçim

dokuz basamak

## <a name="pattern"></a>Desen

dokuz basamak

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- Regex `Regex_Ukraine_Passport_Domestic` , desenle eşleşen içeriği bulur.
- `Keyword_Ukraine_Passport_Domestic` içinden bir anahtar sözcük bulundu.

```xml
      <!-- Ukraine Passport Domestic -->
      <Entity id="1817a540-221f-4459-9202-3bd78b81d803" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_Ukraine_Passport_Domestic"/>
          <Match idRef="Keyword_Ukraine_Passport_Domestic"/>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_ukraine_passport_domestic"></a>Keyword_ukraine_passport_domestic

- ukrayna pasaportu
- pasaport numarası
- pasaport no
- паспорт України
- номер паспорта
- персональний