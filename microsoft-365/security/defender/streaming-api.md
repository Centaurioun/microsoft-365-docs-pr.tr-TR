---
title: Microsoft 365 Defender olaylarını akışla aktar
description: Gelişmiş Tehdit Avcılığı olaylarını Event Hubs'a veya Azure depolama hesabına akışla aktarmaya yönelik Microsoft 365 Defender yapılandırmayı öğrenin
keywords: ham veri dışarı aktarma, akış API'si, API, Olay hub'ları, Azure depolama, depolama hesabı, Gelişmiş Tehdit Avcılığı, ham veri paylaşımı
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.collection:
- m365-security
- tier3
ms.topic: article
ms.openlocfilehash: e0066d33aa0066b01e32a1f5ad02dfc7f780dce1
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68084495"
---
# <a name="streaming-api"></a>Akış API'si

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Gelişmiş Tehdit Avcılığı olaylarını Event Hubs'a ve/veya Azure depolama hesabına akışla aktar.

Microsoft 365 Defender[, Gelişmiş Tehdit Avcılığı](../defender/advanced-hunting-overview.md) aracılığıyla [Event Hubs](/azure/event-hubs/) ve/veya [Azure depolama hesabına](/azure/event-hubs/) akış olaylarını destekler.

Microsoft 365 Defender akış API'si hakkında daha fazla bilgi için [videoya](https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga) bakın.

## <a name="in-this-section"></a>Bu bölümde

Konu | Açıklama
:---|:---
[Olayları Azure Event Hubs akışla aktar](streaming-api-event-hub.md)| Kiracınızda akış API'sini etkinleştirme hakkında bilgi edinin ve Microsoft 365 Defender Event Hubs'a [Gelişmiş Avcılık](../defender/advanced-hunting-overview.md) akışı sağlayacak şekilde yapılandırın.
[Olayları Azure depolama hesabınıza akışla aktarma](streaming-api-storage.md)| Kiracınızda akış API'sini etkinleştirme hakkında bilgi edinin ve Microsoft 365 Defender Azure depolama hesabınıza [Gelişmiş Tehdit Avcılığı](advanced-hunting-overview.md) akışı sağlayacak şekilde yapılandırın.
[Desteklenen olay türleri](supported-event-types.md) | Akış API'sinin hangi Gelişmiş Tehdit Avcılığı olay türlerini desteklediğini öğrenin.

Olay bilgilerini görselleştirme hizmetleri, veri işleme altyapıları veya uzun süreli veri saklama için Azure depolama tarafından kullanılmak üzere doğrudan Azure Event hubs'a göndermek üzere akış API'sini ayarlamayı öğrenmek için bu kısa videoyu izleyin.  
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]

## <a name="related-topics"></a>İlgili konular
- [Gelişmiş Avcılık'a Genel Bakış](../defender/advanced-hunting-overview.md)
- [Azure Event Hubs belgeleri](/azure/event-hubs/)
- [Azure Depolama Hesabı belgeleri](/azure/storage/common/storage-account-overview)
