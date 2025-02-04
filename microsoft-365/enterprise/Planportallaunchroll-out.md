---
title: SharePoint Online'da portalı başlatma dağıtım planınızı planlama
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: Bu makalede, SharePoint Online'da portal başlatmanızı nasıl planlayabileceğiniz ve başarılı bir başlatma için atılması gereken adımlar açıklanmaktadır
ms.openlocfilehash: 572300720aafc720befd954cf2d250d41b94dc9b
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68198569"
---
# <a name="planning-your-portal-launch-roll-out-plan-in-sharepoint-online"></a>SharePoint Online'da portalı başlatma dağıtım planınızı planlama

Portal, intranetinizdeki bir SharePoint sitesidir ve sitedeki içeriği kullanan birçok site görüntüleyicisi vardır. Büyük kuruluşların birkaç portalı olabilir. Örneğin, bir şirket portalı ve bir İk portalı. Genellikle portallarda siteyi ve içeriğini oluşturan ve yazan kişi sayısı nispeten azdır. Portalın ziyaretçilerin çoğu yalnızca içeriği okur ve tüketir.

Bu makalede, SharePoint Online'da dağıtım ve dağıtım planınızı planlama açıklanmaktadır. Ayrıca, SharePoint Online'da geleneksel yük testlerine izin verilmediğinden izleyebileceğiniz yaklaşımlar da sağlar. SharePoint Online bir bulut hizmetidir ve hizmetteki yük özellikleri, sistem durumu ve genel yük dengelemesi Microsoft tarafından yönetilir.

Başarılı bir portal oluşturmaya yardımcı olmak için, sağlıklı bir portal oluşturma, başlatma ve sürdürme konusunda ayrıntılı olarak açıklanan temel ilkeleri[, uygulamaları ve](/sharepoint/portal-health) önerileri izleyin

Dağıtım yaklaşımı aşağıda vurgulanır.

## <a name="portal-launch-scheduler"></a>Portal Başlatma Zamanlayıcısı

Portalınızı kuruluşunuzdaki kullanıcılara zamanlanmış aşamalarda yayınlamak için portal başlatma zamanlayıcısını kullanın. Daha fazla bilgi edinin:

![Takvim simgesi.](../media/calendar.png) [Portal Başlatma Zamanlayıcısı](/microsoft-365/enterprise/portallaunchscheduler)

## <a name="overview-of-capacity-planning-in-sharepoint-online"></a>SharePoint Online'da kapasite planlamasına genel bakış

Kapasiteyi verimli bir şekilde kullanmak ve beklenmeyen büyümeyle başa çıkmak için herhangi bir çiftlikte belirli kullanım senaryolarını izleyen otomasyona sahibiz. Herhangi bir gruptaki herhangi bir kiracı için tam büyüme öngörülemez olsa da, isteklerin toplam toplamı zaman içinde tahmin edilebilir. SharePoint Online'daki büyüme eğilimlerini belirleyerek gelecekteki genişlemeyi planlayabiliriz. [SharePoint Online'da kapasite planlaması ve yük testi](capacity-planning-and-load-testing-sharepoint-online.md) hakkında daha fazla bilgi için.

Başarılı bir başlatmanın önemli bir parçası, aşağıda ayrıntılı olarak açıklanan "dalga" veya "aşamalı dağıtım" yaklaşımıdır.

## <a name="can-i-load-test-sharepoint-online"></a>SharePoint Online testlerini yükleyebilir miyim?

SharePoint Online, gruplarda dengelenen ve ölçek sürekli olarak ayarlanan paylaşılan çok kiracılı bir ortamdır. SharePoint Online gibi bir ortamın yük testi, ölçek değişiklikleri sürekli olarak size yalnızca beklenmeyen sonuçlar vermez ancak buna izin verilmez.

Daha fazla bilgi edinin:  [SharePoint Online'da kapasite planlaması ve yük testi](capacity-planning-and-load-testing-sharepoint-online.md)

## <a name="optimize-pages-by-following-recommended-guidelines"></a>Önerilen yönergeleri izleyerek sayfaları iyileştirme

Şirket içi dağıtımdaki sayfalar, SharePoint Online için önerilen yönergelere göre gözden geçirilmeden SharePoint Online'a taşındıkları gibi taşınmamalıdır. En iyi yaklaşım, kuruluşunuzdaki çoğu kullanıcının sitelerinizin başlangıç noktası olarak erişeceği yer olduğundan, SharePoint'teki herhangi bir site veya portal için her zaman herhangi bir giriş sayfasını iyileştirmektir.

Birkaç temel faktör dikkate alınmalıdır:

- Şirket içi dağıtımlar nesne önbelleği, çıkış önbelleği ve blob önbelleği gibi geleneksel sunucu tarafı önbellekleri kullanabilir. Buluttaki topoloji farklılıklarıyla, ölçek farklılıklarının daha az uygulanabilir yaklaşımlar haline getirmesi için bu seçeneklerin mevcut olması şart değildir.
- Bulut tüketimi için kullanılan tüm sayfalar/özellikler/özelleştirmeler, farklı alanlarda veya bölgelerdeki kullanıcıların daha tutarlı bir deneyime sahip olması için daha yüksek gecikme süresi ve kullanıcıların dağıtılmış konumları için iyileştirilmelidir. Bulut, dağıtılmış bir kullanıcı tabanı için iyileştirme yapmak için content delivery networks (CDN) gibi iyileştirmeler sunar ve modern SharePoint için bilinen son iyi (LKG) kullanıma hazır (OOTB) web bölümlerimiz tarafından kullanılır.

**Yapılması gerekenler**:

- SharePoint Online'daki tüm site sayfaları için, analiz etme ve rehberlik sağlama konusunda yardımcı olan Chromium bir uzantı olan [Sayfa Tanılama aracını](./page-diagnostics-for-spo.md) kullanın. Bu araç, analiz ve iyileştirme için bir başlangıç noktası olarak tasarlandığından site sahipleri, düzenleyiciler, yöneticiler ve geliştiriciler tarafından kullanılabilir.
- Geliştiriciler ayrıca modern sayfalarda tarayıcıda F12 tarayıcı geliştirici aracı ve CTRL-F12 gibi geliştirme araçlarını kullanmalıdır. [Fiddler](https://www.telerik.com/download/fiddler) , sayfanın boyutunu (sayfanın megabayt cinsinden ne kadar büyük olduğunu) ve genel sayfa yükünü etkileyen çağrı ve öğe sayısını gözden geçirmek için de kullanılabilir.

Bu bölüm, sayfaları iyileştirmeye yönelik kısa bir özetti.  Daha fazla bilgi edinmek için bkz.  [Sağlıklı bir portal oluşturma, başlatma ve koruma](/sharepoint/portal-health).

## <a name="follow-a-wave--phased-roll-out-approach"></a>Dalga / Aşamalı dağıtım yaklaşımını izleme

Site lansmanları için geleneksel büyük patlama yaklaşımı özelleştirmelerin, dış kaynakların, hizmetlerin veya işlemlerin doğru ölçekte test edildiğini doğrulamaya izin vermez. Bu yaklaşım, başlatmanın aylar süreceği anlamına gelmez, ancak kuruluşunuzun boyutuna bağlı olarak en az birkaç gün boyunca önerilir. Bu nedenle bir dalga dağıtım planını takip etmek, sonraki aşamaya geçmeden önce sorunları duraklatma ve çözme seçeneği sunar ve bu nedenle herhangi bir sorundan etkilenen olası kullanıcı sayısını düşürür. Hizmet olarak SharePoint, kapasitenizi kullanıma ve tahmin edilen kullanıma göre ölçeklendirir ve lansmanınızı bize bildirmeniz gerekmese de, başarıyı sağlamak için yönergeleri izlemeniz gerekir.

Aşağıdaki görüntüde gösterildiği gibi, davet edilen kullanıcıların sayısı genellikle siteyi gerçekten kullananlardan önemli ölçüde daha fazladır. Bu görüntüde bir sürümün nasıl dağıtılmasının nasıl yapıldığını gösteren bir strateji gösterilmektedir. Bu yöntem, kullanıcıların çoğu görmeden önce SharePoint sitesini geliştirmenin yollarını belirlemeye yardımcı olur.

![Davet edilen ve etkin kullanıcıları gösteren grafik.](../media/0bc14a20-9420-4986-b9b9-fbcd2c6e0fb9.png)

Pilot aşamada, kullanıcılardan kuruluşun güvendiği ve etkileşime geçeceğini bildiği geri bildirim almak iyidir. Bu şekilde sistemin nasıl kullanıldığını ve nasıl performans sergilemekte olduğunu ölçmek mümkündür.

Dalgaların her biri sırasında, her dağıtım dalgası sırasında özellikler ve performansla ilgili kullanıcı geri bildirimlerini toplayın. Geri bildirim toplama, sisteme yavaş bir şekilde giriş yapma ve sistem daha fazla kullandıkça iyileştirmeler yapma avantajına sahiptir. Bu, site daha fazla kullanıcıya dağıtıldığından ve sayfa iyileştirme yönergelerini izleyerek kullanıcılarınız için olumlu bir deneyim sağladığından artan yüke tepki vermemizi de sağlar.

**Yapılması gerekenler**:

- Her aşamanın zamanlamasına karar verin ve devam etmeden önce ayarlamalar yapmanız gerekiyorsa bir olasılık /duraklatma fırsatına sahip olduğunuzdan emin olun
- İlerlemeniz için gereken geri bildirimi aldığınızdan emin olmak için etkinleştirmek istediğiniz ilk kullanıcı grubunuzu planlayın.  Mümkün olduğunda, zamanında geri bildirim sağlayacak etkin bir kullanıcı grubu seçin
- Her dalgayı planladığınızda, küçük bir kullanıcı tabanıyla (5000'den az kullanıcı) başlamayı deneyin. Her dalgayla devam ederken grup boyutlarını artırın. Aşamalı bir yaklaşım oluşturarak gerektiğinde daha kolay duraklatma fırsatları sağlar.
