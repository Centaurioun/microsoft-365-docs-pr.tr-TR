---
title: SharePoint Online modern ve klasik yayımlama sitesi sayfalarında sayfa çağrılarını iyileştirme
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
description: SharePoint Online hizmet uç noktalarına yapılan çağrı sayısını sınırlayarak SharePoint Online'da modern ve klasik yayımlama sitesi sayfalarını iyileştirmeyi öğrenin.
ms.openlocfilehash: b5a1830d9dbd10aa950150c9b66d2fffb179ae9b
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67702104"
---
# <a name="optimize-page-calls-in-sharepoint-online-modern-and-classic-publishing-site-pages"></a>SharePoint Online modern ve klasik yayımlama sitesi sayfalarında sayfa çağrılarını iyileştirme

Hem SharePoint Online modern hem de klasik yayımlama siteleri, SharePoint özellikleri ve CDN'lerinden veri yükleyen (veya aramalar yapılan) bağlantılar içerir. Bir sayfa tarafından ne kadar çok çağrı yapılırsa, sayfanın yüklenmesi o kadar uzun sürer. Bu, **son kullanıcının algılanan gecikme süresi** veya **EUPL** olarak bilinir.

Bu makale, modern ve klasik yayımlama sitesi sayfalarınızdaki dış uç noktalara yapılan çağrıların sayısını ve etkisini belirlemeyi ve son kullanıcının algıladığı gecikme süresini nasıl sınırlayacağınızı anlamanıza yardımcı olur.

>[!NOTE]
>SharePoint Online modern portallarındaki performans hakkında daha fazla bilgi için bkz. [Modern SharePoint deneyiminde performans](/sharepoint/modern-experience-performance).

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-calls"></a>Sayfa çağrılarını analiz etmek için SharePoint için Sayfa Tanılama aracını kullanma

SharePoint için Sayfa Tanılama aracı, hem SharePoint Online modern portalını hem de klasik yayımlama sitesi sayfalarını analiz eden yeni Microsoft Edge (https://www.microsoft.com/edge) ve Chrome tarayıcıları için bir tarayıcı uzantısıdır. Araç, analiz edilen her sayfa için sayfanın tanımlı bir performans ölçütleri kümesine göre nasıl performans gösterdiğini gösteren bir rapor sağlar. SharePoint için Sayfa Tanılama aracını yüklemek ve hakkında bilgi edinmek için [SharePoint Online için Sayfa Tanılama aracını kullanma](page-diagnostics-for-spo.md) sayfasını ziyaret edin.

>[!NOTE]
>Sayfa Tanılama aracı yalnızca SharePoint Online için çalışır ve SharePoint sistem sayfasında kullanılamaz.

SharePoint için Sayfa Tanılama aracıyla bir SharePoint sitesi sayfasını çözümlediğinizde, **SharePoint'e yapılan istekler** sonucundaki _Tanılama testleri_ bölmesinde dış çağrılar hakkındaki bilgileri görebilirsiniz. Site sayfası çağrıların taban çizgisi sayısından daha azını içeriyorsa çizgi yeşil, sayfa taban çizgisi numarasını aşarsa kırmızı görünür. Klasik site sayfaları HTTP1.1 ve modern sayfalar HTTP2.0 kullandığından, modern ve klasik sayfalar için taban çizgisi numarası farklıdır:

- Modern site sayfaları **en fazla 25** çağrı içermelidir
- Klasik yayımlama sayfaları **en fazla 6** çağrı içermelidir

Olası sonuçlar şunlardır:

- **Dikkat gerekiyor** (kırmızı): Sayfa, çağrıların taban çizgisi sayısını aşıyor
- **Eylem gerekmez** (yeşil): Sayfa, temel çağrı sayısından daha az sayıda çağrı içeriyor

**SharePoint'e İstekler** sonucu **Dikkat gerekiyor** bölümünde görünüyorsa, sayfadaki toplam çağrı sayısı ve URL'lerin listesi de dahil olmak üzere ayrıntılar için sonuda tıklayabilirsiniz.

![SharePoint sonuçlarına yönelik istekler.](../media/modern-portal-optimization/pagediag-requests.png)

## <a name="remediate-performance-issues-related-to-too-many-calls-on-a-page"></a>Bir sayfada çok fazla çağrıyla ilgili performans sorunlarını düzeltme

Bir sayfada çok fazla çağrı varsa, Yinelenen çağrılar, toplu işlenmeleri gereken çağrılar veya önbelleğe alınması gereken verileri döndüren çağrılar olup olmadığını belirlemek için **SharePoint İstekleri** sonuçlarındaki URL'lerin listesini kullanabilirsiniz.

**REST çağrılarının toplu olarak gerçeklenmesi** , performans yükünü azaltmaya yardımcı olabilir. API çağrısı toplu işlemi hakkında daha fazla bilgi için bkz. [REST API'leriyle toplu iş istekleri yapma](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).

Bir API çağrısının sonuçlarını depolamak için **önbellek kullanmak**, istemcinin izleyen her sayfa yükü için ek çağrı yapmak yerine önbelleğe alınmış verileri kullanmasına izin vererek sıcak bir isteğin performansını artırabilir. İş gereksinimine bağlı olarak bu çözüme yaklaşmanın birden çok yolu vardır. Genellikle veriler tüm kullanıcılar için aynı olacaksa [_, Azure Redis_ önbelleği](https://azure.microsoft.com/services/cache/) gibi bir orta katman önbelleğe alma hizmeti kullanmak, kullanıcılar verileri doğrudan SPO'dan değil önbelleğe alma hizmetinden istediğinden, sitedeki API trafiğini önemli ölçüde azaltmak için harika bir seçenektir. Gereken tek SPO çağrısı, orta katmanın önbelleğini yenilemektir. Veriler tek tek kullanıcı bazında dalgalanacaksa, LocalStorage ve hatta Tanımlama Bilgisi gibi bir istemci tarafı önbelleği uygulamak en iyi yöntem olabilir. Bu, önbellek süresi boyunca aynı kullanıcı tarafından yapılan sonraki istekleri ortadan kaldırarak çağrı birimlerini azaltmaya devam eder, ancak ayrılmış önbelleğe alma hizmetinden daha az verimli olur. PnP, LocalStorage'ı çok az ek geliştirmeyle kullanmanıza olanak tanır.

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