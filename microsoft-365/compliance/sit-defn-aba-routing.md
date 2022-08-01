---
title: ABA yönlendirme numarası varlık tanımı
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
description: ABA yönlendirme numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 5efc835b5d5dced7fbfe9a0b1ce7c59b89b60ac0
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948547"
---
# <a name="aba-routing-number"></a>ABA yönlendirme numarası

## <a name="format"></a>Biçim

biçimlendirilmiş veya biçimlendirilmemiş bir desende olabilecek dokuz basamak

## <a name="pattern"></a>Desen

- 00-12, 21-32, 61-72 veya 80 aralığındaki iki basamak
- iki basamak
- isteğe bağlı kısa çizgi
- dört basamak
- isteğe bağlı kısa çizgi
- basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

İlke, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev Func_aba_routing desenle eşleşen içeriği bulur.
- Keyword_ABA_Routing anahtar sözcüğü bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- İşlev Func_aba_routing desenle eşleşen içeriği bulur.

```xml
    <!-- ABA Routing Number -->
    <Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_aba_routing" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_aba_routing"></a>Keyword_aba_routing

- aba numarası
- Aba #
- Aba
- abarouting #
- abaroutingnumber
- americanbankassociationrouting #
- americanbankassociationroutingnumber
- bankrouting #
- bankroutingnumber
- Yönlendirme #
- yönlendirme no
- yönlendirme numarası
- yönlendirme aktarım numarası
- Yönlendirme #
- RTN
