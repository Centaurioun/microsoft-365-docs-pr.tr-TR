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
- tier3
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Güney Kore yerleşik kayıt numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: d775cadefa4007b2770b42901530c8a78e7f0eb2
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472453"
---
# <a name="south-korea-resident-registration-number"></a>Güney Kore mukim kayıt numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

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

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_south_korea_resident_number`, desenle eşleşen içeriği bulur.
- `Keyword_south_korea_resident_number` içinden bir anahtar sözcük bulundu.
- Sağlama toplamı başarılı.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_south_korea_resident_number`, desenle eşleşen içeriği bulur.
- Sağlama toplamı başarılı.

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
