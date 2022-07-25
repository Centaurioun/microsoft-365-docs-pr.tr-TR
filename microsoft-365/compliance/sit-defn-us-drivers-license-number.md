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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: ABD ehliyet numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: d25de827c913781c0426d8c6262bcb9f421ee73e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66989318"
---
# <a name="us-drivers-license-number"></a>ABD ehliyet numarası

## <a name="format"></a>Biçim

Duruma bağlıdır

## <a name="pattern"></a>Desen

eyalete bağlıdır; örneğin, New York:

- ddd ddd ddd gibi biçimlendirilmiş dokuz basamak eşleşir.
- ddd gibi dokuz basamak eşleşmez.

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_new_york_drivers_license_number` , desenle eşleşen içeriği bulur.
- 'den `Keyword_[state_name]_drivers_license_name` bir anahtar sözcük bulunur.
- 'den `Keyword_us_drivers_license` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının güvenilirliği düşüktür:

- İşlev `Func_new_york_drivers_license_number` , desenle eşleşen içeriği bulur.
- 'den `Keyword_[state_name]_drivers_license_name` bir anahtar sözcük bulunur.
- 'den `Keyword_us_drivers_license_abbreviations` bir anahtar sözcük bulunur.
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

- DL
- DLS
- CDL
- CDLS
- Kimlik
- Kimlik
- DL #
- DLS #
- CDL #
- CDLS #
- KİMLİĞİ #
- Kimlik #
- Kimlik numarası
- Kimlik numaraları
- LİSANSI
- LİSANSI #
- DLN

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