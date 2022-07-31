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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Endonezya kimlik kartı (KTP) numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: d70e6ca902c6246e6faa67a91c5b52ae65e4fd47
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948340"
---
# <a name="indonesia-identity-card-ktp-number"></a>Endonezya kimlik kartı (KTP) numarası

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

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- Normal ifade `Regex_indonesia_id_card` , desenle eşleşen içeriği bulur.
- 'den `Keyword_indonesia_id_card` bir anahtar sözcük bulunur.

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

- KTP
- Kartu Tanda Penduduk
- Nomor Induk Kependudukan