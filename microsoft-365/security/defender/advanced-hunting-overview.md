---
title: Genel Bakış - Gelişmiş avcılık
description: Microsoft 365'teki gelişmiş tehdit avcılığı sorguları ve ağınızdaki tehditleri ve zayıf noktaları proaktif olarak bulmak için bunları nasıl kullanacağınızı öğrenin
keywords: gelişmiş avcılık, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, özel algılamalar, şema, kusto
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
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
search.appverid: met150
ms.openlocfilehash: 0203f5df758a530c48bee22d4a3ea6371f1f57a7
ms.sourcegitcommit: 078149c9645ce220911ccd6ce54f984a4c92ce53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67812546"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>Microsoft 365 Defender'da gelişmiş arama ile tehditleri proaktif olarak avlama

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Gelişmiş avcılık, 30 güne kadar ham verileri keşfetmenizi sağlayan sorgu tabanlı bir tehdit avcılığı aracıdır. Tehdit göstergelerini ve varlıkları bulmak için ağınızdaki olayları proaktif olarak inceleyebilirsiniz. Verilere esnek erişim, hem bilinen hem de olası tehditler için kısıtlanmamış avcılık sağlar.

Gelişmiş avcılık, destekli ve gelişmiş iki modu destekler. Kusto Sorgu Dili (KQL) hakkında henüz bilgi sahibi değilseniz veya sorgu oluşturucunun rahatlığını tercih ediyorsanız [destekli modu](advanced-hunting-query-builder.md) kullanın. Sıfırdan sorgu oluşturmak için KQL'yi rahatça kullanıyorsanız [gelişmiş modu](advanced-hunting-query-language.md) kullanın. 

**Avlanmaya başlamak için [Microsoft 365 Defender'da avlanmak için kılavuzlu ve gelişmiş modlar arasında seçim yapma](advanced-hunting-modes.md) bölümünü okuyun.**
<br><br>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4G6DO]

Özel algılama kuralları oluşturmak için aynı tehdit avcılığı sorgularını kullanabilirsiniz. Bu kurallar, şüpheli ihlal etkinliğini, yanlış yapılandırılmış makineleri ve diğer bulguları denetlemek ve yanıtlamak için otomatik olarak çalıştırılır.

Bu özellik[, Uç Nokta için Microsoft Defender gelişmiş avcılık](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) özelliklerine benzer ve aşağıdakilerden gelen daha geniş bir veri kümesini denetleyebilen sorguları destekler:

- Uç Nokta için Microsoft Defender
- Office 365 için Microsoft Defender
- Bulut Uygulamaları için Microsoft Defender
- Kimlik için Microsoft Defender

Gelişmiş avcılığı kullanmak için [Microsoft 365 Defender açın](m365d-enable.md).

Microsoft Defender for Cloud Apps verilerde gelişmiş avlanma hakkında daha fazla bilgi için [videoya](https://www.microsoft.com/en-us/videoplayer/embed/RWFISa) bakın. 



## <a name="get-access"></a>Erişim alma
Gelişmiş avcılık veya diğer [Microsoft 365 Defender](microsoft-365-defender.md) özelliklerini kullanmak için Azure Active Directory'de uygun bir role sahip olmanız gerekir. [Gelişmiş avcılık için gerekli roller ve izinler hakkında bilgi edinin](custom-roles.md).

Ayrıca, uç nokta verilerine erişiminiz Uç Nokta için Microsoft Defender rol tabanlı erişim denetimi (RBAC) ayarları tarafından belirlenir. [Microsoft 365 Defender erişimini yönetme hakkında bilgi edinin](m365d-permissions.md).


## <a name="data-freshness-and-update-frequency"></a>Veri güncelliği ve güncelleştirme sıklığı
Gelişmiş tehdit avcılığı verileri, her biri farklı şekilde birleştirilmiş iki ayrı türe kategorilere ayırılabilir.

- **Olay veya etkinlik verileri**; uyarılar, güvenlik olayları, sistem olayları ve rutin değerlendirmeler hakkındaki tabloları doldurur. Gelişmiş avcılık, bu verileri toplayan algılayıcılar tarafından ilgili bulut hizmetlerine başarıyla iletildikten hemen sonra alır. Örneğin, iş istasyonlarındaki veya etki alanı denetleyicilerindeki iyi durumdaki algılayıcılardan gelen olay verilerini, Uç Nokta için Microsoft Defender ve Kimlik için Microsoft Defender kullanıma sunulduktan hemen sonra sorgulayabilirsiniz.
- **Varlık verileri**; tabloları kullanıcılar ve cihazlar hakkındaki bilgilerle doldurur. Bu veriler hem görece statik veri kaynaklarından hem de Active Directory girişleri ve olay günlükleri gibi dinamik kaynaklardan gelir. Yeni veriler sağlamak için, tablolar her 15 dakikada bir yeni bilgilerle güncelleştirilir ve tam olarak doldurulmayabilecek satırlar eklenir. Her 24 saatte bir veriler birleştirerek her varlıkla ilgili en son ve en kapsamlı veri kümesini içeren bir kayıt eklenir.


## <a name="time-zone"></a>Saat dilimi
### <a name="queries"></a>Sorgu
Gelişmiş tehdit avcılığı verileri UTC (Evrensel Saat Eşgüdümlü) saat dilimini kullanır. 
![Özel zaman aralığının ekran görüntüsü.](../../media/custom-time-range.png)

Sorgular UTC'de oluşturulmalıdır.

### <a name="results"></a>Sonuç -ları
Gelişmiş avlanma sonuçları, Microsoft 365 Defender'de ayarlanan [saat dilimine](m365d-time-zone.md) dönüştürülür. 




## <a name="related-topics"></a>İlgili konular
- [Kılavuzlu ve gelişmiş avcılık modları arasında seçim yapma](advanced-hunting-modes.md)
- [Kılavuzlu modu kullanarak tehdit avcılığı sorguları oluşturma](advanced-hunting-query-builder.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Özel algılamalara genel bakış](custom-detections-overview.md)
