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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Medicare Beneficiary Identifier (MBI) karta duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 601c34adcb0f9b19ab2c23a3df7d1c574cdd5031
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66989540"
---
# <a name="medicare-beneficiary-identifier-mbi-card"></a>Medicare (Tıbbi Bakım Sigortası) Faydalanıcı Kimlik (MBI) kartı

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

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- Normal ifade `Regex_mbi_card` , desenle eşleşen içeriği bulur.
- 'den `Keyword_mbi_card` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

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