---
title: Singapur ulusal kayıt kimlik kartı (NRIC) numarası varlık tanımı
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
description: Singapur ulusal kayıt kimlik kartı (NRIC) numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: f77564f85444f3928a3ed6d3437d04e19774c411
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68471804"
---
# <a name="singapore-national-registration-identity-card-nric-number"></a>Singapur ulusal kayıt kimlik kartı (NRIC) numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

dokuz harf ve rakam

## <a name="pattern"></a>Desen

- dokuz harf ve rakam:

- "F", "G", "M", "S" veya "T" harfi (büyük/küçük harfe duyarlı değildir)
- yedi basamak
- alfabetik denetim basamalı

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- Normal ifade `Regex_singapore_nric` , desenle eşleşen içeriği bulur.
- `Keyword_singapore_nric` içinden bir anahtar sözcük bulundu.
- Sağlama toplamı başarılı.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- Normal ifade `Regex_singapore_nric` , desenle eşleşen içeriği bulur.
- Sağlama toplamı başarılı.

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_singapore_nric"></a>Keyword_singapore_nric

- Ulusal Kayıt Kimlik Kartı
- Kimlik Kartı Numarası
- NRIC
- Ic
- Yabancı Kimlik Numarası
- FIN
- 身份证
- 身份證
