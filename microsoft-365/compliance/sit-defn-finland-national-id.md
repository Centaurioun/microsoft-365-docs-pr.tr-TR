---
title: Finlandiya ulusal kimliği varlık tanımı
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
description: Finlandiya ulusal kimliği hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 7d196482051afb6a889d855c80616a4a15ce1df2
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948866"
---
# <a name="finland-national-id"></a>Finlandiya ulusal kimliği

## <a name="format"></a>Biçim

altı basamak artı bir yüzyıl artı üç basamak artı bir onay basamağı gösteren bir karakter

## <a name="pattern"></a>Desen

Desen aşağıdakilerin tümünü içermelidir:

- doğum tarihi olan DDMMYY biçiminde altı basamak
- yüzyıl işaretçisi ('-', '+' veya 'a')
- üç basamaklı kişisel kimlik numarası
- denetim basamağı olan bir rakam veya harf (büyük/küçük harfe duyarsız)

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- işlevi `Func_finnish_national_id` , desenle eşleşen içeriği bulur
- anahtar sözcüğü `Keyword_finnish_national_id` bulundu
- sağlama toplamı geçer

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- işlevi `Func_finnish_national_id` , desenle eşleşen içeriği bulur
- sağlama toplamı geçer

```xml
      <!-- Finnish National ID-->
      <Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finnish_national_id" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

- ainutlaatuinen henkilökohtainen tunnus
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero #
- henkilötunnusnumero
- Hetu
- kimlik no
- kimlik numarası
- kimlik numarası
- identiteetti numero
- kimlik numarası
- idnumber
- kansallinen henkilötunnus
- kansallisen henkilökortin
- ulusal kimlik kartı
- ulusal kimlik no.
- kişisel kimlik
- kişisel kimlik kodu
- personalidnumber #
- personbeteckning
- personnummer
- sosyal güvenlik numarası
- sosiaaliturvatunnus
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
- tunnistenumero
- tunnus numero
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus