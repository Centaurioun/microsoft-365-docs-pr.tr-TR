---
title: Uç Nokta için Microsoft Defender'da gelişmiş avlanmaya genel bakış
description: Ağınızdaki tehditleri ve zayıflıkları bu alan sorgular oluşturmak için Uç Nokta için Microsoft Defender tehdit avcılığı özelliklerini kullanın
keywords: gelişmiş avcılık, tehdit avcılığı, siber tehdit avcılığı, mdatp, microsoft defender atp, uç nokta için microsoft defender, wdatp, arama, sorgu, telemetri, özel algılamalar, şema, kusto, saat dilimi, UTC
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
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
ms.subservice: mde
ms.openlocfilehash: 4995e9b2090b3de237581bb2200304a7a37db7f1
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67679437"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting"></a>Gelişmiş avcılık ile tehditleri proaktif olarak avlama

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-advancedhunting-abovefoldlink)

Gelişmiş avcılık, 30 güne kadar ham verileri keşfetmenizi sağlayan sorgu tabanlı bir tehdit avcılığı aracıdır. Tehdit göstergelerini ve varlıkları bulmak için ağınızdaki olayları proaktif olarak inceleyebilirsiniz. Verilere esnek erişim, hem bilinen hem de olası tehditler için kısıtlanmamış avcılık sağlar.

Gelişmiş avlanmaya hızlı bir genel bakış ve hızlı bir başlangıç yapacak kısa bir öğretici için bu videoyu izleyin.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqo]

Özel algılama kuralları oluşturmak için aynı tehdit avcılığı sorgularını kullanabilirsiniz. Bu kurallar, şüpheli ihlal etkinliğini, yanlış yapılandırılmış makineleri ve diğer bulguları denetlemek ve yanıtlamak için otomatik olarak çalıştırılır.

> [!TIP]
> Uç Nokta, Office 365 için Microsoft Defender, Microsoft Defender for Cloud Apps ve Defender'dan gelen verileri kullanarak tehditleri avlamak için Microsoft 365 Defender gelişmiş [avcılığı](/microsoft-365/security/defender/advanced-hunting-overview) kullanma Kimlik için Microsoft Defender. [Microsoft 365 Defender açın](/microsoft-365/security/defender/m365d-enable).

Gelişmiş avcılık iş akışlarınızı Uç Nokta için Microsoft Defender'den Microsoft 365 Defender taşıma hakkında daha fazla bilgi için [bkz. Gelişmiş avcılık sorgularını Uç Nokta için Microsoft Defender geçirme](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde).

## <a name="get-started-with-advanced-hunting"></a>Gelişmiş avcılık ile çalışmaya başlama

Gelişmiş avcılık bilginizi artırmaya yönelik aşağıdaki adımları izleyin.

Gelişmiş avcılık ile hızlı bir şekilde çalışmaya başlamak için birkaç adımdan geçmenizi öneririz.

<br>

****

|Öğrenme hedefi|Açıklama|Kaynak|
|---|---|---|
|**Dili öğrenme**|Gelişmiş avcılık, aynı söz dizimini ve işleçleri destekleyen [Kusto sorgu dilini](/azure/kusto/query/) temel alır. İlk sorgunuzu çalıştırarak sorgu dilini öğrenmeye başlayın.|[Sorgu diline genel bakış](advanced-hunting-query-language.md)|
|**Sorgu sonuçlarını kullanmayı öğrenin**|Grafikler ve sonuçlarınızı görüntülemek veya dışarı aktarmak için kullanabileceğiniz çeşitli yollar hakkında bilgi edinin. Daha zengin bilgiler elde etmek için sorguları hızlı bir şekilde ayarlamayı ve detaya gitmeyi keşfedin.|[Sorgu sonuçlarıyla çalışın](advanced-hunting-query-results.md)|
|**Şemayı anlayın**|Şemadaki tablolar ve sütunları hakkında iyi ve üst düzey bir anlayış elde edin. Sorgularınızı oluştururken verileri nerede arayacağınızı öğrenin.|[Şema başvurusu](advanced-hunting-schema-reference.md)|
|**Önceden tanımlanmış sorguları kullanma**|Farklı tehdit avcılığı senaryolarını kapsayan önceden tanımlanmış sorgu koleksiyonlarını keşfedin.|[Paylaşılan sorgular](advanced-hunting-shared-queries.md)|
|**Sorguları iyileştirme ve hataları işleme**|Verimli ve hatasız sorgular oluşturmayı öğrenin.|[En iyi sorgu yöntemleri](advanced-hunting-best-practices.md) <p> [Hataları işleyin](advanced-hunting-errors.md)|
|**En eksiksiz kapsamı alma**|Kuruluşunuz için daha iyi veri kapsamı sağlamak için denetim ayarlarını kullanın.|[Gelişmiş avcılık kapsamını genişletme](advanced-hunting-extend-data.md)|
|**Hızlı bir araştırma çalıştırma**|Şüpheli etkinliği araştırmak için hızlı bir şekilde gelişmiş bir tehdit avcılığı sorgusu çalıştırın.|[Go hunt ile varlık veya olay bilgilerini hızla *avla*](advanced-hunting-go-hunt.md)|
|**Tehditler içerir ve risklere çözüm sağlar**|Dosyalar arasında geçiş yaparak, uygulama yürütmeyi kısıtlayarak ve diğer eylemlerle saldırılara yanıt verme|[Gelişmiş tehdit avcılığı sorgu sonuçları üzerinde eylem gerçekleştirme](advanced-hunting-take-action.md)|
|**Özel algılama kuralları oluşturma**|Uyarıları tetikleme ve yanıt eylemlerini otomatik olarak gerçekleştirme amacıyla gelişmiş tehdit avcılığı sorgularını nasıl kullanabileceğinizi anlayın.|[Özel algılamalara genel bakış](overview-custom-detections.md) <p> [Özel algılama kuralları](custom-detection-rules.md)|
|

## <a name="data-freshness-and-update-frequency"></a>Veri güncelliği ve güncelleştirme sıklığı

Gelişmiş tehdit avcılığı verileri, her biri farklı şekilde birleştirilmiş iki ayrı türe kategorilere ayırılabilir.

- **Olay veya etkinlik verileri**: Uyarılar, güvenlik olayları, sistem olayları ve rutin değerlendirmeler hakkındaki tabloları doldurur. Gelişmiş avcılık, bu verileri toplayan algılayıcılar uç nokta için Defender'a başarıyla iletildikten hemen sonra alır.
- **Varlık verileri**: Tabloları kullanıcılar ve cihazlar hakkında birleştirilmiş bilgilerle doldurur. Bu veriler hem görece statik veri kaynaklarından hem de Active Directory girişleri ve olay günlükleri gibi dinamik kaynaklardan gelir. Yeni veriler sağlamak için, tablolar her 15 dakikada bir yeni bilgilerle güncelleştirilir ve tam olarak doldurulmayabilecek satırlar eklenir. Her 24 saatte bir veriler birleştirerek her varlıkla ilgili en son ve en kapsamlı veri kümesini içeren bir kayıt eklenir.

## <a name="time-zone"></a>Saat dilimi

Gelişmiş avcılıkta saat bilgileri şu anda UTC saat dilimindedir.

## <a name="related-topics"></a>İlgili konular

- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Sorgu sonuçlarıyla çalışın](advanced-hunting-query-results.md)
- [Paylaşılan sorguları kullanın](advanced-hunting-shared-queries.md)
- [Şemayı anlayın](advanced-hunting-schema-reference.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)
- [Özel algılamalara genel bakış](overview-custom-detections.md)
- [Depolama hesabına genel bakış](/azure/storage/common/storage-account-overview)
- [Azure Event Hubs — Büyük veri akışı platformu ve olay alımı hizmeti](/azure/event-hubs/event-hubs-about)
