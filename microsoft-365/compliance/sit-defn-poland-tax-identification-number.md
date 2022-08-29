---
title: Polonya vergi kimlik numarası varlık tanımı
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
description: Polonya vergi tanımlama numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 38909e64a5ab3d4756d9cc11e64041076e6ca7da
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67368003"
---
# <a name="poland-tax-identification-number"></a>Polonya vergi kimlik numarası

## <a name="format"></a>Biçim

Boşluk veya sınırlayıcı içermeyen 11 basamak

## <a name="pattern"></a>Desen

11 basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_poland_eu_tax_file_number`, desenle eşleşen içeriği bulur.
- `Keywords_poland_eu_tax_file_number` içinden bir anahtar sözcük bulundu.

```xml
      <!-- Poland Tax Identification Number -->
      <Entity id="1ff28b4d-40f2-49e9-b677-9606a88e2bca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_poland_eu_tax_file_number"></a>Keywords_poland_eu_tax_file_number

- Nip #
- Nip
- numer identyfikacji podatkowej
- numeridentyfikacjipodatkowej #
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
- kdv kimliği #
- kdv kimliği
- kdv no
- kdv numarası
- vatid #
- vatid
- vatno #