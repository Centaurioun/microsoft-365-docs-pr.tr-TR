---
title: Güvenlik temelleri değerlendirme profilleri
description: "\"Microsoft Defender Güvenlik Açığı Yönetimi\" verileri çeken güvenlik temelleri değerlendirme profilleri API'leri hakkında bilgi sağlar. Farklı veri türlerini almak için farklı API çağrıları vardır. Genel olarak, her API çağrısı kuruluşunuzdaki cihazlar için gerekli verileri içerir."
keywords: api, API'ler, dışarı aktarma değerlendirmesi, cihaz değerlendirmesi başına, makine değerlendirmesi başına, güvenlik açığı değerlendirmesi raporu, cihaz güvenlik açığı değerlendirmesi, cihaz güvenlik açığı raporu, güvenli yapılandırma değerlendirmesi, güvenli yapılandırma raporu, yazılım güvenlik açıkları değerlendirmesi, yazılım güvenlik açığı raporu, makineye göre güvenlik açığı raporu,
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 5aa9ba2cc42784c39f183346f41b72f24424f6a9
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67694601"
---
# <a name="list-all-security-baselines-assessment-profiles"></a>Tüm güvenlik temelleri değerlendirme profillerini listeleme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender Güvenlik Açığı Yönetimi](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender Güvenlik Açığı Yönetimi mı yaşamak istiyorsunuz? [Microsoft Defender Güvenlik Açığı Yönetimi genel önizleme denemesine](../defender-vulnerability-management/get-defender-vulnerability-management.md) nasıl kaydolabileceğiniz hakkında daha fazla bilgi edinin.

## <a name="1-get-security-baselines-assessment-profiles"></a>1. Güvenlik temelleri değerlendirme profillerini alma

Bu API, kuruluş tarafından oluşturulan tüm güvenlik temelleri değerlendirme profillerinin listesini alır.

### <a name="11-parameters"></a>1.1 Parametreler

- OData V4 sorgularını destekler.
- OData tarafından desteklenen işleçler:
  - üzerinde $filter: id,name, operatingSystem, operatingSystemVersion, status, settingsNumber, passedDevices, totalDevices
  - maksimum değeri 10.000 olan $top.
  - $skip.

### <a name="12-http-request"></a>1.2 HTTP isteği

```http
GET:/api/baselineProfiles
```

### <a name="13-request-headers"></a>1.3 İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme|Dize|Taşıyıcı {token}. **Gerekli**.

### <a name="14-properties"></a>1.4 Özellikleri

|Özellik | Tür | Açıklama |
|:---|:---|:---|
|Kimlik | Dize | Belirli temel profilin benzersiz tanımlayıcısı.
|Adı | Dize | Profil adı.
|Açıklama | Dize | Profil açıklaması.
|Kriter | Dize | Profil karşılaştırması.
|Sürüm | Dize | Profil sürümü.
|Operatingsystem|Dize|Profilin geçerli işletim sistemi.
|operatingSystemVersion|Dize|Profilin geçerli işletim sistemi sürümü.
|Durum|Boole|Profilin etkin olup olmadığını gösterir
|complianceLevel|Dize|Profil için seçilen uyumluluk düzeyi.
|settingsNumber|Int|Profildeki seçili yapılandırmaların sayısı.
|Createdby|Dize|Bu profili oluşturan kullanıcı.
|lastUpdatedBy|Datetime|Bu profili değiştiren son kullanıcı.
|createdOnTimeOffset|Datetime|Profilin oluşturulduğu tarih ve saat.
|lastUpdateTimeOffset|Datetime|Profilin son güncelleştirildiği tarih ve saat.
|passedDevices|Int|Bu profil için geçerli olan ve tüm profil yapılandırmalarıyla uyumlu olan cihaz sayısı.
|totalDevices|Int|Bu profil için geçerli cihaz sayısı.

## <a name="15-example"></a>1.5 Örneği

### <a name="151-request-example"></a>1.5.1 İstek örneği

```http
GET https://api.securitycenter.microsoft.com/api/baselineProfiles
```

### <a name="162-response-example"></a>1.6.2 Yanıt örneği

```json
{
    "@odata.context": "https:// api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicBaselineProfileDto)",
    "value":
    [
        {
            "id": "02bcbb9d-d197-479e-811e-1cd5a6f9f8fa",
            "name": "Windows 10 build 1909 CIS profile",
            "description": "important",
            "benchmark": "CIS",
            "version": "1.0.0",
            "operatingSystem": "Windows 10",
            "operatingSystemVersion": "1909",
            "status": true,
            "complianceLevel": "Level 1 (L1) - Corporate/Enterprise Environment (general use)",
            "settingsNumber": 51,
            "createdBy": "user@org.net",
            "lastUpdatedBy": null,
            "createdOnTimestampUTC": "0001-01-01T00:00:00Z",
            "lastUpdateTimestampUTC": "0001-01-01T00:00:00Z",
            "passedDevices": 0,
            "totalDevices": 10
        }
     ]
}
```

## <a name="see-also"></a>Ayrıca bkz.

- [Güvenlik temelleri değerlendirmesini dışarı aktar](export-security-baseline-assessment.md)
- [Güvenlik temelleri değerlendirme yapılandırmalarını alma](get-security-baselines-assessment-configurations.md)
