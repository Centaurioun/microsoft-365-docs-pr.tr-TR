---
title: RBAC makine grupları toplama API'si alma
description: Uç Nokta için Microsoft Defender'da RBAC cihaz gruplarının koleksiyonunu almak için KB koleksiyonu alma API'sini kullanmayı öğrenin.
keywords: apis, graph api, desteklenen API'ler, get, RBAC, group
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
ms.date: 10/07/2018
ms.custom: api
ms.openlocfilehash: d1f4fd7af4161315b9b15fd5dd15be91d3713932
ms.sourcegitcommit: e8dd5cd434d17af7096d28d467a2b3b021cbb233
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "67051172"
---
# <a name="get-kb-collection-api"></a>KB toplama API'sini al

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:** 
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

RBAC cihaz gruplarının koleksiyonunu alır.

## <a name="permissions"></a>İzinler

Kullanıcının okuma izinlerine sahip olması gerekir.

## <a name="http-request"></a>HTTP isteği

```http
GET https://graph.microsoft.com/testwdatppreview/machinegroups
```

## <a name="request-headers"></a>İstek üst bilgileri

Üstbilgi|Değer
:---|:---
Yetkilendirme | Taşıyıcı {token}. **Gerekli**.
İçerik türü | application/json

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Başarılı olursa - 200 Tamam.

## <a name="example"></a>Örnek

### <a name="request"></a>Istek

burada isteğin bir örneği verilmiştir.

```http
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

### <a name="response-example"></a>Yanıt örneği

Yanıtın bir örneği aşağıda verilmiştir.
Alan kimliği, cihaz bilgilerinde cihaz grubu **kimliğini** ve **rbacGroupId** alanına eşit değeri içerir.
**Gruplanmamış** alan, herhangi bir gruba atanmamış tüm cihazlar için yalnızca bir grup için geçerlidir. Her zamanki gibi bu grubun adı "UnassignedGroup".

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineGroups",
    "@odata.count":7,
    "value":[
        {
            "id":86,
            "name":"UnassignedGroup",
            "description":"",
            "ungrouped":true},
        ...
}
```
