---
title: Avustralya tıbbi hesap numarası varlık tanımı
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
description: Avustralya tıbbi hesap numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: c17de71ef0c16b5c14ba118c66ae0d9274ce4468
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948477"
---
# <a name="australia-medical-account-number"></a>Avustralya tıbbi hesap numarası

## <a name="format"></a>Biçim

10-11 basamak

## <a name="pattern"></a>Desen

10-11 basamak:

- İlk basamak 2-6 aralığındadır
- Dokuzuncu basamak bir denetim basamadır
- Onuncu basamak sorun basamaktır
- 11. basamak (isteğe bağlı) tek tek sayıdır

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev Func_australian_medical_account_number desenle eşleşen içeriği bulur.
- Keyword_Australia_Medical_Account_Number anahtar sözcüğü bulunur.
- Sağlama toplamı geçer.

```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
    </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_australia_medical_account_number"></a>Keyword_Australia_Medical_Account_Number

- banka hesabı ayrıntıları
- medicare ödemeleri
- ipotek hesabı
- banka ödemeleri
- bilgi dalı
- kredi kartı kredisi
- insan hizmetleri bölümü
- yerel hizmet
- Medicare
