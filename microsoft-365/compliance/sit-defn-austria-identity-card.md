---
title: Avusturya kimlik kartı varlık tanımı
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
description: Avusturya kimlik kartına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 5a7cae0eabfa179bda83a09dc6a70a3e6e5048a6
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948806"
---
# <a name="austria-identity-card"></a>Avusturya kimlik kartı

Bu hassas bilgi türü yalnızca şu durumlarda kullanılabilir:

- veri kaybı önleme ilkeleri
- iletişim uyumluluk ilkeleri
- veri yaşam döngüsü yönetimi
- kayıt yönetimi
- Bulut Uygulamaları için Microsoft Defender

## <a name="format"></a>Biçim

Harflerin, basamakların ve özel karakterlerin 24 karakterlik birleşimi

## <a name="pattern"></a>Desen

24 karakter:

- 22 harf (büyük/küçük harfe duyarlı değil), basamaklar, ters eğik çizgi, eğik çizgi veya artı işareti

- iki harf (büyük/küçük harfe duyarlı değil), basamaklar, ters eğik çizgi, eğik çizgi, artı işareti veya eşittir işareti

## <a name="checksum"></a>Sağlama toplamı

Geçerli değil

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade `Regex_austria_eu_national_id_card` , desenle eşleşen içeriği bulur.
- 'den `Keywords_austria_eu_national_id_card` bir anahtar sözcük bulunur.

```xml
      <!-- Austria Identity Card -->
      <Entity id="5ec06c3b-007e-4820-8343-7ff73b889735" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

- kimlik numarası
- ulusal kimlik
- personalausweis republik österreich