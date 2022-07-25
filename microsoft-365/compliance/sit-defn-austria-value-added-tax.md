---
title: Avusturya katma değer vergisi varlık tanımı
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
description: Avusturya katma değer vergisine duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: b4d6841e857d81c42255eec1184e51623f78059f
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66989432"
---
# <a name="austria-value-added-tax"></a>Avusturya katma değer vergisi

Bu hassas bilgi türü yalnızca şu durumlarda kullanılabilir:

- veri kaybı önleme ilkeleri
- iletişim uyumluluk ilkeleri
- veri yaşam döngüsü yönetimi
- kayıt yönetimi
- Bulut Uygulamaları için Microsoft Defender

## <a name="format"></a>Biçim

11 karakterli alfasayısal desen

## <a name="pattern"></a>Desen

11 karakterli alfasayısal desen:

- A veya a
- T veya t
- İsteğe bağlı alan
- U veya u
- isteğe bağlı alan
- iki veya üç basamak
- isteğe bağlı alan
- dört basamak
- isteğe bağlı alan
- bir veya iki basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev Func_Austria_Value_Added_Tax desenle eşleşen içeriği bulur.
- Keyword_Austria_Value_Added_Tax anahtar sözcüğü bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev Func_Austria_Value_Added_Tax desenle eşleşen içeriği bulur.

```xml
      <!-- Austria Value Added Tax -->
      <Entity id="b6a3eda2-c56c-4b69-a5f7-dca34db00f48" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
          <Match idRef="Keyword_Austria_Value_Added_Tax" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
        </Pattern>
      </Entity>
```
## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_austria_value_added_tax"></a>Keyword_austria_value_added_tax

- kdv numarası
- Kdv #
- avusturya kdv numarası
- kdv no.
- vatno #
- katma değer vergi numarası
- avusturya kdv
- mwst
- umsatzsteuernummer
- mwstnummer
- ust.-identifikationsnummer
- umsatzsteuer-identifikationsnummer
- kdv kimlik numarası
- atu numarası
- uid numarası