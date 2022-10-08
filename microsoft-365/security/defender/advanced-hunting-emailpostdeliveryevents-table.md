---
title: Gelişmiş tehdit avcılığı şemasında EmailPostDeliveryEvents tablosu
description: Gelişmiş tehdit avcılığı şemasının EmailPostDeliveryEvents tablosunda Microsoft 365 e-postalarında gerçekleştirilen teslim sonrası eylemler hakkında bilgi edinin
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, tablo, sütun, veri türü, açıklama, EmailPostDeliveryEvents, ağ ileti kimliği, gönderen, alıcı, ek kimliği, ek adı, kötü amaçlı yazılım kararı, kimlik avı kararı, ek sayısı, bağlantı sayısı, URL sayısı
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
ms.openlocfilehash: 6fc2e43b0e7be9534b9065420f017af678ea4d31
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68091377"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender
- Office 365 için Microsoft Defender

`EmailPostDeliveryEvents` [Gelişmiş tehdit avcılığı](advanced-hunting-overview.md) şemasındaki tablo, Microsoft 365 tarafından işlenen e-posta iletilerinde gerçekleştirilen teslim sonrası eylemler hakkında bilgi içerir. Bu tablodan bilgi döndüren sorgular oluşturmak için bu başvuruyu kullanın.

>[!TIP]
> Bir tablo tarafından desteklenen olay türleri (`ActionType` değerler) hakkında ayrıntılı bilgi için Bulut için Defender'da bulunan yerleşik şema başvurusunu kullanın.

Tek tek e-posta iletileri hakkında daha fazla bilgi edinmek için , [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md)ve tablolarını [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) da kullanabilirsiniz[`EmailEvents`](advanced-hunting-emailevents-table.md). Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında bilgi için [gelişmiş avcılık başvurusuna bakın](advanced-hunting-schema-tables.md).

> [!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

| Sütun adı | Veri türü | Açıklama |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Olayın kaydedilildiği tarih ve saat |
| `NetworkMessageId` | `string` | Microsoft 365 tarafından oluşturulan e-posta için benzersiz tanımlayıcı |
| `InternetMessageId` | `string` | Gönderen e-posta sistemi tarafından ayarlanan e-posta için genel kullanıma yönelik tanımlayıcı |
| `Action` | `string` | Varlık üzerinde gerçekleştirilen eylem |
| `ActionType` | `string` | Olayı tetikleyen etkinlik türü: El ile düzeltme, Kimlik Avı ZAP, Kötü Amaçlı Yazılım ZAP |
| `ActionTrigger` | `string` | Bir eylemin yönetici tarafından mı (el ile mi yoksa bekleyen otomatik eylemin onayıyla mı) yoksa ZAP veya Dinamik Teslim gibi özel bir mekanizma tarafından mı tetiklenip tetiklenmediğini gösterir |
| `ActionResult` | `string` | Eylemin sonucu |
| `RecipientEmailAddress` | `string` | Dağıtım listesi genişletildikten sonra alıcının adresini veya alıcının e-posta adresini Email |
| `DeliveryLocation` | `string` | E-postanın teslim edildiği konum: Gelen Kutusu/Klasör, Şirket İçi/Dış, Gereksiz, Karantina, Başarısız, Bırakılan, Silinen öğeler |
| `ReportId` | `long` | Yinelenen sayacı temel alan olay tanımlayıcısı. Benzersiz olayları tanımlamak için bu sütunun DeviceName ve Timestamp sütunlarıyla birlikte kullanılması gerekir. |
| `ThreatTypes` | `string` | E-posta filtreleme yığınından, e-postanın kötü amaçlı yazılım, kimlik avı veya diğer tehditler içerip içermediğine ilişkin karar |
| `DetectionMethods` | `string` | E-postada bulunan kötü amaçlı yazılımları, kimlik avı veya diğer tehditleri algılamak için kullanılan yöntemler |

## <a name="supported-event-types"></a>Desteklenen olay türleri
Bu tablo olayları aşağıdaki `ActionType` değerlerle yakalar:

- **El ile düzeltme** – Yönetici, kullanıcı posta kutusuna teslim edildikten sonra bir e-posta iletisi üzerinde el ile işlem yaptı. Bu, [Tehdit Gezgini](../office-365-security/threat-explorer.md) aracılığıyla el ile gerçekleştirilen eylemleri veya [otomatik araştırma ve yanıt (AIR) eylemlerinin](m365d-autoir-actions.md) onaylarını içerir.
- **Kimlik avı ZAP** – Teslimden sonra kimlik avı [e-postası üzerinde sıfır saatlik otomatik temizleme (ZAP)](../office-365-security/zero-hour-auto-purge.md) işlemi yaptı.
- **Kötü amaçlı yazılım ZAP** – Teslimden sonra kötü amaçlı yazılım içeren bir e-posta iletisinde sıfır saatlik otomatik temizleme (ZAP) işlemi gerçekleştirilir.

## <a name="related-topics"></a>İlgili konular
- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Paylaşılan sorguları kullanın](advanced-hunting-shared-queries.md)
- [Cihazlar, e-postalar, uygulamalar ve kimlikler arasında avlayın](advanced-hunting-query-emails-devices.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)
