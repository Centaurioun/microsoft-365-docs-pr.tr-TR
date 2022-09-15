---
title: Cihaz kimliğine göre eksik KB'leri alma
description: Cihaz kimliğine göre eksik güvenlik güncelleştirmelerini alır
keywords: apis, graph api, desteklenen API'ler, get, list, file, information, device id, threat & vulnerability management api, Uç Nokta için Microsoft Defender tvm api
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 9a470cfce6f7fe6cbe5c603a0fa8967d712bb6d8
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67696165"
---
# <a name="get-missing-kbs-by-device-id"></a>Cihaz kimliğine göre eksik KB'leri alma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender Güvenlik Açığı Yönetimi](../defender-vulnerability-management/index.yml)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> Microsoft Defender Güvenlik Açığı Yönetimi mı yaşamak istiyorsunuz? [Microsoft Defender Güvenlik Açığı Yönetimi genel önizleme denemesine](../defender-vulnerability-management/get-defender-vulnerability-management.md) nasıl kaydolabileceğiniz hakkında daha fazla bilgi edinin.

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Cihaz kimliğine göre eksik KB'leri (güvenlik güncelleştirmeleri) alır

## <a name="http-request"></a>HTTP isteği

```http
GET /api/machines/{machineId}/getmissingkbs
```
## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izin gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi için bkz. [Uç Nokta için Microsoft Defender API'leri kullanma](apis-intro.md).

İzin türü | Izni | İzin görünen adı
:---|:---|:---
Uygulama | Software.Read.All | 'Tehdit ve Güvenlik Açığı Yönetim Yazılımı bilgilerini okuyun'

## <a name="request-header"></a>İstek üst bilgisi

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme | Dize | Taşıyıcı {token}. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem 200 Tamam döndürür ve belirtilen cihazda gövdede kb verileri eksiktir.

## <a name="example"></a>Örnek

### <a name="request"></a>Istek

burada isteğin bir örneği verilmiştir.

```http
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a>Yanıt

Yanıtın bir örneği aşağıda verilmiştir.


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
        {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "windows_10",
                "edge",
                "internet_explorer"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 1,
            "cveAddressed": 97
        }
        ]
}
```

## <a name="related-topics"></a>İlgili konular

- [Microsoft Defender Güvenlik Açığı Yönetimi](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Defender Güvenlik Açığı Yönetimi yazılım envanteri](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
