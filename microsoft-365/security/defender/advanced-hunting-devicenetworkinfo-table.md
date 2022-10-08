---
title: Gelişmiş tehdit avcılığı şemasındaki DeviceNetworkInfo tablosu
description: Gelişmiş tehdit avcılığı şemasının DeviceNetworkInfo tablosunda ağ yapılandırma bilgileri hakkında bilgi edinin
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, tablo, sütun, veri türü, açıklama, machinenetworkinfo, DeviceNetworkInfo, cihaz, makine, mac, ip, bağdaştırıcı, dns, dhcp, ağ geçidi, tünel
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
ms.openlocfilehash: 91f6d12619a698028974616ffe6628ea9d4f3116
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68083021"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender
- Uç Nokta için Microsoft Defender



`DeviceNetworkInfo` [Gelişmiş tehdit avcılığı](advanced-hunting-overview.md) şemasındaki tablo, ağ bağdaştırıcıları, IP ve MAC adresleri ve bağlı ağlar veya etki alanları da dahil olmak üzere makinelerin ağ yapılandırması hakkında bilgi içerir. Bu tablodan bilgi döndüren sorgular oluşturmak için bu başvuruyu kullanın.

Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında bilgi için [gelişmiş avcılık başvurusuna bakın](advanced-hunting-schema-tables.md).

| Sütun adı | Veri türü | Açıklama |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Olayın kaydedilildiği tarih ve saat |
| `DeviceId` | `string` | Hizmetteki makine için benzersiz tanımlayıcı |
| `DeviceName` | `string` | Makinenin tam etki alanı adı (FQDN) |
| `NetworkAdapterName` | `string` | Ağ bağdaştırıcısının adı |
| `MacAddress` | `string` | Ağ bağdaştırıcısının MAC adresi |
| `NetworkAdapterType` | `string` | Ağ bağdaştırıcısı türü. Olası değerler için [bu numaralandırmaya](/dotnet/api/system.net.networkinformation.networkinterfacetype) bakın |
| `NetworkAdapterStatus` | `string` | Ağ bağdaştırıcısının çalışma durumu. Olası değerler için [bu numaralandırmaya](/dotnet/api/system.net.networkinformation.operationalstatus) bakın |
| `TunnelType` | `string` | Arabirim bu amaçla kullanılıyorsa tünel protokolü, örneğin 6'dan 4'e, Teredo, ISATAP, PPTP, SSTP ve SSH |
| `ConnectedNetworks` | `string` | Bağdaştırıcının bağlı olduğu ağlar. Her JSON dizisi ağ adını, kategorisini (genel, özel veya etki alanı), bir açıklamayı ve İnternet'e genel olarak bağlanıp bağlanmadığını belirten bir bayrak içerir |
| `DnsAddresses` | `string` | JSON dizi biçiminde DNS sunucusu adresleri |
| `IPv4Dhcp` | `string` | DHCP sunucusunun IPv4 adresi |
| `IPv6Dhcp` | `string` | DHCP sunucusunun IPv6 adresi |
| `DefaultGateways` | `string` | JSON dizi biçimindeki varsayılan ağ geçidi adresleri |
| `IPAddresses` | `string` | Bağdaştırıcıya atanan tüm IP adreslerini içeren JSON dizisi, ilgili alt ağ ön eki ve ip adresi alanıyla birlikte ortak, özel veya bağlantı yerel gibi |
| `ReportId` | `long` | Yinelenen sayacı temel alan olay tanımlayıcısı. Benzersiz olayları tanımlamak için bu sütunun DeviceName ve Timestamp sütunlarıyla birlikte kullanılması gerekir |

## <a name="related-topics"></a>İlgili konular
- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Paylaşılan sorguları kullanın](advanced-hunting-shared-queries.md)
- [Cihazlar, e-postalar, uygulamalar ve kimlikler arasında avlayın](advanced-hunting-query-emails-devices.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)