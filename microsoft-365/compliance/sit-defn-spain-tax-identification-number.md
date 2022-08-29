---
title: İspanya vergi kimlik numarası varlık tanımı
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
description: İspanya vergi tanımlama numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 678eeb3964cfa30676a302f879069d28351c2acc
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67368245"
---
# <a name="spain-tax-identification-number"></a>İspanya vergi kimlik numarası

## <a name="format"></a>Biçim

belirtilen düzende yedi veya sekiz basamak ve bir veya iki harf

## <a name="pattern"></a>Desen

İspanya Ulusal Kimlik Kartı olan İspanyol Gerçek Kişiler:

- sekiz basamak
- bir büyük harf (büyük/küçük harfe duyarlı)

İspanya Ulusal Kimlik Kartı olmayan yerleşik olmayan İspanyollar

- bir büyük harf "L" (büyük/küçük harfe duyarlı)
- yedi basamak
- bir büyük harf (büyük/küçük harfe duyarlı)

İspanya Ulusal Kimlik Kartı olmayan 14 yaşın altındaki yerleşik İspanyollar:

- bir büyük harf "K" (büyük/küçük harfe duyarlı)
- yedi basamak
- bir büyük harf (büyük/küçük harfe duyarlı)

Yabancı Kimlik Numarası olan Yabancılar

- "X", "Y" veya "Z" (büyük/küçük harfe duyarlı) olan bir büyük harf
- yedi basamak
- bir büyük harf (büyük/küçük harfe duyarlı)

Yabancı Kimlik Numarası Olmayan Yabancılar

- "M" olan bir büyük harf (büyük/küçük harfe duyarlı)
- yedi basamak
- bir büyük harf (büyük/küçük harfe duyarlı)

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_spain_eu_tax_file_number` veya `Func_spain_eu_DL_and_NI_number_citizen` desenle eşleşen içeriği bulur.
- `Keywords_spain_eu_tax_file_number` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_spain_eu_tax_file_number` veya `Func_spain_eu_DL_and_NI_number_citizen` desenle eşleşen içeriği bulur.

```xml
      <!-- Spain Tax Identification Number -->
      <Entity id="10f0d113-b0e1-47dc-872a-a4f45b9376a3" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_spain_eu_tax_file_number"></a>Keywords_spain_eu_tax_file_number

- Cıf
- cifid #
- cifnúmero #
- número de contribuyente
- número de identificación fiscal
- número de impuesto corporativo
- İspanyolca #
- İspanyolca
- spanishcifno #
- spanishcifno
- vergi dosyası no
- vergi dosyası numarası
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