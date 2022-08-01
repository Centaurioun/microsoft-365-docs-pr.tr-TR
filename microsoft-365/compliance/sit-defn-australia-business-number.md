---
title: Avustralya iş numarası varlık tanımı
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
description: Avustralya iş numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 5d3b238dc631086be26399e3adf6c4fa2ef0cf99
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948372"
---
# <a name="australia-business-number"></a>Avustralya iş numarası

Bu hassas bilgi türü yalnızca şu durumlarda kullanılabilir:

- veri kaybı önleme ilkeleri
- iletişim uyumluluk ilkeleri
- veri yaşam döngüsü yönetimi
- kayıt yönetimi
- Bulut Uygulamaları için Microsoft Defender

## <a name="format"></a>Biçim

İsteğe bağlı sınırlayıcılarla 11 basamak

## <a name="pattern"></a>Desen

İsteğe bağlı sınırlayıcıları olan 11 basamak:

- iki basamak
- isteğe bağlı kısa çizgi veya boşluk
- üç basamak
- isteğe bağlı kısa çizgi veya boşluk
- üç basamak
- isteğe bağlı kısa çizgi veya boşluk
- üç basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev Func_australian_business_number desenle eşleşen içeriği bulur.
- Keywords_australian_business_number anahtar sözcüğü bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev Func_australian_business_number desenle eşleşen içeriği bulur.

```xml
      <!-- Australia Business Number -->
      <Entity id="76e83b3b-01ee-4530-aced-e667a6609f49" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_australian_business_number" />
          <Match idRef="Keywords_australian_business_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_australian_business_number" />
        </Pattern>
      </Entity>
```
## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_australia_business_number"></a>Keyword_australia_business_number

- avustralya iş no
- iş numarası
- Abn #
- businessid #
- iş kimliği
- Abn
- businessno #