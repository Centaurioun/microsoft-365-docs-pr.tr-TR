---
title: Gelişmiş tehdit avcılığı şemasında DeviceTvmSoftwareVulnerabilitiesKB tablosu
description: Gelişmiş tehdit avcılığı şemasının DeviceTvmSoftwareVulnerabilitiesKB tablosunda Microsoft Defender Güvenlik Açığı Yönetimi tarafından izlenen yazılım güvenlik açıkları hakkında bilgi edinin.
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema, başvuru, kusto, tablo, sütun, veri türü, açıklama, tehdit & güvenlik açığı yönetimi, TVM, cihaz yönetimi, yazılım, envanter, güvenlik açıkları, CVE Kimliği, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: 221684faa9106de680393767654a1ca49fa425bd
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68622782"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a>DeviceTvmSoftwareVulnerabilitiesKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender
- Uç Nokta için Microsoft Defender



`DeviceTvmSoftwareVulnerabilitiesKB` Gelişmiş tehdit avcılığı şemasındaki tablo, cihazları [değerlendiren Microsoft Defender Güvenlik Açığı Yönetimi](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) güvenlik açıklarının listesini içerir. Tablodan bilgi döndüren sorgular oluşturmak için bu başvuruyu kullanın.

Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında bilgi için gelişmiş [avcılık başvurusuna](advanced-hunting-schema-tables.md) bakın.

| Sütun adı | Veri türü | Açıklama |
|-------------|-----------|-------------|
| `CveId` | `string` | Ortak Güvenlik Açıkları ve Etkilenmeler (CVE) sistemi altında güvenlik açığına atanan benzersiz tanımlayıcı |
| `CvssScore` | `string` | th Common Vulnerability Scoring System (CVSS) altında güvenlik açığına atanan önem derecesi puanı |
| `IsExploitAvailable` | `boolean` | Güvenlik açığı için açık kodun genel kullanıma açık olup olmadığını gösterir |
| `VulnerabilitySeverityLevel` | `string` | CVSS puanına ve tehdit manzarasından etkilenen dinamik faktörlere bağlı olarak güvenlik açığına atanan önem düzeyi |
| `LastModifiedTime` | `datetime` | Öğenin veya ilgili meta verilerin son değiştirildiği tarih ve saat |
| `PublishedDate` | `datetime` | Güvenlik açığının herkese açıklandığı tarih |
| `VulnerabilityDescription` | `string` | Güvenlik açığı ve ilişkili risklerin açıklaması |
| `AffectedSoftware` | `string` | Güvenlik açığından etkilenen tüm yazılım ürünlerinin listesi |

## <a name="related-topics"></a>İlgili konular

- [Tehditleri proaktif olarak avlama](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Paylaşılan sorguları kullanın](advanced-hunting-shared-queries.md)
- [Cihazlar, e-postalar, uygulamalar ve kimlikler arasında avlayın](advanced-hunting-query-emails-devices.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)
- [Microsoft Defender Güvenlik Açığı Yönetimi genel bakış](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)