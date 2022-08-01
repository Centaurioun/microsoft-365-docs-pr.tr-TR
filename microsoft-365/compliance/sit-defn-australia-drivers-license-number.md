---
title: Avustralya sürücüleri lisans numarası varlık tanımı
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
description: Avustralya ehliyet numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 100bc203f5e3df7445e4067db286f31257b2df9b
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948476"
---
# <a name="australia-drivers-license-number"></a>Avustralya ehliyet numarası

## <a name="format"></a>Biçim

dokuz harf ve rakam

## <a name="pattern"></a>Desen

dokuz harf ve rakam:

- iki basamak veya harf (büyük/küçük harfe duyarlı değil)
- iki basamak
- beş basamak veya harf (büyük/küçük harfe duyarlı değil)

VEYA

- bir-iki isteğe bağlı harf (büyük/küçük harfe duyarlı değil)
- dört -dokuz basamak

VEYA

- dokuz basamak veya harf (büyük/küçük harfe duyarlı değil)

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade Regex_australia_drivers_license_number desenle eşleşen içeriği bulur.
- Keyword_australia_drivers_license_number anahtar sözcüğü bulunur.
- Keyword_australia_drivers_license_number_exclusions anahtar sözcüğü bulunamadı.

```xml
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_australia_drivers_license_number"></a>Keyword_australia_drivers_license_number

- uluslararası sürüş izinleri
- avustralya otomobil birliği
- uluslararası sürüş izni
- DriverLicence
- DriverLicences
- Sürücü Lic
- Sürücü Belgesi
- Sürücü Lisansları
- DriversLic
- DriversLicence
- DriversLicences
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
- Driver'sLicence
- Driver'sLicences
- Sürücü Lic
- Sürücü Lics
- Sürücü Belgesi
- Sürücü Lisansları
- DriverLic #
- DriverLics #
- DriverLicence #
- DriverLicences #
- Sürücü Lic #
- Sürücü Lics #
- Sürücü Belgesi #
- Sürücü Lisansları #
- DriversLic #
- DriversLics #
- DriversLicence #
- DriversLicences #
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
- Driver'sLicence #
- Driver'sLicences #
- Sürücü Lic #
- Sürücü Lics #
- Sürücü Belgesi #
- Sürücü Lisansları #

### <a name="keyword_australia_drivers_license_number_exclusions"></a>Keyword_australia_drivers_license_number_exclusions

- Acar
- DriverLicense
- DriverLicenses
- Sürücü Lisansı
- Sürücü Lisansları
- DriversLicense
- DriversLicenses
- Sürücü Lisansı
- Sürücü Lisansları
- Sürücü Belgesi
- Sürücü Lisansları
- Sürücü Belgesi
- Sürücü Lisansları
- Driver'sLicense
- Sürücü Lisansları
- Sürücü Belgesi
- Sürücü Lisansları
- DriverLicense #
- DriverLicenses #
- Sürücü Lisansı #
- Sürücü Lisansları #
- DriversLicense #
- DriversLicenses #
- Sürücü Lisansı #
- Sürücü Lisansları #
- Sürücü Belgesi #
- Sürücü Lisansları #
- Sürücü Belgesi #
- Sürücü Lisansları #
- Driver'sLicense #
- Sürücü Lisansları #
- Sürücü Belgesi #
- Sürücü Lisansları #
