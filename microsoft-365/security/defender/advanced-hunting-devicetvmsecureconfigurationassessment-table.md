---
title: Gelişmiş tehdit avcılığı şemasında DeviceTvmSecureConfigurationAssessment tablosu
description: Gelişmiş tehdit avcılığı şemasının DeviceTvmSecureConfigurationAssessment tablosunda güvenlik değerlendirmesi olayları hakkında bilgi edinin. Bu olaylar cihaz bilgileri, güvenlik yapılandırma ayrıntıları, etki ve uyumluluk bilgileri sağlar.
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, tablo, sütun, veri türü, açıklama, tehdit & güvenlik açığı yönetimi, TVM, cihaz yönetimi, güvenlik yapılandırması, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: dc0e193167eb4cadf658a78de3a1fd497c76be5e
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479632"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender
- Uç Nokta için Microsoft Defender

Tablodaki `DeviceTvmSecureConfigurationAssessment` her satır, [Microsoft Defender Güvenlik Açığı Yönetimi](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) belirli bir güvenlik yapılandırması için bir değerlendirme olayı içerir. En son değerlendirme sonuçlarını denetlemek ve cihazların uyumlu olup olmadığını belirlemek için bu başvuruyu kullanın.

Bu tabloyu [DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) tablosuyla `ConfigurationId` birleştirerek yapılandırma değerlendirme sonuçlarında tablonun sütunundaki yapılandırmanın `ConfigurationDescription` `DeviceTvmSecureConfigurationAssessmentKB` metin açıklamasını görüntüleyebilirsiniz.

Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında bilgi için gelişmiş [avcılık başvurusuna](advanced-hunting-schema-tables.md) bakın.

| Sütun adı | Veri türü | Açıklama |
|-------------|-----------|-------------|
| `DeviceId` | `string` | Hizmetteki cihaz için benzersiz tanımlayıcı |
| `DeviceName` | `string` | Cihazın tam etki alanı adı (FQDN) |
| `OSPlatform` | `string` | Cihazda çalışan işletim sisteminin platformu. Windows 11, Windows 10 ve Windows 7 gibi aynı aile içindeki varyasyonlar da dahil olmak üzere belirli işletim sistemlerini gösterir.|
| `Timestamp` | `datetime` | Kaydın oluşturulduğu tarih ve saat |
| `ConfigurationId` | `string` | Belirli bir yapılandırma için benzersiz tanımlayıcı |
| `ConfigurationCategory` | `string` | Yapılandırmanın ait olduğu kategori veya gruplandırma: Uygulama, İşletim Sistemi, Ağ, Hesaplar, Güvenlik denetimleri |
| `ConfigurationSubcategory` | `string` | Yapılandırmanın ait olduğu alt kategori veya alt gruplama. Çoğu durumda, dize belirli özellikleri veya özellikleri açıklar. |
| `ConfigurationImpact` | `string` | Yapılandırmanın genel yapılandırma puanına etkisi derecelendirilmiştir (1-10) |
| `IsCompliant` | `boolean` | Yapılandırmanın veya ilkenin düzgün yapılandırılıp yapılandırılmadığını gösterir |
| `IsApplicable` | `boolean` | Yapılandırmanın veya ilkenin cihaza uygulanıp uygulanmayacağını gösterir |
| `Context` | `string` | Yapılandırma veya ilke hakkında ek bağlamsal bilgiler |
| `IsExpectedUserImpact` | `boolean` | Yapılandırma veya ilke uygulandığında kullanıcı etkisi olup olmayacağını gösterir |

Uyumlu olmayan virüsten koruma yapılandırmalarına sahip cihazlardaki bilgileri ve tablodaki ilgili yapılandırma meta verilerini döndürmek için bu örnek sorguyu `DeviceTvmSecureConfigurationAssessmentKB` deneyebilirsiniz:

```kusto
// Get information on devices with antivirus configurations issues
DeviceTvmSecureConfigurationAssessment
| where ConfigurationSubcategory == 'Antivirus' and IsApplicable == 1 and IsCompliant == 0
| join kind=leftouter (
    DeviceTvmSecureConfigurationAssessmentKB
    | project ConfigurationId, ConfigurationName, ConfigurationDescription, RiskDescription, Tags, ConfigurationImpact
) on ConfigurationId
| project DeviceName, OSPlatform, ConfigurationId, ConfigurationName, ConfigurationCategory, ConfigurationSubcategory, ConfigurationDescription, RiskDescription, ConfigurationImpact, Tags
```

## <a name="related-topics"></a>İlgili konular

- [Tehditleri proaktif olarak avlama](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Paylaşılan sorguları kullanın](advanced-hunting-shared-queries.md)
- [Cihazlar, e-postalar, uygulamalar ve kimlikler arasında avlayın](advanced-hunting-query-emails-devices.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)
- [Microsoft Defender Güvenlik Açığı Yönetimi genel bakış](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)