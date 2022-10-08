---
title: ABD banka hesabı numarası varlık tanımı
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
description: ABD banka hesabı numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 94eec07def3ffc9d4c8b5b7bf9e7a85dc988ecb1
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68471936"
---
# <a name="us-bank-account-number"></a>ABD banka hesap numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

6-17 basamak

## <a name="pattern"></a>Desen

6-17 ardışık basamak

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- Normal ifade `Regex_usa_bank_account_number` , desenle eşleşen içeriği bulur.
- `Keyword_usa_Bank_Account` içinden bir anahtar sözcük bulundu.

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_usa_bank_account"></a>Keyword_usa_Bank_Account

- Hesap Numarası Denetleniyor
- Hesap Denetleniyor
- Hesap Denetleniyor #
- Acct Numarası Denetleniyor
- Acct Denetleniyor #
- Tahakkuk No denetleniyor.
- Hesap No denetleniyor.
- Banka Hesap Numarası
- Banka Hesabı #
- Banka Tahakkuk Numarası
- Banka Hesabı #
- Banka Tahakkuk No
- Banka Hesabı No.
- Tasarruf Hesabı Numarası
- Tasarruf Hesabı.
- Tasarruf Hesabı #
- TasarrufLar Acct Numarası
- TasarrufLar Acct #
- TasarrufLar Tahakkuk No
- Tasarruf Hesabı No.
- Banka Hesabı Numarası
- Borç Hesabı
- Borç Hesabı #
- Borç Tahakkuk Numarası
- Borç Hesabı #
- Borç Tahakkuk No
- Borç Hesabı No
