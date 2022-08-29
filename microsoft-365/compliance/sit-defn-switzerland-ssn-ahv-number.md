---
title: İsviçre SSN AHV numarası varlık tanımı
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
description: İsviçre SSN AHV numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: d4f5971a1ee2d0dcf96ee023ff609ba70f6ec052
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67368179"
---
# <a name="switzerland-ssn-ahv-number"></a>İsviçre SSN AHV numarası

## <a name="format"></a>Biçim

13 basamaklı sayı

## <a name="pattern"></a>Desen

13 basamaklı sayı:

- üç basamak - 756
- isteğe bağlı nokta
- dört basamak
- isteğe bağlı nokta
- dört basamak
- isteğe bağlı nokta
- iki basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_swiss_social_security_number_ahv`, desenle eşleşen içeriği bulur.
- `Keywords_swiss_social_security_number_ahv` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_swiss_social_security_number_ahv`, desenle eşleşen içeriği bulur.

```xml
      <!-- Swiss SSN AHV Number -->
      <Entity id="277cfa4b-6eaa-4a1b-9492-099dec849971" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
          <Match idRef="Keywords_swiss_social_security_number_ahv" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_swiss_ssn_ahv_number"></a>Keyword_swiss_ssn_AHV_number

- ahv
- ssn
- Pıd
- sigorta numarası
- personalidno #
- sosyal güvenlik numarası
- kişisel kimlik numarası
- kişisel kimlik no.
- insuranceno #
- uniqueidno #
- benzersiz kimlik no.
- avs numarası
- kişisel kimlik no versicherungsnummer
- identifikationsnummer
- einzigartige identität nicht
- sozialversicherungsnummer
- kimlik personel kimliği
- numéro de sécurité sociale