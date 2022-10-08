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
- tier3
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Japonya banka hesap numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 3035a12a4c98c0e5c289006676c48056ea98903a
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68383029"
---
# <a name="japan-bank-account-number"></a>Japonya banka hesap numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

yedi veya sekiz basamak

## <a name="pattern"></a>Desen

banka hesap numarası:

- yedi veya sekiz basamak
- banka hesabı dal kodu:

- dört basamak
- boşluk veya tire (isteğe bağlı)
- üç basamak

Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_jp_bank_account`, desenle eşleşen içeriği bulur.
- `Keyword_jp_bank_account` içinden bir anahtar sözcük bulundu.
- Aşağıdakilerden biri doğrudur:

- İşlev `Func_jp_bank_account_branch_code`, desenle eşleşen içeriği bulur.
- `Keyword_jp_bank_branch_code` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_jp_bank_account`, desenle eşleşen içeriği bulur.
- `Keyword_jp_bank_account` içinden bir anahtar sözcük bulundu.

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
