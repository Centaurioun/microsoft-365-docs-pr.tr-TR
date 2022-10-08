---
title: ABD sürücüleri lisans numarası varlık tanımı
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
description: ABD ehliyet numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 9659bfce35958409e54ffe7ff15e948e5b980d6f
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472573"
---
# <a name="us-drivers-license-number"></a>ABD ehliyet numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

Duruma bağlıdır

## <a name="pattern"></a>Desen

eyalete bağlıdır; örneğin, New York:

- ddd ddd ddd gibi biçimlendirilmiş dokuz basamak eşleşir.
- ddd gibi dokuz basamak eşleşmez.

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_new_york_drivers_license_number`, desenle eşleşen içeriği bulur.
- `Keyword_[state_name]_drivers_license_name` içinden bir anahtar sözcük bulundu.
- `Keyword_us_drivers_license` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- İşlev `Func_new_york_drivers_license_number`, desenle eşleşen içeriği bulur.
- `Keyword_[state_name]_drivers_license_name` içinden bir anahtar sözcük bulundu.
- `Keyword_us_drivers_license_abbreviations` içinden bir anahtar sözcük bulundu.
- anahtar `Keyword_us_drivers_license` sözcüğü bulunamadı.

```xml
<Entity id="dfeb356f-61cd-459e-bf0f-7c6d28b458c6 patternsProximity="300">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_us_drivers_license_abbreviations"></a>Keyword_us_drivers_license_abbreviations

- Dl
- Dls
- CDL
- CDLS
- Kimlik
- Kimlik
- Dl #
- Dls #
- CDL #
- CDLS #
- Kimliği #
- Kimlik #
- Kimlik numarası
- Kimlik numaraları
- Lisansı
- Lisansı #
- Dln

### <a name="keyword_us_drivers_license"></a>Keyword_us_drivers_license

- DriverLic
- DriverLics
- DriverLicense
- DriverLicenses
- Sürücü Lic
- Sürücü Lics
- Sürücü Lisansı
- Sürücü Lisansları
- DriversLic
- DriversLics
- DriversLicense
- DriversLicenses
- Sürücüler Lic
- Sürücüler Lics
- Sürücü Lisansı
- Sürücü Lisansları
- Driver'Lic
- Driver'Lics
- Sürücü Belgesi
- Sürücü Lisansları
- Driver' Lic
- Sürücü Lics
- Sürücü Belgesi
- Sürücü Lisansları
- Driver'sLic
- Driver'sLics
- Driver'sLicense
- Sürücü Lisansları
- Sürücü Lic
- Sürücü Lics
- Sürücü Belgesi
- Sürücü Lisansları
- kimlik numarası
- kimlik numaraları
- Kimlik #
- kimlik kartı
- kimlik kartları
- kimlik kartı
- kimlik kartları
- DriverLic #
- DriverLics #
- DriverLicense #
- DriverLicenses #
- Sürücü Lic #
- Sürücü Lics #
- Sürücü Lisansı #
- Sürücü Lisansları #
- DriversLic #
- DriversLics #
- DriversLicense #
- DriversLicenses #
- Sürücüler Lic #
- Sürücüler Lics #
- Sürücü Lisansı #
- Sürücü Lisansları #
- Driver'Lic #
- Driver'Lics #
- Sürücü Belgesi #
- Sürücü Lisansları #
- Driver' Lic #
- Sürücü Lics #
- Sürücü Belgesi #
- Sürücü Lisansları #
- Driver'sLic #
- Driver'sLics #
- Driver'sLicense #
- Sürücü Lisansları #
- Sürücü Lic #
- Sürücü Lics #
- Sürücü Belgesi #
- Sürücü Lisansları #
- kimlik kartı #
- kimlik kartları #
- kimlik kartı #
- kimlik kartları #

### <a name="keyword_state_name_drivers_license_name"></a>Keyword_[state_name]_drivers_license_name

- eyalet kısaltması (örneğin, "NY")
- eyalet adı (örneğin, "New York")
