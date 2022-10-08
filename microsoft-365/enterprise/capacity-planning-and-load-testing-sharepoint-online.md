---
title: SharePoint Online’da kapasite planlaması ve yük testi
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 04/10/2019
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
ms.assetid: c932bd9b-fb9a-47ab-a330-6979d03688c0
description: Bu makalede, izin verilmediğinden geleneksel yük testi gerçekleştirmeden SharePoint Online'a nasıl dağıtım yapabileceğiniz açıklanmaktadır.
ms.openlocfilehash: 26f65adfb5dcfff66d1c732b5c1c1e1783c7b618
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68180725"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a>SharePoint Online’da kapasite planlaması ve yük testi
Bu makalede, SharePoint Online'da yük testine izin verilmediğinden, geleneksel yük testi olmadan SharePoint Online'a nasıl dağıtım yapabileceğiniz açıklanır. SharePoint Online bir bulut hizmetidir ve hizmetteki yük özellikleri, sistem durumu ve genel yük dengelemesi Microsoft tarafından yönetilir.
  
Sitenizi başlatmanın başarısını sağlamaya yönelik en iyi yaklaşım, [portalınızın piyasaya](planportallaunchroll-out.md) sürülmesini planlarken vurgulanan temel ilkeleri, uygulamaları ve önerileri izlemektir.

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a>SharePoint Online'ın Kapasite planlaması gerçekleştirme şekline genel bakış 
SharePoint Online'ın şirket içi dağıtım üzerindeki temel avantajlarından biri, bulutun esnekliği ve dağıtılmış bölgelerdeki kullanıcılar için iyileştirmelerdir. Büyük ölçekli ortamımız günlük olarak milyonlarca kullanıcıya hizmet vermek üzere ayarlanmıştır, bu nedenle grupları dengeleyerek ve genişleterek kapasiteyi etkili bir şekilde ele almamız önemlidir.
  
Büyüme genellikle tek bir gruptaki herhangi bir kiracı için tahmin edilemez olsa da, isteklerin toplam toplamı zaman içinde tahmin edilebilir. SharePoint Online'daki büyüme eğilimlerini belirleyerek gelecekteki genişlemeyi planlayabiliriz.
  
Kapasiteyi verimli bir şekilde kullanmak ve beklenmeyen büyümeyle başa çıkmak için, herhangi bir çiftlikte hizmetin çeşitli öğelerini izleyen ve izleyen otomasyona sahibiz. Ana ölçümlerden biri CPU yükü olan ve ön uç sunucularının ölçeğini artırmak için sinyal olarak kullanılan birden çok ölçüm kullanılır. Buna ek olarak, SQL ortamları zaman içinde yük ve büyümeye göre ölçeklendirileceği ve aşamaların ve dalgaların izlenmesi bu yükün ve büyümenin doğru dağılımını sağladığından [aşamalı /dalga yaklaşımı](planportallaunchroll-out.md) öneririz. 

Kapasite, sürekli olarak daha fazla donanım eklemekten ibaret değildir, aynı zamanda geçerli yük isteklerine hizmet sağladığından emin olmak için bu kapasiteyi yönetmeye ve denetlemeye de bağlıdır. Müşterilerin en iyi deneyime sahip olduklarından emin olmak için önerilen yönergeleri izlemelerini öneririz. Ayrıca hizmette "kötü amaçlı" davranışa izin vermediğimizden emin olmak için azaltma desenleri ve denetimlerimiz olduğu anlamına gelir. Tüm "kötü" davranışlar kasıtlı olmasa da, bu davranışın etkisini sınırladığımızdan emin olmamız gerekir. Azaltma ve bundan kaçınma hakkında daha fazla bilgi için [kısıtlanmaktan kaçınma kılavuzu](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online) makalesini gözden geçirin.

## <a name="why-you-cannot-load-test-sharepoint-online"></a>Test SharePoint Online'ını neden yükleyemiyoruz?
Şirket içi ortamlarda yük testi, ölçek varsayımını doğrulamak ve sonuçta bir çiftliğin kırılma noktasını bulmak için kullanılır; yüke doygunluk sağlayarak. 

SharePoint Online ile, ölçek görece akıcı olduğundan ve belirli buluşsal yöntemlere göre yük ayarlayıp azaltma ve denetim yükü sağladığından işleri farklı yapmamız gerekir. Bu kadar büyük ölçekli çok kiracılı bir ortam olarak, tüm yük testlerini otomatik olarak azaltmamız için aynı gruptaki tüm kiracıları korumamız gerekir. Ancak testi yüklemeyi denerseniz, azaltmanın yanı sıra hayal kırıklığı ve yanıltıcı sonuçlar alırsınız çünkü bugün test ettiğiniz grup muhtemelen test penceresi sırasında veya test sonrasında saatler içinde ölçek değişiklikleri yapmış olacaktır çünkü ölçek ve grup dengeleme eylemleri sürekli olarak gerçekleştirilir.

SharePoint'i hizmet olarak yüklemeye çalışmak yerine önerilen uygulamaları izlemeye odaklanın ve [İyi durumda bir portal oluşturma, başlatma ve koruma](/sharepoint/portal-health) yönergelerini izleyin.