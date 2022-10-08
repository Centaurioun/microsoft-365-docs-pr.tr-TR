---
title: Portekiz vatandaş kart numarası varlık tanımı
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
description: Portekiz vatandaş kartı numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 350391a56f6dfc46e9d037ff23da491a5035357a
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472858"
---
# <a name="portugal-citizen-card-number"></a>Portekiz vatandaşlık kart numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

sekiz basamak

## <a name="pattern"></a>Desen

sekiz basamak

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- Normal ifade `Regex_portugal_citizen_card` , desenle eşleşen içeriği bulur.
- `Keyword_portugal_citizen_card` içinden bir anahtar sözcük bulundu.

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_portugal_citizen_card"></a>Keyword_portugal_citizen_card

- bilhete de identidade
- cartão de cidadão
- vatandaş kartı
- belge numarası
- documento de identificação
- kimlik numarası
- tanımlama no
- kimlik numarası
- kimlik kartı no
- kimlik kartı numarası
- ulusal kimlik kartı
- Nıc
- número bi de portugal
- número de identificação civil
- número de identificação fiscal
- número do documento
- portugal bi numarası
