---
title: Yeni Zelanda banka hesap numarası varlık tanımı
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
description: Yeni Zelanda banka hesap numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 0afeadefe65844be7d86ea2f53154510423c41de
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68381687"
---
# <a name="new-zealand-bank-account-number"></a>Yeni Zelanda banka hesap numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

İsteğe bağlı sınırlayıcı ile 14 basamaklıdan 16 basamaklı desene

## <a name="pattern"></a>Desen

İsteğe bağlı sınırlayıcı ile 14 basamaklıdan 16 basamaklı desene:

- iki basamak
- isteğe bağlı kısa çizgi veya boşluk
- üç-dört basamak
- isteğe bağlı kısa çizgi veya boşluk
- yedi basamak
- isteğe bağlı kısa çizgi veya boşluk
- iki ile üç basamak
- seçenekler kısa çizgi veya boşluk

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_new_zealand_bank_account_number`, desenle eşleşen içeriği bulur.
- `Keywords_new_zealand_bank_account_number` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_new_zealand_bank_account_number`, desenle eşleşen içeriği bulur.

```xml
      <!-- New Zealand Bank Account Number -->
      <Entity id="1a97fc2b-dd2f-48f1-bc4e-2ddf25813956" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
          <Match idRef="Keywords_new_zFealand_bank_account_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_new_zealand_bank_account_number"></a>Keyword_new_zealand_bank_account_number

- hesap numarası
- banka hesabı
- bank_acct_id
- bank_acct_branch
- bank_acct_nbr
