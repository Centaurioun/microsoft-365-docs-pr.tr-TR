---
title: Makinelerin güvenlik durumları toplama API'sini al
description: Uç Nokta için Microsoft Defender kullanarak cihaz güvenlik durumlarından oluşan bir koleksiyon alın.
keywords: api'ler, graf api'leri, desteklenen API'ler, alma, cihaz, güvenlik, durum
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.custom: api
ms.openlocfilehash: c7750868c557ba4ebb4c37584b69e710ae1a449b
ms.sourcegitcommit: e8dd5cd434d17af7096d28d467a2b3b021cbb233
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "67051458"
---
# <a name="get-machines-security-states-collection-api"></a>Makine güvenlik durumları toplama API'lerini alma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:** 
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

Cihaz güvenlik durumlarının bir koleksiyonunu alır.

## <a name="permissions"></a>İzinler

Kullanıcının okuma izinlerine sahip olması gerekir.

## <a name="http-request"></a>HTTP isteği

```http
GET /testwdatppreview/machinesecuritystates
```

## <a name="request-headers"></a>İstek üst bilgileri

Üstbilgi|Değer
:---|:---
Yetkilendirme|Taşıyıcı {token}. **Gerekli**.
İçerik türü|application/json

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Başarılı olursa - 200 Tamam.

## <a name="example"></a>Örnek

### <a name="request-example"></a>İstek örneği

burada isteğin bir örneği verilmiş.

```http
GET https://graph.microsoft.com/testwdatppreview/machinesecuritystates
Content-type: application/json
```

### <a name="response-example"></a>Yanıt örneği

Yanıtın bir örneğini aşağıda bulabilirsiniz.

Alan *kimliği* cihaz kimliğini içerir ve cihaz bilgilerinde alan *kimliğine** eşittir.

```json
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineSecurityStates",
    "@odata.count":444,
    "@odata.nextLink":"https://graph.microsoft.com/testwdatppreview/machinesecuritystates?$skiptoken=[continuation token]",
    "value":[
        {
            "id":"000050e1b4afeee3742489ede9ad7a3e16bbd9c4",
            "build":14393,
            "revision":2485,
            "architecture":"Amd64",
            "osVersion":"10.0.14393.2485.amd64fre.rs1_release.180827-1809",
            "propertiesRequireAttention":[
                "AntivirusNotReporting",
                "EdrImpairedCommunications"
            ]
        },
        ...
    ]
}
```
