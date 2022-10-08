---
title: Portekiz sürücü lisans numarası varlık tanımı
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
description: Portekiz sürücü lisansı numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 235e33c55531e1f5bbc2de28a33ed6bb2b74390b
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472771"
---
# <a name="portugal-drivers-license-number"></a>Portekiz ehliyet numarası

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

iki desen - iki harf ve ardından özel karakterler içeren 5-8 basamak

## <a name="pattern"></a>Desen

Desen 1: İki harf ve ardından özel karakterlerle 5/6:

- İki harf (büyük/küçük harfe duyarlı değil)
- Kısa çizgi
- Beş veya Altı basamak
- Boşluk
- Bir basamak

Desen 2: Bir harf ve ardından özel karakterler içeren 6/8 basamak:

- Bir harf (büyük/küçük harfe duyarlı değil)
- Kısa çizgi
- Altı veya sekiz basamak
- Boşluk
- Bir basamak

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- Normal ifade `Regex_portugal_eu_driver's_license_number` , desenle eşleşen içeriği bulur.
- veya `Keywords_portugal_eu_driver's_license_number` anahtar `Keywords_eu_driver's_license_number` sözcüğü bulunur.

```xml
      <!-- Portugal Driver's License Number -->
      <Entity id="977f1e5a-2c33-4bcc-b516-95bb275cff23" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_portugal_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- sürücü
- driverlics
- driverlicense
- sürücü lisansları
- sürücülik
- driverlicences
- sürücü lic
- sürücü lisansları
- sürücü lisansı
- sürücü lisansları
- sürücü lisansı
- sürücü lisansları
- sürücüler
- sürücüler
- sürücüler
- sürücüler
- driverslicense
- sürücü lisansları
- sürücüler lic
- sürücüler lics
- sürücü lisansı
- sürücü lisansları
- sürücü lisansı
- sürücü lisansları
- driver'lic
- driver'lics
- sürücü lisansı
- sürücü lisansları
- sürücü belgesi
- sürücü lisansları
- driver'lic
- sürücü lisansları
- sürücü lisansı
- sürücü lisansları
- sürücü belgesi
- sürücü lisansları
- driver'slic
- sürücü dilimleri
- driver'slicense
- driver'slicenses
- sürücü dilimi
- sürücü dilimleri
- sürücü lic
- sürücü lics
- sürücü belgesi
- sürücü lisansları
- sürücü belgesi
- sürücü lisansları
- Dl #
- Dls #
- sürücü #
- driverlics #
- driverlicense #
- sürücü lisansları #
- sürücülik #
- driverlicences #
- sürücü lic #
- sürücü lisansları #
- sürücü lisansı #
- sürücü lisansları #
- sürücü lisansları #
- sürücüler #
- sürücüler #
- driverslicense #
- sürücü lisansları #
- sürücüler #
- sürücüler #
- sürücüler lic #
- sürücüler lics #
- sürücü lisansı #
- sürücü lisansları #
- sürücü lisansı #
- sürücü lisansları #
- driver'lic #
- driver'lics #
- sürücü lisansı #
- sürücü lisansları #
- sürücü belgesi #
- sürücü lisansları #
- driver'lic #
- sürücü lisansları #
- sürücü lisansı #
- sürücü lisansları #
- sürücü belgesi #
- sürücü lisansları #
- driver'slic #
- sürücü dilimleri #
- driver'slicense #
- driver'slicenses #
- sürücü dilimi #
- sürücü dilimleri #
- sürücü lic #
- sürücü lics #
- sürücü belgesi #
- sürücü lisansları #
- sürücü belgesi #
- sürücü lisansları #
- Ehliyet
- Ehliyet
- dlno #
- driv lic
- driv licen
- driv lisansı
- driv lisansları
- driv lisansı
- driv lisansları
- sürücü lisans
- sürücüler lisans
- sürücü lisans
- sürüş lic
- sürüş licen
- sürücü lisansları
- Ehliyet
- ehliyetler
- sürüş izni
- dl no
- dlno
- dl numarası

### <a name="keywords_portugal_eu_drivers_license_number"></a>Keywords_portugal_eu_driver s_license_number

- carteira de motorista
- carteira motorista
- carteira de habilitação
- carteira habilitação
- número de licença
- número licença
- permissão de condução
- permissão condução
- Licença condução Portugal
- carta de condução
