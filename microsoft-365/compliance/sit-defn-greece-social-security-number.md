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
ms.openlocfilehash: c28819240da0fe67a93f848502a9f274fc7f9229
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948834"
---
# <a name="greece-social-security-number-amka"></a>Yunanistan Sosyal Güvenlik Numarası (AMKA)

Bu hassas bilgi türü yalnızca şu durumlarda kullanılabilir:

- veri kaybı önleme ilkeleri
- iletişim uyumluluk ilkeleri
- veri yaşam döngüsü yönetimi
- kayıt yönetimi
- Bulut Uygulamaları için Microsoft Defender

## <a name="format"></a>Biçim

Boşluk ve sınırlayıcı içermeyen 11 basamak

## <a name="pattern"></a>Desen

- Doğum tarihi olarak altı basamak YYMMDD
- Dört basamak
- denetim basamalı

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_greece_eu_ssn` , desenle eşleşen içeriği bulur.
- 'den `Keywords_greece_eu_ssn_or_equivalent` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_greece_eu_ssn` , desenle eşleşen içeriği bulur.

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