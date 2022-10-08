---
title: Gelişmiş tehdit avcılığı şemasında DeviceProcessEvents tablosu
description: Gelişmiş tehdit avcılığı şemasının DeviceProcessEventstable'ında işlem oluşturma veya oluşturma olayları hakkında bilgi edinin
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, tablo, sütun, veri türü, processcreationevents, DeviceProcessEvents, işlem kimliği, komut satırı, DeviceProcessEvents
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
ms.openlocfilehash: b28fb5b05ae0bfdb34d8793e1e0f63814c4dd597
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68089509"
---
# <a name="deviceprocessevents"></a>DeviceProcessEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender
- Uç Nokta için Microsoft Defender



Gelişmiş `DeviceProcessEvents` [tehdit avcılığı](advanced-hunting-overview.md) şemasındaki tablo, işlem oluşturma ve ilgili olaylar hakkında bilgi içerir. Bu tablodan bilgi döndüren sorgular oluşturmak için bu başvuruyu kullanın.

>[!TIP]
> Bir tablo tarafından desteklenen olay türleri (`ActionType` değerler) hakkında ayrıntılı bilgi için Bulut için Defender'da bulunan yerleşik şema başvurusunu kullanın.

Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında bilgi için [gelişmiş avcılık başvurusuna bakın](advanced-hunting-schema-tables.md).

| Sütun adı | Veri türü | Açıklama |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Olayın kaydedilildiği tarih ve saat |
| `DeviceId` | `string` | Hizmetteki makine için benzersiz tanımlayıcı |
| `DeviceName` | `string` | Makinenin tam etki alanı adı (FQDN) |
| `ActionType` | `string` | Olayı tetikleyen etkinlik türü. Ayrıntılar için [bkz. portal içi şema başvurusu](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `FileName` | `string` | Kaydedilen eylemin uygulandığı dosyanın adı |
| `FolderPath` | `string` | Kaydedilen eylemin uygulandığı dosyayı içeren klasör |
| `SHA1` | `string` | Kaydedilen eylemin uygulandığı dosyanın SHA-1 |
| `SHA256` | `string` | Kaydedilen eylemin uygulandığı dosyanın SHA-256'sı. Bu alan genellikle doldurulmamaktadır; kullanılabilir olduğunda SHA1 sütununu kullanın. |
| `MD5` | `string` | Kaydedilen eylemin uygulandığı dosyanın MD5 karması |
| `FileSize` | `long` | Dosyanın bayt cinsinden boyutu |
| `ProcessVersionInfoCompanyName` | `string` | Yeni oluşturulan işlemin sürüm bilgilerinden şirket adı |
| `ProcessVersionInfoProductName` | `string` | Yeni oluşturulan işlemin sürüm bilgilerinden ürün adı |
| `ProcessVersionInfoProductVersion` | `string` | Yeni oluşturulan işlemin sürüm bilgilerinden ürün sürümü |
| `ProcessVersionInfoInternalFileName` | `string` | Yeni oluşturulan işlemin sürüm bilgilerinden iç dosya adı |
| `ProcessVersionInfoOriginalFileName` | `string` | Yeni oluşturulan işlemin sürüm bilgilerinden özgün dosya adı |
| `ProcessVersionInfoFileDescription` | `string` | Yeni oluşturulan işlemin sürüm bilgilerinden açıklama |
| `ProcessId` | `int` | Yeni oluşturulan işlemin İşlem Kimliği (PID) |
| `ProcessCommandLine` | `string` | Yeni işlemi oluşturmak için kullanılan komut satırı |
| `ProcessIntegrityLevel` | `string` | Yeni oluşturulan işlemin bütünlük düzeyi. Windows, belirli özelliklere göre işlemlere bütünlük düzeyleri atar( örneğin, indirilen bir internetten başlatılmışlarsa). Bu bütünlük düzeyleri kaynaklara yönelik izinleri etkiler |
| `ProcessTokenElevation` | `string` | Yeni oluşturulan işleme uygulanan belirteç yükseltme türünü gösterir. Olası değerler: TokenElevationTypeLimited (kısıtlı), TokenElevationTypeDefault (standart) ve TokenElevationTypeFull (yükseltilmiş) |
| `ProcessCreationTime` | `datetime` | İşlemin oluşturulduğu tarih ve saat |
| `AccountDomain` | `string` | Hesabın etki alanı |
| `AccountName` | `string` | Hesabın kullanıcı adı |
| `AccountSid` | `string` | Hesabın Güvenlik Tanımlayıcısı (SID) |
| `AccountUpn` | `string` | Hesabın kullanıcı asıl adı (UPN) |
| `AccountObjectId` | `string` | Azure AD'daki hesap için benzersiz tanımlayıcı |
| `LogonId` | `string` | Oturum açma oturumlarının tanımlayıcısı. Bu tanımlayıcı aynı makinede yalnızca yeniden başlatmalar arasında benzersizdir |
| `InitiatingProcessAccountDomain` | `string` | Olaydan sorumlu işlemi çalıştıran hesabın etki alanı |
| `InitiatingProcessAccountName` | `string` | Olaydan sorumlu işlemi çalıştıran hesabın kullanıcı adı |
| `InitiatingProcessAccountSid` | `string` | Olaydan sorumlu işlemi çalıştıran hesabın Güvenlik Tanımlayıcısı (SID) |
| `InitiatingProcessAccountUpn` | `string` | Olaydan sorumlu işlemi çalıştıran hesabın kullanıcı asıl adı (UPN) |
| `InitiatingProcessAccountObjectId` | `string` | Olaydan sorumlu işlemi çalıştıran kullanıcı hesabının nesne kimliğini Azure AD |
| `InitiatingProcessLogonId` | `string` | Olayı başlatan işlemin oturum açma oturumunun tanımlayıcısı. Bu tanımlayıcı aynı makinede yalnızca yeniden başlatmalar arasında benzersizdir. |
| `InitiatingProcessIntegrityLevel` | `string` | Olayı başlatan işlemin bütünlük düzeyi. Windows, bir internet indirmesinden başlatılmış olmaları gibi belirli özelliklere göre işlemlere bütünlük düzeyleri atar. Bu bütünlük düzeyleri kaynaklara yönelik izinleri etkiler |
| `InitiatingProcessTokenElevation` | `string` | Olayı başlatan işleme uygulanan Kullanıcı Access Control (UAC) ayrıcalık yükseltmesinin varlığını veya yokluğunu gösteren belirteç türü |
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
| `InitiatingProcessParentId` | `int` | Olaydan sorumlu işlemi oluşturan üst işlemin İşlem Kimliği (PID) |
| `InitiatingProcessParentFileName` | `string` | Olaydan sorumlu işlemi oluşturan üst işlemin adı |
| `InitiatingProcessParentCreationTime` | `datetime` | Olaydan sorumlu işlemin üst öğesinin başlatıldığı tarih ve saat |
| `InitiatingProcessSignerType` | `string` | Olayı başlatan işlemin dosya imzalayan türü (görüntü dosyası) |
| `InitiatingProcessSignatureStatus` | `string` | Olayı başlatan işlemin (görüntü dosyası) imza durumu hakkında bilgi |
| `ReportId` | `long` | Yinelenen sayacı temel alan olay tanımlayıcısı. Benzersiz olayları tanımlamak için bu sütunun DeviceName ve Timestamp sütunlarıyla birlikte kullanılması gerekir |
| `AppGuardContainerId` | `string` | tarayıcı etkinliğini yalıtmak için Application Guard tarafından kullanılan sanallaştırılmış kapsayıcının tanımlayıcısı |
| `AdditionalFields` | `string` | JSON dizi biçimindeki olay hakkında ek bilgi |


## <a name="related-topics"></a>İlgili konular
- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Paylaşılan sorguları kullanın](advanced-hunting-shared-queries.md)
- [Cihazlar, e-postalar, uygulamalar ve kimlikler arasında avlayın](advanced-hunting-query-emails-devices.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)
