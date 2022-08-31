---
title: Gelişmiş tehdit avcılığı şemasında IdentityLogonEvents tablosu
description: Gelişmiş tehdit avcılığı şemasının IdentityLogonEvents tablosunda Active Directory tarafından kaydedilen kimlik doğrulama olayları hakkında bilgi edinin
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, tablo, sütun, veri türü, açıklama, IdentityLogonEvents, Azure AD, Active Directory, Kimlik için Microsoft Defender, kimlikler
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
ms.openlocfilehash: 177710ef709d6c9d3f40882a370620f908671114
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67481448"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender

`IdentityLogonEvents` [Gelişmiş tehdit avcılığı](advanced-hunting-overview.md) şemasındaki tablo, Kimlik için Microsoft Defender tarafından yakalanan şirket içi Active Directory aracılığıyla yapılan kimlik doğrulama etkinlikleri ve Microsoft çevrimiçi hizmetler ile ilgili kimlik doğrulama etkinlikleri hakkında bilgi içerir Microsoft Defender for Cloud Apps tarafından yakalanır. Bu tablodan bilgi döndüren sorgular oluşturmak için bu başvuruyu kullanın.

>[!TIP]
> Bir tablo tarafından desteklenen olay türleri (`ActionType` değerler) hakkında ayrıntılı bilgi için Bulut için Defender'da bulunan yerleşik şema başvurusunu kullanın.

>[!NOTE]
>Bu tablo, Cloud Apps için Defender tarafından izlenen Azure Active Directory (Azure AD) oturum açma etkinliklerini, özellikle ActiveSync ve diğer eski protokolleri kullanan etkileşimli oturum açma ve kimlik doğrulama etkinliklerini kapsar. Bu tabloda bulunmayan etkileşimli olmayan oturum açma işlemleri Azure AD denetim günlüğünde görüntülenebilir. [Cloud Apps için Defender'ı Microsoft 365'e bağlama hakkında daha fazla bilgi edinin](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında bilgi için [gelişmiş avcılık başvurusuna bakın](advanced-hunting-schema-tables.md).

| Sütun adı | Veri türü | Açıklama |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Olayın kaydedilildiği tarih ve saat |
| `ActionType` | `string` | Olayı tetikleyen etkinlik türü. Ayrıntılar için [bkz. portal içi şema başvurusu](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `Application` | `string` | Kaydedilen eylemi gerçekleştiren uygulama |
| `LogonType` | `string` | Özellikle oturum açma oturumunun türü:<br><br> - **Etkileşimli** - Kullanıcı yerel klavyeyi ve ekranı kullanarak makineyle fiziksel olarak etkileşim kurar<br><br> - **Uzaktan etkileşimli (RDP) oturum açmalar** - Kullanıcı Uzak Masaüstü, Terminal Hizmetleri, Uzaktan Yardım veya diğer RDP istemcilerini kullanarak makineyle uzaktan etkileşim kurar<br><br> - **Ağ** - Makineye PsExec kullanılarak erişildiğinde veya makinedeki yazıcılar ve paylaşılan klasörler gibi paylaşılan kaynaklara erişildiğinde başlatılan oturum<br><br> - **Batch** - Zamanlanmış görevler tarafından başlatılan oturum<br><br> - **Hizmet** - Hizmetler başlatılırken başlatılan oturum |
| `Protocol` | `string` | Kullanılan ağ protokolü |
| `FailureReason` | `string` | Kaydedilen eylemin neden başarısız olduğunu açıklayan bilgiler |
| `AccountName` | `string` | Hesabın kullanıcı adı |
| `AccountDomain` | `string` | Hesabın etki alanı |
| `AccountUpn` | `string` | Hesabın kullanıcı asıl adı (UPN) |
| `AccountSid` | `string` | Hesabın Güvenlik Tanımlayıcısı (SID) |
| `AccountObjectId` | `string` | Azure AD'daki hesap için benzersiz tanımlayıcı |
| `AccountDisplayName` | `string` | Adres defterinde görüntülenen hesap kullanıcısının adı. Genellikle belirli bir adın veya adın, ikinci bir başlatmanın ve soyadının veya soyadının birleşimidir. |
| `DeviceName` | `string` | Cihazın tam etki alanı adı (FQDN) |
| `DeviceType` | `string` | Cihaz türü |
| `OSPlatform` | `string` | Makinede çalışan işletim sisteminin platformu. Bu, Windows 11, Windows 10 ve Windows 7 gibi aynı aile içindeki varyasyonlar da dahil olmak üzere belirli işletim sistemlerini gösterir. |
| `IPAddress` | `string` | Uç noktaya atanan ve ilgili ağ iletişimleri sırasında kullanılan IP adresi |
| `Port` | `string` | İletişim sırasında kullanılan TCP bağlantı noktası |
| `DestinationDeviceName` | `string` | Kaydedilen eylemi işleyen sunucu uygulamasını çalıştıran cihazın adı |
| `DestinationIPAddress` | `string` | Kaydedilen eylemi işleyen sunucu uygulamasını çalıştıran cihazın IP adresi |
| `DestinationPort` | `string` | İlgili ağ iletişimlerinin hedef bağlantı noktası |
| `TargetDeviceName` | `string` | Kaydedilen eylemin uygulandığı cihazın tam etki alanı adı (FQDN) |
| `TargetAccountDisplayName` | `string` | Kaydedilen eylemin uygulandığı hesabın görünen adı |
| `Location` | `string` | Etkinlikle ilişkili şehir, ülke veya diğer coğrafi konum |
| `Isp` | `string` | Uç nokta IP adresiyle ilişkili İnternet servis sağlayıcısı (ISS) |
| `ReportId` | `long` | Olayın benzersiz tanımlayıcısı |
| `AdditionalFields` | `string` | Varlık veya olay hakkında ek bilgi |

## <a name="related-topics"></a>İlgili konular
- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Paylaşılan sorguları kullanın](advanced-hunting-shared-queries.md)
- [Cihazlar, e-postalar, uygulamalar ve kimlikler arasında avlayın](advanced-hunting-query-emails-devices.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)
