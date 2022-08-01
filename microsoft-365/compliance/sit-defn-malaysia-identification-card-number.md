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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Malezya kimlik kartı numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: ed233a9aa91c1c178644c4468271ee6839c55268
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948646"
---
# <a name="malaysia-identification-card-number"></a>Malezya kimlik kartı numarası

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

## <a name="checksum"></a>Sağlama toplamı

Hayır

### <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- Normal ifade `Regex_malaysia_id_card_number` , desenle eşleşen içeriği bulur.
- 'den `Keyword_malaysia_id_card_number` bir anahtar sözcük bulunur.

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