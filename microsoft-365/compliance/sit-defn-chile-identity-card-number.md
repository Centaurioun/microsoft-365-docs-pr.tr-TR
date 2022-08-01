---
title: Şili kimlik kartı numarası varlık tanımı
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
description: Şili kimlik kartı numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 1ec3b90d52d5404bf49a343cba7fb2c7f5464870
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948564"
---
# <a name="chile-identity-card-number"></a>Şili kimlik kartı numarası

## <a name="format"></a>Biçim

yedi ila sekiz basamak artı bir çek basamağı veya harfi sınırlandıran

## <a name="pattern"></a>Desen

yedi ila sekiz basamak artı sınırlayıcılar:

- bir-iki basamak
- isteğe bağlı bir dönem
- üç basamak
- isteğe bağlı bir dönem
- üç basamak
- tire
- bir basamak veya harf (büyük/küçük harfe duyarlı değil) bu bir denetim basamalı

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_chile_id_card` , desenle eşleşen içeriği bulur.
- 'den `Keyword_chile_id_card` bir anahtar sözcük bulunur.
- Sağlama toplamı geçer.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_chile_id_card` , desenle eşleşen içeriği bulur.
- Sağlama toplamı geçer.

```xml
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_chile_id_card"></a>Keyword_chile_id_card

- cédula de identidad
- identificación
- ulusal kimlik
- ulusal kimlik numarası
- ulusal kimlik
- número de identificación nacional
- rol único nacional
- rol único tributario
- ÇALIŞTIRMAK
- RUT
- tarjeta de identificación
- Rol Unico Nacional
- Rol Unico Tributario
- ÇALIŞTIRMAK #
- RUT #
- nationaluniqueroleID #
- nacional identidad
- número identificación
- identidad número
- çok sayıda identificacion
- identidad numero
- Şili kimliği hayır.
- Şili kimlik numarası
- Şili kimliği #
- Benzersiz Vergi Kayıt Defteri
- Benzersiz Tributary Rolü
- Benzersiz Vergi Rolü
- Benzersiz Tributary Numarası
- Benzersiz Ulusal Numara
- Benzersiz Ulusal Rol
- Ulusal benzersiz rol
- Şili kimliği hayır.
- Şili kimlik numarası
- Şili kimliği #
- R.U.T
- R.U.N