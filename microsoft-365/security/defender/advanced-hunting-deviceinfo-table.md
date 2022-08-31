---
title: Gelişmiş tehdit avcılığı şemasındaki DeviceInfo tablosu
description: Gelişmiş tehdit avcılığı şemasının DeviceInfo tablosunda işletim sistemi, bilgisayar adı ve diğer makine bilgileri hakkında bilgi edinin
keywords: gelişmiş avcılık, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, tablo, sütun, veri türü, açıklama, machineinfo, DeviceInfo, cihaz, makine, işletim sistemi, platform, kullanıcılar
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
ms.openlocfilehash: 1808e0fa69f1ea683986b534a88b93e9e4a53af0
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482658"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender
- Uç Nokta için Microsoft Defender

`DeviceInfo` [Gelişmiş tehdit avcılığı](advanced-hunting-overview.md) şemasındaki tablo işletim sistemi sürümü, etkin kullanıcılar ve bilgisayar adı gibi kuruluştaki cihazlar hakkında bilgi içerir. Bu tablodan bilgi döndüren sorgular oluşturmak için bu başvuruyu kullanın.

Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında bilgi için [gelişmiş avcılık başvurusuna bakın](advanced-hunting-schema-tables.md).

| Sütun adı | Veri türü | Açıklama |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Olayın kaydedilildiği tarih ve saat |
| `DeviceId` | `string` | Hizmetteki makine için benzersiz tanımlayıcı |
| `DeviceName` | `string` | Makinenin tam etki alanı adı (FQDN) |
| `ClientVersion` | `string` | Makinede çalışan uç nokta aracısının veya algılayıcının sürümü |
| `PublicIP` | `string` | Uç Nokta için Microsoft Defender hizmetine bağlanmak için eklenen makine tarafından kullanılan genel IP adresi. Bu, makinenin IP adresi, NAT cihazı veya ara sunucu olabilir |
| `OSArchitecture` | `string` | Makinede çalışan işletim sisteminin mimarisi |
| `OSPlatform` | `string` | Makinede çalışan işletim sisteminin platformu. Bu, Windows 11, Windows 10 ve Windows 7 gibi aynı aile içindeki varyasyonlar da dahil olmak üzere belirli işletim sistemlerini gösterir. |
| `OSBuild` | `string` | Makinede çalışan işletim sisteminin derleme sürümü |
| `IsAzureADJoined` | `boolean` | Makinenin Azure Active Directory'ye katılıp katılmadığını gösteren Boole göstergesi |
| `AadDeviceId` | `string` | Azure AD'da cihaz için benzersiz tanımlayıcı |
| `LoggedOnUsers` | `string` | Olay sırasında JSON dizi biçiminde makinede oturum açan tüm kullanıcıların listesi |
| `RegistryDeviceTag` | `string` | Kayıt defteri aracılığıyla eklenen makine etiketi |
| `OSVersion` | `string` | Makinede çalışan işletim sisteminin sürümü |
| `MachineGroup` | `string` | Makinenin makine grubu. Bu grup, makineye erişimi belirlemek için rol tabanlı erişim denetimi tarafından kullanılır |
| `ReportId` | `long` | Yinelenen sayacı temel alan olay tanımlayıcısı. Benzersiz olayları tanımlamak için bu sütunun DeviceName ve Timestamp sütunlarıyla birlikte kullanılması gerekir |
| `OnboardingStatus` | `string` | Cihazın şu anda eklenip eklenmediğini veya Uç Nokta için Microsoft Defender ya da cihazın desteklenip desteklenmediğini gösterir |
|`AdditionalFields` | `string` | JSON dizi biçimindeki olay hakkında ek bilgi |
|`DeviceCategory` | `string` | Aşağıdaki kategoriler altında belirli cihaz türlerini gruplandıran daha geniş bir sınıflandırma: Uç Nokta, Ağ cihazı, IoT, Bilinmiyor |
|`DeviceType` | `string` | Ağ cihazı, iş istasyonu, sunucu, mobil, oyun konsolu veya yazıcı gibi amaca ve işlevselliğe dayalı cihaz türü |
|`DeviceSubType` | `string` | Mobil cihaz gibi belirli cihaz türleri için ek değiştirici tablet veya akıllı telefon olabilir; yalnızca cihaz bulma bu öznitelik hakkında yeterli bilgi bulursa kullanılabilir |
|`Model` | `string` | Satıcıdan veya üreticiden gelen ürünün model adı veya numarası, yalnızca cihaz keşfi bu öznitelik hakkında yeterli bilgi bulursa kullanılabilir |
|`Vendor` | `string` | Ürün satıcısının veya üreticinin adı; yalnızca cihaz keşfi bu öznitelik hakkında yeterli bilgi bulursa kullanılabilir |
|`OSDistribution` | `string` | Linux platformları için Ubuntu veya RedHat gibi işletim sistemi platformunun dağıtımı |
|`OSVersionInfo` | `string` | İşletim sistemi sürümü hakkında popüler ad, kod adı veya sürüm numarası gibi ek bilgiler |
|`MergedDeviceIds` | `string` | Aynı cihaza atanmış önceki cihaz kimlikleri |
|`MergedToDeviceId` | `string` | Bir cihaza atanan en son cihaz kimliği |

Tablo, `DeviceInfo` düzenli raporlar veya bir cihazdan gelen sinyaller olan sinyalleri temel alan cihaz bilgilerini sağlar. Cihaz, her on beş dakikada bir gibi `LoggedOnUsers`sık değişen öznitelikleri içeren kısmi bir sinyal gönderir. Günde bir kez, cihazın özniteliklerini içeren tam sinyal gönderilir.

Bir cihazın en son durumunu almak için aşağıdaki örnek sorguyu kullanabilirsiniz:

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a>İlgili konular
- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Paylaşılan sorguları kullanın](advanced-hunting-shared-queries.md)
- [Cihazlar, e-postalar, uygulamalar ve kimlikler arasında avlayın](advanced-hunting-query-emails-devices.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)
