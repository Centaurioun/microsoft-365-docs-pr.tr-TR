---
title: Cihaz güvenli puanını alma
description: Kuruluş cihazının güvenli puanını alır.
keywords: api'ler, graf api'leri, desteklenen API'ler, alma, uyarılar, son kullanılanlar
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
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
ms.openlocfilehash: 130155711355c0e19109672bdcb241775f3db1e9
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68209788"
---
# <a name="get-device-secure-score"></a>Cihaz güvenlik puanı al

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[Cihazlar için Microsoft Güvenli Puanınızı](tvm-microsoft-secure-score-devices.md) alır. Cihazlar için Daha Yüksek Bir Microsoft Güvenli Puanı, uç noktalarınızın siber güvenlik tehdit saldırılarına karşı daha dayanıklı olduğu anlamına gelir.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için ayrıntılar için bkz. [Uç Nokta için Microsoft Defender API'lerini kullanma](apis-intro.md).

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|Score.Read.All|'Tehdit ve Güvenlik Açığı Yönetimi puanını okuma'
Temsilci (iş veya okul hesabı)|Score.Read|'Tehdit ve Güvenlik Açığı Yönetimi puanını okuma'

## <a name="http-request"></a>HTTP isteği

```http
GET /api/configurationScore
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme|Dize|Taşıyıcı {token}. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem yanıt gövdesinde cihaz güvenli puan verileriyle birlikte 200 Tamam döndürür.

## <a name="example"></a>Örnek

### <a name="request-example"></a>İstek örneği

burada isteğin bir örneği verilmiştir.

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response-example"></a>Yanıt örneği

Yanıtın bir örneği aşağıda verilmiştir.

> [!NOTE]
> Burada gösterilen yanıt listesi kısa bir süre için kesilebilir.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a>Ayrıca bkz.

- [Uç Nokta için Microsoft Defender ile OData sorguları](exposed-apis-odata-samples.md)
