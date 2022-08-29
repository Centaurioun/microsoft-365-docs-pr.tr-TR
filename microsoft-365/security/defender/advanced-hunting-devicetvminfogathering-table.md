---
title: DeviceTvmInfoGathering tablosu gelişmiş tehdit avcılığı şemasında
description: Gelişmiş tehdit avcılığı şemasının DeviceTvmInfoGathering tablosundaki çeşitli yapılandırmaların durumu ve cihazların saldırı yüzeyi alanı durumları da dahil olmak üzere değerlendirme olayları hakkında bilgi edinin.
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, tablo, sütun, veri türü, açıklama, tehdit & güvenlik açığı yönetimi, TVM, cihaz yönetimi, yazılım, envanter, güvenlik açıkları, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities, Microsoft Defender Güvenlik Açığı Yönetimi
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
ms.openlocfilehash: efd3ed40963c1114ddc61e2fb86f84410795959d
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2022
ms.locfileid: "67329497"
---
# <a name="devicetvminfogathering"></a>DeviceTvmInfoGathering

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender
- Uç Nokta için Microsoft Defender

>[!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

`DeviceTvmInfoGathering` Gelişmiş tehdit avcılığı şemasındaki tablo, çeşitli yapılandırmaların durumu ve cihazların saldırı yüzeyi alanı durumları da dahil olmak üzere [Microsoft Defender Güvenlik Açığı Yönetimi](/microsoft-365/security/defender-vulnerability-management/defender-vulnerability-management) değerlendirme olayları içerir. Sıfır gün için risk azaltmayla ilgili değerlendirme olaylarını, tehdit analizi azaltma durum raporlarını destekleyen yeni tehditlere yönelik duruş değerlendirmesini, sunucularda etkinleştirilmiş TLS protokol sürümlerini ve daha fazlasını aramak için bu tabloyu kullanabilirsiniz. Tablodan bilgi döndüren sorgular oluşturmak için bu başvuruyu kullanın.

Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında bilgi için gelişmiş [avcılık başvurusuna](advanced-hunting-schema-tables.md) bakın.

| Sütun adı | Veri türü | Açıklama |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Olayın kaydedilildiği tarih ve saat |
| `LastSeenTime` | `datetime` | Hizmetin cihazı en son gördüğü tarih ve saat |
| `DeviceId` | `string` | Hizmetteki cihaz için benzersiz tanımlayıcı |
| `DeviceName` | `string` | Cihazın tam etki alanı adı (FQDN) |
| `OSPlatform` | `string` | Cihazda çalışan işletim sisteminin platformu. Bu, Windows 10 ve Windows 7 gibi aynı aile içindeki varyasyonlar da dahil olmak üzere belirli işletim sistemlerini gösterir. |
| `AdditionalFields` | `string` | Olay hakkında ek bilgi  |

Örneğin, geçici çözüm azaltmanın henüz uygulanmadığı veya uygulandığı ve yeniden başlatmayı beklediğiniz [Log4Shell güvenlik açığından](https://www.microsoft.com/security/blog/2021/12/11/guidance-for-preventing-detecting-and-hunting-for-cve-2021-44228-log4j-2-exploitation/) etkilenen cihazları görüntülemek için aşağıdaki sorguyu kullanabilirsiniz.

```kusto
DeviceTvmInfoGathering
| where AdditionalFields.Log4JEnvironmentVariableMitigation in ("RebootRequired", "false")
| join kind=inner (
    DeviceTvmSoftwareVulnerabilities
    | where CveId == "CVE-2021-44228"
) on DeviceId
| summarize any(DeviceName), any(AdditionalFields.Log4JEnvironmentVariableMitigation) by DeviceId
```

## <a name="related-topics"></a>İlgili konular
- [DeviceTvmInfoGatheringKB](advanced-hunting-devicetvminfogatheringkb-table.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)
- [Defender Güvenlik Açığı Yönetimine Genel Bakış](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
- [Uç Nokta için Microsoft Defender'de Log4Shell güvenlik açığını yönetmeyi öğrenin](/microsoft-365/security/defender-endpoint/tvm-manage-log4shell-guidance)