---
title: Microsoft 365 Defender için gelişmiş avcılıkta SeenBy() işlevi
description: Hangi eklenen cihazların belirli bir cihazı keşfettiğine bakmak için SeenBy() işlevini kullanmayı öğrenin
keywords: gelişmiş avcılık, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgulama, telemetri, şema başvurusu, Kusto, SeenBy, cihaz bulma, işlev, zenginleştirme
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
ms.openlocfilehash: c44288276431d5a479f47a46289dfaad8089448f
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67477197"
---
# <a name="seenby"></a>SeenBy()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender

İşlev `SeenBy()` , cihaz bulma özelliğini kullanan belirli bir cihazı gören eklenen cihazların listesini görmek için çağrılır.

Bu işlev aşağıdaki sütuna sahip bir tablo döndürür:

| Sütun | Veri türü | Açıklama |
|------------|---------------|-------------|
| `DeviceId` | `string` | Hizmetteki cihaz için benzersiz tanımlayıcı |


## <a name="syntax"></a>Sözdizimi

```kusto
invoke SeenBy(x)
```

- burada **x** , ilgilendiğin cihaz kimliğidir

>[!TIP]
> Zenginleştirme işlevleri yalnızca kullanılabilir olduğunda ek bilgileri gösterir. Bilgilerin kullanılabilirliği çeşitlidir ve birçok faktöre bağlıdır. Sorgularınızda veya özel algılamalar oluştururken SeenBy() kullanırken bunu dikkate aldığınızdan emin olun. En iyi sonuçları elde için, DeviceInfo tablosuyla SeenBy() işlevini kullanmanızı öneririz.

### <a name="example-obtain-list-of-onboarded-devices-that-have-seen-a-device"></a>Örnek: Cihaz gören eklenen cihazların listesini alma

```kusto
DeviceInfo 
| where OnboardingStatus <> "Onboarded" 
| limit 100 | invoke SeenBy()
```

## <a name="related-topics"></a>İlgili konular
- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Daha fazla sorgu örneği edinin](advanced-hunting-shared-queries.md)
