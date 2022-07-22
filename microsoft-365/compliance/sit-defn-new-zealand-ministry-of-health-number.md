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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Yeni Zelanda sağlık bakanlığı numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 62a7b181626d36930da36451ccd109ecc6d04812
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948917"
---
# <a name="new-zealand-ministry-of-health-number"></a>Yeni Zelanda sağlık bakanlığı numarası

## <a name="format"></a>Biçim

üç harf ve dört basamak

## <a name="pattern"></a>Desen

- 'I' ve 'O' dışında üç harf (büyük/küçük harfe duyarlı değil)
- dört basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_new_zealand_ministry_of_health_number` , desenle eşleşen içeriği bulur.
- 'den `Keyword_nz_terms` bir anahtar sözcük bulunur.
- Sağlama toplamı geçer.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_new_zealand_ministry_of_health_number` , desenle eşleşen içeriği bulur.
- Sağlama toplamı geçer.

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