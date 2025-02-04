---
title: Araştırma kaynak türü
description: araştırma varlığını Uç Nokta için Microsoft Defender.
keywords: api'ler, graf api'leri, desteklenen API'ler, alma, uyarılar, araştırmalar
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
ms.topic: conceptual
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: faaafb94f1b3278900d7f184ba462638deac375c
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68636442"
---
# <a name="investigation-resource-type"></a>Araştırma kaynak türü

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

Uç Nokta için Defender'da Otomatik Araştırma varlığını temsil eder.

Daha fazla bilgi için bkz. [Otomatik araştırmalara genel bakış](automated-investigations.md).

## <a name="methods"></a>Yöntemler

Yöntem|Dönüş Türü|Açıklama
:---|:---|:---
[Araştırma Listele](get-investigation-collection.md)|Araştırma koleksiyonu|Araştırma koleksiyonunu alma
[Tek Bir Araştırma Alma](get-investigation-object.md)|Araştırma varlığı|Tek bir Araştırma varlığını alır.
[Araştırmayı Başlat](initiate-autoir-investigation.md)|Araştırma varlığı|Cihazda Araştırma'ya başlar.

## <a name="properties"></a>Özellikler

Özellik|Tür|Açıklama
:---|:---|:---
Kimlik|Dize|Araştırma varlığının kimliği. 
Starttime|DateTime Nullable|Araştırmanın oluşturulduğu tarih ve saat.
Endtime|DateTime Nullable|Araştırmanın tamamlandığı tarih ve saat.
cancelledBy|Dize|Bu araştırmayı iptal eden kullanıcının/uygulamanın kimliği.
Durum|Enum|Araştırmanın geçerli durumu. Olası değerler şunlardır: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.
statusDetails|Dize|Araştırmanın durumu hakkında ek bilgiler.
machineId|Dize|Araştırmanın yürütüldiği cihazın kimliği.
computerDnsName|Dize|Araştırmanın yürütüldiği cihazın adı.
triggeringAlertId|Dize|Araştırmayı tetikleyen uyarının kimliği.

## <a name="json-representation"></a>Json gösterimi

```json
{
    "id": "63004",
    "startTime": "2020-01-06T13:05:15Z",
    "endTime": null,
    "state": "Running",
    "cancelledBy": null,
    "statusDetails": null,
    "machineId": "e828a0624ed33f919db541065190d2f75e50a071",
    "computerDnsName": "desktop-test123",
    "triggeringAlertId": "da637139127150012465_1011995739"
}
```
