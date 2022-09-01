---
title: Canlı yanıt kitaplığı yöntemleri ve özellikleri
description: Canlı yanıt kitaplığı yöntemlerini ve özelliklerini kullanmayı öğrenin.
keywords: api'ler, graf api'leri, desteklenen API'ler, get, cihazlar
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
ms.subservice: m365d
ms.openlocfilehash: 8338805bebc21e538242ebb902a5d581d5af42f5
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67520829"
---
#  <a name="live-response-library-methods-and-properties"></a>Canlı yanıt kitaplığı yöntemleri ve özellikleri

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:** [Uç Nokta için Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

- Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a>Yöntemler

| **Yöntem**          | **Dönüş Türü**         | **Açıklama**                         |
|---------------------|-------------------------|-----------------------------------------|
| Kitaplık dosyalarını listele  | Kitaplık dosyası koleksiyonu | Liste kitaplığı dosya varlıkları              |
| Kitaplığa yükleme   | Kitaplık dosyası varlığı     | Canlı yanıt kitaplığına dosya yükleme |
| Kitaplıktan sil | İçerik yok              | Kitaplık dosyası varlığını silme              |

## <a name="properties"></a>Özellikler

| **Özellik** | **Tür**                         | **Açıklama**                                        |
|--------------|----------------------------------|--------------------------------------------------------|
| Komut     | Live Response komut koleksiyonu | Command nesneleri dizisi. Bkz. [canlı yanıt komutları](live-response.md#live-response-commands). |

