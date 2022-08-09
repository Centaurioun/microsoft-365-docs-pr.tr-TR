---
title: Gelişmiş tehdit avcılığı şemasındaki DeviceAlertEvents tablosu
description: Gelişmiş tehdit avcılığı şemasının DeviceAlertEvents tablosunda uyarı oluşturma olayları hakkında bilgi edinin
keywords: gelişmiş avcılık, tehdit avcılığı, siber tehdit avcılığı, mdatp, microsoft defender atp, uç nokta için microsoft defender, wdatp arama, sorgu, telemetri, şema başvurusu, kusto, tablo, sütun, veri türü, açıklama, DeviceAlertEvents, uyarı, önem derecesi, kategori
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: 1742c674cb982282d8edbe73e43e6ea59fedf8f6
ms.sourcegitcommit: 414682b9bf42dc19a89c893d3c515aee9765b6e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2022
ms.locfileid: "67281849"
---
# <a name="devicealertevents"></a>CihazUyarıEtkinlikleri

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!IMPORTANT]
> ve tabloları, `AlertInfo` Uç Nokta için Microsoft Defender şemasındaki tablonun yerini alır`DeviceAlertEvents`.`AlertEvidence` Daha fazla bilgi için bkz. [DeviceAlertEvents Tablosunu Eşleme](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde).

Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

`DeviceAlertEvents` [Gelişmiş tehdit avcılığı](advanced-hunting-overview.md) şemasındaki tablo, Microsoft 365 Defender uyarıları hakkında bilgi içerir. Tablodan bilgi döndüren sorgular oluşturmak için bu başvuruyu kullanın.

Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında daha fazla bilgi için gelişmiş [tehdit avcılığı şeması başvurusuna](advanced-hunting-schema-reference.md) bakın.

|Sütun adı|Veri türü|Açıklama|
|---|---|---|
|`AlertId`|Dize|Uyarının benzersiz tanımlayıcısı|
|`Timestamp`|Datetime|Olayın kaydedilildiği tarih ve saat|
|`DeviceId`|Dize|Hizmetteki cihaz için benzersiz tanımlayıcı|
|`DeviceName`|Dize|Cihazın tam etki alanı adı (FQDN)|
|`Severity`|Dize|Uyarı tarafından tanımlanan tehdit göstergesinin veya ihlal etkinliğinin olası etkisini (yüksek, orta veya düşük) gösterir|
|`Category`|Dize|Uyarı tarafından tanımlanan tehdit göstergesi veya ihlal etkinliğinin türü|
|`Title`|Dize|Uyarının başlığı|
|`FileName`|Dize|Kaydedilen eylemin uygulandığı dosyanın adı|
|`SHA1`|Dize|Kaydedilen eylemin uygulandığı dosyanın SHA-1|
|`RemoteUrl`|Dize|Bağlı olan URL veya tam etki alanı adı (FQDN)|
|`RemoteIP`|Dize|Bağlanılmakta olan IP adresi|
|`AttackTechniques`|Dize|MITRE ATT&uyarıyı tetikleyen etkinlikle ilişkili CK teknikleri|
|`ReportId`|Uzun|Yinelenen sayacı temel alan olay tanımlayıcısı. Benzersiz olayları tanımlamak için bu sütunun `DeviceName` ve `Timestamp` sütunlarıyla birlikte kullanılması gerekir|
|`Table`|Dize|Olayın ayrıntılarını içeren tablo|

## <a name="related-topics"></a>İlgili konular

- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Şemayı anlayın](advanced-hunting-schema-reference.md)
