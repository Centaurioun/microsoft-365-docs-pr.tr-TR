---
title: BK ulusal sağlık hizmeti numarası varlık tanımı
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
description: BK ulusal sağlık hizmeti numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: d636be281b1652934fa7b4b83b3a4b5da7794a09
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948383"
---
# <a name="uk-national-health-service-number"></a>BK ulusal sağlık hizmeti numarası

## <a name="format"></a>Biçim

Boşluklarla ayrılmış 10-17 basamak

## <a name="pattern"></a>Desen

10-17 basamak:

- 3 veya 10 basamak
- boşluk
- üç basamak
- boşluk
- dört basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_uk_nhs_number` , desenle eşleşen içeriği bulur.
- Aşağıdakilerden biri doğrudur:
    - 'den `Keyword_uk_nhs_number` bir anahtar sözcük bulunur.
    - 'den `Keyword_uk_nhs_number1` bir anahtar sözcük bulunur.
    - 'den `Keyword_uk_nhs_number_dob` bir anahtar sözcük bulunur.
- Sağlama toplamı geçer.

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_uk_nhs_number"></a>Keyword_uk_nhs_number

- ulusal sağlık hizmeti
- Nhs
- sağlık hizmetleri yetkilisi
- sistem durumu yetkilisi

### <a name="keyword_uk_nhs_number1"></a>Keyword_uk_nhs_number1

- hasta kimliği
- hasta belirleme
- hasta hayır
- hasta numarası

### <a name="keyword_uk_nhs_number_dob"></a>Keyword_uk_nhs_number_dob

- GP
- DOB
- D.O.B
- Doğum tarihi
- Doğum Tarihi