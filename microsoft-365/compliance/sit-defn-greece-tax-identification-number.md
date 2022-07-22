---
title: Yunanistan vergi kimlik numarası varlık tanımı
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
description: Yunanistan vergi kimlik numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 13fe64c6cae50526e0e3bd3b631b1ca936c10b71
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948830"
---
# <a name="greece-tax-identification-number"></a>Yunanistan vergi kimlik numarası

Bu hassas bilgi türü yalnızca şu durumlarda kullanılabilir:

- veri kaybı önleme ilkeleri
- iletişim uyumluluk ilkeleri
- veri yaşam döngüsü yönetimi
- kayıt yönetimi
- Bulut Uygulamaları için Microsoft Defender

## <a name="format"></a>Biçim

Boşluk ve sınırlayıcı içermeyen dokuz basamak

## <a name="pattern"></a>Desen

Dokuz basamak

## <a name="checksum"></a>Sağlama toplamı

Geçerli değil

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade `Regex_greece_eu_tax_file_number` , desenle eşleşen içeriği bulur.
- 'den `Keywords_greece_eu_tax_file_number` bir anahtar sözcük bulunur.

```xml
      <!-- Greek Tax Identification Number -->
      <Entity id="15a54a5a-53d4-4080-ad43-a2a4fe1d3bf7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_greece_eu_tax_file_number"></a>Keywords_greece_eu_tax_file_number

- Afm #
- Afm
- aφμ|aφμ αριθμός
- aφμ
- vergi kimliği
- vergi tanımlama no
- vergi kimlik numarası
- vergi no #
- vergi no
- vergi numarası
- vergi kayıt numarası
- vergi kayıt defteri no
- vergi kayıt defteri numarası
- taksiye bindi #
- taxidno #
- taxidnumber #
- taxno #
- vergi numarası #
- vergi numarası
- taxregistryno #
- teneke kimlik
- tin no
- Teneke #
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο
