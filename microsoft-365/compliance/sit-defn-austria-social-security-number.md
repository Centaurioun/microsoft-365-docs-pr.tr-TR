---
title: Avusturya sosyal güvenlik numarası varlık tanımı
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
description: Avusturya sosyal güvenlik numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 24b909e2b45bce3db5c4b4cfd1e0d3cf3d74296c
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948561"
---
# <a name="austria-social-security-number"></a>Avusturya sosyal güvenlik numarası

## <a name="format"></a>Biçim

Belirtilen biçimde 10 basamak

## <a name="pattern"></a>Desen

10 basamak:

- seri numarasına karşılık gelen üç basamak
- bir denetim basamalı
- doğum tarihine karşılık gelen altı basamak (DDMMYY)

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_austria_eu_ssn_or_equivalent` , desenle eşleşen içeriği bulur.
- anahtar sözcüğü `Keywords_austria_eu_ssn_or_equivalent` bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_austria_eu_ssn_or_equivalent` , desenle eşleşen içeriği bulur.

```xml
      <!-- Austria Social Security Number -->
      <Entity id="6896a906-86c9-4d19-a2da-6e43ccd19b7b" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_austria_eu_telephone_number" />
            <Match idRef="Keywords_austria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_austria_eu_ssn_or_equivalent"></a>Keywords_austria_eu_ssn_or_equivalent

- avusturya ssn
- ehik sayı
- ehic no
- sigorta kodu
- insurancecode #
- sigorta numarası
- sigorta no
- krankenkassennummer
- krankenversicherung
- socialsecurityno
- socialsecurityno #
- sosyal güvenlik hayır
- sosyal güvenlik numarası
- sosyal güvenlik kodu
- sozialversicherungsnummer
- sozialversicherungsnummer #
- soziale sicherheit kein
- sozialesicherheitkein #
- ssn #
- ssn
- versicherungscode
- versicherungsnummer
- zdravstveno zavarovanje