---
title: Kanada kişisel sistem durumu kimlik numarası (PHIN) varlık tanımı
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
description: Kanada kişisel sistem durumu kimlik numarası (PHIN) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 0d2ac2f8deeb4cb9139d0ab66cb02bbd4bccd7c8
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66989294"
---
# <a name="canada-personal-health-identification-number-phin"></a>Kanada kişisel sağlık kimlik numarası (PHIN)

## <a name="format"></a>Biçim

dokuz basamak

## <a name="pattern"></a>Desen

dokuz basamak

## <a name="checksum"></a>Sağlama toplamı

Hayır

### <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade `Regex_canada_phin` , desenle eşleşen içeriği bulur.
- veya `Keyword_canada_provinces` anahtar sözcüğünden `Keyword_canada_phin` en az iki anahtar sözcük bulunur.

```xml
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_canada_phin"></a>Keyword_canada_phin

- sosyal sigorta numarası
- sistem durumu bilgileri eylemi
- gelir vergisi bilgileri
- manitoba health
- sistem durumu kaydı
- reçeteli satın almalar
- avantaj uygunluğu
- kişisel sağlık
- vekaletname
- kayıt numarası
- kişisel sağlık numarası
- uygulayıcı başvurusu
- wellness professional
- hasta referansı
- sağlık ve sağlıklı yaşam

### <a name="keyword_canada_provinces"></a>Keyword_canada_provinces

- Nunavut
- Quebec
- Kuzeybatı Bölgeleri
- Ontario
- britanya Kolumbiyası
- Alberta
- Saskatchewan
- Manitoba
- Yukon
- Newfoundland ve Labrador
- Yeni Brunswick
- Nova Scotia
- Prens Edward Adası
- Kanada