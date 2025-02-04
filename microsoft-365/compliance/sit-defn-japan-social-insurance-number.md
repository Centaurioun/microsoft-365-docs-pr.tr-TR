---
title: Japonya sosyal sigorta numarası (SIN) varlık tanımı
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
description: Japonya sosyal sigorta numarası (SIN) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 27f812ec99c1ef7c2e4d3a913c039cab4fda65e7
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948526"
---
# <a name="japan-social-insurance-number-sin"></a>Japonya sosyal sigorta numarası (SIN)

## <a name="format"></a>Biçim

7-12 basamak

## <a name="pattern"></a>Desen

7-12 basamak:

- dört basamak
- kısa çizgi (isteğe bağlı)
- altı basamak OR
- 7-12 ardışık basamak

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- Desenle eşleşen işlev `Func_jp_sin finds` içeriği.
- 'den `Keyword_jp_sin` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_jp_sin_pre_1997` , desenle eşleşen içeriği bulur.
- 'den `Keyword_jp_sin` bir anahtar sözcük bulunur.

```xml
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_jp_sin"></a>Keyword_jp_sin

- Sosyal Sigorta No.
- Sosyal Sigorta Numarası
- Sosyal Sigorta Numarası
- 健康保険被保険者番号
- 健保番号
- 基礎年金番号
- 雇用保険被保険者番号
- 雇用保険番号
- 保険証番号
- 社会保険番号
- 社会保険No.
- 社会保険
- 介護保険
- 介護保険被保険者番号
- 健康保険被保険者整理番号
- 雇用保険被保険者整理番号
- 厚生年金
- 厚生年金被保険者整理番号