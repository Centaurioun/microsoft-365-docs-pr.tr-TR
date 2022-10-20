---
title: Gelişmiş tehdit avcılığı şemasındaki DeviceFileEvents tablosu
description: Gelişmiş tehdit avcılığı şemasının DeviceFileEvents tablosunda dosyayla ilgili olaylar hakkında bilgi edinin
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, tablo, sütun, veri türü, açıklama, dosya oluşturmaevents, DeviceFileEvents, dosyalar, yol, karma, sha1, sha256, md5
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
ms.openlocfilehash: 3b056054f9e24b3b1a5520ec8acb6da750bbbb67
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68646033"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender
- Uç Nokta için Microsoft Defender

Gelişmiş `DeviceFileEvents` [tehdit avcılığı](advanced-hunting-overview.md) şemasındaki tablo dosya oluşturma, değiştirme ve diğer dosya sistemi olayları hakkında bilgi içerir. Bu tablodan bilgi döndüren sorgular oluşturmak için bu başvuruyu kullanın.

>[!TIP]
> Bir tablo tarafından desteklenen olay türleri (`ActionType` değerler) hakkında ayrıntılı bilgi için Bulut için Defender'da bulunan yerleşik şema başvurusunu kullanın.

Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında bilgi için [gelişmiş avcılık başvurusuna bakın](advanced-hunting-schema-tables.md).

| Sütun adı | Veri türü | Açıklama |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Olayın kaydedilildiği tarih ve saat |
| `DeviceId` | `string` | Hizmetteki makine için benzersiz tanımlayıcı |
| `DeviceName` | `string` | Makinenin tam etki alanı adı (FQDN) |
| `ActionType` | `string` | Olayı tetikleyen etkinlik türü. Ayrıntılar için [bkz. portal içi şema başvurusu](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `FileName` | `string`| Kaydedilen eylemin uygulandığı dosyanın adı |
| `FolderPath` | `string` | Kaydedilen eylemin uygulandığı dosyayı içeren klasör |
| `SHA1` | `string` | Kaydedilen eylemin uygulandığı dosyanın SHA-1 |
| `SHA256` | `string` | Kaydedilen eylemin uygulandığı dosyanın SHA-256'sı. Bu alan genellikle doldurulmamaktadır; kullanılabilir olduğunda SHA1 sütununu kullanın. |
| `MD5` | `string` | Kaydedilen eylemin uygulandığı dosyanın MD5 karması |
| `FileOriginUrl` | `string` | Dosyanın indirildiği URL |
| `FileOriginReferrerUrl` | `string` | İndirilen dosyaya bağlanan web sayfasının URL'si |
| `FileOriginIP` | `string` | Dosyanın indirildiği IP adresi |
| `PreviousFolderPath` | `string` | Kaydedilen eylem uygulanmadan önce dosyayı içeren özgün klasör |
| `PreviousFileName` | `string` | Eylemin sonucu olarak yeniden adlandırılan dosyanın özgün adı |
| `FileSize` | `long` | Dosyanın bayt cinsinden boyutu |
| `InitiatingProcessAccountDomain` | `string` | Olaydan sorumlu işlemi çalıştıran hesabın etki alanı |
| `InitiatingProcessAccountName` | Dize | Olaydan sorumlu işlemi çalıştıran hesabın kullanıcı adı |
| `InitiatingProcessAccountSid` | `string` | Olaydan sorumlu işlemi çalıştıran hesabın Güvenlik Tanımlayıcısı (SID) |
| `InitiatingProcessAccountUpn` | `string` | Olaydan sorumlu işlemi çalıştıran hesabın kullanıcı asıl adı (UPN) |
| `InitiatingProcessAccountObjectId` | `string` | Olaydan sorumlu işlemi çalıştıran kullanıcı hesabının nesne kimliğini Azure AD |
| `InitiatingProcessMD5` | `string` | Olayı başlatan işlemin MD5 karması (görüntü dosyası) |
| `InitiatingProcessSHA1` | `string` | Olayı başlatan işlemin SHA-1 'i (görüntü dosyası) |
| `InitiatingProcessSHA256` | `string` | Olayı başlatan işlemin SHA-256'sı (görüntü dosyası). Bu alan genellikle doldurulmamaktadır; kullanılabilir olduğunda SHA1 sütununu kullanın. |
| `InitiatingProcessFolderPath` | `string` | Olayı başlatan işlemi (görüntü dosyası) içeren klasör |
| `InitiatingProcessFileName` | `string` | Olayı başlatan işlemin adı |
| `InitiatingProcessFileSize` | `long` | Olayı başlatan işlemin boyutu (görüntü dosyası) |
| `InitiatingProcessVersionInfoCompanyName` | `string` | Olayın sorumlu olduğu işlemin sürüm bilgilerinden (görüntü dosyası) şirket adı |
| `InitiatingProcessVersionInfoProductName` | `string` | Olaydan sorumlu işlemin sürüm bilgilerinden (görüntü dosyası) ürün adı |
|` InitiatingProcessVersionInfoProductVersion` | `string` | Olaydan sorumlu işlemin sürüm bilgilerinden (görüntü dosyası) ürün sürümü |
|` InitiatingProcessVersionInfoInternalFileName` | `string` | Olayın sorumlu olduğu işlemin sürüm bilgilerinden (görüntü dosyası) iç dosya adı |
| `InitiatingProcessVersionInfoOriginalFileName` | `string` | Olaydan sorumlu işlemin sürüm bilgilerinden (görüntü dosyası) özgün dosya adı |
| `InitiatingProcessVersionInfoFileDescription` | `string` | Olaydan sorumlu işlemin sürüm bilgilerinden açıklama (görüntü dosyası) |
| `InitiatingProcessId` | `int` | Olayı başlatan işlemin İşlem Kimliği (PID) |
| `InitiatingProcessCommandLine` | `string` | Olayı başlatan işlemi çalıştırmak için kullanılan komut satırı |
| `InitiatingProcessCreationTime` | `datetime` | Olayı başlatan işlemin başlatıldığı tarih ve saat |
| `InitiatingProcessIntegrityLevel` | `string` | Olayı başlatan işlemin bütünlük düzeyi. Windows, bir internet indirmesinden başlatılmış olmaları gibi belirli özelliklere göre işlemlere bütünlük düzeyleri atar. Bu bütünlük düzeyleri kaynaklara yönelik izinleri etkiler |
| `InitiatingProcessTokenElevation` | `string` | Olayı başlatan işleme uygulanan Kullanıcı Access Control (UAC) ayrıcalık yükseltmesinin varlığını veya yokluğunu gösteren belirteç türü |
| `InitiatingProcessParentId` | `int` | Olaydan sorumlu işlemi oluşturan üst işlemin İşlem Kimliği (PID) |
| `InitiatingProcessParentFileName` | `string` | Olaydan sorumlu işlemi oluşturan üst işlemin adı |
| `InitiatingProcessParentCreationTime` | `datetime` | Olaydan sorumlu işlemin üst öğesinin başlatıldığı tarih ve saat |
| `RequestProtocol` | `string` | Varsa, etkinliği başlatmak için kullanılan ağ protokolü: Bilinmiyor, Yerel, SMB veya NFS |
| `RequestSourceIP` | `string` | Etkinliği başlatan uzak cihazın IPv4 veya IPv6 adresi |
| `RequestSourcePort` | `string` | Etkinliği başlatan uzak cihazda kaynak bağlantı noktası |
| `RequestAccountName` | `string` | Etkinliği uzaktan başlatmak için kullanılan hesabın kullanıcı adı |
| `RequestAccountDomain` | `string` | Etkinliği uzaktan başlatmak için kullanılan hesabın etki alanı |
| `RequestAccountSid` | `string` | Etkinliği uzaktan başlatmak için kullanılan hesabın Güvenlik Tanımlayıcısı (SID) |
| `ShareName` | `string` | Dosyayı içeren paylaşılan klasörün adı |
| `InitiatingProcessFileSize` | `long` | Olaydan sorumlu işlemi çalıştıran dosyanın boyutu |
| `SensitivityLabel` | `string` | Bir e-postaya, dosyaya veya diğer içeriğe uygulanan etiket, bu içeriği bilgi koruması için sınıflandırmak için |
| `SensitivitySubLabel` | `string` | E-postaya, dosyaya veya diğer içeriğe uygulanan alt etiket, bunu bilgi koruması için sınıflandırmak için; duyarlılık alt etiketleri duyarlılık etiketleri altında gruplandırılır ancak bağımsız olarak işlenir |
| `IsAzureInfoProtectionApplied` | `boolean` | Dosyanın Azure Information Protection tarafından şifrelenip şifrelenmediğini gösterir |
| `ReportId` | `long` | Yinelenen sayacı temel alan olay tanımlayıcısı. Benzersiz olayları tanımlamak için bu sütunun DeviceName ve Timestamp sütunlarıyla birlikte kullanılması gerekir. |
| `AppGuardContainerId` | `string` | tarayıcı etkinliğini yalıtmak için Application Guard tarafından kullanılan sanallaştırılmış kapsayıcının tanımlayıcısı |
| `AdditionalFields` | `string` | Varlık veya olay hakkında ek bilgi |
>[!NOTE]
> Dosya karması bilgileri her zaman kullanılabilir olduğunda gösterilir. Ancak SHA1, SHA256 veya MD5'in hesaplanamamasının birkaç olası nedeni vardır. Örneğin, dosya uzak depolama alanında, başka bir işlem tarafından kilitlenmiş, sıkıştırılmış veya sanal olarak işaretlenmiş olabilir. Bu senaryolarda, dosya karması bilgileri boş görünür.

## <a name="related-topics"></a>İlgili konular
- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Paylaşılan sorguları kullanın](advanced-hunting-shared-queries.md)
- [Cihazlar, e-postalar, uygulamalar ve kimlikler arasında avlayın](advanced-hunting-query-emails-devices.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)
