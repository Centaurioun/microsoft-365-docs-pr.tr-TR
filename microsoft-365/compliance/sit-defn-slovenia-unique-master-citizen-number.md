---
title: Slovenya Benzersiz Ana Vatandaş Numarası varlık tanımı
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
description: Slovenya Benzersiz Ana Vatandaş Numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 23c484946c8e73e7f21b251aa35935dba37b110b
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948554"
---
# <a name="slovenia-unique-master-citizen-number"></a>Slovenya Benzersiz Birincil Vatandaşlık Numarası

Bu hassas bilgi türü yalnızca şu durumlarda kullanılabilir:

- veri kaybı önleme ilkeleri
- iletişim uyumluluk ilkeleri
- veri yaşam döngüsü yönetimi
- kayıt yönetimi
- Bulut Uygulamaları için Microsoft Defender

## <a name="format"></a>Biçim

Boşluk veya sınırlayıcı içermeyen 13 basamak

## <a name="pattern"></a>Desen

Belirtilen desende 13 basamak:

- doğum tarihine (DDMMLLL) karşılık gelen yedi basamak; burada "LLL" doğum yılının son üç basamağını ifade eder
- doğum alanına karşılık gelen iki basamak "50"
- aynı gün doğan kişiler için cinsiyet ve seri numarasının birleşimine karşılık gelen üç basamak. Erkek için 000-499, kadın için 500-999.
- bir denetim basamalı

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_slovenia_eu_national_id_card` , desenle eşleşen içeriği bulur.
- 'den `Keywords_slovenia_eu_national_id_card` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_slovenia_eu_national_id_card` , desenle eşleşen içeriği bulur.

```xml
      <!-- Slovenia Unique Master Citizen Number -->
      <Entity id="68948b27-803d-41e4-adf1-13e05eb541bb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_slovenia_eu_national_id_card"></a>Keywords_slovenia_eu_national_id_card

- edinstvena številka glavnega državljana
- emšo
- enotna maticna številka obcana
- kimlik kartı
- kimlik numarası
- identifikacijska številka
- kimlik kartı
- nacionalna id
- nacionalni potni list
- ulusal kimlik
- osebna izkaznica
- osebni koda
- osebni ne
- osebni številka
- kişisel kod
- kişisel numara
- kişisel sayısal kod
- številka državljana
- benzersiz vatandaş numarası
- benzersiz kimlik numarası
- benzersiz kimlik numarası
- benzersiz ana vatandaş numarası
- benzersiz kayıt numarası
- uniqueidentityno #
- uniqueidentityno #