---
title: Yeni Zelanda iç gelir numarası varlık tanımı
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
description: Yeni Zelanda iç gelir numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 26604014771674a2177f3fee6c062e3bfcee4175
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66989492"
---
# <a name="new-zealand-inland-revenue-number"></a>Yeni Zelanda iç gelir numarası

Bu hassas bilgi türü yalnızca şu durumlarda kullanılabilir:

- veri kaybı önleme ilkeleri
- iletişim uyumluluk ilkeleri
- veri yaşam döngüsü yönetimi
- kayıt yönetimi
- Bulut Uygulamaları için Microsoft Defender

## <a name="format"></a>Biçim

isteğe bağlı sınırlayıcılarla sekiz veya dokuz basamak

## <a name="pattern"></a>Desen

isteğe bağlı sınırlayıcılarla sekiz veya dokuz basamak

- iki veya üç basamak
- isteğe bağlı bir boşluk veya kısa çizgi
- üç basamak
- isteğe bağlı bir boşluk veya kısa çizgi
- üç basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_new_zealand_inland_revenue_number` , desenle eşleşen içeriği bulur.
- 'den `Keywords_new_zealand_inland_revenue_number` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_new_zealand_inland_revenue_number` , desenle eşleşen içeriği bulur.

```xml
      <!-- New Zealand Inland Revenue Number -->
      <Entity id="dd0fe2bc-7bcf-455f-bac1-83b1e3eb25fd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
          <Match idRef="Keywords_new_zealand_inland_revenue_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_new_zealand_inland_revenue_number"></a>Keyword_new_zealand_inland_revenue_number

- ird hayır.
- ird no #
- nz ird
- yeni zelanda ird
- ird numarası
- iç gelir numarası