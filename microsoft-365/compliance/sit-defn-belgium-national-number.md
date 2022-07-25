---
title: Belçika ulusal sayı varlık tanımı
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
description: Belçika ulusal sayıya duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 5fc644a8dcb275cba2986139dfdd16444e47c218
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66989525"
---
# <a name="belgium-national-number"></a>Belçika ulusal numarası

## <a name="format"></a>Biçim

11 basamak artı isteğe bağlı sınırlayıcılar

## <a name="pattern"></a>Desen

11 basamak ve sınırlayıcılar:

- YY biçiminde altı basamak ve iki isteğe bağlı nokta. Doğum tarihi için MM.DD
- Nokta, tire, boşluktan isteğe bağlı sınırlayıcı
- üç sıralı basamak (erkekler için, hatta dişiler için)
- Nokta, tire, boşluktan isteğe bağlı sınırlayıcı
- iki denetim basamağı

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_belgium_national_number` , desenle eşleşen içeriği bulur.
- 'den `Keyword_belgium_national_number` bir anahtar sözcük bulunur.
- Sağlama toplamı geçer.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- İşlev `Func_belgium_national_number` , desenle eşleşen içeriği bulur.
- Sağlama toplamı geçer.

```xml
<!-- Belgium National Number -->
       <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_national_number" />
          <Match idRef="Keyword_belgium_national_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_belgium_national_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_belgium_national_number"></a>Keyword_belgium_national_number

- belasting aantal
- Bnn #
- Bnn
- carte d'identité
- identifiant national
- identifiantnational #
- identificatie
- Kimlik
- identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- Kimlik
- Yazıt
- ulusal sayı
- ulusal kayıt defteri
- nationalnumber #
- nationalnumber
- Nif #
- Nif
- numéro d'assuré
- numéro de registre national
- numéro de sécurité
- numéro d'identification
- numéro d'immatriculation
- numéro national
- numéronational #
- kişisel kimlik numarası
- personalausweis
- personalidnumber #
- registratie
- Kayıt
- registrationsnumme
- registrierung
- sosyal güvenlik numarası
- ssn #
- ssn
- steuernummer
- vergi kimliği
- vergi tanımlama no
- vergi kimlik numarası
- vergi no #
- vergi no
- vergi numarası
- vergi kayıt numarası
- taksiye bindi #
- taxidno #
- taxidnumber #
- taxno #
- vergi numarası #
- vergi numarası
- teneke kimlik
- tin no
- Teneke #