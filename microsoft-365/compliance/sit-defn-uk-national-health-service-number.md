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
- tier3
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: BK ulusal sağlık hizmeti numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: b16ac1cc66b53bff232967aedc8b9f5265908d0e
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472266"
---
# <a name="uk-national-health-service-number"></a>BK ulusal sağlık hizmeti numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

Boşluklarla ayrılmış 10-17 basamak

## <a name="pattern"></a>Desen

10-17 basamak:

- 3 veya 10 basamak
- boşluk
- üç basamak
- boşluk
- dört basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_uk_nhs_number`, desenle eşleşen içeriği bulur.
- Aşağıdaki durumlardan biri doğrudur:
    - `Keyword_uk_nhs_number` içinden bir anahtar sözcük bulundu.
    - `Keyword_uk_nhs_number1` içinden bir anahtar sözcük bulundu.
    - `Keyword_uk_nhs_number_dob` içinden bir anahtar sözcük bulundu.
- Sağlama toplamı başarılı.

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

- Gp
- Dob
- D.O.B
- Doğum tarihi
- Doğum Tarihi
