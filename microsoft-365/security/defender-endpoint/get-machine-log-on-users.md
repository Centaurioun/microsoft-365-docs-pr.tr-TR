---
title: Makine oturum açma kullanıcıları API'lerini alma
description: Uç Nokta için Microsoft Defender'da bir cihazda oturum açmış kullanıcıların koleksiyonunu almak için Makine oturum açma kullanıcılarını alma API'sini kullanmayı öğrenin.
keywords: api'ler, graf api'leri, desteklenen API'ler, alma, cihaz, oturum açma, kullanıcılar
ms.prod: m365-security
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
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 9ca2ccb7486131024f6c69c6203944f5b57fd878
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2022
ms.locfileid: "67331807"
---
# <a name="get-machine-logon-users-api"></a>Makine oturum açma kullanıcıları API'lerini alma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:** 
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API açıklaması
Belirli bir cihazda oturum açmış kullanıcıların koleksiyonunu alır.

## <a name="limitations"></a>Sınırlamalar
1. Yapılandırdığınız saklama süresine göre son güncelleştirilen uyarıları sorgulayabilirsiniz.
2. Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz[. Uç Nokta için Microsoft Defender API'leri kullanma](apis-intro.md)

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama |User.Read.All |'Kullanıcı profillerini oku'
Temsilci (iş veya okul hesabı) | User.Read.All | 'Kullanıcı profillerini oku'

> [!NOTE]
> Kullanıcı kimlik bilgilerini kullanarak belirteç alırken:
>
> - Kullanıcının en az şu rol iznine sahip olması gerekir: 'Verileri Görüntüle'. Daha fazla bilgi için bkz. [Rolleri oluşturma ve yönetme](user-roles.md).
> - Yanıt, yalnızca cihaz grubu ayarlarına bağlı olarak cihazın kullanıcı tarafından görünür olması durumunda kullanıcıları içerir. Daha fazla bilgi için bkz. [Cihaz gruplarını oluşturma ve yönetme](machine-groups.md).

## <a name="http-request"></a>HTTP isteği

```http
GET /api/machines/{id}/logonusers
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme | Dize | Taşıyıcı {token}. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Başarılıysa ve cihaz varsa - Gövdedeki [kullanıcı](user.md) varlıklarının listesiyle 200 Tamam. Cihaz bulunamadıysa - 404 Bulunamadı.

## <a name="example"></a>Örnek

### <a name="request"></a>Istek

burada isteğin bir örneği verilmiştir.

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/logonusers
```

### <a name="response"></a>Yanıt

Yanıtın bir örneği aşağıda verilmiştir.

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users",
    "value": [
        {
            "id": "contoso\\user1",
            "accountName": "user1",
            "accountDomain": "contoso",
            "firstSeen": "2019-12-18T08:02:54Z",
            "lastSeen": "2020-01-06T08:01:48Z",
            "logonTypes": "Interactive",
            "isDomainAdmin": true,
            "isOnlyNetworkUser": false
        },
        ...
    ]
}
```
