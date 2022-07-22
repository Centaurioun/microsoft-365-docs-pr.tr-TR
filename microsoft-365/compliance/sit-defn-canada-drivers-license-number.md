---
title: Kanada sürücü lisans numarası varlık tanımı
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
description: Kanada sürücü lisansı numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: a42af206eef8508bd971fad60d213c15f131e2b2
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948994"
---
# <a name="canada-drivers-license-number"></a>Kanada sürücü lisans numarası

## <a name="format"></a>Biçim

İllere göre değişir

## <a name="pattern"></a>Desen

Çeşitli desenler kapsayan:

- Alberta
- britanya Kolumbiyası
- Manitoba
- Yeni Brunswick
- Newfoundland/Labrador
- Nova Scotia
- Ontario
- Prens Edward Adası
- Quebec
- Saskatchewan

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_[province_name]_drivers_license_number` , desenle eşleşen içeriği bulur.
- 'den `Keyword_[province_name]_drivers_license_name` bir anahtar sözcük bulunur.
- 'den `Keyword_canada_drivers_license` bir anahtar sözcük bulunur.

```xml
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_province_name_drivers_license_name"></a>Keyword_[province_name]_drivers_license_name

- Bölge kısaltması, örneğin AB
- Bölge adı, örneğin Alberta

### <a name="keyword_canada_drivers_license"></a>Keyword_canada_drivers_license

- DL
- DLS
- CDL
- CDLS
- DriverLic
- DriverLics
- DriverLicense
- DriverLicenses
- DriverLicence
- DriverLicences
- Sürücü Lic
- Sürücü Lics
- Sürücü Lisansı
- Sürücü Lisansları
- Sürücü Belgesi
- Sürücü Lisansları
- DriversLic
- DriversLics
- DriversLicence
- DriversLicences
- DriversLicense
- DriversLicenses
- Sürücüler Lic
- Sürücüler Lics
- Sürücü Lisansı
- Sürücü Lisansları
- Sürücü Lisansı
- Sürücü Lisansları
- Driver'Lic
- Driver'Lics
- Sürücü Belgesi
- Sürücü Lisansları
- Sürücü Belgesi
- Sürücü Lisansları
- Driver' Lic
- Sürücü Lics
- Sürücü Belgesi
- Sürücü Lisansları
- Sürücü Belgesi
- Sürücü Lisansları
- Driver'sLic
- Driver'sLics
- Driver'sLicense
- Sürücü Lisansları
- Driver'sLicence
- Driver'sLicences
- Sürücü Lic
- Sürücü Lics
- Sürücü Belgesi
- Sürücü Lisansları
- Sürücü Belgesi
- Sürücü Lisansları
- Permis de Conduire
- Kimliği
- Kimlik
- kimlik kartı numarası
- kimlik kartı numaraları
- idcard #
- idcard #s
- kimlik kartı
- kimlik kartı kartları
- idcard
- kimlik numarası
- kimlik numaraları
- Kimlik #
- tanımlama #s
- kimlik kartı
- kimlik kartları
- Kimlik
- DL #
- DLS #
- CDL #
- CDLS #
- DriverLic #
- DriverLics #
- DriverLicense #
- DriverLicenses #
- DriverLicence #
- DriverLicences #
- Sürücü Lic #
- Sürücü Lics #
- Sürücü Lisansı #
- Sürücü Lisansları #
- Sürücü Lisansı #
- Sürücü Lisansları #
- DriversLic #
- DriversLics #
- DriversLicense #
- DriversLicenses #
- DriversLicence #
- DriversLicences #
- Sürücüler Lic #
- Sürücüler Lics #
- Sürücü Lisansı #
- Sürücü Lisansları #
- Sürücü Lisansı #
- Sürücü Lisansları #
- Driver'Lic #
- Driver'Lics #
- Sürücü Belgesi #
- Sürücü Lisansları #
- Sürücü Belgesi #
- Sürücü Lisansları #
- Driver' Lic #
- Sürücü Lics #
- Sürücü Belgesi #
- Sürücü Lisansları #
- Sürücü Belgesi #
- Sürücü Lisansları #
- Driver'sLic #
- Driver'sLics #
- Driver'sLicense #
- Sürücü Lisansları #
- Driver'sLicence #
- Driver'sLicences #
- Sürücü Lic #
- Sürücü Lics #
- Sürücü Belgesi #
- Sürücü Lisansları #
- Sürücü Belgesi #
- Sürücü Lisansları #
- Permis de Conduire #
- Kimliği #
- Kimlik #
- kimlik kartı #
- kimlik kartı kartları #
- idcard #
- kimlik kartı #
- kimlik kartları #
- Kimlik #