---
title: Brezilya tüzel kişilik numarası (CNPJ) varlık tanımı
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
description: Brezilya tüzel kişilik numarası (CNPJ) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: a8cf09eb283cea08e72a5858e7bfd4752486a01e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948842"
---
# <a name="brazil-legal-entity-number-cnpj"></a>Brezilya tüzel kişilik numarası (CNPJ)

## <a name="format"></a>Biçim

Kayıt numarası, dal numarası ve denetim basamakları ile sınırlayıcıları içeren 14 basamak

## <a name="pattern"></a>Desen

14 basamak ve sınırlayıcılar:

- iki basamak
- dönem
- üç basamak
- dönem
- üç basamak (bu ilk sekiz basamak kayıt numarasıdır)
- eğik çizgi
- dört basamaklı dal numarası
- kısa çizgi
- denetim basamakları olan iki basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_brazil_cnpj` , desenle eşleşen içeriği bulur.
- 'den `Keyword_brazil_cnpj` bir anahtar sözcük bulunur.
- Sağlama toplamı geçer.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_brazil_cnpj` , desenle eşleşen içeriği bulur.
- Sağlama toplamı geçer.

```xml
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_brazil_cnpj"></a>Keyword_brazil_cnpj

- CNPJ
- CNPJ/MF
- CNPJ-MF
- Tüzel Kişiliklerin Ulusal Kayıt Defteri
- Vergi Mükellefleri Kayıt Defteri
- Tüzel
- Tüzel kişilikler
- Kayıt Durumu
- Business
- Şirket
- CNPJ
- Cadastro Nacional da Pessoa Jurídica
- Cadastro Geral de Contribuintes
- CGC
- Pessoa jurídica
- Pessoas jurídicas
- Situação kadastro
- Inscrição
- Empresa