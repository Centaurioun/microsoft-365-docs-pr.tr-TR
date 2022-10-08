---
title: Endonezya kimlik kartı (KTP) numarası varlık tanımı
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
description: Endonezya kimlik kartı (KTP) numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 0569be435baf2763c6de63db77926189bfb4a78c
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68380619"
---
# <a name="indonesia-identity-card-ktp-number"></a>Endonezya kimlik kartı (KTP) numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

İsteğe bağlı dönemleri içeren 16 basamak

## <a name="pattern"></a>Desen

16 basamak:

- İki basamaklı il kodu
- Nokta (isteğe bağlı)
- İki basamaklı kayıt defteri veya şehir kodu
- İki basamaklı alt dağıtım kodu
- Nokta (isteğe bağlı)
- Doğum tarihi olan DDMMYY biçiminde altı basamak
- Nokta (isteğe bağlı)
- Dört basamak

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- Normal ifade `Regex_indonesia_id_card` , desenle eşleşen içeriği bulur.
- `Keyword_indonesia_id_card` içinden bir anahtar sözcük bulundu.

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_indonesia_id_card"></a>Keyword_indonesia_id_card

- Ktp
- Kartu Tanda Penduduk
- Nomor Induk Kependudukan
