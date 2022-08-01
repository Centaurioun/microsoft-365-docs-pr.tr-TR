---
title: Çin yerleşik kimlik kartı (PRC) numarası varlık tanımı
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
description: Çin yerleşik kimlik kartı (PRC) numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 9ab0f1af6de2c8ffdcb835824e1559ab1a574718
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948426"
---
# <a name="china-resident-identity-card-prc-number"></a>Çin mukim kimlik kartı (PRC) numarası

## <a name="format"></a>Biçim

18 basamak

## <a name="pattern"></a>Desen

18 basamak:

- adres kodu olan altı basamak
- doğum tarihi olan YYYYMMDD biçiminde sekiz basamak
- sipariş kodu olan üç basamak
- denetim basamalı bir basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_china_resident_id` , desenle eşleşen içeriği bulur.
- 'den `Keyword_china_resident_id` bir anahtar sözcük bulunur.
- Sağlama toplamı geçer.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_china_resident_id` , desenle eşleşen içeriği bulur.
- Sağlama toplamı geçer.

```xml
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

## <a name="keyword_china_resident_id"></a>Keyword_china_resident_id

- Yerleşik Kimlik Kartı
- ÇHC
- Ulusal Kimlik Kartı
- 身份证
- 居民 身份证
- 居民身份证
- 鉴定
- 身分證
- 居民 身份證
- 鑑定