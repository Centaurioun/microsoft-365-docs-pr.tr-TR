---
title: Yeni Zelanda sosyal yardım numarası varlık tanımı
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
description: Yeni Zelanda sosyal yardım numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 9885956e7011f2c52a8b78d4e03822f8201c1b3a
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948913"
---
# <a name="new-zealand-social-welfare-number"></a>Yeni Zelanda sosyal yardım numarası

Bu hassas bilgi türü yalnızca şu durumlarda kullanılabilir:

- veri kaybı önleme ilkeleri
- iletişim uyumluluk ilkeleri
- veri yaşam döngüsü yönetimi
- kayıt yönetimi
- Bulut Uygulamaları için Microsoft Defender

## <a name="format"></a>Biçim

dokuz basamak

## <a name="pattern"></a>Desen

dokuz basamak

- üç basamak
- isteğe bağlı kısa çizgi
- üç basamak
- isteğe bağlı kısa çizgi
- üç basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

### <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_newzealand_social_welfare_number` , desenle eşleşen içeriği bulur.
- 'den `Keywords_newzealand_social_welfare_number` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- İşlev `Func_newzealand_social_welfare_number` , desenle eşleşen içeriği bulur.

```xml
      <!-- Newzealand Social Welfare Number -->
      <Entity id="20f3c48d-4ac1-4cd2-86bd-34ecc1826e9d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
          <Match idRef="Keywords_newzealand_social_welfare_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
        </Pattern>
      </Entity>
    </Version>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_new_zealand_social_welfare_number"></a>Keyword_new_zealand_social_welfare_number

- sosyal yardım #
- sosyal yardım #
- sosyal yardım no.
- sosyal yardım numarası
- swn #