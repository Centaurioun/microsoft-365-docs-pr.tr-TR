---
title: Sorgu sonuçlarını bir olayla bağlayın
description: Sorgu sonuçlarını bir olayla bağlayın
keywords: gelişmiş avcılık, olay, özet, varlık, go hunt, ilgili olaylar, tehdit avcılığı, siber tehdit avcılığı, arama, sorgu, telemetri, Microsoft 365, Microsoft 365 Defender
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
- m365initiative-m365-defender
- tier1
ms.topic: article
ms.openlocfilehash: 9664fbcd1b4fe7796f3d2e30a7a44563635105d4
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68091355"
---
# <a name="link-query-results-to-an-incident"></a>Sorgu sonuçlarını bir olayla bağlayın

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender
- Uç Nokta için Microsoft Defender

Araştırma aşamasındaki yeni veya mevcut bir olaya gelişmiş tehdit avcılığı sorgusu sonuçları eklemek için olay bağlantısını kullanabilirsiniz. Bu özellik, gelişmiş tehdit avcılığı etkinliklerindeki kayıtları kolayca yakalamanıza yardımcı olur ve bu sayede bir olayla ilgili daha zengin bir zaman çizelgesi veya olay bağlamı oluşturabilirsiniz. 

## <a name="link-results-to-new-or-existing-incidents"></a>Sonuçları yeni veya mevcut olaylara bağlama

1. Gelişmiş tehdit avcılığı sorgusu sayfasında, önce sorgunuzu sağlanan sorgu alanına girin, ardından sonuçlarınızı almak için **Sorguyu çalıştır'ı** seçin.

    :::image type="content" source="../../media/link-to-incident-1.png" alt-text="Microsoft 365 Defender portalındaki Sorgu sayfası" lightbox="../../media/link-to-incident-1.png":::

2. Sonuçlar sayfasında, üzerinde çalıştığınız yeni veya geçerli araştırmayla ilgili olayları veya kayıtları seçin, ardından **Olaya bağla'yı** seçin.

    :::image type="content" source="../../media/link-to-incident-1b.png" alt-text="Microsoft 365 Defender portalındaki Sonuçlar sekmesinin Olaya bağlan seçeneği" lightbox="../../media/link-to-incident-1b.png":::

3. Olay bağlantısı bölmesinde **Uyarı ayrıntıları** bölümünü bulun, ardından **Yeni olay oluştur'u** seçerek olayları uyarılara dönüştürün ve bunları yeni bir olaya gruplandırın:

    :::image type="content" source="../../media/link-to-incident-3-create-new.png" alt-text="Microsoft 365 Defender portalındaki Olaya bağla bölmesindeki Uyarı ayrıntıları bölümü" lightbox="../../media/link-to-incident-3-create-new.png":::
    
    Alternatif olarak, seçilen kayıtları **var olan bir olaya eklemek için Var olan bir olaya bağla'ya** da tıklayabilirsiniz. Mevcut olayların açılan listesinden ilgili olayı seçin. Mevcut olayı bulmak için olay adının veya kimliğin ilk birkaç karakterini de girebilirsiniz. 

    :::image type="content" source="../../media/link-to-incident-3-link-to-existing.png" alt-text="Microsoft 365 Defender portalındaki Uyarı ayrıntıları bölümü" lightbox="../../media/link-to-incident-3-link-to-existing.png":::

4. Her iki seçim için de aşağıdaki ayrıntıları sağlayın ve **İleri'yi** seçin:
      - **Uyarı başlığı** - Olay yanıtlayıcılarınızın anlayabileceği sonuçlar için açıklayıcı bir başlık sağlayın. Bu açıklayıcı başlık, uyarı başlığı olur.
      - **Önem Derecesi** - Uyarı grubu için geçerli olan önem derecesini seçin.
      - **Kategori** - Uyarılar için uygun tehdit kategorisini seçin.
      - **Açıklama** - Gruplandırılmış uyarılar için yararlı bir açıklama verin.
      - **Önerilen eylemler** - Düzeltme eylemleri sağlayın.

5. **Etkilenen varlıklar** bölümünde, etkilenen veya etkilenen ana varlığı seçin. Bu bölümde yalnızca sorgu sonuçlarını temel alan geçerli varlıklar görüntülenir. Örneğimizde, olası bir e-posta sızdırma olayıyla ilgili olayları bulmak için bir sorgu kullandık, bu nedenle Gönderen etkilenen varlıktır. Örneğin dört farklı gönderen varsa, dört uyarı oluşturulur ve seçilen olaya bağlanır.

     :::image type="content" source="../../media/link-to-incident-4-impacted-entities.png" alt-text="Microsoft 365 Defender portalındaki Olaya bağlan bölümündeki etkilenen varlık" lightbox="../../media/link-to-incident-4-impacted-entities.png":::

1. **İleri**'yi seçin.
1. **Özet** bölümünde sağladığınız ayrıntıları gözden geçirin.
   :::image type="content" source="../../media/link-to-incident-5-summary.png" alt-text="Microsoft 365 Defender portalındaki Olaya bağlan bölümündeki sonuçlar sayfası" lightbox="../../media/link-to-incident-5-summary.png":::
     
1. **Bitti'yi** seçin.

## <a name="view-linked-records-in-the-incident"></a>Olaydaki bağlantılı kayıtları görüntüleme

Olayların bağlı olduğu olayı görüntülemek için olay adını seçebilirsiniz.
:::image type="content" source="../../media/link-to-incident-6-incident-pg.png" alt-text="Microsoft 365 Defender portalındaki Özet sekmesindeki olay ayrıntıları ekranı" lightbox="../../media/link-to-incident-6-incident-pg.png":::

Örneğimizde, seçilen dört olayı temsil eden dört uyarı yeni bir olaya başarıyla bağlandı. 

Uyarı sayfalarının her birinde, olay veya olaylar hakkındaki tüm bilgileri zaman çizelgesi görünümünde (varsa) ve sorgu sonuçları görünümünde bulabilirsiniz.
:::image type="content" source="../../media/link-to-incident-7-alert-story.png" alt-text="Microsoft 365 Defender portalındaki Zaman Çizelgesi sekmesindeki bir olayın tüm ayrıntıları" lightbox="../../media/link-to-incident-7-alert-story.png":::

Kaydı **incele** bölmesini açmak için olayı da seçebilirsiniz.
:::image type="content" source="../../media/link-to-incident-7-inspect-record.png" alt-text="Microsoft 365 Defender portalındaki Zaman Çizelgesi sekmesindeki bir olayın kayıt ayrıntılarını inceleme" lightbox="../../media/link-to-incident-7-inspect-record.png":::

## <a name="filter-for-events-added-using-advanced-hunting"></a>Gelişmiş avcılık kullanılarak eklenen olaylar için filtre uygulama
Olaylar kuyruğunu ve Uyarılar kuyruğunu **El ile** algılama kaynağına göre filtreleyerek gelişmiş tehdit avcılığından hangi uyarıların oluşturulduğunu görüntüleyebilirsiniz.

:::image type="content" source="../../media/link-to-incident-8-filter.png" alt-text="Microsoft 365 Defender portalındaki Filtreler sayfasında Olaylar ve Uyarılar kuyruğunun el ile filtrelenmesi" lightbox="../../media/link-to-incident-8-filter.png":::
