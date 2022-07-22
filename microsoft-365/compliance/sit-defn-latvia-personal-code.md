---
title: Letonya kişisel kodu varlık tanımı
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
description: Letonya kişisel koduna duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 16e736220fa402df6ebcb87e947e75090b4a0f57
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948325"
---
# <a name="latvia-personal-code"></a>Letonya kişisel kodu

## <a name="format"></a>Biçim

11 basamak ve isteğe bağlı kısa çizgi

## <a name="pattern"></a>Desen

Eski biçim

11 basamak ve kısa çizgi:

- doğum tarihine karşılık gelen altı basamak (DDMMYY)
- kısa çizgi
- doğum yüzyıla karşılık gelen bir basamak ("19. yüzyıl için 0", 20. yüzyıl için "1" ve 21. yüzyıl için "2")
- rastgele oluşturulan dört basamak

Yeni biçim

11 basamak

- İki basamak "32"
- Dokuz basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_latvia_eu_national_id_card` veya regex `Regex_latvia_eu_national_id_card_new_format` desenle eşleşen içeriği bulur.
- 'den `Keywords_latvia_eu_national_id_card` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_latvia_eu_national_id_card` veya regex `Regex_latvia_eu_national_id_card_new_format` desenle eşleşen içeriği bulur.

```xml
      <!-- Latvia Personal Code -->
      <Entity id="03fcf763-27c2-49ed-9422-2641c6c895c9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>

```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

- yönetim numarası
- alvas nē
- doğum numarası
- vatandaş numarası
- sivil numara
- elektronik sayım numarası
- elektronik numara
- mali kod
- sağlık hizmeti kullanıcı numarası
- Kimliği #
- id-code
- kimlik numarası
- identifikācijas numurs
- id-number
- bireysel sayı
- latvija alva
- nacionālais id
- ulusal kimlik
- ulusal tanımlayıcı sayı
- ulusal kimlik numarası
- ulusal sigorta numarası
- ulusal kayıt numarası
- nodokļa numurs
- nodokļu kimliği
- nodokļu identifikācija numurs
- kişisel sertifika numarası
- kişisel kod
- kişisel kimlik kodu
- kişisel kimlik numarası
- kişisel kimlik kodu
- kişisel tanımlayıcı
- kişisel kimlik numarası
- kişisel numara
- kişisel sayısal kod
- personalcodeno #
- personas kodlar
- nüfus tanımlama kodu
- kamu hizmeti numarası
- kayıt numarası
- gelir numarası
- sosyal sigorta numarası
- sosyal güvenlik numarası
- eyalet vergi kodu
- vergi dosyası numarası
- vergi kimliği
- vergi tanımlama no
- vergi kimlik numarası
- vergi no #
- vergi no
- vergi numarası
- taksiye bindi #
- taxidno #
- taxidnumber #
- taxno #
- vergi numarası #
- vergi numarası
- teneke kimlik
- tin no
- Teneke #
- seçmen sayısı