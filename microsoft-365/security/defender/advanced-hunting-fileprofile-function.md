---
title: Microsoft 365 Defender için gelişmiş avcılıkta FileProfile() işlevi
description: Gelişmiş tehdit avcılığı sorgu sonuçlarınızdaki dosyalar hakkındaki bilgileri zenginleştirmek için FileProfile() kullanmayı öğrenin
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, FileProfile, dosya profili, işlev, zenginleştirme
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
ms.openlocfilehash: de7f8553236669f4e675f3133acdc18addae14b8
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479586"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender

`FileProfile()` işlevi, sorgu tarafından bulunan dosyalara aşağıdaki verileri ekleyen [gelişmiş avcılıkta](advanced-hunting-overview.md) bir zenginleştirme işlevidir.

| Sütun | Veri türü | Açıklama |
|------------|---------------|-------------|
| `SHA1` | `string` | Kaydedilen eylemin uygulandığı dosyanın SHA-1 |
| `SHA256` | `string` | Kaydedilen eylemin uygulandığı dosyanın SHA-256'sı |
| `MD5` | `string` | Kaydedilen eylemin uygulandığı dosyanın MD5 karması |
| `FileSize` | `int` | Dosyanın bayt cinsinden boyutu |
| `GlobalPrevalence` | `int` | Microsoft tarafından genel olarak gözlemlenen varlığın örnek sayısı |
| `GlobalFirstSeen` | `datetime` | Varlığın Microsoft tarafından genel olarak ilk gözlemlendiği tarih ve saat |
| `GlobalLastSeen` | `datetime` | Varlığın Microsoft tarafından genel olarak son gözlemlendiği tarih ve saat |
| `Signer` | `string` | Dosyanın imzalayanı hakkında bilgi |
| `Issuer` | `string` | Sertifika veren sertifika yetkilisi (CA) hakkında bilgi |
| `SignerHash` | `string` | İmzalayanı tanımlayan benzersiz karma değer |
| `IsCertificateValid` | `boolean` | Dosyayı imzalamak için kullanılan sertifikanın geçerli olup olmadığı |
| `IsRootSignerMicrosoft` | `boolean` | Kök sertifikanın imzalayanının Microsoft olup olmadığını ve dosyanın Windows işletim sisteminde yerleşik olup olmadığını gösterir |
| `SignatureState` | `string` | Dosya imzasının durumu: SignedValid - dosya geçerli bir imzayla imzalandı, SignedInvalid - dosya imzalandı ama sertifika geçersiz, İmzasız - dosya imzalanmamış, Bilinmiyor - dosya hakkındaki bilgiler alınamıyor
| `IsExecutable` | `boolean` | Dosyanın Taşınabilir Yürütülebilir Dosya (PE) dosyası olup olmadığı |
| `ThreatName` | `string` | Bulunan tüm kötü amaçlı yazılımlar veya diğer tehditler için algılama adı |
| `Publisher` | `string` | Dosyayı yayımlayan kuruluşun adı |
| `SoftwareName` | `string` | Yazılım ürününün adı |

## <a name="syntax"></a>Sözdizimi

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Bağımsız değişken

- **x**—kullanılacak dosya kimliği sütunu: `SHA1`, `SHA256`, `InitiatingProcessSHA1`veya `InitiatingProcessSHA256`; işlevi belirtilmemişse kullanır `SHA1`
- **y**—zenginleştirecek kayıt sayısıyla sınır, 1-1000; işlev belirtilmemişse 100 kullanır


>[!TIP]
> Zenginleştirme işlevleri yalnızca kullanılabilir olduğunda ek bilgileri gösterir. Bilgilerin kullanılabilirliği çeşitlidir ve birçok faktöre bağlıdır. Sorgularınızda veya özel algılamalar oluştururken FileProfile() kullanırken bunu dikkate aldığınızdan emin olun. En iyi sonuçları elde için, SHA1 ile FileProfile() işlevini kullanmanızı öneririz.

## <a name="examples"></a>Örnekler

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Yalnızca SHA1 sütununu yansıtma ve zenginleştirme

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>İlk 500 kaydı zenginleştirin ve düşük yaygınlık dosyalarını listeleyin

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a>İlgili konular
- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Daha fazla sorgu örneği edinin](advanced-hunting-shared-queries.md)
