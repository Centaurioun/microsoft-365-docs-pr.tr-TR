---
title: Liste Göstergeleri API'si
description: Uç Nokta için Microsoft Defender'daki tüm etkin Göstergelerin koleksiyonunu almak için Liste Göstergeleri API'sini kullanmayı öğrenin.
keywords: apis, genel API, desteklenen API'ler, Göstergeler koleksiyonu
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.custom: api
ms.openlocfilehash: 93f805ab85438e764d1fcee2a9571fa684cefa91
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67522179"
---
# <a name="list-indicators-api"></a>Liste Göstergeleri API'si

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

Tüm etkin [Göstergelerin](ti-indicator.md) koleksiyonunu alır.

[OData V4 sorgularını](https://www.odata.org/documentation/) destekler.

OData'nın `$filter` sorgusu şu sürümlerde desteklenir: `application`, `createdByDisplayName`, `expirationTime`, `generateAlert`, `title`, , `rbacGroupIds``creationTimeDateTimeUtc``rbacGroupNames``indicatorType``createdBy``indicatorValue``action`ve `severity` özellikleri.
<br>```$stop``` 10.000 maksimum değere sahip. 
<br>```$skip```.

[Uç Nokta için Microsoft Defender ile OData sorgularında](exposed-apis-odata-samples.md) örneklere bakın

## <a name="limitations"></a>Sınırlamalar

1. Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır. 

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz [. Başlarken](apis-intro.md)

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|Ti.ReadWrite|'Gösterge okuma ve yazma'
Uygulama|Ti.ReadWrite.All|'Tüm Göstergeleri Okuma ve Yazma'
Temsilci (iş veya okul hesabı)|Ti.ReadWrite|'Gösterge okuma ve yazma'

## <a name="http-request"></a>HTTP isteği

```http
GET https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme|Dize|Taşıyıcı {token}. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem [Bir Gösterge](ti-indicator.md) varlıkları koleksiyonuyla 200 Tamam yanıt kodu döndürür.

> [!NOTE]
> Uygulama 'Ti.ReadWrite.All' iznine sahipse, tüm Göstergelere gösterilir. Aksi takdirde, yalnızca oluşturduğu Göstergelere maruz kalır.

## <a name="example-1"></a>Örnek 1

### <a name="example-1-request"></a>Örnek 1 istek

Tüm Göstergeleri alan bir istek örneği aşağıda verilmiştir

```http
GET https://api.securitycenter.microsoft.com/api/indicators
```

### <a name="example-1-response"></a>Örnek 1 yanıt

Yanıtın bir örneği aşağıda verilmiştir.

```json
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "995",
            "indicatorValue": "12.13.14.15",
            "indicatorType": "IpAddress",
            "action": "Alert",
            "application": "demo-test",
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T11:15:35.3688259Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "test",
            "rbacGroupNames": []
        },
        {
            "id": "996",
            "indicatorValue": "220e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```

## <a name="example-2"></a>Örnek 2

### <a name="example-2-request"></a>Örnek 2 istek

'AlertAndBlock' eylemiyle tüm Göstergeleri alan bir istek örneği aşağıda verilmiştir 

```http
GET https://api.securitycenter.microsoft.com/api/indicators?$filter=action+eq+'AlertAndBlock'
```

### <a name="example-2-response"></a>Örnek 2 yanıt

Yanıtın bir örneği aşağıda verilmiştir.

```json
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "997",
            "indicatorValue": "111e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```
