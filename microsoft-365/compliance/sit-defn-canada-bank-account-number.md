---
title: Kanada banka hesap numarası varlık tanımı
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
description: Kanada banka hesabı numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: c7008b17ff532a55dfefc079a07fc8e95f789b04
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948582"
---
# <a name="canada-bank-account-number"></a>Kanada banka hesap numarası

## <a name="format"></a>Biçim

7 veya 12 basamak

## <a name="pattern"></a>Desen

Kanada Banka Hesap Numarası 7 veya 12 basamaktır.

Kanada banka hesabı geçiş numarası:

- beş basamak
- kısa çizgi
- üç basamak OR
- sıfır "0"
- sekiz basamak

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- Normal ifade `Regex_canada_bank_account_number` , desenle eşleşen içeriği bulur.
- 'den `Keyword_canada_bank_account_number` bir anahtar sözcük bulunur.
- Normal ifade `Regex_canada_bank_account_transit_number` , desenle eşleşen içeriği bulur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- Normal ifade `Regex_canada_bank_account_number` , desenle eşleşen içeriği bulur.
- 'den `Keyword_canada_bank_account_number` bir anahtar sözcük bulunur.

```xml
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_canada_bank_account_number"></a>Keyword_canada_bank_account_number

- kanada tasarruf bonoları
- kanada gelir ajansı
- kanada finans kurumu
- doğrudan para yatırma formu
- kanada vatandaşı
- yasal temsilci
- noter
- yeminler komiseri
- çocuk bakımı avantajı
- evrensel çocuk bakımı
- kanada çocuk vergisi avantajı
- gelir vergisi avantajı
- uyumlaştırılmış satış vergisi
- sosyal sigorta numarası
- gelir vergisi iadesi
- çocuk vergisi avantajı
- bölgesel ödemeler
- kurum numarası
- para yatırma isteği
- bankacılık bilgileri
- doğrudan para yatırma