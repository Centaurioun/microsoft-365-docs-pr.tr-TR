---
title: Gelişmiş tehdit avcılığı şemasında IdentityInfo tablosu
description: Gelişmiş tehdit avcılığı şemasının IdentityInfo tablosunda kullanıcı hesabı bilgileri hakkında bilgi edinin
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, tablo, sütun, veri türü, açıklama, AccountInfo, IdentityInfo, hesap
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
ms.openlocfilehash: aab05f07855749824a1bb40ef4eb8426a35d610b
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68084913"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender

`IdentityInfo` [Gelişmiş tehdit avcılığı](advanced-hunting-overview.md) şemasındaki tablo, Azure Active Directory dahil olmak üzere çeşitli hizmetlerden elde edilen kullanıcı hesapları hakkında bilgi içerir. Bu tablodan bilgi döndüren sorgular oluşturmak için bu başvuruyu kullanın.

>[!NOTE]
>Bu tablo' dan `AccountInfo`yeniden adlandırıldı. Yeniden adlandırmalar sırasında portala kaydedilen tüm sorgular otomatik olarak güncelleştirilir. Başka bir yere kaydettiğiniz sorguları denetleyin.

Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında bilgi için [gelişmiş avcılık başvurusuna bakın](advanced-hunting-schema-tables.md).

| Sütun adı | Veri türü | Açıklama |
|-------------|-----------|-------------|
| `AccountObjectId` | `string` | Azure AD'daki hesap için benzersiz tanımlayıcı |
| `AccountUpn` | `string` | Hesabın kullanıcı asıl adı (UPN) |
| `OnPremSid` | `string` | Hesabın şirket içi güvenlik tanımlayıcısı (SID) |
| `CloudSid` | `string` | Hesabın bulut güvenlik tanımlayıcısı |
| `GivenName` | `string` | Hesap kullanıcısının adı veya adı |
| `Surname` | `string` | Hesap kullanıcısının soyadı, aile adı veya soyadı |
| `AccountDisplayName` | `string` | Adres defterinde görüntülenen hesap kullanıcısının adı. Genellikle belirli bir adın veya adın, ikinci bir başlatmanın ve soyadının veya soyadının birleşimidir. |
| `Department` | `string` | Hesap kullanıcısının ait olduğu bölümün adı |
| `JobTitle` | `string` | Hesap kullanıcısının iş unvanı |
| `AccountName` | `string` | Hesabın kullanıcı adı |
| `AccountDomain` | `string` | Hesabın etki alanı |
| `EmailAddress` | `string` | Hesabın SMTP adresi |
| `SipProxyAddress` | `string` | Hesabın IP üzerinden ses (VOIP) oturum başlatma protokolü (SIP) adresi |
| `City` | `string` | Hesap kullanıcısının bulunduğu şehir |
| `Country` | `string` | Hesap kullanıcısının bulunduğu ülke/bölge |
| `IsAccountEnabled` | `boolean` | Hesabın etkin olup olmadığını gösterir |

## <a name="related-topics"></a>İlgili konular
- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Paylaşılan sorguları kullanın](advanced-hunting-shared-queries.md)
- [Cihazlar, e-postalar, uygulamalar ve kimlikler arasında avlayın](advanced-hunting-query-emails-devices.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)
