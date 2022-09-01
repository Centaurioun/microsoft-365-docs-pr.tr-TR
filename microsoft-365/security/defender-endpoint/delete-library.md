---
title: Canlı yanıt kitaplığından dosya silme
description: Canlı yanıt kitaplığından bir dosyayı silmeyi öğrenin.
keywords: api'ler, graf api'leri, desteklenen API'ler, kitaplıktan silme
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: reference
ms.subservice: mde
ms.custom: api
ms.openlocfilehash: da4da672f3ae513a60f5d4a9fb7134c7b36bc8df
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67499046"
---
#  <a name="delete-a-file-from-the-live-response-library"></a>Canlı yanıt kitaplığından dosya silme  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)

[!include[Prerelease information](../../includes/prerelease.md)]

>Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

Canlı yanıt kitaplığından bir dosyayı silin.

## <a name="limitations"></a>Sınırlamalar

1.  Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz. [Kullanmaya başlama](apis-intro.md).

| İzin türü                    | Izni     | İzin görünen adı        |
|------------------------------------|----------------|--------------------------------|
| Uygulama                        | Library.Manage | Canlı yanıt kitaplığını yönetme |
| Temsilci (iş veya okul hesabı) | Library.Manage | Canlı yanıt kitaplığını yönetme |

## <a name="http-request"></a>HTTP isteği

SİLMEK https://api.securitycenter.microsoft.com/api/libraryfiles/{fileName}

## <a name="request-headers"></a>İstek üst bilgileri

| Name            | Tür   | Açıklama               |
|-----------------|--------|---------------------------|
| Yetkilendirme   | Dize | Taşıyıcı\<token>\. Gerekli. |

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

-   Kitaplıkta dosya varsa ve başarıyla silindiyse 204 İçerik Yok.

-   Belirtilen dosya adı bulunamadıysa 404 Bulunamadı.

## <a name="example"></a>Örnek

Istek

burada isteğin bir örneği verilmiştir.

```HTTP
DELETE https://api.securitycenter.microsoft.com/api/libraryfiles/script1.ps1
```

## <a name="related-topic"></a>İlgili konu
- [Canlı yanıt çalıştır](run-live-response.md) 