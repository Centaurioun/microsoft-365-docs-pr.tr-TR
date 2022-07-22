---
title: Polonya REGON numarası varlık tanımı
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
description: Polonya REGON numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 0c7de5f7645154d49a4bf7d8e53daa89ac6df1a5
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948882"
---
# <a name="poland-regon-number"></a>Polonya REGON numarası

Bu hassas bilgi türü yalnızca şu durumlarda kullanılabilir:

- veri kaybı önleme ilkeleri
- iletişim uyumluluk ilkeleri
- veri yaşam döngüsü yönetimi
- kayıt yönetimi
- Bulut Uygulamaları için Microsoft Defender

## <a name="format"></a>Biçim

9 basamaklı veya 14 basamaklı sayı

## <a name="pattern"></a>Desen

dokuz basamaklı veya 14 basamaklı sayı:

- dokuz basamak veya
- dokuz basamak
- Tire
- beş basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_polish_regon_number` , desenle eşleşen içeriği bulur.
- 'den `Keywords_polish_regon_number` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- İşlev `Func_polish_regon_number` , desenle eşleşen içeriği bulur.

```xml
      <!-- Polish REGON Number  -->
      <Entity id="fc87b421-f437-4f8b-b739-29a735ead0d9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_regon_number" />
          <Match idRef="Keywords_polish_regon_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_regon_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_poland_regon_number"></a>Keywords_poland_regon_number

- regon id
- istatistiksel sayı
- istatistiksel kimlik
- istatistiksel hayır
- regon sayısı
- regonid #
- regonno #
- şirket kimliği
- şirket kimliği #
- companyidno #
- sayı statystyczny
- numeru regon
- numerstatystyczny #
- numeruregon #