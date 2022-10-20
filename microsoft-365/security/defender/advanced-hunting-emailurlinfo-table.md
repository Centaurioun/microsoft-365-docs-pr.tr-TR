---
title: Gelişmiş tehdit avcılığı şemasında EmailUrlInfo tablosu
description: Gelişmiş tehdit avcılığı şemasının EmailUrlInfo tablosunda URL veya bağlantı bilgileri hakkında bilgi edinin
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, tablo, sütun, veri türü, açıklama, EmailUrlInfo, ağ iletisi kimliği, URL, bağlantı
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.openlocfilehash: 3c4ca49c60340a84c2bf053d231233e20af0327e
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68636814"
---
# <a name="emailurlinfo"></a>EmailUrlInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender
- Office 365 için Microsoft Defender

`EmailUrlInfo` [Gelişmiş tehdit avcılığı](advanced-hunting-overview.md) şemasındaki tablo, Office 365 için Microsoft Defender tarafından işlenen e-postalar ve eklerdeki URL'ler hakkında bilgi içerir. Bu tablodan bilgi döndüren sorgular oluşturmak için bu başvuruyu kullanın. 

Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında bilgi için [gelişmiş avcılık başvurusuna bakın](advanced-hunting-schema-tables.md).

| Sütun adı | Veri türü | Açıklama |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Olayın kaydedilildiği tarih ve saat |
| `NetworkMessageId` | `string` | Microsoft 365 tarafından oluşturulan e-posta için benzersiz tanımlayıcı |
| `Url` | `string` | E-posta konusu, gövdesi veya ekindeki tam URL |
| `UrlDomain` | `string` | URL'nin etki alanı adı veya ana bilgisayar adı |
| `ReportId` | `long` | Yinelenen sayacı temel alan olay tanımlayıcısı. Benzersiz olayları tanımlamak için bu sütunun DeviceName ve Timestamp sütunlarıyla birlikte kullanılması gerekir |

## <a name="related-topics"></a>İlgili konular
- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Paylaşılan sorguları kullanın](advanced-hunting-shared-queries.md)
- [Cihazlar, e-postalar, uygulamalar ve kimlikler arasında avlayın](advanced-hunting-query-emails-devices.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)
