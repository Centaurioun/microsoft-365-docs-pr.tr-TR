---
title: Japonya pasaport numarası varlık tanımı
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
description: Japonya pasaport numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: bb9841bdf6c6e9d86d2bf7242f8e1252d4acc62c
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68381481"
---
# <a name="japan-passport-number"></a>Japonya pasaport numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

iki harf ve ardından yedi basamak

## <a name="pattern"></a>Desen

iki harf (büyük/küçük harfe duyarlı değil) ve ardından yedi basamak

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_jp_passport`, desenle eşleşen içeriği bulur.
- `Keyword_jp_passport` içinden bir anahtar sözcük bulundu.

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_jp_passport"></a>Keyword_jp_passport

- Pasaport
- Pasaport Numarası
- Pasaport No.
- Pasaport #
- パスポート
- パスポート番号
- パスポートナンバー
- パスポート＃
- パスポート #
- パスポートNo.
- 旅券番号
- 旅券番号＃
- 旅券番号♯
- 旅券ナンバー
