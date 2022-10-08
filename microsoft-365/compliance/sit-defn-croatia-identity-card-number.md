---
title: Hırvatistan kimlik kartı numarası varlık tanımı
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
description: Hırvatistan kimlik kartı numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 9b657a4a59dfc9b1b142c7a68ce1e919a162a030
ms.sourcegitcommit: 2ff545246fec060ea7829da5afbc1cdc698d51ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68363155"
---
# <a name="croatia-identity-card-number"></a>Hırvatistan kimlik kartı numarası

Bu varlık, AB Ulusal Kimlik Numarası hassas bilgi türüne dahil edilir. Tek başına hassas bilgi türü varlığı olarak kullanılabilir.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

dokuz basamak

## <a name="pattern"></a>Desen

art arda dokuz basamak

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_croatia_id_card`, desenle eşleşen içeriği bulur.
- `Keyword_croatia_id_card` içinden bir anahtar sözcük bulundu.

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_croatia_id_card"></a>Keyword_croatia_id_card

- majstorski broj građana
- ana vatandaş numarası
- nacionalni identifikacijski broj
- ulusal kimlik numarası
- oib #
- oib
- osobna iskaznica
- osobni kimliği
- osobni identifikacijski broj
- kişisel kimlik numarası
- porezni broj
- porezni identifikacijski broj
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
