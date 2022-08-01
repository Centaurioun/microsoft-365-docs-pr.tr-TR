---
title: Ukrayna pasaportu uluslararası varlık tanımı
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
description: Ukrayna pasaportu uluslararası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 333475ad89f8437c046a572ae5377fb030b173fe
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948562"
---
# <a name="ukraine-passport-international"></a>Ukrayna pasaportu uluslararası

Bu hassas bilgi türü yalnızca şu durumlarda kullanılabilir:

- veri kaybı önleme ilkeleri
- iletişim uyumluluk ilkeleri
- veri yaşam döngüsü yönetimi
- kayıt yönetimi
- Bulut Uygulamaları için Microsoft Defender

## <a name="format"></a>Biçim

sekiz karakterli alfasayısal desen

## <a name="pattern"></a>Desen

sekiz karakterli alfasayısal desen:

- iki harf veya basamak
- altı basamak

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Regex `Regex_Ukraine_Passport_International` , desenle eşleşen içeriği bulur.
- 'den `Keyword_Ukraine_Passport_International` bir anahtar sözcük bulunur.

```xml
      <!-- Ukraine Passport International -->
      <Entity id="cfbe032d-22e0-4f28-ab68-d66e9641f1e2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Ukraine_Passport_International"/>
          <Match idRef="Keyword_Ukraine_Passport_International"/>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_ukraine_passport_international"></a>Keyword_ukraine_passport_international

- ukrayna pasaportu
- pasaport numarası
- pasaport no
- паспорт України
- номер паспорта
