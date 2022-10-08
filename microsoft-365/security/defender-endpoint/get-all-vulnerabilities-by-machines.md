---
title: Makine ve yazılıma göre tüm güvenlik açıklarını alma
description: Makine ve Yazılım tarafından kuruluşu etkileyen tüm güvenlik açıklarının listesini alır
keywords: api'ler, graph api'leri, desteklenen API'ler, alma, güvenlik açığı bilgileri, Uç Nokta için Microsoft Defender tvm API'leri
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 4468c7f8399e6ed30a38867565fca3740d168b6e
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68190869"
---
# <a name="list-vulnerabilities-by-machine-and-software"></a>Makine ve yazılıma göre güvenlik açıklarını listele

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[Makine](machine.md) ve [yazılım](software.md) başına kuruluşu etkileyen tüm güvenlik açıklarının listesini alır.

- Güvenlik açığının düzeltilmesi gereken bir KB varsa yanıtta görünür.
- [OData V4 sorgularını](https://www.odata.org/documentation/) destekler.
- OData'nın `$filter` sorgusu şu özelliklerde desteklenir: `id`, `cveId`, `machineId``fixingKbId`, , `productName`, `productVersion`, , `severity`ve `productVendor` özellikleri.
<br>```$stop``` maksimum değeri 10.000 olan
<br>```$skip```

> [!TIP]
> Bu, [Power BI tümleştirmesi](api-power-bi.md) için harika bir API'dir.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için ayrıntılar için bkz. [Uç Nokta için Microsoft Defender API'lerini kullanma](apis-intro.md).

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|Vulnerability.Read.All|'Tehdit ve Güvenlik Açığı Yönetimi güvenlik açığı bilgilerini okuyun'
Temsilci (iş veya okul hesabı)|Vulnerability.Read|'Tehdit ve Güvenlik Açığı Yönetimi güvenlik açığı bilgilerini okuyun'

## <a name="http-request"></a>HTTP isteği

```http
GET /api/vulnerabilities/machinesVulnerabilities
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme|Dize|Taşıyıcı {token}. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem gövdedeki güvenlik açıklarının listesiyle birlikte 200 Tamam döndürür.

## <a name="example"></a>Örnek

### <a name="request-example"></a>İstek örneği

burada isteğin bir örneği verilmiştir.

```http
GET https://api.securitycenter.microsoft.com/api/vulnerabilities/machinesVulnerabilities
```

### <a name="response-example"></a>Yanıt örneği

Yanıtın bir örneği aşağıda verilmiştir.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicAssetVulnerabilityDto)",
    "value": [
        {
            "id": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21-_-CVE-2020-6494-_-microsoft-_-edge_chromium-based-_-81.0.416.77-_-",
            "cveId": "CVE-2020-6494",
            "machineId": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21",
            "fixingKbId": null,
            "productName": "edge_chromium-based",
            "productVendor": "microsoft",
            "productVersion": "81.0.416.77",
            "severity": "Low"
        },
        {
            "id": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283-_-CVE-2016-3348-_-microsoft-_-windows_server_2012_r2-_-6.3.9600.19728-_-3185911",
            "cveId": "CVE-2016-3348",
            "machineId": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283",
            "fixingKbId": "3185911",
            "productName": "windows_server_2012_r2",
            "productVendor": "microsoft",
            "productVersion": "6.3.9600.19728",
            "severity": "Low"
        },
        ...
    ]

}
```

## <a name="see-also"></a>Ayrıca bkz.

- [Microsoft Defender Güvenlik Açığı Yönetimi](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Kuruluşunuzdaki güvenlik açıkları](/microsoft-365/security/defender-endpoint/tvm-weaknesses)
