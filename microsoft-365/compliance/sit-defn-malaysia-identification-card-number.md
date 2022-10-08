---
title: Malezya kimlik kartı numarası varlık tanımı
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
description: Malezya kimlik kartı numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: bbfa171aa426a2f71b05eeca2ce36573d01b647f
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68382488"
---
# <a name="malaysia-identification-card-number"></a>Malezya kimlik kartı numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

İsteğe bağlı kısa çizgi içeren 12 basamak

## <a name="pattern"></a>Desen

12 basamak:

- doğum tarihi olan YYMMDD biçiminde altı basamak
- tire (isteğe bağlı)
- iki harfli doğum yeri kodu
- tire (isteğe bağlı)
- üç rastgele basamak
- tek basamaklı cinsiyet kodu

## <a name="checksum"></a>Sağlama Toplamı

Hayır

### <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- Normal ifade `Regex_malaysia_id_card_number` , desenle eşleşen içeriği bulur.
- `Keyword_malaysia_id_card_number` içinden bir anahtar sözcük bulundu.

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_malaysia_id_card_number"></a>Keyword_malaysia_id_card_number

- dijital uygulama kartı
- i/c
- i/c hayır
- ıc
- ic no
- kimlik kartı
- kimlik kartı
- kimlik kartı
- k/p
- k/p no
- kad akuan diri
- kad aplikasi digital
- kad pengenalan malaysia
- kp
- kp no
- mykad
- mykas
- mykid
- mypr
- mytentera
- malezya kimlik kartı
- malezya kimlik kartı
- nric
- kişisel kimlik kartı
