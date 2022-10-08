---
title: Desteklenen Microsoft 365 Defender API'leri
description: Desteklenen Microsoft 365 Defender API'leri
keywords: Microsoft 365 Defender, API'ler, api
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
- m365-security
- tier3
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.custom: api
ms.openlocfilehash: c43f2f3d60fe5e73984be8721750a29bcfc10740
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68077963"
---
# <a name="supported-microsoft-365-defender-apis"></a>Desteklenen Microsoft 365 Defender API'leri 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

## <a name="list-of-available-apis"></a>Kullanılabilir API'lerin listesi

Makale | Açıklama
-|-
[Gelişmiş Avcılık API'si](api-advanced-hunting.md) | Gelişmiş Tehdit Avcılığı sorguları çalıştırın.
[Olay API'leri](api-incident.md) | Olayları ve diğer pratik görevleri listeleyin ve güncelleştirin.
[Akış API'si](streaming-api.md) | Gerçek zamanlı olayları ve uyarıları tek bir veri akışında gerçekleşirken gönderme.

### <a name="endpoint-uris"></a>Uç nokta URI'leri

Ana API'lerin her ikisi için de temel URI: https://api.security.microsoft.com. Daha iyi performans için coğrafi konumunuza daha yakın bir sunucu kullanın:

- Birleşik Devletler: api-us.security.microsoft.com
- Avrupa: api-eu.security.microsoft.com
- Birleşik Krallık: api-uk.security.microsoft.com

Belirteçler erişimiyle https://api.security.microsoft.comedinilebilir.

Yol boyunca tüm `/api` API'ler [OData](/odata/overview) Protokolünü kullanır; örneğin, https://api.security.microsoft.com/api/incidents.

## <a name="related-articles"></a>İlgili makaleler

- [Microsoft 365 Defender API'lere genel bakış](api-overview.md)
- [Microsoft 365 Defender API'lerine erişme](api-access.md)
- [Akış API'si](../defender-endpoint/raw-data-export.md)
- [API sınırları ve lisanslama hakkında bilgi edinin](api-terms.md)
- [Hata kodlarını anlama](api-error-codes.md)
