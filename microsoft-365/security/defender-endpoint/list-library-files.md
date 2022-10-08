---
title: Kitaplık dosyalarını listele
description: Canlı yanıt kitaplığı dosyalarını listelemeyi öğrenin.
keywords: api'ler, graf api'leri, desteklenen API'ler, get, cihazlar
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: reference
ms.subservice: mde
ms.custom: api
ms.openlocfilehash: 5699f13fba91d02a8a5e00656487b12d882d07d8
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68226877"
---
#  <a name="list-library-files"></a>Kitaplık dosyalarını listele 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:** [Uç Nokta için Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

- Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

Canlı yanıt kitaplığı dosyalarını listeleyin.

## <a name="limitations"></a>Sınırlamalar

1.  Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz. [Kullanmaya başlama](apis-intro.md).

|İzin türü                       |      Izni          |  İzin görünen adı | 
|-----------------|--------|---------------------------|  
| Uygulama                        | Library.Manage | Canlı yanıt kitaplığını yönetme |
| Temsilci (iş veya okul hesabı) | Library.Manage | Canlı yanıt kitaplığını yönetme |

## <a name="http-request"></a>HTTP isteği

```HTTP
GET https://api.securitycenter.microsoft.com/api/libraryfiles
```

## <a name="request-headers"></a>İstek üst bilgileri

| Name         |      Tür                     | Açıklama
|-----------------|--------|---------------------------|
| Yetkilendirme   | Dize | Taşıyıcı {token}. Gerekli. |

## <a name="request-body"></a>İstek gövdesi
Boş

## <a name="response"></a>Yanıt 
Başarılı olursa, bu yöntem canlı yanıt kitaplığı dosya varlıklarından oluşan bir koleksiyona sahip 200 - Tamam yanıt kodunu döndürür.

## <a name="example"></a>Örnek

**Istek**

Burada tüm canlı yanıt kitaplığı dosyalarını alan bir istek örneği verilmiştir

```HTTP
GET https://api.securitycenter.microsoft.com/api/libraryfiles
```

## <a name="response-example"></a>Yanıt örneği

Yanıtın bir örneği aşağıda verilmiştir.

```JSON
HTTP/1.1 200 Ok
Content-type: application/json
{
"\@odata.context": "https://api.securitycenter.microsoft.com
/api/\$metadata\#LibraryFiles",
"value": [
    {
    "fileName": "script1.ps1",
    "sha256": "6e212a0db618507c44e4ec8ee7499dfef7e5767e5f8d31144df3b96fd1145caf",
    "description": null,
    "creationTime": "2019-10-24T10:54:23.2009016Z",
    "lastUpdatedTime": "2019-10-24T10:54:23.2009016Z",
    "createdBy": "admin",
    "hasParameters": true,
    "parametersDescription": "test"
    },
    {
    "fileName": "script.sh",
    "sha256": "d0f3e3b0641dbf88ee39c822516e81a909d1d06d22341dd9b1f12aa5e5c027a2",
    "description": null,
    "creationTime": "2018-10-24T11:15:35.3688259Z",
    "lastUpdatedTime": "2018-10-24T11:15:35.3688259Z",
    "createdBy": "username",
    "hasParameters": false
    },
    {
    "fileName": "memdump.exe",
    "sha256": "fa70b87730290c0d30fe255d1dfb65de82f96286ebfeeb1d88ed3cc831329825",
    "description": "Process memory dump",
    "creationTime": "2018-10-24T10:54:23.2009016Z",
    "lastUpdatedTime": "2018-10-24T10:54:23.2009016Z",
    "createdBy": "admin",
    "hasParameters": false
    }
]
}
```


## <a name="related-topic"></a>İlgili konu
- [Canlı yanıt çalıştır](run-live-response.md) 