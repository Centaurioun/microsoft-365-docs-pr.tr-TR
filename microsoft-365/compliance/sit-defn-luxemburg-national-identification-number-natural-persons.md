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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Luxemburg ulusal kimlik numarası (gerçek kişiler) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: d70052fdccfae70302a89069b5292c0daf5b8b2f
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66949002"
---
# <a name="luxemburg-national-identification-number-natural-persons"></a>Luxemburg ulusal kimlik numarası (gerçek kişiler)

Bu hassas bilgi türü yalnızca şu durumlarda kullanılabilir:

- veri kaybı önleme ilkeleri
- iletişim uyumluluk ilkeleri
- veri yaşam döngüsü yönetimi
- kayıt yönetimi
- Bulut Uygulamaları için Microsoft Defender

## <a name="format"></a>Biçim

Boşluk veya sınırlayıcı içermeyen 13 basamak

## <a name="pattern"></a>Desen

13 basamak:

- 11 basamak
- iki denetim basamağı

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_luxemburg_eu_tax_file_number` , desenle eşleşen içeriği bulur.
- 'den `Keywords_luxemburg_eu_national_id_card` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_luxemburg_eu_tax_file_number` , desenle eşleşen içeriği bulur.

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