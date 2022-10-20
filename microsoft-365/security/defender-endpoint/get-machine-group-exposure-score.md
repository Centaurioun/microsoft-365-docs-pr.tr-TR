---
title: Cihaz grubuna göre pozlama puanını listeleme
description: Cihaz grubuna göre maruz kalma puanlarının listesini alır.
keywords: api'ler, graf api'leri, desteklenen API'ler, alma, maruz kalma puanı, cihaz grubu, cihaz grubu maruz kalma puanı
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
ms.topic: conceptual
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: adc65d8cde79acd782b88c47bf281fe6cead61ea
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68642535"
---
# <a name="list-exposure-score-by-device-group"></a>Cihaz grubuna göre pozlama puanını listeleme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Her makine grubu için pozlama puanını alır.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz[. Uç Nokta için Microsoft Defender API'leri kullanma](apis-intro.md)

İzin türü|Izni|İzin görünen adı
---|---|---
Uygulama|Score.Read.All|'Tehdit ve Güvenlik Açığı Yönetimi puanını okuma'
Temsilci (iş veya okul hesabı)|Score.Read|'Tehdit ve Güvenlik Açığı Yönetimi puanını okuma'

## <a name="http-request"></a>HTTP isteği

```http
GET /api/exposureScore/ByMachineGroups
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
---|---|---
|Yetkilendirme|Dize|Taşıyıcı {token}. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Başarılı olursa bu yöntem 200 Tamam döndürür ve yanıt gövdesindeki cihaz grubu başına maruz kalma puanı verilerinin bir listesi bulunur.

## <a name="example"></a>Örnek

### <a name="example-request"></a>Örnek istek

burada isteğin bir örneği verilmiştir.

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore/ByMachineGroups
```

### <a name="example-response"></a>Örnek yanıt

Yanıtın bir örneği aşağıda verilmiştir.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore",
    "value": [
        {
            "time": "2019-12-03T09:51:28.214338Z",
            "score": 41.38041766305988,
            "rbacGroupName": "GroupOne"
        },
        {
            "time": "2019-12-03T09:51:28.2143399Z",
            "score": 37.403726933165366,
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a>İlgili konular

- [Microsoft Defender Güvenlik Açığı Yönetimi](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Defender Güvenlik Açığı Yönetimi açığa çıkarma puanı](/microsoft-365/security/defender-endpoint/tvm-exposure-score)
