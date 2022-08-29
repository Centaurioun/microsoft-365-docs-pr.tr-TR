---
title: Avustralya şirket numarası varlık tanımı
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
description: Avustralya şirket numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 86b9167340d4730f6c1726d57e94c16b3ef9993c
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67368464"
---
# <a name="australia-company-number"></a>Avustralya şirket numarası



## <a name="format"></a>Biçim

sınırlayıcılı dokuz basamak

## <a name="pattern"></a>Desen

sınırlayıcılı dokuz basamak:

- üç basamak
- boşluk
- üç basamak
- boşluk
- üç basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev Func_Australian_Company_Number desenle eşleşen içeriği bulur.
- Keyword_Australian_Company_Number anahtar sözcüğü bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- İşlev Func_Australian_Company_Number desenle eşleşen içeriği bulur.

```xml
      <!-- Australia Company Number -->
      <Entity id="b1fba4f7-7b3e-4bb9-8f9a-9366df604dbb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Australian_Company_Number" />
          <Match idRef="Keyword_Australian_Company_Number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_Australian_Company_Number" />
        </Pattern>
      </Entity>
```
## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_australia_company_number"></a>Keyword_australia_company_number

- -bilirsiniz
- avustralya şirketi hayır
- avustralya şirketi hayır #
- avustralya şirket numarası
- avustralyalı şirket hayır
- avustralyalı şirket hayır #
- avustralya şirket numarası
