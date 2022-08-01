---
title: Hindistan GST Numarası varlık tanımı
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
description: Hindistan GST Numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 19d51294b8ff53b53bceba1a047976802359f09e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948398"
---
# <a name="india-gst-number"></a>Hindistan GST Numarası

## <a name="format"></a>Biçim

15 karakterli alfasayısal desen

## <a name="pattern"></a>Desen

15 harf veya rakam:

- geçerli durum kodunu temsil eden iki basamak
- isteğe bağlı bir boşluk veya tire
- Kalıcı Hesap Numarasını (PAN) temsil eden on karakter
- bir harf veya rakam
- isteğe bağlı bir boşluk veya tire
- tek harfli 'z' veya 'Z'
- isteğe bağlı bir boşluk veya tire
- bir denetim basamalı

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_india_gst_number` , desenle eşleşen içeriği bulur.
- 'den `Keyword_india_gst_number` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_india_gst_number` , desenle eşleşen içeriği bulur.

```xml
    <!-- India GST number  -->
      <Entity id="9f5a721c-2fd2-446a-a27e-0c02fbe4630c" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_india_gst_number" />
          <Match idRef="Keyword_india_gst_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_india_gst_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_india_gst_number"></a>Keyword_india_gst_number

- Gst
- gstin
- mal ve hizmet vergisi
- mal ve hizmet vergisi