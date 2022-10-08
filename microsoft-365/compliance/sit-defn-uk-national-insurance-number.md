---
title: BK ulusal sigorta numarası (NINO) varlık tanımı
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
description: BK ulusal sigorta numarası (NINO) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: a975ec23f2677846503e87087470452e952a7df6
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472902"
---
# <a name="uk-national-insurance-number-nino"></a>BK ulusal sigorta numarası (NINO)

Bu hassas bilgi türü varlığı AB Ulusal Kimlik Numarası hassas bilgi türüne dahil edilir. Tek başına hassas bilgi türü varlığı olarak da kullanılabilir.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

boşluk veya tirelerle ayrılmış yedi karakter veya dokuz karakter

## <a name="pattern"></a>Desen

iki olası desen:

- iki harf (geçerli NINO'lar bu ön ekte yalnızca belirli karakterler kullanır; bu desen bunu doğrular; büyük/küçük harfe duyarlı değildir)
- altı basamak
- 'A', 'B', 'C' veya 'D' (ön ek gibi, son ekte yalnızca belirli karakterlere izin verilir; büyük/küçük harfe duyarlı değildir)

VEYA

- iki harf
- boşluk veya tire
- iki basamak
- boşluk veya tire
- iki basamak
- boşluk veya tire
- iki basamak
- boşluk veya tire
- 'A', 'B', 'C' veya 'D'

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_uk_nino`, desenle eşleşen içeriği bulur.
- `Keyword_uk_nino` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_uk_nino`, desenle eşleşen içeriği bulur.

```xml
    <!-- U.K. NINO -->
    <Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Match idRef="Keyword_uk_nino" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_uk_nino"></a>Keyword_uk_nino

- ulusal sigorta numarası
- ulusal sigorta katkıları
- koruma eylemi
- Sigorta
- sosyal güvenlik numarası
- sigorta uygulaması
- tıbbi uygulama
- sosyal sigorta
- tıbbi müdahale
- sosyal güvenlik
- Ingiltere
- NI Numarası
- NI Hayır.
- NI #
- NI #
- Sigorta #
- insurancenumber
- ulusal dayanıklılık #
- nationalinsurancenumber
