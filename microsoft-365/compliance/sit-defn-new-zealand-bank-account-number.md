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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Yeni Zelanda banka hesap numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: b33eeb1e83f5efc9dd805c9ea036c6f30de600a0
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948482"
---
# <a name="new-zealand-bank-account-number"></a>Yeni Zelanda banka hesap numarası

Bu hassas bilgi türü yalnızca şu durumlarda kullanılabilir:

- veri kaybı önleme ilkeleri
- iletişim uyumluluk ilkeleri
- veri yaşam döngüsü yönetimi
- kayıt yönetimi
- Bulut Uygulamaları için Microsoft Defender

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

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_new_zealand_bank_account_number` , desenle eşleşen içeriği bulur.
- 'den `Keywords_new_zealand_bank_account_number` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_new_zealand_bank_account_number` , desenle eşleşen içeriği bulur.

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