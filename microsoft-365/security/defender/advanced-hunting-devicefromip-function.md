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
ms.collection: m365-security-compliance
ms.topic: article
ms.openlocfilehash: 62df7a7c7bbf61c176d69b115f88bddae09fa04f
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479410"
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
