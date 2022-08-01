---
title: İrlanda kişisel kamu hizmeti (PPS) numarası varlık tanımı
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
description: İrlanda kişisel kamu hizmeti (PPS) numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 9473886085fe3ae5630becdeeb69efb82f428edd
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948665"
---
# <a name="ireland-personal-public-service-pps-number"></a>İrlanda kişisel kamu hizmeti (PPS) numarası

## <a name="format"></a>Biçim

Eski biçim (31 Aralık 2012'ye kadar):

- yedi basamak ve ardından 1-2 harf

Yeni biçim (1 Ocak 2013 ve sonrası):

- yedi basamak ve ardından iki harf

## <a name="pattern"></a>Desen

Eski biçim (31 Aralık 2012'ye kadar):

- yedi basamak
- bir-iki harf (büyük/küçük harfe duyarlı değil)

Yeni biçim (1 Ocak 2013 ve sonrası):

- yedi basamak
- alfabetik bir denetim basamalı harf (büyük/küçük harfe duyarlı değil)
- A-I veya "W" aralığında isteğe bağlı bir harf

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- Desenle eşleşen işlev `Func_ireland_pps finds` içeriği.
- 'den `Keywords_ireland_eu_national_id_card` bir anahtar sözcük bulunur.
- Sağlama toplamı geçer.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- İşlev `Func_ireland_pps` , desenle eşleşen içeriği bulur.
- Sağlama toplamı geçer.

```xml
      <!-- Ireland Personal Public Service (PPS) Number -->
      <Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_pps" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_ireland_pps" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

- istemci kimlik hizmeti
- kimlik numarası
- kişisel kimlik numarası
- kişisel kamu hizmeti numarası
- kişisel hizmet no
- phearsanta seirbhíse poiblí
- pps no
- pps numarası
- pps num
- pps hizmeti hayır
- ppsn
- ppsno #
- ppsno
- Psp
- kamu hizmeti hayır
- publicserviceno #
- publicserviceno
- gelir ve sosyal sigorta numarası
- rsi no
- rsi numarası
- rsin
- seirbhís aitheantais istemcisi
- uimh
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí
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