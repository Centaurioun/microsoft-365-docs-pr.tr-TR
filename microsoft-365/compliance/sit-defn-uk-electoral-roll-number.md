---
title: BK seçim rulosu numarası varlık tanımı
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
description: BK seçim rulosu numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: d821878a155ec6c2393150265ddac1dc18fc5f10
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948384"
---
# <a name="uk-electoral-roll-number"></a>BK seçim rulosu numarası

## <a name="format"></a>Biçim

iki harf ve ardından 1-4 basamak

## <a name="pattern"></a>Desen

iki harf (büyük/küçük harfe duyarlı değil) ve ardından 1-4 sayı

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade `Regex_uk_electoral` , desenle eşleşen içeriği bulur.
- 'den `Keyword_uk_electoral` bir anahtar sözcük bulunur.

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_uk_electoral"></a>Keyword_uk_electoral

- konsey adaylığı
- adaylık formu
- seçmen kaydı
- seçim rulosu