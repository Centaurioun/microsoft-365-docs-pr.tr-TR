---
title: Gelişmiş tehdit avcılığı şemasında AlertEvidence tablosu
description: Gelişmiş tehdit avcılığı şemasının AlertEvidence tablosunda uyarılarla ilişkili bilgiler hakkında bilgi edinin
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, tablo, sütun, veri türü, açıklama, AlertInfo, uyarı, varlıklar, kanıt, dosya, IP adresi, cihaz, makine, kullanıcı, hesap
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
ms.openlocfilehash: 731d72ff5e42b85a5ddc68ed58e8914e142cea9f
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68636990"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender

`AlertEvidence` [Gelişmiş tehdit avcılığı](advanced-hunting-overview.md) şemasındaki tablo, Uç Nokta, Office 365 için Microsoft Defender, Microsoft Defender for Cloud Apps ve için Microsoft Defender'dan gelen uyarılarla ilişkili çeşitli varlıklar (dosyalar, IP adresleri, URL'ler, kullanıcılar veya cihazlar) hakkında bilgi içerir Kimlik için Microsoft Defender. Bu tablodan bilgi döndüren sorgular oluşturmak için bu başvuruyu kullanın.

Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında bilgi için [gelişmiş avcılık başvurusuna bakın](advanced-hunting-schema-tables.md).

| Sütun adı | Veri türü | Açıklama |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Olayın kaydedilildiği tarih ve saat |
| `AlertId` | `string` | Uyarının benzersiz tanımlayıcısı |
| `ServiceSource` | `string` | Uyarı bilgilerini sağlayan ürün veya hizmet |
| `EntityType` | `string` | Dosya, işlem, cihaz veya kullanıcı gibi nesne türü |
| `EvidenceRole` | `string` | Varlığın bir uyarıya nasıl dahil olduğu, bunun etkilenip etkilenmediğini veya yalnızca ilgili olup olmadığını gösterir |
| `EvidenceDirection` | `string` | Varlığın bir ağ bağlantısının kaynağı mı yoksa hedefi mi olduğunu gösterir |
| `FileName` | `string` | Kaydedilen eylemin uygulandığı dosyanın adı |
| `FolderPath` | `string` | Kaydedilen eylemin uygulandığı dosyayı içeren klasör |
| `SHA1` | `string` | Kaydedilen eylemin uygulandığı dosyanın SHA-1 |
| `SHA256` | `string` | Kaydedilen eylemin uygulandığı dosyanın SHA-256'sı. Bu alan genellikle doldurulmamaktadır; kullanılabilir olduğunda SHA1 sütununu kullanın. |
| `FileSize` | `int` | Dosyanın bayt cinsinden boyutu |
| `ThreatFamily` | `string` | Şüpheli veya kötü amaçlı dosya veya işlemin altında sınıflandırıldığı kötü amaçlı yazılım ailesi |
| `RemoteIP` | `string` | Bağlanılmakta olan IP adresi |
| `RemoteUrl` | `string` | Bağlı olan URL veya tam etki alanı adı (FQDN) |
| `AccountName` | `string` | Hesabın kullanıcı adı |
| `AccountDomain` | `string` | Hesabın etki alanı |
| `AccountSid` | `string` | Hesabın Güvenlik Tanımlayıcısı (SID) |
| `AccountObjectId` | `string` | Azure Active Directory'de hesabın benzersiz tanımlayıcısı |
| `AccountUpn` | `string` | Hesabın kullanıcı asıl adı (UPN) |
| `DeviceId` | `string` | Hizmetteki cihaz için benzersiz tanımlayıcı |
| `DeviceName` | `string` | Makinenin tam etki alanı adı (FQDN) |
| `LocalIP` | `string` | İletişim sırasında kullanılan yerel cihaza atanan IP adresi |
| `NetworkMessageId` | `string` | Office 365 tarafından oluşturulan e-postanın benzersiz tanımlayıcısı |
| `EmailSubject` | `string` | E-postanın konusu |
| `ApplicationId` | `string` | Uygulama için benzersiz tanımlayıcı |
| `Application` | `string` | Kaydedilen eylemi gerçekleştiren uygulama |
| `ProcessCommandLine` | `string` | Yeni işlemi oluşturmak için kullanılan komut satırı |
| `AdditionalFields` | `string` | JSON dizi biçimindeki olay hakkında ek bilgi |
| `RegistryKey` |`string` | Kaydedilen eylemin uygulandığı kayıt defteri anahtarı |
| `RegistryValueName` |`string` | Kaydedilen eylemin uygulandığı kayıt defteri değerinin adı |
| `RegistryValueData` |`string` | Kaydedilen eylemin uygulandığı kayıt defteri değerinin verileri |

## <a name="related-topics"></a>İlgili konular
- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Paylaşılan sorguları kullanın](advanced-hunting-shared-queries.md)
- [Cihazlar, e-postalar, uygulamalar ve kimlikler arasında avlayın](advanced-hunting-query-emails-devices.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)
