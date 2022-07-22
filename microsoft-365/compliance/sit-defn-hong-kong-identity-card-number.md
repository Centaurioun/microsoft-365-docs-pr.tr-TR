---
title: Hong Kong kimlik kartı (HKID) numarası varlık tanımı
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
description: Hong Kong kimlik kartı (HKID) numarasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 6d382d50334036aaa0a7ff8fce698246b1e5ccb0
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948977"
---
# <a name="hong-kong-identity-card-hkid-number"></a>Hong Kong kimlik kartı (HKID) numarası

## <a name="format"></a>Biçim

Son karakter çevresinde 8-9 harf ve rakam ile isteğe bağlı parantezlerin birleşimi

## <a name="pattern"></a>Desen

8-9 harf birleşimi:

- 1-2 harf (büyük/küçük harfe duyarlı değil)
- Altı basamak
- isteğe bağlı alan
- isteğe bağlı olarak parantez içine alınmış bir onay karakteri (herhangi bir rakam veya A harfi)

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_hong_kong_id_card` , desenle eşleşen içeriği bulur.
- 'den `Keyword_hong_kong_id_card` bir anahtar sözcük bulunur.
- Sağlama toplamı geçer.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- İşlev `Func_hong_kong_id_card` , desenle eşleşen içeriği bulur.
- Sağlama toplamı geçer.

```xml
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_hong_kong_id_card"></a>Keyword_hong_kong_id_card

- hkid
- hong kong kimlik kartı
- HKIDC
- kimlik kartı
- kimlik kartı
- hk kimlik kartı
- hong kong kimliği
- 香港身份證
- 香港永久性居民身份證
- 身份證
- 身份証
- 身分證
- 身分証
- 香港身份証
- 香港身分證
- 香港身分証
- 香港身份證
- 香港居民身份證
- 香港居民身份証
- 香港居民身分證
- 香港居民身分証
- 香港永久性居民身份証
- 香港永久性居民身分證
- 香港永久性居民身分証
- 香港永久性居民身份證
- 香港非永久性居民身份證
- 香港非永久性居民身份証
- 香港非永久性居民身分證
- 香港非永久性居民身分証
- 香港特別行政區永久性居民身份證
- 香港特別行政區永久性居民身份証
- 香港特別行政區永久性居民身分證
- 香港特別行政區永久性居民身分証
- 香港特別行政區非永久性居民身份證
- 香港特別行政區非永久性居民身份証
- 香港特別行政區非永久性居民身分證
- 香港特別行政區非永久性居民身分証