---
title: Güney Kore yerleşik kayıt numarası varlık tanımı
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
description: Güney Kore yerleşik kayıt numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 94de2ebb31e8bd7a0d9c175e318e166da691bbca
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948329"
---
# <a name="south-korea-resident-registration-number"></a>Güney Kore mukim kayıt numarası

## <a name="format"></a>Biçim

Kısa çizgi içeren 13 basamak

## <a name="pattern"></a>Desen

13 basamak:

- doğum tarihi olan YYMMDD biçiminde altı basamak
- kısa çizgi
- yüzyıla ve cinsiyete göre belirlenen bir rakam
- dört basamaklı doğum bölgesi kodu
- önceki sayıların özdeş olduğu kişileri ayırt etmek için kullanılan bir basamak
- onay basamalı.

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_south_korea_resident_number` , desenle eşleşen içeriği bulur.
- 'den `Keyword_south_korea_resident_number` bir anahtar sözcük bulunur.
- Sağlama toplamı geçer.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_south_korea_resident_number` , desenle eşleşen içeriği bulur.
- Sağlama toplamı geçer.

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_south_korea_resident_number"></a>Keyword_south_korea_resident_number

- Ulusal kimlik kartı
- Vatandaşın Kayıt Numarası
- Jumin deungnok beonho
- RRN
- 주민등록번호