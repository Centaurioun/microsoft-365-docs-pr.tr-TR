---
title: Gelişmiş tehdit avcılığı şemasında DeviceTvmInfoGatheringKB tablosu
description: Gelişmiş tehdit avcılığı şemasının DeviceTvmInfoGathering tablosunda değerlendirme olayları için meta veriler hakkında bilgi edinin.
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, tablo, sütun, veri türü, açıklama, tehdit & güvenlik açığı yönetimi, TVM, cihaz yönetimi, yazılım, envanter, güvenlik açıkları, CVE KIMLIĞI, İşletim Sistemi CihazıTvmSoftwareInventoryVulnerabilities, MDVM
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
ms.openlocfilehash: e83ff6391e40f015bfeda48d429d50ae9cc9f9fc
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2022
ms.locfileid: "67329475"
---
# <a name="devicetvminfogatheringkb"></a>DeviceTvmInfoGatheringKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender
- Uç Nokta için Microsoft Defender

> [!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

`DeviceTvmInfoGatheringKB` Gelişmiş tehdit avcılığı şemasındaki tablo, tabloda toplanan [Microsoft Defender Güvenlik Açığı Yönetimi](/microsoft-365/security/defender-vulnerability-management/defender-vulnerability-management) değerlendirme olayları verilerinin `DeviceTvmInfoGathering` meta verilerini içerir. Tablo, `DeviceTvmInfoGatheringKB` Defender Güvenlik Açığı Yönetimi bilgileri tarafından cihazları değerlendirmek için kullanılan çeşitli yapılandırma ve saldırı yüzeyi alanı değerlendirmelerinin listesini içerir. Tablodan bilgi döndüren sorgular oluşturmak için bu başvuruyu kullanın.

Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında bilgi için gelişmiş [avcılık başvurusuna](advanced-hunting-schema-tables.md) bakın.

| Sütun adı | Veri türü | Açıklama |
|-------------|-----------|-------------|
| `IgId` | `string` | Toplanan bilgi parçası için benzersiz tanımlayıcı |
| `FieldName` | `string` | Bu bilgilerin DeviceTvmInfoGathering tablosunun AdditionalFields sütununda göründüğü alanın adı |
| `Description` | `string` | Toplanan bilgilerin açıklaması |
| `Categories` | `string` | JSON dizi biçiminde bilgilerin ait olduğu kategorilerin listesi  |
| `DataStructure` | `string` | Toplanan bilgilerin veri yapısı  |

Bu tabloyu kullanarak içinde bulunan `DeviceTvmInfoGathering` bilgi türlerini inceleyebilir, böylece daha sonra tehdit avcılığı sorgunuzda ince ayarlamalar yapabilirsiniz.

Örneğin, toplanan bilgilerin listesini görmek için aşağıdaki sorguyu deneyebilirsiniz:

```kusto
// Check out what is being collected 
DeviceTvmInfoGatheringKB  
```

Sonuçlardan, kullanılabilir kategorilerle ilgilendiğinizi varsayalım, aşağıdaki sorguyu kullanabilirsiniz:

```kusto
// Return all available categories 
DeviceTvmInfoGatheringKB 
| mv-expand Categories to typeof(string) 
| distinct Categories 
```

Ardından, TLS protokollerini içeren değerlendirme kategorilerini görmek istediğinizi varsayalım:

```kusto
// Return all findings for a specified category 
DeviceTvmInfoGatheringKB 
| where Categories contains "tls" 
```

Sonuçta elde edilen alanları kullanarak, TLS istemci sürümü 1.0'ı kullanarak cihazların listesini almak için tabloyu kullanabilirsiniz `DeviceTvmInfoGathering` .

```kusto
// Return all devices on which the TLS version 1.0 is enabled 
DeviceTvmInfoGathering 
| where AdditionalFields.TlsClient10 == "Enabled" or AdditionalFields.TlsServer10 == "Enabled" 
```

## <a name="related-topics"></a>İlgili konular

- [DeviceTvmInfoGathering](advanced-hunting-devicetvminfogathering-table.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)
- [Genel Bakış Defender Güvenlik Açığı Yönetimi](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
