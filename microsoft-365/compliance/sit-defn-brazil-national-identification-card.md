---
title: Brezilya ulusal kimlik kartı (RG) varlık tanımı
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
description: Brezilya ulusal kimlik kartı (RG) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 7f4fe7a0eda911639c0c7650d4ac71f07dfe4f3a
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948360"
---
# <a name="brazil-national-identification-card-rg"></a>Brezilya ulusal kimlik kartı (RG)

## <a name="format"></a>Biçim

Registro Geral (eski biçim): Dokuz basamak

Registro de Identidade (RIC) (yeni biçim): 11 basamak

### <a name="pattern"></a>Desen

Registro Geral (eski biçim):

- iki basamak
- dönem
- üç basamak
- dönem
- üç basamak
- kısa çizgi
- denetim basamalı bir basamak

Registro de Identidade (RIC) (yeni biçim):

- 10 basamak
- kısa çizgi
- denetim basamalı bir basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_brazil_rg` , desenle eşleşen içeriği bulur.
- 'den `Keyword_brazil_rg` bir anahtar sözcük bulunur.
- Sağlama toplamı geçer.

```xml
      <!-- Brazil National ID Card (RG) -->
      <Entity id="486de900-db70-41b3-a886-abdf25af119c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_brazil_rg" />
          <Match idRef="Keyword_brazil_rg" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_brazil_rg"></a>Keyword_brazil_rg

- Cédula de identidade
- kimlik kartı
- ulusal kimlik
- número de rregistro
- registro de Iidentidade
- registro geral
- RG (bu anahtar sözcük büyük/küçük harfe duyarlıdır)
- RIC (bu anahtar sözcük büyük/küçük harfe duyarlıdır)