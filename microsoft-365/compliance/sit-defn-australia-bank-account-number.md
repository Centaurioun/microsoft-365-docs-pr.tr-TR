---
title: Avustralya banka hesap numarası varlık tanımı
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
description: Avustralya banka hesabı numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: df46075da0b85f306a52b1971db7b15c6a13028b
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948371"
---
# <a name="australia-bank-account-number"></a>Avustralya banka hesap numarası

## <a name="format"></a>Biçim

banka eyalet şube numarası olan veya olmayan altı ile 10 basamak

## <a name="pattern"></a>Desen

Hesap numarası 6 ile 10 basamaktır.

Avustralya banka eyalet şube numarası:

- üç basamak
- kısa çizgi
- üç basamak

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- Normal ifade Regex_australia_bank_account_number desenle eşleşen içeriği bulur.
- Keyword_australia_bank_account_number anahtar sözcüğü bulunur.
- Normal ifade Regex_australia_bank_account_number_bsb desenle eşleşen içeriği bulur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade Regex_australia_bank_account_number desenle eşleşen içeriği bulur.

- Keyword_australia_bank_account_number anahtar sözcüğü bulunur.

```xml
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_australia_bank_account_number"></a>Keyword_australia_bank_account_number

- swift banka kodu
- muhabir banka
- temel para birimi
- usa hesabı
- tutucu adresi
- banka adresi
- bilgi hesabı
- fon transferleri
- banka ücretleri
- banka ayrıntıları
- bankacılık bilgileri
- tam adlar
- Uaea