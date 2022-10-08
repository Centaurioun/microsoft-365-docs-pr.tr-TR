---
title: Japonya yerleşik kayıt numarası varlık tanımı
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
description: Japonya yerleşik kayıt numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 59e9b4a8eeef1ecc206cccd34ecccbf27de1a2e7
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68382589"
---
# <a name="japan-resident-registration-number"></a>Japonya mukim kayıt numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

11 basamak

## <a name="pattern"></a>Desen

Ardışık 11 basamak

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_jp_resident_registration_number`, desenle eşleşen içeriği bulur.
- `Keyword_jp_resident_registration_number` içinden bir anahtar sözcük bulundu.

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_jp_resident_registration_number"></a>Keyword_jp_resident_registration_number

- Yerleşik Kayıt Numarası
- Yerleşikler Temel Kayıt Defteri Numarası
- Yerleşik Kayıt No.
- Yerleşik Kayıt No.
- Residents Basic Registry No.
- Temel Yerleşik Kayıt No.
- 外国人登録証明書番号
- 証明書番号
- 登録番号
- 外国人登録証
