---
title: Hollanda vatandaşlık hizmeti (BSN) numarası varlık tanımı
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
description: Hollanda vatandaşlık hizmeti (BSN) numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 4a5ca70bbbffe2d89b2dd05bd51e3dcda525e6a3
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66989531"
---
# <a name="netherlands-citizens-service-bsn-number"></a>Hollanda vatandaşlık hizmeti (BSN) numarası

## <a name="format"></a>Biçim

isteğe bağlı boşluklar içeren sekiz veya dokuz basamak

## <a name="pattern"></a>Desen

sekiz-dokuz basamak:

- üç basamak
- boşluk (isteğe bağlı)
- üç basamak
- boşluk (isteğe bağlı)
- iki-üç basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- Desenle eşleşen işlev `Func_netherlands_bsn finds` içeriği.
- 'den `Keyword_netherlands_bsn` bir anahtar sözcük bulunur.
- Sağlama toplamı geçer.

```xml
      <!-- Netherlands Citizen's Service (BSN) Number -->
      <Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_bsn" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card

- bsn #
- bsn
- burgerservicenummer
- vatandaş hizmet numarası
- kişi numarası
- kişisel numara
- kişisel sayısal kod
- kişiyle ilgili numara
- persoonlijk nummer
- persoonlijke numerieke code
- persoonsgebonden
- persoonsnummer
- sociaal-fiscaal nummer
- sosyal-mali sayı
- sofi
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- benzersiz kimlik numarası
- benzersiz kimlik numarası
- uniqueidentityno #