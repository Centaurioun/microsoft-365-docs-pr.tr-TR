---
title: İsrail banka hesap numarası varlık tanımı
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
description: İsrail banka hesap numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: a68f90cd92432778d89d3f8494522a5ab2822d07
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948957"
---
# <a name="israel-bank-account-number"></a>İsrail banka hesap numarası

## <a name="format"></a>Biçim

13 basamak

## <a name="pattern"></a>Desen

Biçimlendirilmiş:

- iki basamak
- tire
- üç basamak
- tire
- sekiz basamak

Biçimlendir -ilmemiş:

- Ardışık 13 basamak

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade `Regex_israel_bank_account_number` , desenle eşleşen içeriği bulur.
- 'den `Keyword_israel_bank_account_number` bir anahtar sözcük bulunur.

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_israel_bank_account_number"></a>Keyword_israel_bank_account_number

- Banka Hesap Numarası
- Banka Hesabı
- Hesap Numarası
- מספר חשבון בנק