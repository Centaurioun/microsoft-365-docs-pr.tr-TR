---
title: Katar kimlik kartı numarası
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
description: Katar kimlik kartı numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 35b609753afd7f63674ef8b50f42257c78409e16
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472815"
---
# <a name="qatari-id-card-number"></a>Katar kimlik kartı numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

on bir basamak

## <a name="pattern"></a>Desen

On bir basamak:

- 2 veya 3 rakamı 
- doğum yılının son iki sayısını temsil eden iki basamak 
- ISO ülke kodunu temsil eden üç basamak 
- beş basamak.

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir: 

- Normal ifade Regex_qatari_id_card desenle eşleşen içeriği bulur. 
- Keyword_qatari_id_card anahtar sözcüğü bulunur. 

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir: 

- Normal ifade Regex_qatari_id_card desenle eşleşen içeriği bulur. 

```xml
     <!-- Qatari ID Card Number-->
        <Entity id="52b1b60e-a4be-4b5a-a67b-6f9bbb7811da" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
          <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_qatari_id_card" />
            <Match idRef="Keyword_qatari_id_card" />
          </Pattern>
          <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_qatari_id_card" />
          </Pattern>
        </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_qatari_id_card"></a>Keyword_qatari_id_card

- Gp 
- Dob 
- D.O.B 
- Doğum tarihi 
- Doğum Tarihi 
- sorun tarihi 
- süre sonu tarihi 
