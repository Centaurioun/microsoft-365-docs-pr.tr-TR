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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Uyuşturucu Uygulama Kurumu (DEA) numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 7b1ade056621f619d8be0293708dd51cfc2e85dd
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948410"
---
# <a name="drug-enforcement-agency-dea-number"></a>Uyuşturucuyla Mücadele Ajansı (DEA) numarası 

## <a name="format"></a>Biçim

iki harf ve ardından yedi basamak

## <a name="pattern"></a>Desen

Desen aşağıdakilerin tümünü içermelidir:

- Bu olası harf kümesinden bir harf (büyük/küçük harfe duyarlı değil): Kayıt yapan kod olan A/B/F/G/M/P/R
- bir harf (büyük/küçük harfe duyarlı değil), kayıt sahibinin soyadının veya '9' rakamının ilk harfidir
- yedi basamak, sonuncusu ise denetim basamağıdır

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_dea_number` , desenle eşleşen içeriği bulur.
- 'den `Keyword_dea_number` bir anahtar sözcük bulundu
- Sağlama toplamı geçer.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_dea_number` , desenle eşleşen içeriği bulur.
- Sağlama toplamı geçer.

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