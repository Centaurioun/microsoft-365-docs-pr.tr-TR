---
title: Yazılımı kimlikle al
description: Kimliğine göre yazılım ayrıntılarının listesini alır.
keywords: apis, graph api, desteklenen API'ler, get, software, Uç Nokta için Microsoft Defender tvm api, mdvm, Microsoft Defender Güvenlik Açığı Yönetimi
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: b6aab4ef544c1dc515163d93038ad761a2f4ac93
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67694325"
---
# <a name="get-software-by-id"></a>Yazılımı kimlikle al

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:** 
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Yazılım ayrıntılarını kimliğine göre alır.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için ayrıntılar için bkz. [Uç Nokta için Microsoft Defender API'lerini kullanma](apis-intro.md).

İzin türü|Izni|İzin görünen adı
---|---|---
Uygulama|Software.Read.All|'Tehdit ve Güvenlik Açığı Yönetim Yazılımı bilgilerini okuyun'
Temsilci (iş veya okul hesabı)|Software.Read|'Tehdit ve Güvenlik Açığı Yönetim Yazılımı bilgilerini okuyun'

## <a name="http-request"></a>HTTP isteği

```http
GET /api/Software/{Id}
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
---|---|---
Yetkilendirme|Dize|Taşıyıcı {token}. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem gövdede belirtilen yazılım verileriyle 200 Tamam döndürür.

## <a name="example"></a>Örnek

### <a name="request-example"></a>İstek örneği

burada isteğin bir örneği verilmiş.

```http
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge
```

### <a name="response-example"></a>Yanıt örneği

Yanıtın bir örneğini aşağıda bulabilirsiniz.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software/$entity",
    "id": "microsoft-_-edge",
    "name": "edge",
    "vendor": "microsoft",
    "weaknesses": 467,
    "publicExploit": true,
    "activeAlert": false,
    "exposedMachines": 172,
    "impactScore": 2.39947438
}
```

## <a name="related-topics"></a>İlgili konular

- [Microsoft Defender Güvenlik Açığı Yönetimi](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Defender Güvenlik Açığı Yönetimi yazılım envanteri](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
