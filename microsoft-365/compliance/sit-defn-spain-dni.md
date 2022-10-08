---
title: İspanya DNI varlık tanımı
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
description: İspanya DNI hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 046c7ed6bcc567f5260bafa9c87a40a10a5a1a6a
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472968"
---
# <a name="spain-dni"></a>İspanya DNI

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

sekiz basamak ve ardından bir karakter

## <a name="pattern"></a>Desen

yedi basamak ve ardından bir karakter

- sekiz basamak
- İsteğe bağlı bir boşluk veya kısa çizgi
- bir onay harfi (büyük/küçük harfe duyarlı değil)

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_spain_eu_DL_and_NI_number_citizen` veya `Func_spain_eu_DL_and_NI_number_foreigner` desenle eşleşen içeriği bulur.
- `Keywords_spain_eu_national_id_card"` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_spain_eu_DL_and_NI_number_citizen` veya `Func_spain_eu_DL_and_NI_number_foreigner` desenle eşleşen içeriği bulur.

```xml
      <!-- Spain DNI -->
      <Entity id="8e6251b9-47b4-40e8-a42b-0f80876be192" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

- carné de identidad
- dni #
- dni
- dninúmero #
- documento nacional de identidad
- identidad único
- identidadúnico #
- sigorta numarası
- ulusal kimlik numarası
- ulusal kimlik
- nationalid #
- nationalidno #
- Nie #
- Nie
- nienúmero #
- número de identificación
- número nacional identidad
- kişisel kimlik numarası
- kişisel kimlik no
- benzersiz kimlik numarası
- Uniqueıd #
