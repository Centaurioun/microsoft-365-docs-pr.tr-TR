---
title: Brezilya CPF numarası varlık tanımı
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
description: Brezilya CPF numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: b8164d44f20237b5eb74d45369f3bffbe1dc07e3
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66989329"
---
# <a name="brazil-cpf-number"></a>Brezilya CPF numarası

## <a name="format"></a>Biçim

Denetim basamağı içeren ve biçimlendirilebilen veya biçimlendirilemeyen 11 basamak

## <a name="pattern"></a>Desen

Biçimlendirilmiş:

- üç basamak
- dönem
- üç basamak
- dönem
- üç basamak
- kısa çizgi
- denetim basamakları olan iki basamak

Biçimlendir -ilmemiş:

- Son iki basamağın denetim basamakları olduğu 11 basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_brazil_cpf` , desenle eşleşen içeriği bulur.
- 'den `Keyword_brazil_cpf` bir anahtar sözcük bulunur.
- Sağlama toplamı geçer.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_brazil_cpf` , desenle eşleşen içeriği bulur.
- Sağlama toplamı geçer.

```xml
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_brazil_cpf"></a>Keyword_brazil_cpf

- CPF
- Kimlik
- Kayıt
- Gelir
- Cadastro de Pessoas Físicas
- Imposto
- Identificação
- Inscrição
- Receita