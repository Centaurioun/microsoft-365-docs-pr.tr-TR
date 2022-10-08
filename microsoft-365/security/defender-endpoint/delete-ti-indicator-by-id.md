---
title: Gösterge API'lerini silin.
description: Uç Nokta için Microsoft Defender'da Bir Gösterge varlığını kimliğine göre silmek için Göstergeyi Sil API'sini kullanmayı öğrenin.
keywords: apis, genel API, desteklenen API'ler, silme, ti göstergesi, varlık, kimlik
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
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 38a7cfff0d1ae3681a3f238f03462ff6e222047e
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68194411"
---
# <a name="delete-indicator-api"></a>Gösterge API'lerini Sil

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API açıklaması

[Bir Gösterge](ti-indicator.md) varlığını kimliğine göre siler.

## <a name="limitations"></a>Sınırlamalar

Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz [. Başlarken](apis-intro.md)

İzin türü | Izni | İzin görünen adı
:---|:---|:---
Uygulama | Ti.ReadWrite | 'TI Göstergelerini okuma ve yazma'
Uygulama | Ti.ReadWrite.All | 'Gösterge okuma ve yazma'

## <a name="http-request"></a>HTTP isteği

```http
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme | Dize | Taşıyıcı {token}. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Gösterge varsa ve başarıyla silindiyse - İçerik olmadan 204 Tamam

Belirtilen kimliği içeren Gösterge bulunamadıysa - 404 Bulunamadı

## <a name="example"></a>Örnek

### <a name="request"></a>Istek

burada isteğin bir örneği verilmiş.

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
