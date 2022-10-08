---
title: Luxemburg ulusal kimlik numarası (gerçek kişiler) varlık tanımı
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
description: Luxemburg ulusal kimlik numarası (gerçek kişiler) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: b6f718c25e79a6a59f30135e579c55d17ab06a2d
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68381959"
---
# <a name="luxemburg-national-identification-number-natural-persons"></a>Lüksemburg ulusal kimlik numarası (gerçek kişiler)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

Boşluk veya sınırlayıcı içermeyen 13 basamak

## <a name="pattern"></a>Desen

13 basamak:

- 11 basamak
- iki denetim basamağı

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_luxemburg_eu_tax_file_number`, desenle eşleşen içeriği bulur.
- `Keywords_luxemburg_eu_national_id_card` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_luxemburg_eu_tax_file_number`, desenle eşleşen içeriği bulur.

```xml
      <!-- Luxemburg National Identification Number (Natural persons) -->
      <Entity id="aaf661ed-29ec-426d-8bf9-880cad298ebb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

- eindeutige kimliği
- eindeutige id-nummer
- eindeutigeid #
- id personel
- idpersonnelle #
- idpersonnelle
- tek tek kod
- bireysel kimlik
- bireysel kimlik
- bireysel kimlik
- numéro d'identification personeli
- kişisel kimlik
- kişisel kimlik
- kişisel kimlik
- personalidno #
- personalidnumber #
- persönliche identifikationsnummer
- benzersiz kimlik
- benzersiz kimlik
- uniqueidkey #
