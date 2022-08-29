---
title: Gelişmiş tehdit avcılığı şemasında DeviceTvmSoftwareVulnerabilities tablosu
description: Cihazlarda bulunan yazılım güvenlik açıkları ve gelişmiş tehdit avcılığı şemasının DeviceTvmSoftwareVulnerabilities tablosundaki her güvenlik açığını gideren kullanılabilir güvenlik güncelleştirmelerinin listesi hakkında bilgi edinin.
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, tablo, sütun, veri türü, açıklama, tehdit & güvenlik açığı yönetimi, TVM, cihaz yönetimi, yazılım, envanter, güvenlik açıkları, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 6e0d28b0b4f421ba4f5b41bfbfa049787c7cce0a
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2022
ms.locfileid: "67329277"
---
# <a name="devicetvmsoftwarevulnerabilities"></a>DeviceTvmSoftwareVulnerabilities

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender
- Uç Nokta için Microsoft Defender

>[!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanan ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

`DeviceTvmSoftwareVulnerabilities` Gelişmiş tehdit avcılığı şemasındaki tablo, yüklü yazılım ürünlerindeki güvenlik açıklarının [Microsoft Defender Güvenlik Açığı Yönetimi](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) listesini içerir. Bu tabloda işletim sistemi bilgileri, CVE kimlikleri ve güvenlik açığı önem derecesi bilgileri de yer alır. Bu tabloyu, örneğin yazılımlarında ciddi güvenlik açıkları olan cihazlarla ilgili olayları aramak için kullanabilirsiniz. Tablodan bilgi döndüren sorgular oluşturmak için bu başvuruyu kullanın.

>[!NOTE]
> `DeviceTvmSoftwareInventory` ve `DeviceTvmSoftwareVulnerabilities` tabloları tablonun yerini aldı`DeviceTvmSoftwareInventoryVulnerabilities`. İlk iki tablo birlikte, güvenlik açığı yönetim etkinliklerinizi bilgilendirmek veya savunmasız cihazları avlamak için kullanabileceğiniz daha fazla sütun içerir.

Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında bilgi için gelişmiş [avcılık başvurusuna](advanced-hunting-schema-tables.md) bakın.

| Sütun adı | Veri türü | Açıklama |
|-------------|-----------|-------------|
| `DeviceId` | `string` | Hizmetteki makine için benzersiz tanımlayıcı |
| `DeviceName` | `string` | Makinenin tam etki alanı adı (FQDN) |
| `OSPlatform` | `string` | Makinede çalışan işletim sisteminin platformu. Windows 11, Windows 10 ve Windows 7 gibi aynı aile içindeki varyasyonlar da dahil olmak üzere belirli işletim sistemlerini gösterir. |
| `OSVersion` | `string` | Makinede çalışan işletim sisteminin sürümü |
| `OSArchitecture` | `string` | Makinede çalışan işletim sisteminin mimarisi |
| `SoftwareVendor` | `string` | Yazılım yayımcısının adı |
| `SoftwareName` | `string` | Yazılım ürününün adı |
| `SoftwareVersion` | `string` | Yazılım ürününün sürüm numarası |
| `CveId` | `string` | Ortak Güvenlik Açıkları ve Etkilenmeler (CVE) sistemi altında güvenlik açığına atanan benzersiz tanımlayıcı |
| `VulnerabilitySeverityLevel` | `string` | CVSS puanına ve tehdit manzarasından etkilenen dinamik faktörlere bağlı olarak güvenlik açığına atanan önem düzeyi |
| `RecommendedSecurityUpdate` | `string` | Yazılım yayımcısı tarafından güvenlik açığını gidermek için sağlanan güvenlik güncelleştirmesinin adı veya açıklaması |
| `RecommendedSecurityUpdateId` | `string` | İlgili kılavuz veya bilgi bankası (KB) makaleleri için geçerli güvenlik güncelleştirmelerinin veya tanımlayıcısının tanımlayıcısı |



## <a name="related-topics"></a>İlgili konular

- [Tehditleri proaktif olarak avlama](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Paylaşılan sorguları kullanın](advanced-hunting-shared-queries.md)
- [Cihazlar, e-postalar, uygulamalar ve kimlikler arasında avlayın](advanced-hunting-query-emails-devices.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)
- [Microsoft Defender Güvenlik Açığı Yönetimi genel bakış](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)