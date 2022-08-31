---
title: Gelişmiş tehdit avcılığı şemasında DeviceNetworkEvents tablosu
description: Gelişmiş tehdit avcılığı şemasının DeviceNetworkEvents tablosundan sorgulayabileceğiniz ağ bağlantısı olayları hakkında bilgi edinin
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, tablo, sütun, veri türü, devicenetworkevents, NetworkCommunicationEvents, ağ bağlantısı, uzak ip, yerel ip
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
ms.openlocfilehash: cfd6fbd52aad3837ec6b330706215a4f9af745eb
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67472798"
---
# <a name="devicenetworkevents"></a>DeviceNetworkEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender
- Uç Nokta için Microsoft Defender



`DeviceNetworkEvents` [Gelişmiş tehdit avcılığı](advanced-hunting-overview.md) şemasındaki tablo, ağ bağlantıları ve ilgili olaylar hakkında bilgi içerir. Bu tablodan bilgi döndüren sorgular oluşturmak için bu başvuruyu kullanın.

>[!TIP]
> Bir tablo tarafından desteklenen olay türleri (`ActionType` değerler) hakkında ayrıntılı bilgi için Bulut için Defender'da bulunan yerleşik şema başvurusunu kullanın.

Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında bilgi için [gelişmiş avcılık başvurusuna bakın](advanced-hunting-schema-tables.md).

| Sütun adı | Veri türü | Açıklama |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Olayın kaydedilildiği tarih ve saat |
| `DeviceId` | `string` | Hizmetteki makine için benzersiz tanımlayıcı |
| `DeviceName` | `string` | Makinenin tam etki alanı adı (FQDN) |
| `ActionType` | `string` | Olayı tetikleyen etkinlik türü. Ayrıntılar için [bkz. portal içi şema başvurusu](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `RemoteIP` | `string` | Bağlanılmakta olan IP adresi |
| `RemotePort` | `int` | Bağlı olan uzak cihazda TCP bağlantı noktası |
| `RemoteUrl` | `string` | Bağlı olan URL veya tam etki alanı adı (FQDN) |
| `LocalIP` | `string` | İletişim sırasında kullanılan yerel makineye atanan IP adresi |
| `LocalPort` | `int` | İletişim sırasında kullanılan yerel makinede TCP bağlantı noktası |
| `Protocol` | `string` | İletişim sırasında kullanılan protokol |
| `LocalIPType` | `string` | Genel, Özel, Ayrılmış, Geri Döngü, Teredo, FourToSixMapping ve Broadcast gibi IP adresi türü |
| `RemoteIPType` | `string` | Genel, Özel, Ayrılmış, Geri Döngü, Teredo, FourToSixMapping ve Broadcast gibi IP adresi türü |
| `InitiatingProcessSHA1` | `string` | Olayı başlatan işlemin SHA-1 'i (görüntü dosyası) |
| `InitiatingProcessSHA256` | `string` | Olayı başlatan işlemin SHA-256'sı (görüntü dosyası). Bu alan genellikle doldurulmamaktadır; kullanılabilir olduğunda SHA1 sütununu kullanın. |
| `InitiatingProcessMD5` | `string` | Olayı başlatan işlemin MD5 karması (görüntü dosyası) |
| `InitiatingProcessFileName` | `string` | Olayı başlatan işlemin adı |
| `InitiatingProcessFileSize` | `long` | Olaydan sorumlu işlemi çalıştıran dosyanın boyutu |
| `InitiatingProcessVersionInfoCompanyName` | `string` | Olayın sorumlu olduğu işlemin sürüm bilgilerinden (görüntü dosyası) şirket adı |
| `InitiatingProcessVersionInfoProductName` | `string` | Olaydan sorumlu işlemin sürüm bilgilerinden (görüntü dosyası) ürün adı |
| `InitiatingProcessVersionInfoProductVersion` | `string` | Olaydan sorumlu işlemin sürüm bilgilerinden (görüntü dosyası) ürün sürümü |
| `InitiatingProcessVersionInfoInternalFileName` | `string` | Olayın sorumlu olduğu işlemin sürüm bilgilerinden (görüntü dosyası) iç dosya adı |
| `InitiatingProcessVersionInfoOriginalFileName` | `string` | Olaydan sorumlu işlemin sürüm bilgilerinden (görüntü dosyası) özgün dosya adı |
| `InitiatingProcessVersionInfoFileDescription` | `string` | Olaydan sorumlu işlemin sürüm bilgilerinden açıklama (görüntü dosyası) |
| `InitiatingProcessId` | `int` | Olayı başlatan işlemin İşlem Kimliği (PID) |
| `InitiatingProcessCommandLine` | `string` | Olayı başlatan işlemi çalıştırmak için kullanılan komut satırı |
| `InitiatingProcessCreationTime` | `datetime` | Olayı başlatan işlemin başlatıldığı tarih ve saat |
| `InitiatingProcessFolderPath` | `string` | Olayı başlatan işlemi (görüntü dosyası) içeren klasör |
| `InitiatingProcessParentFileName` | `string` | Olaydan sorumlu işlemi oluşturan üst işlemin adı |
| `InitiatingProcessParentId` | `int` | Olaydan sorumlu işlemi oluşturan üst işlemin İşlem Kimliği (PID) |
| `InitiatingProcessParentCreationTime` | `datetime` | Olaydan sorumlu işlemin üst öğesinin başlatıldığı tarih ve saat |
| `InitiatingProcessAccountDomain` | `string` | Olaydan sorumlu işlemi çalıştıran hesabın etki alanı |
| `InitiatingProcessAccountName` | `string` | Olaydan sorumlu işlemi çalıştıran hesabın kullanıcı adı |
| `InitiatingProcessAccountSid` | `string` | Olaydan sorumlu işlemi çalıştıran hesabın Güvenlik Tanımlayıcısı (SID) |
| `InitiatingProcessAccountUpn` | `string` | Olaydan sorumlu işlemi çalıştıran hesabın kullanıcı asıl adı (UPN) |
| `InitiatingProcessAccountObjectId` | `string` | Olaydan sorumlu işlemi çalıştıran kullanıcı hesabının nesne kimliğini Azure AD |
| `InitiatingProcessIntegrityLevel` | `string` | Olayı başlatan işlemin bütünlük düzeyi. Windows, bir internet indirmesinden başlatılmış olmaları gibi belirli özelliklere göre işlemlere bütünlük düzeyleri atar. Bu bütünlük düzeyleri kaynaklara yönelik izinleri etkiler |
| `InitiatingProcessTokenElevation` | `string` | Olayı başlatan işleme uygulanan Kullanıcı Access Control (UAC) ayrıcalık yükseltmesinin varlığını veya yokluğunu gösteren belirteç türü |
| `ReportId` | `long` | Yinelenen sayacı temel alan olay tanımlayıcısı. Benzersiz olayları tanımlamak için bu sütunun DeviceName ve Timestamp sütunlarıyla birlikte kullanılması gerekir |
| `AppGuardContainerId` | `string` | Application Guard tarafından tarayıcı etkinliğini yalıtmak için kullanılan sanallaştırılmış kapsayıcının tanımlayıcısı |
| `AdditionalFields` | `string` | JSON dizi biçimindeki olay hakkında ek bilgi |

## <a name="related-topics"></a>İlgili konular
- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Paylaşılan sorguları kullanın](advanced-hunting-shared-queries.md)
- [Cihazlar, e-postalar, uygulamalar ve kimlikler arasında avlayın](advanced-hunting-query-emails-devices.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)
