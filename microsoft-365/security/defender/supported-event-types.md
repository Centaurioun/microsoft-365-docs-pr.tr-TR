---
title: Olay Akışı API'sinde desteklenen Microsoft 365 Defender akış olayı türleri
description: Akış API'sinde hangi akış olay türlerinin (tablolar) desteklendiği hakkında bilgi edinin
keywords: ham veri dışarı aktarma, Akış API'si, API, Olay hub'ları, Azure depolama, depolama hesabı, Tehdit Avcılığı, ham veri paylaşımı
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: a8a95e7e7831696189d21037ed87fdd6fd82c722
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67678549"
---
# <a name="supported-microsoft-365-defender-streaming-event-types-in-event-streaming-api"></a>Olay akışı API Microsoft 365 Defender sinde olay akış türleri desteklenir

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


Olay Akışı API'si, daha fazla olay türünü destekleyecek şekilde sürekli genişletiliyor. Şu anda genel önizleme aşamasında olan veya henüz desteklenmeyen Hangi Avcılık tablolarının genel kullanıma sunulduğu hakkında bilgi edinin. 
**Yeni - Email olay türleri/tabloları artık GA'dır**

## <a name="hunting-tables-support-status-in-event-streaming-api"></a>Olay Akışı API'sinde tehdit avcılığı tabloları destek durumu

Aşağıdaki tablo yalnızca akış API'sinde desteklenen tabloların listesini içerir ve tüm AH şeması dahil değildir. API'nin tam listesi için bkz. [Şema tablolarını öğrenme](advanced-hunting-schema-tables.md#learn-the-schema-tables).

| Tablo adı | Durum<br>(Ticari) | Gcc | GCC Yüksek | Dod |
|----|----|----|----|----|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | Ga | Ga | Ga | Ga |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Ga | Ga | Ga | Ga |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** |Ga | Ga | Ga | Ga |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** |Ga | Ga | Ga | Ga |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Ga | Ga | Ga | Ga |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | Ga | Ga | Ga | Ga |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Ga | Ga | Ga | Ga |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Ga | Ga | Ga | Ga |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** |Ga | Ga | Ga | Ga |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Ga | Ga | Ga | Ga |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Ga | Ga | Ga | Ga |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Ga | Ga | Ga | Ga |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Ga |![Hayır](../defender-endpoint/images/svg/check-no.svg)|![Hayır](../defender-endpoint/images/svg/check-no.svg)|![Hayır](../defender-endpoint/images/svg/check-no.svg)|
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Ga |![Hayır](../defender-endpoint/images/svg/check-no.svg)|![Hayır](../defender-endpoint/images/svg/check-no.svg)|![Hayır](../defender-endpoint/images/svg/check-no.svg)|
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Ga |![Hayır](../defender-endpoint/images/svg/check-no.svg)|![Hayır](../defender-endpoint/images/svg/check-no.svg)|![Hayır](../defender-endpoint/images/svg/check-no.svg)|
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Ga |![Hayır](../defender-endpoint/images/svg/check-no.svg)|![Hayır](../defender-endpoint/images/svg/check-no.svg)|![Hayır](../defender-endpoint/images/svg/check-no.svg)|
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)**|Ga|![Hayır](../defender-endpoint/images/svg/check-no.svg)|![Hayır](../defender-endpoint/images/svg/check-no.svg)|![Hayır](../defender-endpoint/images/svg/check-no.svg)|
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)**|Ga|![Hayır](../defender-endpoint/images/svg/check-no.svg)|![Hayır](../defender-endpoint/images/svg/check-no.svg)|![Hayır](../defender-endpoint/images/svg/check-no.svg)|
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)**|Ga|![Hayır](../defender-endpoint/images/svg/check-no.svg)|![Hayır](../defender-endpoint/images/svg/check-no.svg)|![Hayır](../defender-endpoint/images/svg/check-no.svg)|
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)**|Ga|![Hayır](../defender-endpoint/images/svg/check-no.svg)|![Hayır](../defender-endpoint/images/svg/check-no.svg)|![Hayır](../defender-endpoint/images/svg/check-no.svg)|
