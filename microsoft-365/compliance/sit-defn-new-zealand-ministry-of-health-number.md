---
title: Yeni Zelanda sağlık bakanlığı numarası varlık tanımı
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
description: Yeni Zelanda sağlık bakanlığı numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 187b0e49f6710c0fcb906dc7ba1db3563e4fa109
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68383866"
---
# <a name="new-zealand-ministry-of-health-number"></a>Yeni Zelanda sağlık bakanlığı numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

üç harf ve dört basamak

## <a name="pattern"></a>Desen

- 'I' ve 'O' dışında üç harf (büyük/küçük harfe duyarlı değil)
- dört basamak

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_new_zealand_ministry_of_health_number`, desenle eşleşen içeriği bulur.
- `Keyword_nz_terms` içinden bir anahtar sözcük bulundu.
- Sağlama toplamı başarılı.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_new_zealand_ministry_of_health_number`, desenle eşleşen içeriği bulur.
- Sağlama toplamı başarılı.

```xml
    <!-- New Zealand Health Number -->
    <Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
          <Match idRef="Keyword_nz_terms" />
      </Pattern>
      <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
       </Pattern>
    </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_nz_terms"></a>Keyword_nz_terms

- NHI
- Yeni Zelanda
- Ulusal Sağlık Endeksi
- NHI #
- Ulusal Sağlık Endeksi #
