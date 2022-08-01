---
title: İtalya katma değer vergi numarası varlık tanımı
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
description: İtalya katma değer vergi numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: d370ef3c46cf773791b3b0d599d546ea695a6e97
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948729"
---
# <a name="italy-value-added-tax-number"></a>İtalya katma değer vergi numarası

Bu hassas bilgi türü yalnızca şu durumlarda kullanılabilir:

- veri kaybı önleme ilkeleri
- iletişim uyumluluk ilkeleri
- veri yaşam döngüsü yönetimi
- kayıt yönetimi
- Bulut Uygulamaları için Microsoft Defender

## <a name="format"></a>Biçim

İsteğe bağlı sınırlayıcılarla 13 karakterli alfasayısal desen

## <a name="pattern"></a>Desen

İsteğe bağlı sınırlayıcılarla 13 karakterlik alfasayısal desen:

- Ben veya ben
- T veya t
- isteğe bağlı boşluk, nokta, kısa çizgi veya virgül
- 11 basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_italy_value_added_tax_number` , desenle eşleşen içeriği bulur.
- 'den `Keywords_italy_value_added_tax_number` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_italy_value_added_tax_number` , desenle eşleşen içeriği bulur.

```xml
      <!-- Italy Value Added Tax -->
      <Entity id="26a8cc07-2283-4a2a-ab1d-4ab643c4c67f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
          <Match idRef="Keywords_italy_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_italy_value_added_tax_number"></a>Keyword_italy_value_added_tax_number

- kdv numarası
- kdv no
- Kdv #
- ıva
- ıva #