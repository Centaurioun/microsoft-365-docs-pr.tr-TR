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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Tayvan'da yerleşik sertifika (ARC/TARC) numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 26719642f5cc937909c7357302f660a5a8610189
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948556"
---
# <a name="taiwan-resident-certificate-arctarc-number"></a>Tayvan mukim sertifikası (ARC/TARC) numarası

## <a name="format"></a>Biçim

10 harf ve rakam

## <a name="pattern"></a>Desen

10 harf ve rakam:

- iki harf (büyük/küçük harfe duyarlı değil)
- sekiz basamak

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade `Regex_taiwan_resident_certificate` , desenle eşleşen içeriği bulur.
- 'den `Keyword_taiwan_resident_certificate` bir anahtar sözcük bulunur.

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
- ARC
- Tayvan Alan Yerleşik Sertifikası
- TARC
- 居留證
- 外僑居留證
- 台灣地區居留證