---
title: Gelişmiş tehdit avcılığı şemasındaki AlertInfo tablosu
description: Gelişmiş tehdit avcılığı şemasının AlertInfo tablosunda uyarı oluşturma olayları hakkında bilgi edinin
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, tablo, sütun, veri türü, açıklama, AlertInfo, uyarı, önem derecesi, kategori, MITRE, ATT&CK, Uç Nokta için Microsoft Defender, Office 365 için Microsoft Defender, Microsoft Defender for Cloud Apps ve Kimlik için Microsoft Defender
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
ms.openlocfilehash: 6dbb60d6cd5b7ca208e4e79164b23dfe576b225b
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67495807"
---
# <a name="alertinfo"></a>AlertInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender


## <a name="get-access"></a>Erişim alma
Gelişmiş avcılık veya diğer [Microsoft 365 Defender](microsoft-365-defender.md) özelliklerini kullanmak için Azure Active Directory'de uygun bir role sahip olmanız gerekir. [Gelişmiş avcılık için gerekli roller ve izinler hakkında bilgi edinin](custom-roles.md).

Ayrıca, uç nokta verilerine erişiminiz Uç Nokta için Microsoft Defender rol tabanlı erişim denetimi (RBAC) ayarları tarafından belirlenir. [Microsoft 365 Defender erişimini yönetme hakkında bilgi edinin](m365d-permissions.md).

## <a name="alertinfo"></a>AlertInfo

`AlertInfo` [Gelişmiş tehdit avcılığı](advanced-hunting-overview.md) şemasındaki tablo Uç Nokta, Office 365 için Microsoft Defender, Microsoft Defender for Cloud Apps ve için Microsoft Defender'dan gelen uyarılar hakkında bilgi içerir Kimlik için Microsoft Defender. Bu tablodan bilgi döndüren sorgular oluşturmak için bu başvuruyu kullanın.

Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında bilgi için [gelişmiş avcılık başvurusuna bakın](advanced-hunting-schema-tables.md).

| Sütun adı | Veri türü | Açıklama |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Olayın kaydedilildiği tarih ve saat |
| `AlertId` | `string` | Uyarının benzersiz tanımlayıcısı |
| `Title` | `string` | Uyarının başlığı |
| `Category` | `string` | Uyarı tarafından tanımlanan tehdit göstergesi veya ihlal etkinliğinin türü |
| `Severity` | `string` | Uyarı tarafından tanımlanan tehdit göstergesinin veya ihlal etkinliğinin olası etkisini (yüksek, orta veya düşük) gösterir |
| `ServiceSource` | `string` | Uyarı bilgilerini sağlayan ürün veya hizmet |
| `DetectionSource` | `string` | Önemli bileşeni veya etkinliği tanımlayan algılama teknolojisi veya algılayıcısı |
| `AttackTechniques` | `string` | MITRE ATT&uyarıyı tetikleyen etkinlikle ilişkili CK teknikleri |

## <a name="related-topics"></a>İlgili konular
- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Paylaşılan sorguları kullanın](advanced-hunting-shared-queries.md)
- [Cihazlar, e-postalar, uygulamalar ve kimlikler arasında avlayın](advanced-hunting-query-emails-devices.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)
