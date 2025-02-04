---
title: Çek kişisel kimlik numarası varlık tanımı
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
description: Çek kişisel kimlik numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: df2a7902f136c45e7f406061216e30e3fcec6372
ms.sourcegitcommit: 2ff545246fec060ea7829da5afbc1cdc698d51ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68362936"
---
# <a name="czech-personal-identity-number"></a>Çek kişisel kimlik numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

isteğe bağlı eğik çizgili dokuz basamak (eski biçim)

İsteğe bağlı eğik çizgili 10 basamak (yeni biçim)

## <a name="pattern"></a>Desen

dokuz basamak (eski biçim):

- doğum tarihini temsil eden altı basamak
- isteğe bağlı eğik çizgi
- üç basamak

10 basamak (yeni biçim):

- doğum tarihini temsil eden altı basamak
- isteğe bağlı eğik çizgi
- son basamak bir denetim basamağı olan dört basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_czech_id_card`, desenle eşleşen içeriği bulur.
- `Keyword_czech_id_card` içinden bir anahtar sözcük bulundu.
- Sağlama toplamı başarılı.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_czech_id_card_new_format`, desenle eşleşen içeriği bulur.
- Sağlama toplamı başarılı.

```xml
<!-- Czech Personal Identity Number -->
      <!-- Czech Personal Identity Number -->
      <Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_id_card" />
          <Match idRef="Keyword_czech_id_card" />
        </Pattern>
        <Version minEngineVersion="15.20.3000.000">
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Func_czech_id_card_new_format" />
          </Pattern>
        </Version>
      </Entity>
```
## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_czech_id_card"></a>Keyword_czech_id_card

- doğum numarası
- çek cumhuriyeti kimliği
- czechidno #
- daňové číslo
- identifikační číslo
- kimlik no
- kimlik numarası
- identityno #
- identityno
- sigorta numarası
- ulusal kimlik numarası
- nationalnumber #
- ulusal sayı
- osobní číslo
- personalidnumber #
- kişisel kimlik numarası
- kişisel kimlik numarası
- kişisel numara
- Pıd #
- Pıd
- pojištění číslo
- rč
- rodne cislo
- rodné číslo
- ssn
- ssn #
- sosyal güvenlik numarası
- vergi kimliği
- vergi tanımlama no
- vergi kimlik numarası
- vergi no #
- vergi no
- vergi numarası
- vergi kayıt numarası
- taksiye bindi #
- taxidno #
- taxidnumber #
- taxno #
- vergi numarası #
- vergi numarası
- teneke kimlik
- tin no
- Teneke #
- benzersiz kimlik numarası
