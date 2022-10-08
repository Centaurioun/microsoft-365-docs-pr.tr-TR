---
title: Uyuşturucu Uygulama Dairesi (DEA) numarası varlık tanımı
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
description: Uyuşturucu Uygulama Kurumu (DEA) numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 080ee31c85fc9079668e9a94d139b0833ffa561c
ms.sourcegitcommit: 2ff545246fec060ea7829da5afbc1cdc698d51ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68363441"
---
# <a name="drug-enforcement-agency-dea-number"></a>Uyuşturucuyla Mücadele Ajansı (DEA) numarası 

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

iki harf ve ardından yedi basamak

## <a name="pattern"></a>Desen

Desen aşağıdakilerin tümünü içermelidir:

- Bu olası harf kümesinden bir harf (büyük/küçük harfe duyarlı değil): Kayıt yapan kod olan A/B/F/G/M/P/R
- bir harf (büyük/küçük harfe duyarlı değil), kayıt sahibinin soyadının veya '9' rakamının ilk harfidir
- yedi basamak, sonuncusu ise denetim basamağıdır

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_dea_number`, desenle eşleşen içeriği bulur.
- 'den `Keyword_dea_number` bir anahtar sözcük bulundu
- Sağlama toplamı başarılı.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_dea_number`, desenle eşleşen içeriği bulur.
- Sağlama toplamı başarılı.

```xml
    <!-- DEA Number -->
    <Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_dea_number" />
      </Pattern>
      <Version minEngineVersion="15.20.1207.000" maxEngineVersion="15.20.3134.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
        </Pattern>
      </Version>
      <Version minEngineVersion="15.20.3135.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
          <Match idRef="Keyword_dea_number" />
        </Pattern>
      </Version>
    </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_dea_number"></a>Keyword_dea_number

- Dea
- Dea #
- uyuşturucu uygulama uygulaması
- uyuşturucu uygulama kurumu
