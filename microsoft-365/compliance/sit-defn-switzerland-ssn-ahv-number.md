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
ms.openlocfilehash: e06ef00d0d8c919f4506d829899b0f6150394854
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948733"
---
# <a name="switzerland-ssn-ahv-number"></a>İsviçre SSN AHV numarası

Bu hassas bilgi türü yalnızca şu durumlarda kullanılabilir:

- veri kaybı önleme ilkeleri
- iletişim uyumluluk ilkeleri
- veri yaşam döngüsü yönetimi
- kayıt yönetimi
- Bulut Uygulamaları için Microsoft Defender

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

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_swiss_social_security_number_ahv` , desenle eşleşen içeriği bulur.
- 'den `Keywords_swiss_social_security_number_ahv` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_swiss_social_security_number_ahv` , desenle eşleşen içeriği bulur.

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