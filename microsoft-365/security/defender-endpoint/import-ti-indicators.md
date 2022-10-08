---
title: Göstergeleri İçeri Aktarma API'si
description: Uç Nokta için Microsoft Defender'da Gösterge API'sinin İçeri Aktarma toplu işlemini kullanmayı öğrenin.
keywords: api'ler, desteklenen API'ler, gönderme, ti, gösterge, güncelleştirme
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: article
ms.custom: api
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 905dfbb9aa8a5aee3af9a8d54fff9f4e0e9e5712
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68232528"
---
# <a name="import-indicators-api"></a>Göstergeleri İçeri Aktarma API'si

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:** 
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

[Gösterge](ti-indicator.md) varlıklarını gönderir veya Güncelleştirmeler.

IP'ler için CIDR gösterimi desteklenmez.

## <a name="limitations"></a>Sınırlamalar

1. Bu API için hız sınırlamaları dakikada 30 çağrıdır.
2. Kiracı başına 15.000 etkin [Gösterge](ti-indicator.md) sınırı vardır.
3. Bir API çağrısı için en büyük toplu iş boyutu 500'dür.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz [. Başlarken](apis-intro.md)

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|Ti.ReadWrite|'Gösterge okuma ve yazma'
Uygulama|Ti.ReadWrite.All|'Tüm Göstergeleri Okuma ve Yazma'
Temsilci (iş veya okul hesabı)|Ti.ReadWrite|'Gösterge okuma ve yazma'

## <a name="http-request"></a>HTTP isteği

```http
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme|Dize|Taşıyıcı {token}. **Gerekli**.
İçerik Türü|Dize|application/json. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

İstek gövdesinde aşağıdaki parametreleri içeren bir JSON nesnesi sağlayın:

Parametre|Tür|Açıklama
:---|:---|:---
Göstergeler|Liste<[Göstergesi](ti-indicator.md)>|[Göstergelerin](ti-indicator.md) Listesi. **Gerekli**

## <a name="response"></a>Yanıt

- Başarılı olursa bu yöntem, gösterge başına içeri aktarma sonuçlarının listesini içeren 200 - Tamam yanıt kodunu döndürür, aşağıdaki örne bakın.
- Başarılı olmazsa: Bu yöntem 400 - Hatalı İstek döndürür. Hatalı istek genellikle yanlış gövdeyi gösterir.

## <a name="example"></a>Örnek

### <a name="request-example"></a>İstek örneği

burada isteğin bir örneği verilmiştir.

```http
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

```json
{
    "Indicators":
    [
        {
            "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "title": "demo",
            "application": "demo-test",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Informational",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": ["group1", "group2"]
        },
        {
            "indicatorValue": "2233223322332233223322332233223322332233223322332233223322332222",
            "indicatorType": "FileSha256",
            "title": "demo2",
            "application": "demo-test2",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Medium",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": []
        }
    ]
}
```

### <a name="response-example"></a>Yanıt örneği

Yanıtın bir örneği aşağıda verilmiştir.

```json
{
    "value": [
        {
            "id": "2841",
            "indicator": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "isFailed": false,
            "failureReason": null
        },
        {
            "id": "2842",
            "indicator": "2233223322332233223322332233223322332233223322332233223322332222",
            "isFailed": false,
            "failureReason": null
        }
    ]
}
```

## <a name="related-topic"></a>İlgili konu

- [Göstergeleri yönetin](manage-indicators.md)
