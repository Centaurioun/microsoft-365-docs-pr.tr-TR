---
title: Uluslararası bankacılık hesap numarası (IBAN) varlık tanımı
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
description: Uluslararası bankacılık hesabı numarası (IBAN) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 739c0a1fd90da1da817f46019cd1023be8ab27a3
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948594"
---
# <a name="international-banking-account-number-iban"></a>Uluslararası bankacılık hesap numarası (IBAN)

## <a name="format"></a>Biçim

Ülke kodu (iki harf) artı çek basamakları (iki basamak) artı bban numarası (30 karaktere kadar)

## <a name="pattern"></a>Desen

Desen aşağıdakilerin tümünü içermelidir:

- İki harfli ülke kodu
- İki denetim basamağı (ardından isteğe bağlı bir boşluk)
- Dört harf veya rakamdan oluşan 1-7 grup (boşluklarla ayrılabilir)
- 1-3 harf veya rakam

Her ülkenin biçimi biraz farklıdır. IBAN hassas bilgi türü şu 60 ülkeyi kapsar:

- Reklam
- Ae
- al
- konumunda
- Az
- Ba
- be
- Bg
- bh
- Caner
- Cr
- Cy
- Cz
- de
- Dk
- do
- ee
- Es
- Fi
- Fo
- Fr
- Gb
- Ge
- Gı
- Gl
- Gr
- Hr
- Hu
- Yani
- ıl
- is
- bu
- Kw
- Kz
- Lb
- Li
- Teğmen
- Lu
- Lv
- Mc
- md
- Beni
- Mk
- Bay
- Mt
- mu
- Nl
- No
- Pl
- Pt
- Ro
- rs
- Sa
- Se
- Si
- sk
- Sm
- Tn
- tr
- Vg

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_iban` , desenle eşleşen içeriği bulur.
- Sağlama toplamı geçer.

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

Yok