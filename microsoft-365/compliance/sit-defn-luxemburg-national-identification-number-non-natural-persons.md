---
title: Luxemburg ulusal kimlik numarası (gerçek olmayan kişiler) varlık tanımı
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
- tier3
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Luxemburg ulusal kimlik numarası (gerçek olmayan kişiler) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 01eb9f4bcd10c7441a38600dab406615271f4798
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68382017"
---
# <a name="luxemburg-national-identification-number-non-natural-persons"></a>Lüksemburg ulusal kimlik numarası (gerçek olmayan kişiler)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

11 basamak

## <a name="pattern"></a>Desen

11 basamak

- iki basamak
- isteğe bağlı bir alan
- üç basamak
- isteğe bağlı bir alan
- üç basamak
- isteğe bağlı bir alan
- iki basamak
- bir denetim basamalı

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_luxemburg_eu_tax_file_number_non_natural`, desenle eşleşen içeriği bulur.
- `Keywords_luxemburg_eu_tax_file_number` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_luxemburg_eu_tax_file_number_non_natural`, desenle eşleşen içeriği bulur.

```xml
      <!-- Luxemburg National Identification Number (Non-natural persons) -->
      <Entity id="84bffa3a-d805-4788-a613-b1e4df3804cf" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_luxemburg_eu_tax_file_number"></a>Keywords_luxemburg_eu_tax_file_number

- carte de sécurité sociale
- étain olmayan
- étain #
- identifiant d'impôt
- lüksemburg vergi identifikatiounsnummer
- numéro d'étain
- numéro d'identification fiscal luxembourgeois
- numéro d'identification fiscale
- sosyal güvenlik
- sozialunterstützung
- sozialversécherung
- sozialversicherungsausweis
- steier id
- steier identifikatiounsnummer
- steier nummer
- steuer kimliği
- steueridentifikationsnummer
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
- Zinn #
- Zinn
- zinnzahl
