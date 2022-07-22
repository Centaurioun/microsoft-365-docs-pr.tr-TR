---
title: INGİLTERE. Benzersiz Vergi Mükellefi Başvuru Numarası varlık tanımı
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
description: INGİLTERE. Benzersiz Vergi Mükellefi Başvuru Numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 31f963c73e86f0f2bf4d84b9aeac6e1a29524a3b
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948878"
---
# <a name="uk-unique-taxpayer-reference-number"></a>INGİLTERE. Benzersiz Vergi Mükellefi Başvuru Numarası

Bu hassas bilgi türü yalnızca şu durumlarda kullanılabilir:

- veri kaybı önleme ilkeleri
- iletişim uyumluluk ilkeleri
- veri yaşam döngüsü yönetimi
- kayıt yönetimi
- Bulut Uygulamaları için Microsoft Defender

## <a name="format"></a>Biçim

Boşluk ve sınırlayıcı içermeyen 10 basamak

## <a name="pattern"></a>Desen

10 basamak

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_uk_eu_tax_file_number` , desenle eşleşen içeriği bulur.
- 'den `Keywords_uk_eu_tax_file_number` bir anahtar sözcük bulunur.

```xml
      <!-- U.K. Unique Taxpayer Reference Number -->
      <Entity id="ad4a8116-0db8-439a-b545-6d967642f0ec" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_uk_eu_tax_file_number"></a>Keywords_uk_eu_tax_file_number

- vergi numarası
- vergi dosyası
- vergi kimliği
- vergi tanımlama no
- vergi kimlik numarası
- vergi no #
- vergi no
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