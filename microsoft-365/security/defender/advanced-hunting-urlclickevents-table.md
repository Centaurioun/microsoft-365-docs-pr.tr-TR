---
title: Gelişmiş tehdit avcılığı şemasındaki UrlClickEvents tablosu
description: Gelişmiş tehdit avcılığı şemasındaki UrlClickEvents tablosunu kullanarak kimlik avı kampanyalarını ve şüpheli tıklamaları nasıl avlayacağınızı öğrenin.
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, tablo, sütun, veri türü, açıklama, UrlClickEvents, SafeLinks, kimlik avı, kötü amaçlı yazılım, kötü amaçlı tıklamalar, Outlook, ekipler, e-posta, Office365
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
ms.openlocfilehash: e3e0f5e25535a685f62c6b0e7471b5731cdf8287
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68049000"
---
# <a name="urlclickevents"></a>UrlClickEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender
- Office 365 için Microsoft Defender


`UrlClickEvents` Gelişmiş tehdit avcılığı şemasındaki tablo, desteklenen masaüstü, mobil ve web uygulamalarında e-posta iletileri, Microsoft Teams ve Office 365 uygulamalarından [gelen Güvenli Bağlantılar](../office-365-security/safe-links.md) tıklamaları hakkında bilgi içerir. 

> [!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında bilgi için gelişmiş [avcılık başvurusuna](advanced-hunting-schema-tables.md) bakın.

| Sütun adı | Veri türü | Açıklama |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Kullanıcının bağlantıya tıkladığında tarih ve saat |
| `Url` | `string` | Kullanıcı tarafından tıklanan tam URL |
| `ActionType` | `string` | Tıklamaya güvenli bağlantılar tarafından izin verilip verilmeyeceğini veya engellenip engellenmediğini veya bir kiracı ilkesi nedeniyle engellenip engellenmediğini gösterir; örneğin, Kiracı İzin Ver Bloğu listesinden|
| `AccountUpn` | `string` | Bağlantıya tıklanan hesabın Kullanıcı Asıl Adı|
| `Workload` | `string` | Kullanıcının bağlantıya tıkladığı ve değerlerin Email, Office ve Teams olduğu uygulama|
| `NetworkMessageId` | `string` | Microsoft 365 tarafından oluşturulan tıklanan bağlantıyı içeren e-postanın benzersiz tanımlayıcısı|
| `IPAddress` | `string` | Kullanıcının bağlantıya tıkladığı cihazın genel IP adresi|
| `ThreatTypes` | `string` | Url'nin kötü amaçlı yazılıma mı, kimlik avına mı yoksa diğer tehditlere mi yol açtığını belirten tıklama sırasında karar verme|
| `DetectionMethods` | `string` | Tıklama sırasında tehdidi tanımlamak için kullanılan algılama teknolojisi|
| `IsClickedThrough` | `bool` | Kullanıcının özgün URL'ye tıklayıp tıklayamadığını veya buna izin verilmediğini gösterir|
| `UrlChain` | `string` | Yeniden yönlendirme içeren senaryolar için, yeniden yönlendirme zincirinde bulunan URL'leri içerir|
| `ReportId` | `string` | Bu, tıklama olayının benzersiz tanımlayıcısıdır. Tıklama senaryoları için rapor kimliğinin aynı değere sahip olacağını ve bu nedenle bir tıklama olayını ilişkilendirmek için kullanılması gerektiğini unutmayın.|

Kullanıcının devam etmesine izin verilen bağlantıların `UrlClickEvents` listesini döndürmek için tabloyu kullanan bu örnek sorguyu deneyebilirsiniz: 

```kusto
// Search for malicious links where user was allowed to proceed through
UrlClickEvents
| where ActionType == "ClickAllowed" or IsClickedThrough !="0"
| where ThreatTypes has "Phish"
| summarize by ReportId, IsClickedThrough, AccountUpn, NetworkMessageId, ThreatTypes, Timestamp
```

## <a name="related-topics"></a>İlgili konular

- [Tehditleri proaktif olarak avlama](advanced-hunting-overview.md)
- [Office 365 için Microsoft Defender'da Güvenli Bağlantılar](../office-365-security/safe-links.md)
- [Gelişmiş tehdit avcılığı sorgu sonuçları üzerinde eylem gerçekleştirme](advanced-hunting-take-action.md)