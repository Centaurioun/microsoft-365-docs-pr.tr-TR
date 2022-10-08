---
title: Stream Uç Nokta için Microsoft Defender olayı
description: Gelişmiş Tehdit Avcılığı olaylarını Event Hubs'a veya Azure depolama hesabına akışla aktaracak Uç Nokta için Microsoft Defender yapılandırmayı öğrenin
keywords: ham veri dışarı aktarma, akış API'si, API, Olay hub'ları, Azure depolama, depolama hesabı, Gelişmiş Tehdit Avcılığı, ham veri paylaşımı
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
- tier3
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: bee57e8abb60715fff5f3aca3f64e3c1e5f76b94
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68228042"
---
# <a name="raw-data-streaming-api"></a>Ham Veri Akışı API'si

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configuresiem-abovefoldlink)

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Event Hubs'a ve/veya Azure depolama hesabına Gelişmiş Tehdit Avcılığı olaylarını akışla aktarma

Uç Nokta için Microsoft Defender, [Event Hubs](/azure/event-hubs/) ve/veya [Azure depolama hesabına](/azure/storage/common/storage-account-overview) [Gelişmiş Tehdit Avcılığı](../defender/advanced-hunting-overview.md) aracılığıyla sağlanan akış olaylarını destekler.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4r4ga]

## <a name="in-this-section"></a>Bu bölümde

Konu|Açıklama
:---|:---
[Uç Nokta için Microsoft Defender olaylarını Azure Event Hubs akışla aktar](raw-data-export-event-hub.md)|Kiracınızda akış API'sini etkinleştirme hakkında bilgi edinin ve Uç Nokta için Defender'ı [Gelişmiş Avcılık'ı](advanced-hunting-overview.md) Event Hubs'a akışla aktaracak şekilde yapılandırın.
[Uç Nokta için Stream Defender olaylarını Azure depolama hesabınıza gönderme](raw-data-export-storage.md)|Kiracınızda akış API'sini etkinleştirme hakkında bilgi edinin ve Uç Nokta için Defender'ı [Gelişmiş Tehdit Avcılığı'nı](advanced-hunting-overview.md) Azure depolama hesabınıza akışla aktaracak şekilde yapılandırın.

## <a name="related-topics"></a>İlgili konular

- [Gelişmiş Avcılık'a Genel Bakış](advanced-hunting-overview.md)
- [Azure Event Hubs belgeleri](/azure/event-hubs/)
- [Azure Depolama Hesabı belgeleri](/azure/storage/common/storage-account-overview)