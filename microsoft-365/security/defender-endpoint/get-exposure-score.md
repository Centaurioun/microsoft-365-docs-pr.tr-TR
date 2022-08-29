---
title: Hassaslık puanı al
description: Kurumsal maruz kalma puanını alır.
keywords: api'ler, graf api'leri, desteklenen API'ler, alma, maruz kalma puanı, kurumsal maruz kalma puanı
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 2bc2ab5d622b064e22c868b46a39b1fb3c68e1a0
ms.sourcegitcommit: 48a75b40e607542e5fe219b6e75ffc757804a9c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2022
ms.locfileid: "67345227"
---
# <a name="get-exposure-score"></a>Hassaslık puanı al

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Kurumsal maruz kalma puanını alır.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz[. Uç Nokta için Microsoft Defender API'leri kullanma](apis-intro.md)

İzin türü|Izni|İzin görünen adı
---|---|---
Uygulama|Score.Read.All|'Tehdit ve Güvenlik Açığı Yönetimi puanını okuma'
Temsilci (iş veya okul hesabı)|Score.Read|'Tehdit ve Güvenlik Açığı Yönetimi puanını okuma'

## <a name="http-request"></a>HTTP isteği

```http
GET /api/exposureScore
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
---|---|---
Yetkilendirme|Dize|Taşıyıcı {token}. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem yanıt gövdesindeki açığa çıkarma verileriyle birlikte 200 Tamam döndürür.

## <a name="example"></a>Örnek

### <a name="request"></a>Istek

burada isteğin bir örneği verilmiştir.

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a>Yanıt

Yanıtın bir örneği aşağıda verilmiştir.

> [!NOTE]
> Burada gösterilen yanıt listesi kısa bir süre için kesilebilir.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}
```

## <a name="see-also"></a>Ayrıca bkz.

- [Microsoft Defender Güvenlik Açığı Yönetimi](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Defender Güvenlik Açığı Yönetimi açığa çıkarma puanı](/microsoft-365/security/defender-endpoint/tvm-exposure-score)
