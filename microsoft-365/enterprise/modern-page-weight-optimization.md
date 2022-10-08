---
title: SharePoint Online modern site sayfalarında sayfa kalınlığını iyileştirme
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 03/11/2020
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: sstewart
search.appverid:
- MET150
description: SharePoint Online modern site sayfalarında sayfa kalınlığını iyileştirmek için Sayfa Tanılama aracını kullanmayı öğrenin.
ms.openlocfilehash: d980738659826e3566893a35aee1c3feda9a5e96
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68178591"
---
# <a name="optimize-page-weight-in-sharepoint-online-modern-site-pages"></a>SharePoint Online modern site sayfalarında sayfa kalınlığını iyileştirme

SharePoint Online modern site sayfaları, gezinti/komut çubuklarının altındaki içerik alanındaki resimler, metinler, nesneler ve sayfanın çerçevesini oluşturan diğer HTML kodu dahil olmak üzere sayfanın sayfa içeriğini işlemek için gereken serileştirilmiş kod içerir. Sayfa ağırlığı, bu HTML kodunun ölçümüdür ve en uygun sayfa yükleme sürelerini sağlamak için sınırlandırılmalıdır.

Bu makale, modern site sayfalarınızda sayfa kalınlığını nasıl azaltabileceğinizi anlamanıza yardımcı olur.

>[!NOTE]
>SharePoint Online modern portallarındaki performans hakkında daha fazla bilgi için bkz. [Modern SharePoint deneyiminde performans](/sharepoint/modern-experience-performance).

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-weight"></a>SharePoint için Sayfa Tanılama aracını kullanarak sayfa kalınlığını analiz etme

SharePoint için Sayfa Tanılama aracı, hem SharePoint Online modern portalını hem de klasik yayımlama sitesi sayfalarını analiz eden yeni Microsoft Edge (https://www.microsoft.com/edge) ve Chrome tarayıcıları için bir tarayıcı uzantısıdır. Araç, analiz edilen her sayfa için sayfanın tanımlı bir performans ölçütleri kümesine göre nasıl performans gösterdiğini gösteren bir rapor sağlar. SharePoint için Sayfa Tanılama aracını yüklemek ve hakkında bilgi edinmek için [SharePoint Online için Sayfa Tanılama aracını kullanma](page-diagnostics-for-spo.md) sayfasını ziyaret edin.

>[!NOTE]
>Sayfa Tanılama aracı yalnızca SharePoint Online için çalışır ve SharePoint sistem sayfasında kullanılamaz.

SharePoint için Sayfa Tanılama aracıyla bir SharePoint sitesi sayfasını çözümlediğinizde, _Tanılama testleri_ bölmesinin **500 KB sonucunun altındaki Sayfa kalınlığında** sayfa hakkındaki bilgileri görebilirsiniz. Sayfa ağırlığı taban çizgisi değerinin altındaysa sonuç yeşil, sayfa ağırlığı taban çizgisi değerini aşarsa kırmızı görünür.

Olası sonuçlar şunlardır:

- **Dikkat gerekiyor** (kırmızı): Sayfa ağırlığı 500 KB'ı aşıyor
- **Eylem gerekmez** (yeşil): Sayfa ağırlığı 500 KB'ın altında

**Dikkat gerekiyor** bölümünde **500 KB'ın altındaki Sayfa ağırlığı** sonucu görünüyorsa, ayrıntılar için sonucu tıklatabilirsiniz.

![SharePoint sonuçlarına yönelik istekler.](../media/modern-portal-optimization/pagediag-page-weight.png)

## <a name="remediate-page-weight-issues"></a>Sayfa ağırlığı sorunlarını düzeltme

Sayfa ağırlığı 500 KB'ı aşarsa, web bölümü sayısını azaltarak ve sayfa içeriğini uygun bir dereceyle sınırlayarak genel sayfa yükleme süresini geliştirebilirsiniz.

Sayfa kalınlığını azaltmaya yönelik genel kılavuz şunları içerir:

- Sayfa içeriğini makul bir miktarla sınırlayın ve ilgili içerik için birden çok sayfa kullanın.
- Büyük özellik torbaları olan web bölümlerinin kullanımını en aza indirin.
- Mümkün olduğunda etkileşimli olmayan toplama görünümlerini kullanın.
- Resimleri uygun şekilde boyutlandırarak, sıkıştırılmış görüntü biçimlerini kullanarak ve cdn'den indirildiğinden emin olarak görüntü boyutlarını iyileştirin.

Sayfa kalınlığını sınırlamaya yönelik ek yönergeleri aşağıdaki makalede bulabilirsiniz:

- [SharePoint'te sayfa performansını iyileştirme](/sharepoint/dev/general-development/optimize-page-performance-in-sharepoint)

Performans sorunlarını düzeltmek için sayfa düzeltmeleri yapmadan önce, çözümleme sonuçlarında sayfa yükleme süresini not edin. Yeni sonucun temel standart içinde olup olmadığını görmek için düzeltmenizden sonra aracı yeniden çalıştırın ve bir iyileştirme olup olmadığını görmek için yeni sayfa yükleme süresini denetleyin.

![Sayfa yükleme süresi sonuçları.](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>Sayfa yükleme süresi, ağ yükü, günün saati ve diğer geçici koşullar gibi çeşitli faktörlere bağlı olarak farklılık gösterebilir. Sonuçları ortalamanıza yardımcı olacak değişiklikler yapmadan önce ve sonra sayfa yükleme süresini birkaç kez test etmelisiniz.

## <a name="related-topics"></a>İlgili konular

[SharePoint Online performansını ayarlama](tune-sharepoint-online-performance.md)

[Office 365 performansını ayarlama](tune-microsoft-365-performance.md)

[Modern SharePoint deneyiminde performans](/sharepoint/modern-experience-performance)

[İçerik teslim ağları](content-delivery-networks.md)

[SharePoint Online ile Office 365 Content Delivery Network'i (CDN) kullanma](use-microsoft-365-cdn-with-spo.md)