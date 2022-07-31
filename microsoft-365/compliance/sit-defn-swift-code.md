---
title: SWIFT kodu varlık tanımı
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
description: SWIFT koduna duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: b1bbadf8f2b56218a90eec1cfd2fac7d550efe0e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948324"
---
# <a name="swift-code"></a>SWIFT kodu

## <a name="format"></a>Biçim

dört harf ve ardından 5-31 harf veya rakam

## <a name="pattern"></a>Desen

dört harf ve ardından 5-31 harf veya rakam:

- dört harfli banka kodu (büyük/küçük harfe duyarlı değildir)
- isteğe bağlı bir alan
- 4-28 harf veya rakam (Temel Banka Hesap Numarası (BBAN))
- isteğe bağlı bir alan
- bir ile üç harf veya basamak (BBAN'ın geri kalanı)

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade `Regex_swift` , desenle eşleşen içeriği bulur.
- 'den `Keyword_swift` bir anahtar sözcük bulunur.

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_swift"></a>Keyword_swift

- standardizasyon için uluslararası kuruluş 9362
- iso 9362
- iso9362
- Swift #
- swiftcode
- swiftnumber
- swiftroutingnumber
- swift kodu
- swift numarası #
- swift yönlendirme numarası
- bic numarası
- bic kodu
- Bıc #
- Bıc #
- banka tanımlayıcı kodu
- Organizasyon internationale de normalisation 9362
- rapide #
- kod SWIFT
- le numéro de swift
- swift numéro d'acheminement
- le numéro BIC
- \# BIC
- code identificateur de banque
- SWIFTコード
- SWIFT番号
- BIC番号
- BICコード
- SWIFT コード
- SWIFT 番号
- BIC 番号
- BIC コード
- 金融機関識別コード
- 金融機関コード
- 銀行コード