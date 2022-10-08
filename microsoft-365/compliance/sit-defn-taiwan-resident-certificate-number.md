---
title: Tayvan'da yerleşik sertifika (ARC/TARC) numarası varlık tanımı
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
description: Tayvan'da yerleşik sertifika (ARC/TARC) numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 16e32c0fcfd9ae8be4f0dc7612329594b22ecc37
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472288"
---
# <a name="taiwan-resident-certificate-arctarc-number"></a>Tayvan mukim sertifikası (ARC/TARC) numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

10 harf ve rakam

## <a name="pattern"></a>Desen

10 harf ve rakam:

- iki harf (büyük/küçük harfe duyarlı değil)
- sekiz basamak

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- Normal ifade `Regex_taiwan_resident_certificate` , desenle eşleşen içeriği bulur.
- `Keyword_taiwan_resident_certificate` içinden bir anahtar sözcük bulundu.

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_taiwan_resident_certificate"></a>Keyword_taiwan_resident_certificate

- Yerleşik Sertifika
- Resident Cert
- Yerleşik Sertifika.
- Kimlik kartı
- Yabancı Yerleşik Sertifika
- Arc
- Tayvan Alan Yerleşik Sertifikası
- TARC
- 居留證
- 外僑居留證
- 台灣地區居留證
