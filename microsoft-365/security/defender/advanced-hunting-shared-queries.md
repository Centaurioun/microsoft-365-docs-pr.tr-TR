---
title: Microsoft 365 Defender gelişmiş avcılıkta paylaşılan sorguları kullanma
description: Önceden tanımlanmış ve paylaşılan sorgularla tehdit avcılığı yapmaya hemen başlayın. Sorgularınızı genel veya kuruluşunuzla paylaşın.
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, özel algılamalar, şema, kusto, github deposu, sorgularım, paylaşılan sorgular
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
ms.openlocfilehash: d9e90d1c4e353b9ac460420867ed56632b1e5eeb
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67477131"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>Gelişmiş avcılıkta paylaşılan sorguları kullanma

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender
- Uç Nokta için Microsoft Defender

[Gelişmiş tehdit avcılığı](advanced-hunting-overview.md) sorguları aynı kuruluştaki kullanıcılar arasında paylaşılabilir. Ayrıca yalnızca sizin erişebileceğiniz sorguları da kaydedebilirsiniz. GitHub'da herkese açık olarak paylaşılan topluluk sorgularını da bulabilirsiniz. Kaydedilen bu sorgular, sıfırdan sorgu yazmak zorunda kalmadan belirli tehdit avcılığı senaryolarını hızla izlemenize olanak sağlar.

Gelişmiş tehdit avcılığındaki Sorgular sekmesinin altında **Paylaşılan sorgular**, **Sorgularım** ve **Topluluk sorguları** için açılan menüleri bulabilirsiniz. Menüyü genişletmek için aşağı dönük bir ok seçebilirsiniz.


:::image type="content" source="../../media/advanced-hunting-shared-queries-1.png" alt-text="Microsoft 365 Defender portalında paylaşılan sorgular, Sorgularım ve Topluluk sorguları" lightbox="../../media/advanced-hunting-shared-queries-1.png":::



## <a name="save-modify-and-share-a-query"></a>Sorguyu kaydetme, değiştirme ve paylaşma
Yeni veya mevcut bir sorguyu kaydederek yalnızca sizin için erişilebilir olmasını veya kuruluşunuzdaki diğer kullanıcılarla paylaşılabilmesini sağlayabilirsiniz. 

1. Sorgu oluşturma veya değiştirme. 

2. **Sorguyu kaydet** açılan düğmesine tıklayın ve **Farklı kaydet'i** seçin.
    
3. Sorgu için bir ad girin. 

   :::image type="content" source="../../media/shared-query-2.png" alt-text="Microsoft 365 Defender portalına kaydedilmek üzere olan yeni sorgu" lightbox="../../media/shared-query-2.png":::

4. Sorguyu kaydetmek istediğiniz klasörü seçin.
    - **Paylaşılan sorgular** — kuruluşunuzda tüm kullanıcılarla paylaşıldı
    - **Sorgularım** — yalnızca sizin için erişilebilir
    
5. **Kaydet**'i seçin. 

## <a name="delete-or-rename-a-query"></a>Sorguyu silme veya yeniden adlandırma
1. Yeniden adlandırmak veya silmek istediğiniz sorgunun sağındaki üç noktayı seçin.

    :::image type="content" source="../../media/advanced-hunting-del-save-query.png" alt-text="Microsoft 365 Defender portalındaki Gelişmiş Tehdit Avcılığı sayfasında sorguyu yeniden adlandırma veya silme" lightbox="../../media/advanced-hunting-del-save-query.png":::

2. **Sil'i** seçin ve silmeyi onaylayın. İsterseniz **Yeniden Adlandır'ı** seçip sorgu için yeni bir ad da sağlayabilirsiniz.

## <a name="create-a-direct-link-to-a-query"></a>Sorguya doğrudan bağlantı oluşturma
Sorgunuzu doğrudan gelişmiş tehdit avcılığı sorgu düzenleyicisinde açan bir bağlantı oluşturmak için sorgunuzu sonlandırın ve **Bağlantıyı paylaş'ı** seçin.

## <a name="access-community-queries-in-the-github-repo"></a>GitHub deposunda topluluk sorgularını erişme  
Microsoft güvenlik araştırmacıları [GitHub'daki belirli bir genel depoda](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/Microsoft%20365%20Defender) düzenli olarak gelişmiş avlanma sorgularını paylaşır. Bu depoya yapılan katkılar yayımlanmadan önce gözden geçirilir. Katkıda bulunmak [için GitHub'a ücretsiz katılın](https://github.com/).

Bu sorguları **Topluluk sorguları** açılan menüsünde de kolayca bulabilirsiniz.

:::image type="content" source="../../media/advanced-hunting-shared-queries-2.png" alt-text="Microsoft 365 Defender portalında klasöre göre düzenlenmiş topluluk sorguları" lightbox="../../media/advanced-hunting-shared-queries-2.png":::

Topluluk sorguları *Kampanyalar*, *Koleksiyon*, *Savunma kaçaması* ve benzeri klasörler halinde gruplandırılır. Sorgu hakkında daha fazla bilgi, sorgunun kendisinde satır içi açıklamalar olarak sağlanır. 

>[!tip]
>Microsoft güvenlik araştırmacıları, yeni ortaya çıkan tehditlerle ilişkili etkinlikleri ve göstergeleri bulmak için kullanabileceğiniz gelişmiş tehdit avcılığı sorguları da sağlar. Bu sorgular, [Microsoft 365 Defender'daki tehdit analizi](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) raporlarının bir parçası olarak sağlanır.


## <a name="related-topics"></a>İlgili konular
- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Sorgu sonuçlarıyla çalışın](advanced-hunting-query-results.md)
- [Cihazlar, e-postalar, uygulamalar ve kimlikler arasında avlayın](advanced-hunting-query-emails-devices.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)