---
title: Kredi kartı numarası varlık tanımı
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
description: Kredi kartı numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 0d75c0af6c67c1d617db9f7f28fbc63c27e4d05a
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948456"
---
# <a name="credit-card-number"></a>Kredi kartı numarası

## <a name="format"></a>Biçim

Biçimlendirilebilen veya biçimlendirilemeyen 14 ile 19 basamak (dddddd) ve luhn testini geçmesi gerekir.

## <a name="pattern"></a>Desen

Visa, MasterCard, Discover Card, JCB, American Express, hediye kartları, restoran kartları, Rupay ve China UnionPay dahil olmak üzere dünya çapındaki tüm büyük markaların kartlarını algılar.

## <a name="checksum"></a>Sağlama toplamı

Evet, Luhn çeki

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_credit_card` , desenle eşleşen içeriği bulur.
- Aşağıdaki koşullardan biri doğrudur:
  - 'den `Keyword_cc_verification` bir anahtar sözcük bulunur.
  - 'den `Keyword_cc_name` bir anahtar sözcük bulunur.
  - İşlev `Func_expiration_date` doğru tarih biçiminde bir tarih bulur.
- Sağlama toplamı geçer.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- İşlev `Func_credit_card` , desenle eşleşen içeriği bulur.
- Sağlama toplamı geçer.

```xml
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_cc_verification"></a>Keyword_cc_verification

- kart doğrulama
- kart kimlik numarası
- Cvn
- Cid
- cvc2
- cvv2
- raptiye bloğu
- güvenlik kodu
- güvenlik numarası
- güvenlik no
- sorun numarası
- sorun yok
- cryptogramme
- numéro de sécurité
- numero de securite
- kreditkartenprüfnummer
- kreditkartenprufnummer
- prüfziffer
- prufziffer
- sicherheits Kode
- sicherheitscode
- sicherheitsnummer
- verfalldatum
- codice di verifica
- Cod. sicurezza
- cod sicurezza
- n autorizzazione
- código
- codigo
- Cod. Sönmez
- cod seg
- código de segurança
- codigo de seguranca
- codigo de segurança
- código de seguranca
- cód. segurança
- Cod. seguranca
- Cod. segurança
- cód. seguranca
- cód segurança
- cod seguranca
- cod segurança
- cód seguranca
- número de verificação
- numero de verificacao
- ablauf
- gültig bis
- gültigkeitsdatum
- gultig bis
- gultigkeitsdatum
- scadenza
- data scad
- fecha de süre sonu
- fecha de venc
- vencimiento
- válido hasta
- valido hasta
- vto
- data de expiração
- data de expiracao
- data em que expira
- validade
- Cesaret
- vencimento
- Işlem
- işlem numarası
- başvuru numarası
- セキュリティコード
- セキュリティ コード
- セキュリティナンバー
- セキュリティ ナンバー
- セキュリティ番号

### <a name="keyword_cc_name"></a>Keyword_cc_name

- Amex
- american express
- americanexpress
- americano espresso
- Vize
- Mastercard
- ana kart
- Mc
- Mastercard
- ana kartlar
- diner's Club
- diners club
- dinersclub
- Keşfetmek
- kartı bulma
- discovercard
- kartları bulma
- JCB
- BrandSmart
- japon kart bürosu
- carte blanche
- carteblanche
- kredi kartı
- Cc #
- cc#:

- son kullanma tarihi
- exp tarihi
- süre sonu tarihi
- d'süre sonu tarihi
- date d'exp
- süre sonu tarihi
- banka kartı
- Bankcard
- kart numarası
- kart numarası
- kartsayısı
- kartsayıları
- kart numaraları
- kredi kartı
- kredi kartları
- kredi kartları
- Ccn
- kart tutucu
- Kart
- kart tutucular
- Kart
- onay kartı
- onay kartı
- onay kartları
- onay kartları
- banka kartı
- banka kartı
- banka kartları
- banka kartları
- atm kartı
- atmcard
- atm kartları
- atmcards
- Enroute
- Yolda
- kart türü
- Cardmember Acct
- cardmember hesabı
- Can
- Kurumsal Kart
- Kurumsal kartlar
- Kart türü
- kart hesap numarası
- kart üyesi hesabı
- Cardmember Acct.
- kart no.
- kart hayır
- kart numarası
- carte bancaire
- carte de crédit
- carte de credit
- numéro de carte
- numero de carte
- nº de la carte
- nº de carte
- kreditkarte
- karte
- karteninhaber
- karteninhabers
- kreditkarteninhaber
- kreditkarteninstitut
- kreditkartentyp
- eigentümername
- kartennr
- kartennummer
- kreditkartennummer
- kreditkarten-nummer
- carta di credito
- carta credito
- n. Carta
- n carta
- Nr. Carta
- nr carta
- çok sayıda carta
- numero della carta
- numero di carta
- tarjeta credito
- tarjeta de credito
- tarjeta crédito
- tarjeta de crédito
- tarjeta de atm
- tarjeta atm
- tarjeta debito
- tarjeta de debito
- tarjeta débito
- tarjeta de débito
- nº de tarjeta
- No. de tarjeta
- no de tarjeta
- numero de tarjeta
- número de tarjeta
- tarjeta no
- tarjetahabiente
- cartão de crédito
- cartão de credito
- cartao de crédito
- cartao de credito
- cartão de débito
- cartao de débito
- cartão de debito
- cartao de debito
- débito automático
- debito automatico
- número do cartão
- numero do cartão
- número do cartao
- çok sayıda do cartao
- número de cartão
- numero de cartão
- número de cartao
- numero de cartao
- nº do cartão
- nº do cartao
- nº. do cartão
- no do cartão
- hayır cartao
- No. do cartão
- No. cartao yapma
- rupay
- sendika ödemesi
- unionpay
- lokantalar
- Diners
- クレジットカード番号
- クレジットカードナンバー
- クレジットカード＃
- クレジットカード
- クレジット
- クレカ
- カード番号
- カードナンバー
- カード＃
- アメックス
- アメリカンエクスプレス
- アメリカン エクスプレス
- Visaカード
- Visa カード
- マスターカード
- マスター カード
- マスター
- ダイナースクラブ
- ダイナース クラブ
- ダイナース
- 有効期限
- 期限
- キャッシュカード
- キャッシュ カード
- カード名義人
- カードの名義人
- カードの名義
- デビット カード
- デビットカード
- 中国银联
- 银联