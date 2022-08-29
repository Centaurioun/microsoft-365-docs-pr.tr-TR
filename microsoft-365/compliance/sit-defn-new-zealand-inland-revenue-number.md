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
ms.openlocfilehash: 7df444660c59bd12526d979dd93d5313814083f3
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2022
ms.locfileid: "67368087"
---
# <a name="new-zealand-inland-revenue-number"></a>Yeni Zelanda iç gelir numarası

## <a name="format"></a>Biçim

isteğe bağlı sınırlayıcılarla sekiz veya dokuz basamak

## <a name="pattern"></a>Desen

isteğe bağlı sınırlayıcılarla sekiz veya dokuz basamak

- iki veya üç basamak
- isteğe bağlı bir boşluk veya kısa çizgi
- üç basamak
- isteğe bağlı bir boşluk veya kısa çizgi
- üç basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_new_zealand_inland_revenue_number`, desenle eşleşen içeriği bulur.
- `Keywords_new_zealand_inland_revenue_number` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_new_zealand_inland_revenue_number`, desenle eşleşen içeriği bulur.

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