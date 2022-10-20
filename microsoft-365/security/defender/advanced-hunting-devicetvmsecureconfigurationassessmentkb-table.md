---
title: Gelişmiş tehdit avcılığı şemasında DeviceTvmSecureConfigurationAssessmentKB tablosu
description: Gelişmiş tehdit avcılığı şemasının DeviceTvmSecureConfigurationAssessmentKB tablosunda Microsoft Defender Güvenlik Açığı Yönetimi tarafından değerlendirilen çeşitli güvenli yapılandırmalar hakkında bilgi edinin.
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, tablo, sütun, veri türü, açıklama, tehdit & güvenlik açığı yönetimi, TVM, cihaz yönetimi, güvenlik yapılandırması, MITRE ATT&CK çerçevesi, bilgi bankası, KB, DeviceTvmSecureConfigurationAssessmentKB, MDVM, Microsoft Defender Güvenlik Açığı Yönetimi
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
ms.openlocfilehash: fd43b62e3bbb9d05e51f1b45c3b34fca2860fe3b
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68645857"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender
- Uç Nokta için Microsoft Defender

`DeviceTvmSecureConfigurationAssessmentKB` Gelişmiş tehdit avcılığı şemasındaki tablo, [Microsoft Defender Güvenlik Açığı Yönetimi](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) tarafından denetlenen çeşitli güvenli yapılandırmalar hakkında bilgi içerir. Ayrıca risk bilgilerini, ilgili sektör karşılaştırmalarını ve ilgili MITRE ATT&CK tekniklerini ve taktiklerini içerir.

Bu tablo olayları veya kayıtları döndürmez. Döndürülen değerlendirmelerde güvenlik yapılandırmalarıyla ilgili metin bilgilerini görüntülemek için kullanarak `ConfigurationId` bu tabloyu [DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) tablosuna eklemenizi öneririz.

Örneğin, tabloyu sorguladığınızda `DeviceTvmSecureConfigurationAssessment` , değerlendirme sonuçlarında ortaya çıkacak güvenlik yapılandırmaları için öğesini görüntülemek `ConfigurationDescription` isteyebilirsiniz. Bu tabloyu kullanarak `ConfigurationId` ve projesine `DeviceTvmSecureConfigurationAssessment` `ConfigurationDescription`birleştirerek bu bilgileri görebilirsiniz.

Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında bilgi için gelişmiş [avcılık başvurusuna](advanced-hunting-schema-tables.md) bakın.

| Sütun adı | Veri türü | Açıklama |
|-------------|-----------|-------------|
| `ConfigurationId` | `string` | Belirli bir yapılandırma için benzersiz tanımlayıcı |
| `ConfigurationImpact` | `string` | Yapılandırmanın genel yapılandırma puanına etkisi derecelendirilmiştir (1-10) |
| `ConfigurationName` | `string` | Yapılandırmanın görünen adı |
| `ConfigurationDescription` | `string` | Yapılandırmanın açıklaması |
| `RiskDescription` | `string` | İlişkili riskin açıklaması |
| `ConfigurationCategory` | `string` | Yapılandırmanın ait olduğu kategori veya gruplandırma: Uygulama, İşletim Sistemi, Ağ, Hesaplar, Güvenlik denetimleri|
| `ConfigurationSubcategory` | `string` |Yapılandırmanın ait olduğu alt kategori veya alt gruplama. Çoğu durumda bu, belirli özellikleri veya özellikleri açıklar. |
| `ConfigurationBenchmarks` | `string` | Aynı veya benzer yapılandırmayı öneren sektör karşılaştırmaları listesi |
| `Tags` | `string` | Güvenlik yapılandırmasını tanımlamak veya kategorilere ayırmak için kullanılan çeşitli öznitelikleri temsil eden etiketler |
| `RemediationOptions` | `string` | İlişkili riskleri azaltmak veya ele almak için önerilen eylemler |

Tablodan uyumlu olmayan virüsten koruma yapılandırmalarına sahip cihazlardaki bilgilerle birlikte ilgili yapılandırma meta verilerini döndürmek için bu örnek sorguyu `DeviceTvmSecureConfigurationAssessment` deneyebilirsiniz:

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