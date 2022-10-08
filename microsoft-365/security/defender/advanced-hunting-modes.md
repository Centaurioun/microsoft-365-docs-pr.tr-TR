---
title: Microsoft 365 Defender'de avcılık için kılavuzlu ve gelişmiş modlar arasında seçim yapma
description: Microsoft 365 Defender'da destekli avcılık KQL bilgisi gerektirmezken, gelişmiş avcılık sıfırdan bir sorgu yazmanıza olanak tanır.
keywords: destekli mod, gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, özel algılamalar, şema, Kusto
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
- m365initiative-m365-defender
- tier2
ms.topic: conceptual
ms.custom: seo-marvel-apr2020
search.appverid: met150
ms.openlocfilehash: 1c47ebc606c4dc2e4fd0b7e5d41a5e7a5ea035d1
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68078219"
---
# <a name="choose-between-guided-and-advanced-modes-to-hunt-in-microsoft-365-defender"></a>Microsoft 365 Defender'da avlanmak için kılavuzlu ve gelişmiş modlar arasında seçim yapma

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender

**gelişmiş avcılık** sayfasını bulmak için Microsoft 365 Defender'daki sol gezinti çubuğuna gidip **Hunting** > **Advanced hunting'i** seçebilirsiniz. Gezinti çubuğu daraltılmışsa, avcılık simgesi avcılık simgesini ![](../../media/guided-hunting/hunting-icon.png)seçin. 

**Gelişmiş tehdit avcılığı** sayfasında iki mod desteklenir:
- **Kılavuzlu mod** – sorgu oluşturucusunu kullanarak sorgulamak için
- **Gelişmiş mod** – Kusto Sorgu Dili (KQL) kullanarak sorgu düzenleyicisini kullanarak sorgulamak için

İki mod arasındaki temel fark, kılavuzlu modun avcının veritabanını sorgulamak için KQL'yi bilmesini *gerektirmemesi* , gelişmiş modun ise KQL bilgisi gerektirmemesidir. 

Kılavuzlu modda, kullanılabilir filtreler ve koşullar içeren açılan menüler aracılığıyla sorgu oluşturmanın kullanımı kolay, görsel ve yapı taşı stiline sahip bir sorgu oluşturucusu bulunur. Kılavuzlu modu kullanmak için bkz. [Kılavuzlu avlanma modunu kullanmaya başlama](advanced-hunting-modes.md#get-started-with-guided-hunting-mode).

Gelişmiş mod, kullanıcıların sıfırdan sorgu oluşturabileceği bir sorgu düzenleyicisi alanı içerir. Gelişmiş modu kullanmak için bkz. [Gelişmiş avcılık modunu kullanmaya başlama](advanced-hunting-modes.md#get-started-with-advanced-hunting-mode).

## <a name="get-started-with-guided-hunting-mode"></a>Rehberli avlanma modunu kullanmaya başlama

> [!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

Rehberli avcılık kullanıma sunulduktan sonra gelişmiş avcılık sayfasını ilk kez açtığınızda, sekmeler ve sorgu alanları gibi sayfanın farklı bölümleri hakkında daha fazla bilgi edinmek için tura davetlisiniz. 

Tura gitmek için bu başlık göründüğünde **Tura katılın'ı** seçin:


[![kullanıcıyı tura](../../media/guided-hunting/1-guided-hunting-banner-tb.png) davet eden başlık ](../../media/guided-hunting/1-guided-hunting-banner.png#lightbox)

Sayfada görünen mavi öğretim kabarcıklarını izleyin ve bir adımdan diğerine geçmek için **İleri'yi** seçin.

**İstediğiniz zaman Yardım kaynakları** >  Daha **fazla bilgi edinin'e** gidip **Tura katılın'ı seçerek tura** tekrar gidebilirsiniz.

![Yardım kaynaklarının ekran görüntüsü](../../media/guided-hunting/help-resources.png)


Ardından tehditleri avlamak için sorgunuzu oluşturmaya başlayabilirsiniz. Aşağıdaki makaleler, kılavuzlu modda avlanmadan en iyi şekilde çıkmanıza yardımcı olabilir:


| Öğrenme hedefi | Açıklama | Kaynak |
|--|--|--|
| **İlk sorgunuzu oluşturma** | Veri etki alanını belirtme ve anlamlı bir sorgu oluşturmanıza yardımcı olacak koşullar ve filtreler ekleme gibi sorgu oluşturucusunun temellerini öğrenin. Örnek sorgular çalıştırarak daha fazla bilgi edinin. | [Kılavuzlu modu kullanarak tehdit avcılığı sorguları oluşturma](advanced-hunting-query-builder.md) |
| **Farklı sorgu oluşturucu özelliklerini öğrenin** |  Sorgunuzu ihtiyaçlarınıza göre ayarlamanıza yardımcı olmak için desteklenen farklı veri türlerini ve destekli mod özelliklerini tanıyın. | [Sorgunuzu kılavuzlu modda daraltma](advanced-hunting-query-builder-details.md) |
| **Sorgu sonuçlarıyla neler yapabileceğinizi öğrenin** | Sonuçlar görünümünü ve oluşturulan sonuçlarla ilgili eylem gerçekleştirme veya bunları bir olaya bağlama gibi neler yapabileceğinizi öğrenin. | - [Sorgu sonuçlarıyla kılavuzlu modda çalışma](advanced-hunting-query-builder-results.md)<br /> - [Sorgu sonuçlarında eylem gerçekleştirme](advanced-hunting-take-action.md) <br /> - [Sorgu sonuçlarını bir olaya bağlama](advanced-hunting-link-to-incident.md) |
| **Özel algılama kuralları oluşturma** | Uyarıları tetikleme ve yanıt eylemlerini otomatik olarak gerçekleştirme amacıyla gelişmiş tehdit avcılığı sorgularını nasıl kullanabileceğinizi anlayın. | - [Özel algılamalara genel bakış](custom-detections-overview.md) <br />- [Özel algılama kuralları](custom-detection-rules.md) |

## <a name="get-started-with-advanced-hunting-mode"></a>Gelişmiş tehdit avcılığı modunu kullanmaya başlama
Gelişmiş avcılık ile hızlı bir şekilde başlamak için bu adımların izlenmesini öneririz: 

| Öğrenme hedefi | Açıklama | Kaynak |
|--|--|--|
| **Dili öğrenme** | Gelişmiş avcılık, aynı söz dizimini ve işleçleri destekleyen [Kusto sorgu dilini](/azure/kusto/query/) temel alır. İlk sorgunuzu çalıştırarak sorgu dilini öğrenmeye başlayın. | [Sorgu diline genel bakış](advanced-hunting-query-language.md) |
| **Sorgu sonuçlarını kullanmayı öğrenin** | Grafikler ve sonuçlarınızı görüntülemek veya dışarı aktarmak için kullanabileceğiniz çeşitli yollar hakkında bilgi edinin. Sorguları hızlı bir şekilde ayarlamayı, daha zengin bilgi almak için detaya gitmeyi ve yanıt eylemleri gerçekleştirmeyi keşfedin. | - [Sorgu sonuçlarıyla gelişmiş modda çalışma](advanced-hunting-query-results.md)<br /> - [Sorgu sonuçlarında eylem gerçekleştirme](advanced-hunting-take-action.md) <br /> - [Sorgu sonuçlarını bir olaya bağlama](advanced-hunting-link-to-incident.md)  |
| **Şemayı anlayın** | Şemadaki tablolar ve sütunları hakkında iyi ve üst düzey bir anlayış elde edin. Sorgularınızı oluştururken verileri nerede arayacağınızı öğrenin. | - [Şema başvurusu](advanced-hunting-schema-tables.md) <br />- [Uç Nokta için Microsoft Defender geçiş](advanced-hunting-migrate-from-mde.md) |
| **Uzman ipuçları ve örnekler alın** | Microsoft uzmanlarının kılavuzlarıyla ücretsiz olarak eğitin. Farklı tehdit avcılığı senaryolarını kapsayan önceden tanımlanmış sorgu koleksiyonlarını keşfedin. | - [Uzman eğitimi alma](advanced-hunting-expert-training.md) <br />- [Paylaşılan sorguları kullanma](advanced-hunting-shared-queries.md) <br />- [Git avla](advanced-hunting-go-hunt.md) <br />- [Cihazlar, e-postalar, uygulamalar ve kimlikler arasında tehditleri avlama](advanced-hunting-query-emails-devices.md) |
| **Sorguları iyileştirme ve hataları işleme** | Verimli ve hatasız sorgular oluşturmayı öğrenin. | - [En iyi sorgu yöntemleri](advanced-hunting-best-practices.md)<br />- [Hataları işleme](advanced-hunting-errors.md) |
| **Özel algılama kuralları oluşturma** | Uyarıları tetikleme ve yanıt eylemlerini otomatik olarak gerçekleştirme amacıyla gelişmiş tehdit avcılığı sorgularını nasıl kullanabileceğinizi anlayın. | - [Özel algılamalara genel bakış](custom-detections-overview.md) <br />- [Özel algılama kuralları](custom-detection-rules.md)|

## <a name="see-also"></a>Ayrıca bkz.
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Kılavuzlu modu kullanarak tehdit avcılığı sorguları oluşturma](advanced-hunting-query-builder.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)