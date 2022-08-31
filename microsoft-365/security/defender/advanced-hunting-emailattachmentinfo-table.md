---
title: Gelişmiş tehdit avcılığı şemasında EmailAttachmentInfo tablosu
description: Gelişmiş tehdit avcılığı şemasının EmailAttachmentInfo tablosunda e-posta eki bilgileri hakkında bilgi edinin
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, tablo, sütun, veri türü, açıklama, EmailAttachmentInfo, ağ iletisi kimliği, gönderen, alıcı, ek kimliği, ek adı, kötü amaçlı yazılım kararı
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
ms.openlocfilehash: e2c4ac28a463f2422c096fc4eea6cff8c3b2094d
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67483332"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- Microsoft 365 Defender
- Office 365 için Microsoft Defender

`EmailAttachmentInfo` [Gelişmiş tehdit avcılığı](advanced-hunting-overview.md) şemasındaki tablo, Office 365 için Microsoft Defender tarafından işlenen e-postalardaki ekler hakkında bilgi içerir. Bu tablodan bilgi döndüren sorgular oluşturmak için bu başvuruyu kullanın.

Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında bilgi için [gelişmiş avcılık başvurusuna bakın](advanced-hunting-schema-tables.md).

> [!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

| Sütun adı | Veri türü | Açıklama |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Olayın kaydedilildiği tarih ve saat |
| `NetworkMessageId` | `string` | Microsoft 365 tarafından oluşturulan e-posta için benzersiz tanımlayıcı |
| `SenderFromAddress` | `string` | KIMDEN üst bilgisindeki gönderen e-posta adresi, e-posta istemcilerindeki e-posta alıcıları tarafından görülebilir |
| `SenderDisplayName` | `string` | Adres defterinde görüntülenen gönderenin adı, genellikle verilen veya adın, ikinci bir adın ve soyadının veya soyadının birleşimidir |
| `SenderObjectId` | `string` | Azure AD'da gönderenin hesabının benzersiz tanımlayıcısı |
| `RecipientEmailAddress` | `string` | Dağıtım listesi genişletildikten sonra alıcının adresini veya alıcının e-posta adresini Email |
| `RecipientObjectId` | `string` | Azure AD'de e-posta alıcısı için benzersiz tanımlayıcı |
| `FileName` | `string` | Kaydedilen eylemin uygulandığı dosyanın adı |
| `FileType` | `string` | Dosya uzantısı türü |
| `SHA256` | `string` | Kaydedilen eylemin uygulandığı dosyanın SHA-256'sı. Bu alan genellikle doldurulmamaktadır; kullanılabilir olduğunda SHA1 sütununu kullanın. |
| `ThreatTypes` | `string` | E-posta filtreleme yığınından, e-postanın kötü amaçlı yazılım, kimlik avı veya diğer tehditler içerip içermediğine ilişkin karar |
| `ThreatNames` | `string` | Bulunan kötü amaçlı yazılım veya diğer tehditler için algılama adı |
| `DetectionMethods` | `string` | E-postada bulunan kötü amaçlı yazılımları, kimlik avı veya diğer tehditleri algılamak için kullanılan yöntemler |
| `ReportId` | `long` | Yinelenen sayacı temel alan olay tanımlayıcısı. Benzersiz olayları tanımlamak için bu sütunun DeviceName ve Timestamp sütunlarıyla birlikte kullanılması gerekir. |
| `FileSize` | `string` | Dosyanın bayt cinsinden boyutu |

## <a name="related-topics"></a>İlgili konular

- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Paylaşılan sorguları kullanın](advanced-hunting-shared-queries.md)
- [Cihazlar, e-postalar, uygulamalar ve kimlikler arasında avlayın](advanced-hunting-query-emails-devices.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)
