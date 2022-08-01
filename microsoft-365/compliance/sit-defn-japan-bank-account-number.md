---
title: Japonya banka hesap numarası varlık tanımı
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
description: Japonya banka hesap numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 1e762a32654e6aa14e0b20d7e09ab5167cc330a5
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948544"
---
# <a name="japan-bank-account-number"></a>Japonya banka hesap numarası

## <a name="format"></a>Biçim

yedi veya sekiz basamak

## <a name="pattern"></a>Desen

banka hesap numarası:

- yedi veya sekiz basamak
- banka hesabı dal kodu:

- dört basamak
- boşluk veya tire (isteğe bağlı)
- üç basamak

Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_jp_bank_account` , desenle eşleşen içeriği bulur.
- 'den `Keyword_jp_bank_account` bir anahtar sözcük bulunur.
- Aşağıdakilerden biri doğrudur:

- İşlev `Func_jp_bank_account_branch_code` , desenle eşleşen içeriği bulur.
- 'den `Keyword_jp_bank_branch_code` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_jp_bank_account` , desenle eşleşen içeriği bulur.
- 'den `Keyword_jp_bank_account` bir anahtar sözcük bulunur.

```xml
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_jp_bank_account"></a>Keyword_jp_bank_account

- Hesap Numarası Denetleniyor
- Hesap Denetleniyor
- Hesap Denetleniyor #
- Acct Numarası Denetleniyor
- Acct Denetleniyor #
- Tahakkuk No denetleniyor.
- Hesap No denetleniyor.
- Banka Hesap Numarası
- Banka Hesabı
- Banka Hesabı #
- Banka Tahakkuk Numarası
- Banka Hesabı #
- Banka Tahakkuk No
- Banka Hesabı No.
- Tasarruf Hesabı Numarası
- Tasarruf Hesabı
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
- 口座番号
- 銀行口座
- 銀行口座番号
- 総合口座
- 普通預金口座
- 普通口座
- 当座預金口座
- 当座口座
- 預金口座
- 振替口座
- 銀行
- バンク

### <a name="keyword_jp_bank_branch_code"></a>Keyword_jp_bank_branch_code

- 支店番号
- 支店コード
- 店番号