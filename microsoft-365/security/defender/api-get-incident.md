---
title: Olay API'si alma
description: Microsoft 365 Defender'da tek bir olay almak için Olayları alma API'sini kullanmayı öğrenin.
keywords: api'ler, graf api'leri, desteklenen API'ler, alma, dosya, karma
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 5473be1b45b87d677a7d18ba0bd8174364aa53b5
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67682205"
---
# <a name="get-incident-information-api"></a>Olay bilgileri API'si alma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

Kimliğine göre belirli bir olayı alır

## <a name="limitations"></a>Sınırlamalar

1. Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir.

İzin türü|Izni|İzin görünen adı
---|---|---
Uygulama|Incident.Read.All|'Tüm Olayları Oku'
Uygulama|Incident.ReadWrite.All|'Tüm Olayları okuma ve yazma'
Temsilci (iş veya okul hesabı)|Incident.Read|'Olayları Oku'
Temsilci (iş veya okul hesabı)|Incident.ReadWrite|'Olayları okuma ve yazma'

> [!NOTE]
>
> Kullanıcı kimlik bilgilerini kullanarak belirteç alırken:
>
> - Kullanıcının en az şu rol iznine sahip olması gerekir: 'Verileri Görüntüle'
> - Yanıt yalnızca kullanıcının maruz kaldığı olayları içerir

## <a name="http-request"></a>HTTP isteği

```console
GET .../api/incidents/{id}
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
---|---|---
Yetkilendirme|Dize|Taşıyıcı {token}. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem 200 Tamam değerini ve yanıt gövdesindeki olay varlığını döndürür.
Belirtilen kimlikle ilgili olay bulunamadıysa - 404 Bulunamadı.

## <a name="example"></a>Örnek

### <a name="request"></a>Istek

burada isteğin bir örneği verilmiş.

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
