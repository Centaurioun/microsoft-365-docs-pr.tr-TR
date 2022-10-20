---
title: Go hunt ile bir varlık hakkında ilgili bilgileri alma
description: Gelişmiş avcılığı kullanarak bir varlık veya olay hakkında ilgili bilgileri hızla sorgulamak için go hunt aracını kullanmayı öğrenin.
keywords: gelişmiş avcılık, olay, özet, varlık, go hunt, ilgili olaylar, tehdit avcılığı, siber tehdit avcılığı, arama, sorgu, telemetri, Microsoft 365, Microsoft 365 Defender
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
- tier1
ms.topic: conceptual
ms.openlocfilehash: 4dfa6afcaeee3cadb8dd683ca973654e9398c1dd
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68622760"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>Go hunt ile varlık veya olay bilgilerini hızla avla

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender
- Uç Nokta için Microsoft Defender

*Go hunt* eylemiyle, güçlü sorgu tabanlı [gelişmiş tehdit avcılığı](advanced-hunting-overview.md) özelliklerini kullanarak olayları ve çeşitli varlık türlerini hızla araştırabilirsiniz. Bu eylem, seçilen olay veya varlıkla ilgili bilgileri bulmak için otomatik olarak gelişmiş bir tehdit avcılığı sorgusu çalıştırır.

*Go hunt* eylemi Bulut için Defender'ın çeşitli bölümlerinde kullanılabilir. Bu eylem, olay veya varlık ayrıntıları görüntülendiğinde görüntülenebilir. Örneğin, aşağıdaki bölümlerden *go hunt* seçeneğini kullanabilirsiniz:

- [Olay sayfasında](investigate-incidents.md#summary) kullanıcılar, cihazlar ve bir olayla ilişkili diğer birçok varlık hakkındaki ayrıntıları gözden geçirebilirsiniz. Bir varlığı seçerken ek bilgiler ve bu varlık üzerinde gerçekleştirebileceğin çeşitli eylemler elde edersiniz. Aşağıdaki örnekte, posta kutusuyla ilgili ayrıntıları ve posta kutusu hakkında daha fazla bilgi için avlanma seçeneğini gösteren bir posta kutusu seçilmiştir.

    :::image type="content" source="../../media/go-hunt-1-incident.png" alt-text="Microsoft 365 Defender portalında Git av seçeneğini içeren Posta Kutuları sayfası" lightbox="../../media/go-hunt-1-incident.png":::

- Olay sayfasında, **Kanıt** sekmesinin altındaki varlıkların listesine de erişebilirsiniz. Bu varlıklardan birinin seçilmesi, söz konusu varlık hakkında hızlı bir şekilde bilgi aramak için bir seçenek sağlar.

    :::image type="content" source="../../media/go-hunt-2-entity.png" alt-text="Microsoft 365 Defender portalındaki Olay sayfasında bir kanıt parçası için Git av seçeneği" lightbox="../../media/go-hunt-2-entity.png":::


- Bir cihazın zaman çizelgesini görüntülerken, bu olayla ilgili ek bilgileri görüntülemek için zaman çizelgesinde bir olay seçebilirsiniz. Bir etkinlik seçildikten sonra, gelişmiş avcılıkta diğer ilgili olayları avlama seçeneğine sahip olursunuz.

    :::image type="content" source="../../media/go-hunt-3-event.png" alt-text="Microsoft 365 Defender portalındaki Zaman Çizelgeleri sekmesindeki bir olayın sayfasındaki ilgili olayları avla seçeneği" lightbox="../../media/go-hunt-3-event.png":::

Bir varlığı mı yoksa olayı mı seçtiğinize bağlı olarak, **İlgili olayları** **avla** veya Avla'yı seçtiğinizde farklı sorgular geçer.

## <a name="query-for-entity-information"></a>Varlık bilgilerini sorgulama
Bir kullanıcı, cihaz veya başka bir varlık türü hakkında bilgi sorgulamak için *go hunt* kullanabilirsiniz; sorgu, bilgileri döndürmek için ilgili tüm şema tablolarını ilgili varlıkla ilgili olaylar için denetler. Sonuçları yönetilebilir durumda tutmak için sorgu şu şekildedir:
- kapsamı, varlığı içeren son 30 gün içindeki en erken etkinlikle aynı zaman aralığına göre belirlenmiştir
- olayla ilişkilendirildi.

Bir cihaz için go hunt sorgusu örneği aşağıda verilmiştir:

```kusto
let selectedTimestamp = datetime(2020-06-02T02:06:47.1167157Z);
let deviceName = "fv-az770.example.com";
let deviceId = "device-guid";
search in (DeviceLogonEvents, DeviceProcessEvents, DeviceNetworkEvents, DeviceFileEvents, DeviceRegistryEvents, DeviceImageLoadEvents, DeviceEvents, DeviceImageLoadEvents, IdentityLogonEvents, IdentityQueryEvents)
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
and DeviceName == deviceName
// or RemoteDeviceName == deviceName
// or DeviceId == deviceId
| take 100
```
### <a name="supported-entity-types"></a>Desteklenen varlık türleri
Bu varlık türlerinden herhangi birini seçtikten sonra *go hunt* seçeneğini kullanabilirsiniz:

- Dosyalar
- Emails
- kümeleri Email
- Posta kutu -ları
- Kullanıcılar
- Aygıtları
- IP adresleri
- Url 'leri

## <a name="query-for-event-information"></a>Olay bilgilerini sorgulama
Zaman çizelgesi olayı hakkındaki bilgileri sorgulamak için *go hunt* kullanırken, sorgu seçilen olayın zamanı boyunca diğer olaylar için tüm ilgili şema tablolarını denetler. Örneğin, aşağıdaki sorgu aynı cihazda aynı zaman diliminde gerçekleşen çeşitli şema tablolarındaki olayları listeler:

```kusto
// List relevant events 30 minutes before and after selected LogonAttempted event
let selectedEventTimestamp = datetime(2020-06-04T01:29:09.2496688Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "079ecf9c5798d249128817619606c1c47369eb3e"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a>Sorguyu ayarlama
[Sorgu dili](advanced-hunting-query-language.md) hakkında bilgi sahibi olarak sorguyu tercihinize göre ayarlayabilirsiniz. Örneğin, zaman penceresinin boyutunu belirleyen bu satırı ayarlayabilirsiniz:

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

Daha ilgili sonuçlar elde etmek için sorguyu değiştirmenin yanı sıra şunları da yapabilirsiniz:
- [Sonuçları grafik olarak görüntüleme](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [Özel algılama kuralı oluşturma](custom-detection-rules.md)

>[!NOTE]
>Bu makaledeki bazı tablolar Uç Nokta için Microsoft Defender'de kullanılamayabilir. Daha fazla veri kaynağı kullanarak tehditleri avlamak için [Microsoft 365 Defender açın](m365d-enable.md). Gelişmiş avcılık sorgularını Uç Nokta için Microsoft Defender'den geçirme bölümünde yer alan adımları izleyerek [gelişmiş avcılık iş akışlarınızı Uç Nokta için Microsoft Defender'den Microsoft 365 Defender](advanced-hunting-migrate-from-mde.md) taşıyabilirsiniz.

## <a name="related-topics"></a>İlgili konular
- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Sorgu sonuçlarıyla çalışın](advanced-hunting-query-results.md)
- [Özel algılama kuralları](custom-detection-rules.md)
