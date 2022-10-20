---
title: Gelişmiş tehdit avcılığı şemasında DeviceTvmSoftwareEvidenceBeta tablosu
description: Gelişmiş tehdit avcılığı şemasında DeviceTvmSoftwareEvidenceBeta tablosunu kullanmayı öğrenin.
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, tablo, sütun, veri türü, açıklama, tehdit & güvenlik açığı yönetimi, kanıt, yazılım kanıtı, TVM, cihaz yönetimi, yazılım, envanter, güvenlik açıkları, CVE Kimliği, OS DeviceTvmSoftwareEvidenceBeta
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
ms.openlocfilehash: dc79066e633a3e0a1d7b68f1315e1eeaef16433d
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68636805"
---
# <a name="devicetvmsoftwareevidencebeta"></a>DeviceTvmSoftwareEvidenceBeta

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender
- Uç Nokta için Microsoft Defender

> [!IMPORTANT]
> Tablo `DeviceTvmSoftwareEvidenceBeta` şu anda beta sürümündedir. Beta sürümünden ayrıldıktan sonra, son tablo adı değişir ve sütun adları da değişebilir. Değişiklikler daha sonra büyük olasılıkla hala önceki adları kullanan sorguları bozar. Bu tablo son haline getirildiğinde kullanıcıların sorgularını gözden geçirmeleri ve ayarlamaları tavsiye edilir. 

`DeviceTvmSoftwareEvidenceBeta` Gelişmiş tehdit avcılığı şemasındaki tablo[, yazılım kanıtı bölümüyle](/microsoft-365/security/defender-endpoint/tvm-software-inventory#software-evidence) ilgili [Microsoft Defender Güvenlik Açığı Yönetimi](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) verilerini içerir. Bu tablo, belirli bir yazılımın bir cihazda nerede algılandığının kanıtını görüntülemenizi sağlar. Örneğin, belirli yazılımların dosya yollarını tanımlamak için bu tabloyu kullanabilirsiniz. Tablodan bilgi döndüren sorgular oluşturmak için bu başvuruyu kullanın.

Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında bilgi için gelişmiş [avcılık başvurusuna](advanced-hunting-schema-tables.md) bakın.

| Sütun adı | Veri türü | Açıklama |
|-------------|-----------|-------------|
| `DeviceId` | `string` | Hizmetteki cihaz için benzersiz tanımlayıcı |
| `SoftwareVendor` | `string` | Yazılım yayımcısının adı |
| `SoftwareName` | `string` | Yazılım ürününün adı |
| `SoftwareVersion` | `string` | Yazılım ürününün sürüm numarası |
| `RegistryPaths` | `dynamic` | Bir cihazda yazılımın varlığını gösteren kanıtın algılandığı kayıt defteri yolları |
| `DiskPaths` | `dynamic` | Bir cihazda yazılımın varlığını gösteren dosya düzeyinde kanıtın algılandığı disk yolları |
| `LastSeenTime` | `string` | Cihazın bu hizmet tarafından en son görüldüğü tarih ve saat |

## <a name="related-topics"></a>İlgili konular

- [Microsoft Defender Güvenlik Açığı Yönetimi genel bakış](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
- [Tehditleri proaktif olarak avlama](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Paylaşılan sorguları kullanın](advanced-hunting-shared-queries.md)
- [Cihazlar, e-postalar, uygulamalar ve kimlikler arasında avlayın](advanced-hunting-query-emails-devices.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)
