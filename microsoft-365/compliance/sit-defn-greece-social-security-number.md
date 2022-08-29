---
title: Yunanistan Sosyal Güvenlik Numarası (AMKA) varlık tanımı
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
description: Yunanistan Sosyal Güvenlik Numarası (AMKA) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: f7f313987f647efcb066ac95d64e8aeaec2fa44e
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67369841"
---
# <a name="greece-social-security-number-amka"></a>Yunanistan Sosyal Güvenlik Numarasını (AMKA)

## <a name="format"></a>Biçim

Boşluk ve sınırlayıcı içermeyen 11 basamak

## <a name="pattern"></a>Desen

- Doğum tarihi olarak altı basamak YYMMDD
- Dört basamak
- denetim basamalı

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_greece_eu_ssn`, desenle eşleşen içeriği bulur.
- `Keywords_greece_eu_ssn_or_equivalent` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_greece_eu_ssn`, desenle eşleşen içeriği bulur.

```xml
      <!-- Greece Social Security Number (AMKA) -->
      <Entity id="e39b03f4-50ea-41ae-af7a-a4b9539596ad" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_greece_eu_ssn" />
          <Match idRef="Keywords_greece_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_greece_eu_ssn" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_greece_eu_ssn_or_equivalent"></a>Keywords_greece_eu_ssn_or_equivalent

- ssn
- ssn #
- sosyal güvenlik hayır
- socialsecurityno #
- sosyal güvenlik numarası
- Özdemir
- a.m.k.a.
- Αριθμού Μητρώου Κοινωνικής Ασφάλισης