---
title: Makineleri listeleme API'si
description: Uç Nokta için Microsoft Defender bulutla iletişim kuran makinelerden oluşan bir koleksiyonu almak için Liste makineleri API'sini kullanmayı öğrenin.
keywords: api'ler, graf api'leri, desteklenen API'ler, get, cihazlar
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection: M365-security-compliance
ms.subservice: mde
ms.custom: api
ms.openlocfilehash: b2ce0be32f5172aa1f6f86b450b9444f150eadb6
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67520643"
---
# <a name="list-machines-api"></a>Makineleri listeleme API'si

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:** 
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

Uç Nokta için Microsoft Defender bulutla iletişim kuran [bir Makine](machine.md) koleksiyonunu alır.

[OData V4 sorgularını](https://www.odata.org/documentation/) destekler.

OData'nın `$filter` sorgusu şu konuda desteklenir: `computerDnsName`, `id`, `version`, `deviceValue`, `aadDeviceId`, , `machineTags``lastIpAddress``exposureLevel``lastSeen``healthStatus``osPlatform``onboardingStatus``riskScore` ve .`rbacGroupId`
<br>```$stop``` maksimum değeri 10.000 olan
<br>```$skip```[Uç Nokta için Defender ile OData sorgularında](exposed-apis-odata-samples.md) örneklere bakın

## <a name="limitations"></a>Sınırlamalar

1. Yapılandırdığınız saklama süresine göre en son görülen cihazları alabilirsiniz.
2. Sayfa boyutu üst sınırı 10.000'dir.
3. Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır. 

## <a name="permissions"></a>İzinler

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|Machine.Read.All|'Tüm makine profillerini oku'
Uygulama|Machine.ReadWrite.All|'Tüm makine bilgilerini okuma ve yazma'
Temsilci (iş veya okul hesabı)|Machine.Read|'Makine bilgilerini oku'
Temsilci (iş veya okul hesabı)|Machine.ReadWrite|'Makine bilgilerini okuma ve yazma'

> [!NOTE]
> Kullanıcı kimlik bilgilerini kullanarak belirteç alırken:
>
> - Kullanıcının en az şu rol iznine sahip olması gerekir: 'Verileri Görüntüle' (Daha fazla bilgi için bkz [. Rolleri oluşturma ve yönetme](user-roles.md) )
> - Yanıt, cihaz grubu ayarlarına göre yalnızca kullanıcının erişimi olan cihazları içerir (Daha fazla bilgi için bkz [. Cihaz grupları oluşturma ve yönetme](machine-groups.md) )

## <a name="http-request"></a>HTTP isteği

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme|Dize|Taşıyıcı {token}. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Başarılıysa ve makineler varsa - gövdedeki [makine](machine.md) varlıklarının listesiyle 200 Tamam. Son kullanılan makine yoksa - 404 Bulunamadı.

## <a name="example"></a>Örnek

### <a name="request-example"></a>İstek örneği

burada isteğin bir örneği verilmiştir.

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

### <a name="response-example"></a>Yanıt örneği

Yanıtın bir örneği aşağıda verilmiştir.

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
            "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
            "computerDnsName": "mymachine1.contoso.com",
            "firstSeen": "2018-08-02T14:55:03.7791856Z",
            "lastSeen": "2018-08-02T14:55:03.7791856Z",
            "osPlatform": "Windows10" "Windows11",
            "version": "1709",
            "osProcessor": "x64",
            "lastIpAddress": "172.17.230.209",
            "lastExternalIpAddress": "167.220.196.71",
            "osBuild": 18209,
            "healthStatus": "Active",
            "rbacGroupId": 140,
            "rbacGroupName": "The-A-Team",
            "riskScore": "Low",
            "exposureLevel": "Medium",
            "isAadJoined": true,
            "aadDeviceId": "80fe8ff8-2624-418e-9591-41f0491218f9",
            "machineTags": [ "test tag 1", "test tag 2" ]
        }
        ...
    ]
}
```

## <a name="related-topics"></a>İlgili konular

- [Uç Nokta için Microsoft Defender ile OData sorguları](exposed-apis-odata-samples.md)
