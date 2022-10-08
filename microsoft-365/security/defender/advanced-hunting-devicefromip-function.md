---
title: Microsoft 365 Defender için gelişmiş avcılıkta DeviceFromIP() işlevi
description: Belirli bir IP adresi atanmış cihazları almak için DeviceFromIP() işlevini kullanmayı öğrenin
keywords: gelişmiş avcılık, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, cihaz, cihazfromIP, işlev, zenginleştirme
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
ms.openlocfilehash: 4d8c60e9323b7260ab73635753bea5a4ad5079ab
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68087244"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


`DeviceFromIP()` Belirli bir IP adresine belirli bir zamanda atanmış cihazların listesini hızlı bir şekilde elde etmek için [gelişmiş tehdit avcılığı](advanced-hunting-overview.md) sorgularınızda işlevini kullanın. 

Bu işlev aşağıdaki sütunları içeren bir tablo döndürür:

| Sütun | Veri türü | Açıklama |
|------------|-------------|-------------|
| `IP` | `string` | IP adresi  |
| `DeviceId` | `string` | Hizmetteki cihaz için benzersiz tanımlayıcı |


## <a name="syntax"></a>Sözdizimi

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a>Bağımsız değişken

Bu işlev sorgunun bir parçası olarak çağrılır.

- **x**— İlk parametre genellikle sorguda zaten bir sütundur. Bu durumda, kendisine atanmış cihazların listesini görmek istediğiniz IP adresi adlı `IP`sütundur. Yerel bir IP adresi olmalıdır. Dış IP adresleri desteklenmez.
- **y**—İkinci bir isteğe bağlı parametre, işlevine belirli bir zamandan en son atanan cihazları alma talimatını veren parametresidir `Timestamp`. Belirtilmezse, işlev kullanılabilir en son kayıtları döndürür.

## <a name="example"></a>Örnek


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a>Belirli IP adresleri atanmış en son cihazları alma

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a>İlgili konular
- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
