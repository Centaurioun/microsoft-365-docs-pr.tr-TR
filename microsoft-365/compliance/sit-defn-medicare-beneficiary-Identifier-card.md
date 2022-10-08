---
title: Medicare Beneficiary Identifier (MBI) kartı varlık tanımı
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
description: Medicare Beneficiary Identifier (MBI) karta duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 7ee3545a7a0eb177f7cf8cbb6581aa43546c8f88
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68382501"
---
# <a name="medicare-beneficiary-identifier-mbi-card"></a>Medicare (Tıbbi Bakım Sigortası) Faydalanıcı Kimlik (MBI) kartı

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

11 karakter alfasayısal desen

## <a name="pattern"></a>Desen

- 1 ile 9 arasında bir basamak
- S, L, O, I, B, Z hariç bir harf
- S, L, O, I, B, Z hariç bir basamak veya harf
- bir basamak
- isteğe bağlı kısa çizgi
- S, L, O, I, B, Z hariç bir harf
- S, L, O, I, B, Z hariç bir basamak veya harf
- bir basamak
- isteğe bağlı kısa çizgi
- S, L, O, I, B, Z hariç iki harf
- iki basamak

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- Normal ifade `Regex_mbi_card` , desenle eşleşen içeriği bulur.
- `Keyword_mbi_card` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- Normal ifade `Regex_mbi_card` , desenle eşleşen içeriği bulur.

```xml
    <!-- Medicare Beneficiary Identifier (MBI) card -->
      <Entity id="f753a286-f5cc-47e6-a592-4be25fd02591" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_mbi_card" />
          <Match idRef="Keyword_mbi_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_mbi_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_mbi_card"></a>Keyword_mbi_card

- mbi
- mbi #
- medicare hak sahibi #
- medicare hak sahibi tanımlayıcısı
- medicare hak sahibi hayır
- medicare hak sahibi numarası
- medicare hak sahibi #
