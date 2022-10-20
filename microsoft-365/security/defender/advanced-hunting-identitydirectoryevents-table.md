---
title: Gelişmiş tehdit avcılığı şemasında IdentityDirectoryEvents tablosu
description: Gelişmiş tehdit avcılığı şemasının IdentityDirectoryEvents tablosunda etki alanı denetleyicisi ve Active Directory olayları hakkında bilgi edinin
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, tablo, sütun, veri türü, açıklama, IdentityDirectoryEvents, etki alanı denetleyicisi, Active Directory, Kimlik için Microsoft Defender, kimlikler
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
ms.topic: conceptual
ms.openlocfilehash: 77541e34e1fbc868efd234bc7693a5012258e885
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68625401"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender

`IdentityDirectoryEvents` [Gelişmiş tehdit avcılığı](advanced-hunting-overview.md) şemasındaki tablo, Active Directory (AD) çalıştıran şirket içi etki alanı denetleyicisini içeren olayları içerir. Bu tablo parola değişiklikleri, parola süre sonu ve kullanıcı asıl adı (UPN) değişiklikleri gibi kimlikle ilgili çeşitli olayları yakalar. Ayrıca, görevlerin zamanlanması ve PowerShell etkinliği gibi etki alanı denetleyicisindeki sistem olaylarını yakalar. Bu tablodan bilgi döndüren sorgular oluşturmak için bu başvuruyu kullanın.

>[!TIP]
> Bir tablo tarafından desteklenen olay türleri (`ActionType` değerler) hakkında ayrıntılı bilgi için Bulut için Defender'da bulunan yerleşik şema başvurusunu kullanın.

Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında bilgi için [gelişmiş avcılık başvurusuna bakın](advanced-hunting-schema-tables.md).

| Sütun adı | Veri türü | Açıklama |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Olayın kaydedilildiği tarih ve saat |
| `ActionType` | `string` | Olayı tetikleyen etkinlik türü. Ayrıntılar için [bkz. portal içi şema başvurusu](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `Application` | `string` | Kaydedilen eylemi gerçekleştiren uygulama |
| `TargetAccountUpn` | `string` | Kaydedilen eylemin uygulandığı hesabın kullanıcı asıl adı (UPN) |
| `TargetAccountDisplayName` | `string` | Kaydedilen eylemin uygulandığı hesabın görünen adı |
| `TargetDeviceName` | `string` | Kaydedilen eylemin uygulandığı cihazın tam etki alanı adı (FQDN) |
| `DestinationDeviceName` | `string` | Kaydedilen eylemi işleyen sunucu uygulamasını çalıştıran cihazın adı |
| `DestinationIPAddress` | `string` | Kaydedilen eylemi işleyen sunucu uygulamasını çalıştıran cihazın IP adresi |
| `DestinationPort` | `string` | Etkinliğin hedef bağlantı noktası |
| `Protocol` | `string` | İletişim sırasında kullanılan protokol |
| `AccountName` | `string` | Hesabın kullanıcı adı |
| `AccountDomain` | `string` | Hesabın etki alanı |
| `AccountUpn` | `string` | Hesabın kullanıcı asıl adı (UPN) |
| `AccountSid` | `string` | Hesabın Güvenlik Tanımlayıcısı (SID) |
| `AccountObjectId` | `string` | Azure Active Directory'de hesabın benzersiz tanımlayıcısı |
| `AccountDisplayName` | `string` | Adres defterinde görüntülenen hesap kullanıcısının adı. Genellikle belirli bir adın veya adın, ikinci bir başlatmanın ve soyadının veya soyadının birleşimidir. |
| `DeviceName` | `string` | Cihazın tam etki alanı adı (FQDN) |
| `IPAddress` | `string` | İletişim sırasında cihaza atanan IP adresi |
| `Port` | `string` | İletişim sırasında kullanılan TCP bağlantı noktası |
| `Location` | `string` | Etkinlikle ilişkili şehir, ülke veya diğer coğrafi konum |
| `ISP` | `string` | IP adresiyle ilişkilendirilmiş İnternet servis sağlayıcısı |
| `ReportId` | `long` | Olayın benzersiz tanımlayıcısı |
| `AdditionalFields` | `string` | Varlık veya olay hakkında ek bilgi |

## <a name="related-topics"></a>İlgili konular
- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Paylaşılan sorguları kullanın](advanced-hunting-shared-queries.md)
- [Cihazlar, e-postalar, uygulamalar ve kimlikler arasında avlayın](advanced-hunting-query-emails-devices.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)
