---
title: Japonya Numaram - Kişisel varlık tanımı
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
description: Japonya My Number - Kişisel hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 4c5899c985813fd930672da6c0bd32196eaa279f
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948873"
---
# <a name="japan-my-number---personal"></a>Japonya Numaram - Kişisel

Bu hassas bilgi türü yalnızca şu durumlarda kullanılabilir:

- veri kaybı önleme ilkeleri
- iletişim uyumluluk ilkeleri
- veri yaşam döngüsü yönetimi
- kayıt yönetimi
- Bulut Uygulamaları için Microsoft Defender

## <a name="format"></a>Biçim

12 basamaklı sayı

## <a name="pattern"></a>Desen

12 basamaklı sayı:

- dört basamak
- isteğe bağlı boşluk, nokta veya kısa çizgi
- dört basamak
- isteğe bağlı boşluk, nokta veya kısa çizgi
- dört basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_japanese_my_number_personal` , desenle eşleşen içeriği bulur.
- 'den `Keywords_japanese_my_number_personal` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- İşlev `Func_japanese_my_number_personal` , desenle eşleşen içeriği bulur.

```xml
      <!-- Japanese My Number – Personal -->
      <Entity id="98da8e66-7299-4ebd-9f82-c871ab37d3ef" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_personal" />
          <Match idRef="Keywords_japanese_my_number_personal" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_japanese_my_number_personal" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_japan_my_number_personal"></a>Keyword_japan_my_number_personal

- numaram
- マイナンバー
- 個人番号
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 通知カード