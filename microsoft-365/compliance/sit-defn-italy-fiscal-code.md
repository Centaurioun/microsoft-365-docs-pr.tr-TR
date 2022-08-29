---
title: İtalya mali kodu varlık tanımı
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
description: İtalya mali koduna duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: dd7fae7b927532d9224cc852419f01e31f5dbef4
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67368575"
---
# <a name="italy-fiscal-code"></a>İtalya mali kodu

## <a name="format"></a>Biçim

Belirtilen desendeki harf ve rakamlardan oluşan 16 karakterlik bir birleşim

## <a name="pattern"></a>Desen

Harf ve rakamlardan oluşan 16 karakterlik bir birleşim:

- aile adındaki ilk üç harfe karşılık gelen üç harf
- addaki birinci, üçüncü ve dördüncü ünsüzlere karşılık gelen üç harf
- doğum yılının son rakamlarına karşılık gelen iki basamak
- doğum ayının harfine karşılık gelen bir harf— harfler alfabetik sırada kullanılır, ancak yalnızca A-E, H, L, M, P, R to T harfleri kullanılır (ocak A ve Ekim ayı R olur)
- cinsiyetleri ayırt etmek için doğum ayının gününe karşılık gelen iki basamak, kadınlar için doğum gününe 40 eklenir
- kişinin doğduğu belediyeye özgü alan koduna karşılık gelen dört basamak (ülke genelindeki kodlar yabancı ülkeler için kullanılır)
- tek eşlikli basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_italy_eu_national_id_card`, desenle eşleşen içeriği bulur.
- `Keywords_italy_eu_national_id_card` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_italy_eu_national_id_card`, desenle eşleşen içeriği bulur.

```xml
      <!-- Italy Fiscal Code -->
      <Entity id="4cd79172-8da9-4ff5-9188-98b1e7e2eca6" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_italy_eu_national_id_card"></a>Keywords_italy_eu_national_id_card

- codice fiscal
- kodice fiscale
- codice id personale
- codice personale
- mali kod
- numero certificato personale
- numero di identificazione fiscale
- numero id personale
- çok sayıda kişisel
- kişisel sertifika numarası
- kişisel kod
- kişisel kimlik kodu
- kişisel kimlik numarası
- personalcodeno #
- vergi kodu
- vergi kimliği
- vergi tanımlama no
- vergi kimlik numarası
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