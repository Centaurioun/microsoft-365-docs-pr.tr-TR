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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Singapur ulusal kayıt kimlik kartı (NRIC) numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: b2dfa68f3d69134f7d4eca67648c64075b5d1c44
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948525"
---
# <a name="singapore-national-registration-identity-card-nric-number"></a>Singapur ulusal kayıt kimlik kartı (NRIC) numarası

## <a name="format"></a>Biçim

dokuz harf ve rakam

## <a name="pattern"></a>Desen

- dokuz harf ve rakam:

- "F", "G", "M", "S" veya "T" harfi (büyük/küçük harfe duyarlı değildir)
- yedi basamak
- alfabetik denetim basamalı

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- Normal ifade `Regex_singapore_nric` , desenle eşleşen içeriği bulur.
- 'den `Keyword_singapore_nric` bir anahtar sözcük bulunur.
- Sağlama toplamı geçer.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade `Regex_singapore_nric` , desenle eşleşen içeriği bulur.
- Sağlama toplamı geçer.

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
- IC
- Yabancı Kimlik Numarası
- FIN
- 身份证
- 身份證