---
title: SharePoint Online modern ve klasik yayımlama sitesi sayfalarında iFrame'leri iyileştirme
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 03/11/2020
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.reviewer: sstewart
search.appverid:
- MET150
description: SharePoint Online modern ve klasik yayımlama sitesi sayfalarında iFrame'lerin performansını iyileştirmeyi öğrenin.
ms.openlocfilehash: b61785658e414262435dabe12eb6642d47002497
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67698407"
---
# <a name="optimize-iframes-in-sharepoint-online-modern-and-classic-publishing-site-pages"></a>SharePoint Online modern ve klasik yayımlama sitesi sayfalarında iFrame'leri iyileştirme

iFrame'ler videolar veya diğer medyalar gibi zengin içerikleri önizlemek için yararlı olabilir. Ancak, iFrame'ler SharePoint site sayfası içinde ayrı bir sayfa yüklediğinden, iFrame'e yüklenen içerik, genel sayfa yükleme sürelerine katkıda bulunabilecek ve sayfada denetleyemeyeceğiniz büyük resimler, videolar veya diğer öğeler içerebilir. Bu makale, sayfalarınızdaki iFrame'lerin kullanıcı tarafından algılanan gecikme süresini nasıl etkileyeceğini ve yaygın sorunları nasıl giderebileceğinizi anlamanıza yardımcı olur.

>[!NOTE]
>SharePoint Online modern sitelerindeki performans hakkında daha fazla bilgi için bkz. [Modern SharePoint deneyiminde performans](/sharepoint/modern-experience-performance).

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-web-parts-using-iframes"></a>iFrame'leri kullanarak web bölümlerini analiz etmek için SharePoint için Sayfa Tanılama aracını kullanma

SharePoint için Sayfa Tanılama aracı, hem SharePoint Online modern portalını hem de klasik yayımlama sitesi sayfalarını analiz eden yeni Microsoft Edge (https://www.microsoft.com/edge) ve Chrome tarayıcıları için bir tarayıcı uzantısıdır. Araç, analiz edilen her sayfa için sayfanın tanımlı bir performans ölçütleri kümesine göre nasıl performans gösterdiğini gösteren bir rapor sağlar. SharePoint için Sayfa Tanılama aracını yüklemek ve hakkında bilgi edinmek için [SharePoint Online için Sayfa Tanılama aracını kullanma](page-diagnostics-for-spo.md) sayfasını ziyaret edin.

>[!NOTE]
>Sayfa Tanılama aracı yalnızca SharePoint Online için çalışır ve SharePoint sistem sayfasında kullanılamaz.

SharePoint için Sayfa Tanılama aracıyla bir SharePoint sitesi sayfasını analiz ettiğinizde, _Tanılama testleri_ bölmesinde iFrame'leri içeren web bölümleri hakkındaki bilgileri görebilirsiniz. Temel ölçüm, modern ve klasik sayfalar için aynıdır.

Olası sonuçlar şunlardır:

- **Dikkat gerekiyor** (kırmızı): Sayfa iFrame kullanan **üç veya daha fazla** web bölümü içeriyor
- **İyileştirme fırsatları** (sarı): Sayfa iFrame'leri kullanan **bir veya iki** web bölümü içerir
- **Eylem gerekmez** (yeşil): Sayfada iFrame kullanan web bölümü yok

**iFrame'ler kullanan Web bölümleri algılanan** sonuç, sonuçların **İyileştirme fırsatları** veya **Dikkat gerekiyor)** bölümünde görünüyorsa, iFrame'ler içeren web bölümlerini görmek için sonucu tıklatabilirsiniz.

![Sayfa Tanılama aracı sonuçları.](../media/modern-portal-optimization/pagediag-iframe-yellow.png)

## <a name="remediate-iframe-performance-issues"></a>iFrame performans sorunlarını düzeltme

Hangi **web bölümlerinin iFrame** içerdiğini ve yavaş sayfa yükleme sürelerine katkıda bulunabileceğini belirlemek için, Algılanan iFrame'leri kullanarak Web bölümlerini kullanın.

iFrame'ler javascript, CSS ve çerçeve öğeleri gibi tüm ilişkili içerikler de dahil olmak üzere ayrı bir dış sayfa yüklediklerinden doğası gereği yavaştır ve site sayfasının yükünü iki veya daha fazla kat artırır.

iFrame'lerin en iyi şekilde kullanılmasını sağlamak için aşağıdaki yönergeleri izleyin.

- Mümkün olduğunda, önizleme ile başlamak için küçükse veya etkileşimli değilse iFrame'ler yerine görüntüleri kullanın.
- iFrame'lerin kullanılması gerekiyorsa, sayıyı simge durumuna küçültün ve/veya görünüm penceresinin dışına taşıyın.
- Word, Excel ve PowerPoint gibi eklenmiş Office dosyaları etkileşimlidir, ancak yüklenmesi yavaştır. Belgenin tamamının bağlantısını içeren resim küçük resimleri genellikle daha iyi performans gösterir.
- Ekli YouTube videoları ve Twitter akışları iFrame'lerde daha iyi performans gösterme eğilimindedir, ancak bu tür eklemeleri iddialı bir şekilde kullanır.
- Yalıtılmış web bölümleri makul bir istisnadır, ancak görünüm penceresine sayılarını ve yerleşimlerini en aza indirir.
- Bir iFrame görünüm penceresi dışında yer alıyorsa, iFrame'in görünümüne gelene kadar işlenmesini geciktirmek için _bir IntersectionObserver_ kullanmayı göz önünde bulundurun.

Performans sorunlarını düzeltmek için sayfa düzeltmeleri yapmadan önce, çözümleme sonuçlarında sayfa yükleme süresini not edin. Yeni sonucun temel standart içinde olup olmadığını görmek için düzeltmenizden sonra aracı yeniden çalıştırın ve bir iyileştirme olup olmadığını görmek için yeni sayfa yükleme süresini denetleyin.

![Sayfa yükleme süresi sonuçları.](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>Sayfa yükleme süresi, ağ yükü, günün saati ve diğer geçici koşullar gibi çeşitli faktörlere bağlı olarak farklılık gösterebilir. Sonuçları ortalamanıza yardımcı olacak değişiklikler yapmadan önce ve sonra sayfa yükleme süresini birkaç kez test etmelisiniz.

## <a name="related-topics"></a>İlgili konular

[SharePoint Online performansını ayarlama](tune-sharepoint-online-performance.md)

[Office 365 performansını ayarlama](tune-microsoft-365-performance.md)

[Modern SharePoint deneyiminde performans](/sharepoint/modern-experience-performance)