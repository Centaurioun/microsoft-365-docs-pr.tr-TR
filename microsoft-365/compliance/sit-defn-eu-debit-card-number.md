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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: AB banka kartı numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 53e7ea3475786032d2871092e3c7e6c39697958c
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66949021"
---
# <a name="eu-debit-card-number"></a>AB banka kartı numarası

## <a name="format"></a>Biçim

16 basamak

## <a name="pattern"></a>Desen

Karmaşık ve sağlam desen

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_eu_debit_card` , desenle eşleşen içeriği bulur.
- Aşağıdakilerden en az biri doğrudur:
    - 'den `Keyword_eu_debit_card` bir anahtar sözcük bulunur.
    - 'den `Keyword_card_terms_dict` bir anahtar sözcük bulunur.
    - 'den `Keyword_card_security_terms_dict` bir anahtar sözcük bulunur.
    - 'den `Keyword_card_expiration_terms_dict` bir anahtar sözcük bulunur.
    - İşlev `Func_expiration_date` doğru tarih biçiminde bir tarih bulur.
- Sağlama toplamı geçer.

```xml
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
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
    </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_eu_debit_card"></a>Keyword_eu_debit_card

- hesap numarası
- kart numarası
- kart no.
- güvenlik numarası
- Cc #

### <a name="keyword_card_terms_dict"></a>Keyword_card_terms_dict

- acct nbr
- acct num
- acct no
- american express
- americanexpress
- americano espresso
- Amex
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
- kart tutucu
- kart tutucular
- kart numarası
- kart numarası
- kart numaraları
- kart türü
- cardano numerico
- Kart
- Kart
- kartsayısı
- kartsayıları
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
- Cb
- Ccn
- onay kartı
- onay kartları
- onay kartı
- onay kartları
- chequekaart
- Cirrus
- cirrus-edc-maestro
- controlekaart
- controlekaarten
- kredi kartı
- kredi kartları
- kredi kartı
- kredi kartları
- debetkaart
- debetkaarten
- banka kartı
- banka kartları
- banka kartı
- banka kartları
- debito automatico
- diners club
- dinersclub
- Keşfetmek
- kartı bulma
- kartları bulma
- discovercard
- keşif kartları
- débito automático
- Edc
- eigentümername
- avrupa banka kartı
- hoofdkaart
- hoofdkaarten
- viaggio'da
- japon kart bürosu
- japanse kaartdienst
- Jcb
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
- Maestro
- ana kart
- ana kartlar
- Mastercard
- Mastercard
- Mc
- bay nakit
- n carta
- Carta
- no de tarjeta
- hayır cartao
- no do cartão
- No. de tarjeta
- No. cartao yapma
- No. do cartão
- nr carta
- Nr. Carta
- numeri di scheda
- çok sayıda carta
- numero de cartao
- numero de carte
- numero de cartão
- numero de tarjeta
- numero della carta
- numero di carta
- numero di scheda
- çok sayıda do cartao
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
- Solo
- supporti di scheda
- supporto di scheda
- Anahtarı
- tarjeta atm
- tarjeta credito
- tarjeta de atm
- tarjeta de credito
- tarjeta de debito
- tarjeta debito
- tarjeta no
- tarjetahabiente
- tipo della scheda
- ufficio giapponese della
- scheda
- v pay
- v-pay
- Vize
- visa plus
- visa elektron
- Visto
- visum
- vpay

### <a name="keyword_card_security_terms_dict"></a>Keyword_card_security_terms_dict

- kart kimlik numarası
- kart doğrulama
- cardi la verifica
- Cid
- cod seg
- cod seguranca
- cod segurança
- cod sicurezza
- Cod. Sönmez
- Cod. seguranca
- Cod. segurança
- Cod. sicurezza
- codice di sicurezza
- codice di verifica
- codigo
- codigo de seguranca
- codigo de segurança
- crittogramma
- cryptogram
- cryptogramme
- cv2
- Cvc
- cvc2
- Cvn
- Cvv
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
- sorun yok
- sorun numarası
- kaartidentificatienummer
- kreditkartenprufnummer
- kreditkartenprüfnummer
- kwestieaantal
- No. dell'edizione
- No. di sicurezza
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
- raptiye bloğu
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
- exp tarihi
- exp datum
- Sona erme
- Sona er
- Sona eri -yor
- Bitiş
- fecha de süre sonu
- fecha de venc
- gultig bis
- gultigkeitsdatum
- gültig bis
- gültigkeitsdatum
- la scadenza
- scadenza
- değerli
- validade
- valido hasta
- Cesaret
- venc
- vencimento
- vencimiento
- verloopt
- vervaldag
- vervaldatum
- vto
- válido hasta