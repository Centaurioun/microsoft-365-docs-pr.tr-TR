---
title: Microsoft 365 Defender'de gelişmiş tehdit avcılığı kotaları ve kullanım parametreleri
description: Gelişmiş tehdit avcılığı hizmetinin yanıt vermesini sağlayan çeşitli kotaları ve kullanım parametrelerini (hizmet sınırları) anlama
keywords: gelişmiş avcılık, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema, kusto, CPU sınırı, sorgu sınırı, Kaynaklar, maksimum sonuç, kota, parametreler, ayırma
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
ms.openlocfilehash: dc227ef3dfa9f462fba302fda660843e90215a5c
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67468845"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>Gelişmiş tehdit avcılığı kotaları ve kullanım parametreleri

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Gelişmiş avcılık, hizmetin performansını ve yanıt verme hızını korumak için çeşitli kotaları ve kullanım parametrelerini ("hizmet sınırları" olarak da bilinir) ayarlar. Bu kotalar ve parametreler, el ile çalıştırılacak sorgulara ve [özel algılama kuralları](custom-detection-rules.md) kullanılarak çalıştırılacak sorgulara ayrı ayrı uygulanır. Düzenli olarak birden çok sorgu çalıştıran müşterilerin bu sınırlara dikkat etmesi ve kesintileri en aza indirmek için [en iyi iyileştirme yöntemlerini uygulaması](advanced-hunting-best-practices.md) gerekir.

Mevcut kotaları ve kullanım parametrelerini anlamak için aşağıdaki tabloya bakın.

| Kota veya parametre | Boyut | Yenileme döngüsü | Açıklama |
|--|--|--|--|
| Veri aralığı | 30 gün | Her sorgu | Her sorgu son 30 güne kadar olan verileri arayabilir. |
| Sonuç kümesi | 10.000 satır | Her sorgu | Her sorgu en fazla 10.000 kayıt döndürebilir. |
| Zaman aşımı | 10 dakika | Her sorgu | Her sorgu 10 dakikaya kadar çalıştırılabilir. 10 dakika içinde tamamlanmazsa hizmet bir hata görüntüler.
| CPU kaynakları | Kiracı boyutuna göre | Her 15 dakikada bir | Portal, bir sorgu çalıştırıldığında ve kiracı ayrılan kaynakların %10'undan fazla tüketildiğinde [bir hata görüntüler](advanced-hunting-errors.md) . Kiracı sonraki 15 dakikalık döngüden sonra %100'e ulaşmışsa sorgular engellenir. |

>[!NOTE] 
>API aracılığıyla gerçekleştirilen gelişmiş tehdit avcılığı sorguları için ayrı bir kota ve parametre kümesi geçerlidir. [Gelişmiş avcılık API'leri hakkında bilgi edinin](./api-advanced-hunting.md)

## <a name="related-topics"></a>İlgili konular

- [Gelişmiş avcılık en iyi yöntemleri](advanced-hunting-best-practices.md)
- [Gelişmiş tehdit avcılığı hatalarını işleme](advanced-hunting-errors.md)
- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Özel algılamalara genel bakış](custom-detections-overview.md)