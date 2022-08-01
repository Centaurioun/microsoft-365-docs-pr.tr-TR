---
title: Malta vergi kimlik numarası varlık tanımı
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
description: Malta vergi kimlik numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 5f77f6755ff69bf200a3999e684901bf39bdf6d9
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948490"
---
# <a name="malta-tax-identification-number"></a>Malta vergi kimlik numarası

## <a name="format"></a>Biçim

Malta uyruklular için:

- belirtilen düzende yedi basamak ve bir harf

Malta uyruklu olmayanlar ve Maltalı varlıklar:

- dokuz basamak

## <a name="pattern"></a>Desen

Malta uyruklular: yedi rakam ve bir harf

- yedi basamak
- bir harf (büyük/küçük harfe duyarlı değil)

Malta uyruklu olmayanlar ve Malta varlıkları: dokuz basamak

- dokuz basamak

## <a name="checksum"></a>Sağlama toplamı

Geçerli değil

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Regex `Regex_malta_eu_tax_file_number`  veya `Regex_malta_eu_tax_file_number_non_maltese_national` desenle eşleşen içeriği bulur.
- 'den `Keywords_malta_eu_tax_file_number` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- Regex `Regex_malta_eu_tax_file_number` veya `Regex_malta_eu_tax_file_number_non_maltese_national` desenle eşleşen içeriği bulur.

```xml
      <!-- Malta Tax ID Number -->
      <Entity id="ec830c63-65f4-45d0-9d8c-910dc8334b20" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_malta_eu_tax_file_number"></a>Keywords_malta_eu_tax_file_number

- vatandaş hizmet numarası
- id tat-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- kişisel sayısal kod
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
- benzersiz kimlik numarası
- benzersiz kimlik numarası
- uniqueidentityno #