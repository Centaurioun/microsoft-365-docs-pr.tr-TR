---
title: AB banka kartı numarası varlık tanımı
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
description: AB banka kartı numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 6ed7607d59a9cfe53687b023fb2adbbafee42041
ms.sourcegitcommit: 2ff545246fec060ea7829da5afbc1cdc698d51ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68363397"
---
# <a name="eu-debit-card-number"></a>AB banka kartı numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

16 - 19 basamak

## <a name="pattern"></a>Desen

16 ile 19 arasında biçimlendirilmiş veya biçimlendirilmemiş basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_eu_debit_card`, desenle eşleşen içeriği bulur.
- Aşağıdaki durumlardan en az biri doğrudur:
    - `Keyword_eu_debit_card` içinden bir anahtar sözcük bulundu.
    - `Keyword_card_terms_dict` içinden bir anahtar sözcük bulundu.
    - `Keyword_card_security_terms_dict` içinden bir anahtar sözcük bulundu.
    - `Keyword_card_expiration_terms_dict` içinden bir anahtar sözcük bulundu.
    - İşlev `Func_expiration_date`, doğru tarih biçiminde bir tarih bulur.
- Sağlama toplamı başarılı.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- İşlev Func_eu_debit_card desenle eşleşen içeriği bulur.
- Sağlama toplamı başarılı.

```xml
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
        
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_eu_debit_card" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_eu_debit_card"></a>Keyword_eu_debit_card

- hesap numarası
- kart numarası
- kart no.
- güvenlik numarası
- cc#

### <a name="keyword_card_terms_dict"></a>Keyword_card_terms_dict

- hesap numarası
- hesap numarası
- hesap numarası
- american express
- americanexpress
- americano espresso
- amex
- atm kartı
- atm kartları
- atm kaart
- atmcard
- atmcards
- atmkaart
- atmkaarten
- bancontact
- banka kartı
- bankkaart
- kart sahibi
- kart sahipleri
- kart numarası
- kart numarası
- kart numaraları
- kart türü
- cardano numerico
- cardholder
- cardholders
- cardnumber
- cardnumbers
- carta bianca
- carta credito
- carta di credito
- cartao de credito
- cartao de crédito
- cartao de debito
- cartao de débito
- carte bancaire
- carte blanche
- carte bleue
- carte de credit
- carte de crédit
- carte di credito
- carteblanche
- cartão de credito
- cartão de crédito
- cartão de debito
- cartão de débito
- cb
- ccn
- çek kartı
- çek kartları
- checkcard
- checkcards
- chequekaart
- cirrus
- cirrus-edc-maestro
- controlekaart
- controlekaarten
- kredi kartı
- kredi kartları
- creditcard
- creditcards
- debetkaart
- debetkaarten
- banka kartı
- banka kartları
- debitcard
- debitcards
- debito automatico
- diners club
- dinersclub
- discover
- discover card
- discover cards
- discovercard
- discovercards
- débito automático
- edc
- eigentümername
- avrupa banka kartı
- hoofdkaart
- hoofdkaarten
- in viaggio
- japanese card bureau
- japanse kaartdienst
- jcb
- kaart
- kaart num
- kaartaantal
- kaartaantallen
- kaarthouder
- kaarthouders
- karte
- karteninhaber
- karteninhabers
- kartennr
- kartennummer
- kreditkarte
- kreditkarten-nummer
- kreditkarteninhaber
- kreditkarteninstitut
- kreditkartennummer
- kreditkartentyp
- maestro
- master card
- master cards
- mastercard
- mastercards
- mc
- mister cash
- n carta
- carta
- no de tarjeta
- no do cartao
- no do cartão
- no. de tarjeta
- no. do cartao
- no. do cartão
- nr carta
- nr. carta
- numeri di scheda
- numero carta
- numero de cartao
- numero de carte
- numero de cartão
- numero de tarjeta
- numero della carta
- numero di carta
- numero di scheda
- numero do cartao
- numero do cartão
- numéro de carte
- nº carta
- nº de carte
- nº de la carte
- nº de tarjeta
- nº do cartao
- nº do cartão
- nº. do cartão
- número de cartao
- número de cartão
- número de tarjeta
- número do cartao
- scheda dell'assegno
- scheda dell'atmosfera
- scheda dell'atmosfera
- scheda della banca
- scheda di controllo
- scheda di debito
- scheda matrice
- schede dell'atmosfera
- schede di controllo
- schede di debito
- schede matrici
- scoprono la scheda
- scoprono le schede
- solo
- supporti di scheda
- supporto di scheda
- switch
- tarjeta atm
- tarjeta credito
- tarjeta de atm
- scoprono le schede
- tarjeta de debito
- tarjeta debito
- tarjeta no
- tarjetahabiente
- tipo della scheda
- ufficio giapponese della
- scheda
- v pay
- v-pay
- visa
- visa plus
- visa electron
- visto
- visum
- vpay

### <a name="keyword_card_security_terms_dict"></a>Keyword_card_security_terms_dict

- kart kimlik numarası
- kart doğrulaması
- cardi la verifica
- cid
- cod seg
- cod seguranca
- cod segurança
- cod sicurezza
- cod. seg
- cod. seguranca
- cod. segurança
- cod. sicurezza
- codice di sicurezza
- codice di verifica
- codigo
- codigo de seguranca
- codigo de segurança
- crittogramma
- cryptogram
- cryptogramme
- cv2
- cvc
- cvc2
- cvn
- cvv
- cvv2
- cód seguranca
- cód segurança
- cód. seguranca
- cód. segurança
- código
- código de seguranca
- código de segurança
- de kaart controle
- geeft nr uit
- düzenleme no
- düzenleme numarası
- kaartidentificatienummer
- kreditkartenprufnummer
- kreditkartenprüfnummer
- kwestieaantal
- no. dell'edizione
- no. di sicurezza
- numero de securite
- numero de verificacao
- numero dell'edizione
- numero di identificazione della
- scheda
- numero di sicurezza
- numero van veiligheid
- numéro de sécurité
- nº autorizzazione
- número de verificação
- perno il blocco
- pin engeli
- prufziffer
- prüfziffer
- güvenlik kodu
- güvenlik no
- güvenlik numarası
- sicherheits kode
- sicherheitscode
- sicherheitsnummer
- speldblok
- veiligheid nr
- veiligheidsaantal
- veiligheidscode
- veiligheidsnummer
- verfalldatum

### <a name="keyword_card_expiration_terms_dict"></a>Keyword_card_expiration_terms_dict

- ablauf
- data de expiracao
- data de expiração
- data del exp
- data di exp
- data di scadenza
- data em que expira
- data scad
- data scadenza
- date de validité
- datum afloop
- datum van exp
- de afloop
- espira
- espira
- son kullanma tarihi
- exp datum
- son kullanma
- son kullanma
- son kullanma
- son kullanma
- fecha de expiracion
- fecha de venc
- gultig bis
- gultigkeitsdatum
- gültig bis
- gültigkeitsdatum
- la scadenza
- scadenza
- valable
- validade
- valido hasta
- valor
- venc
- vencimento
- vencimiento
- verloopt
- vervaldag
- vervaldatum
- vto
- válido hasta
