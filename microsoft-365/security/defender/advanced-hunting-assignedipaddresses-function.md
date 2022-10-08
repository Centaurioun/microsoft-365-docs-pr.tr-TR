---
title: Microsoft 365 Defender için gelişmiş avcılıkta AssignedIPAddresses() işlevi
description: Bir cihaza atanan en son IP adreslerini almak için AssignedIPAddresses() işlevini kullanmayı öğrenin
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, FileProfile, dosya profili, işlev, zenginleştirme
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
ms.topic: article
ms.openlocfilehash: b93bcd80021055820f093b3ba52941b8a944781d
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68073019"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender

`AssignedIPAddresses()` Bir cihaza atanmış olan en son IP adreslerini hızla elde etmek için [gelişmiş tehdit avcılığı](advanced-hunting-overview.md) sorgularınızda işlevini kullanın. Bir zaman damgası bağımsız değişkeni belirtirseniz, bu işlev belirtilen zamanda en son IP adreslerini alır. 

Bu işlev aşağıdaki sütunları içeren bir tablo döndürür:

| Sütun | Veri türü | Açıklama |
|------------|-------------|-------------|
| `Timestamp` | `datetime` | Cihazın IP adresi kullanılarak gözlemlendiği en son zaman |
| `IPAddress` | `string` | Cihaz tarafından kullanılan IP adresi |
| `IPType` | `string` | IP adresinin genel mi yoksa özel bir adres mi olduğunu gösterir |
| `NetworkAdapterType` | `int` | IP adresi atanmış olan cihaz tarafından kullanılan ağ bağdaştırıcısı türü. Olası değerler için [bu numaralandırmaya](/dotnet/api/system.net.networkinformation.networkinterfacetype) bakın |
| `ConnectedNetworks` | `int` | Atanan IP adresine sahip bağdaştırıcının bağlı olduğu ağlar. Her JSON dizisi ağ adını, kategorisini (genel, özel veya etki alanı), bir açıklamayı ve İnternet'e genel olarak bağlanıp bağlanmadığını belirten bir bayrak içerir |

## <a name="syntax"></a>Sözdizimi

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>Bağımsız değişken

- **x**—`DeviceId` veya `DeviceName` cihazı tanımlayan değer
- **y**—`Timestamp` (datetime) işlevine belirli bir zamandan en son atanan IP adreslerini almasını belirten değer. Belirtilmezse, işlev en son IP adreslerini döndürür.

## <a name="examples"></a>Örnekler

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>24 saat önce bir cihaz tarafından kullanılan IP adreslerinin listesini alma

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>Cihaz tarafından kullanılan IP adreslerini alma ve cihazla iletişim kuran cihazları bulma
Bu sorgu, `AssignedIPAddresses()` belirli bir tarihte`example-date` () veya öncesinde cihaz (`example-device-name`) için atanmış IP adreslerini almak için işlevini kullanır. Ardından, diğer cihazlar tarafından başlatılan cihaza bağlantıları bulmak için IP adreslerini kullanır. 

```kusto
let Date = datetime(example-date);
let DeviceName = "example-device-name";
// List IP addresses used on or before the specified date
AssignedIPAddresses(DeviceName, Date)
| project DeviceName, IPAddress, AssignedTime = Timestamp 
// Get all network events on devices with the assigned IP addresses as the destination addresses
| join kind=inner DeviceNetworkEvents on $left.IPAddress == $right.RemoteIP
// Get only network events around the time the IP address was assigned
| where Timestamp between ((AssignedTime - 1h) .. (AssignedTime + 1h))
```

## <a name="related-topics"></a>İlgili konular
- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)