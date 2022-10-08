---
title: Microsoft 365 Ağ İçgörüleri
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/06/2021
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- scotvorg
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Ağ İçgörüleri
ms.openlocfilehash: ce5200708ffd0ec3b9beb3de43b8a5f75fb734c1
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68191969"
---
# <a name="microsoft-365-network-insights"></a>Microsoft 365 Ağ İçgörüleri

**Ağ içgörüleri** , Microsoft 365 kiracınızdan toplanan performans ölçümleridir ve yalnızca kiracınızdaki yönetici kullanıcılar tarafından görüntülenebilir. İçgörüler konumundaki Microsoft 365 Yönetici Merkezi'nde <https://portal.microsoft.com/adminportal/home#/networkperformance>görüntülenir.

İçgörüler, ofis konumlarınız için ağ çevreleri tasarlamaya yardımcı olmak için tasarlanmıştır. Her içgörü, kullanıcıların kiracınıza eriştiği her coğrafi konum için belirli bir yaygın sorunun performans özellikleri hakkında canlı ayrıntılar sağlar.

Her ofis konumu için gösterilebilen altı özel ağ içgörüleri vardır:

- [Yeniden vurgulanmış ağ çıkışı](#backhauled-network-egress)
- [Ağ aracı cihazı](#network-intermediary-device)
- [Yakınınızda bulunan müşteriler için daha iyi performans algılandı](#better-performance-detected-for-customers-near-you)
- [En uygun olmayan Exchange Online hizmeti ön kapı kullanımı](#use-of-a-non-optimal-exchange-online-service-front-door)
- [En uygun olmayan SharePoint Online hizmeti ön kapısı kullanımı](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [SharePoint ön kapısından düşük indirme hızı](#low-download-speed-from-sharepoint-front-door)
- [Çin kullanıcı en uygun ağ çıkışı](#china-user-optimal-network-egress)

Kiracı için gösterilebilen iki kiracı düzeyinde ağ içgörüleri vardır:

- [Bağlantı sorunlarından etkilenen exchange örnekli bağlantıları](#exchange-sampled-connections-affected-by-connectivity-issues)
- [Bağlantı sorunlarından etkilenen SharePoint örnekli bağlantılar](#sharepoint-sampled-connections-affected-by-connectivity-issues)

Bu içgörüler üretkenlik puanı sayfalarında da görünür.

>[!IMPORTANT]
>Microsoft 365 Yönetici Merkezi'ndeki ağ içgörüleri, performans önerileri ve değerlendirmeler şu anda önizleme durumundadır ve yalnızca özellik önizleme programına kaydedilmiş Microsoft 365 kiracıları için kullanılabilir.

## <a name="backhauled-network-egress"></a>Yeniden vurgulanmış ağ çıkışı

Ağ içgörüleri hizmeti belirli bir kullanıcı konumundan ağ çıkışına olan mesafenin 500 milden (800 kilometre) büyük olduğunu algılarsa bu içgörü görüntülenir. Bu, Microsoft 365 trafiğinin ortak bir İnternet uç cihazına veya ara sunucuya geri aktarıldığını gösterebilir.

Bu içgörü, bazı özet görünümlerde "Çıkış" olarak kısaltılır.

> [!div class="mx-imgBorder"]
> ![Geri vurgulanmış ağ çıkışı.](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a>Bu ne anlama geliyor?

Bu, ofis konumu ile ağ çıkışı arasındaki mesafenin 500 milden (800 kilometre) fazla olduğunu tanımlar. Ofis konumu, karartılmış bir istemci makine konumuyla ve ağ çıkış konumu ise konum veritabanlarına ters IP Adresi kullanılarak tanımlanır. Makinelerde Windows Konum Hizmetleri devre dışı bırakılırsa office konumu yanlış olabilir. Ters IP adresi veritabanı bilgileri yanlışsa ağ çıkış konumu yanlış olabilir.

Bu içgörü için ayrıntılar şunlardır:

- Office konumu
- Konumdaki toplam kiracı kullanıcısının tahmini yüzdesi
- Geçerli ağ çıkış konumu
- Çıkış konumunun ilgisi
- Konum ile geçerli çıkış noktası arasındaki uzaklık
- Koşulun ilk algılandığı tarih
- Koşulun çözümlenme tarihi

### <a name="what-should-i-do"></a>Ne yapmalıyım?

Ağ çıkışının ofis konumuna mümkün olduğunca yakın olmasını öneririz.  Microsoft 365 trafiği en uygun şekilde Microsoft'un küresel ağına ve en yakın Microsoft 365 hizmeti ön kapısına yönlendirilmelidir. Kullanıcıların ofis konumlarına yakın ağ çıkışına sahip olmak, Microsoft gelecekte hem ağ iletişim noktalarını hem de Microsoft 365 hizmet ön kapılarını genişlettiklerinden performansın iyileştirilmesine de olanak tanır.

Bu sorunu çözme hakkında daha fazla bilgi için bkz. [Microsoft 365 Ağ Bağlantısı İlkeleri'nde](microsoft-365-network-connectivity-principles.md) [yerel olarak çıkış ağ bağlantıları](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally).

## <a name="network-intermediary-device"></a>Ağ aracı cihazı

Kullanıcılarınız ile Microsoft ağı arasında cihazlar algıladıysak bu içgörü görüntülenir. Gecikme süresine duyarlı Microsoft 365 ağ trafiğinin bu cihazları atlamasını öneririz. Bu öneri ayrıca [Microsoft 365 Ağ Bağlantı İlkeleri'nde](microsoft-365-network-connectivity-principles.md) açıklanmaktadır.

Exchange, SharePoint ve Teams için kritik Microsoft 365 ağ uç noktaları ağ aracı cihazları tarafından kesildiğinde ve şifresi çözülürken SSL kesme ve denetleme olduğunu gösteriyoruz.

### <a name="what-does-this-mean"></a>Bu ne anlama geliyor?

Ara sunucular, VPN'ler ve veri kaybı önleme cihazları gibi ağ aracı cihazları, trafiğin ara erişimli olduğu Microsoft 365 istemcilerinin performansını ve kararlılığını etkileyebilir.

### <a name="what-should-i-do"></a>Ne yapmalıyım?

Microsoft 365 ağ trafiği için işlemeyi atlamak üzere algılanan ağ aracı cihazını yapılandırın.

## <a name="better-performance-detected-for-customers-near-you"></a>Yakınınızda bulunan müşteriler için daha iyi performans algılandı

Ağ içgörüleri hizmeti metro bölgenizdeki önemli sayıda müşterinin bu ofis konumundaki kullanıcılardan daha iyi performansa sahip olduğunu algılarsa bu içgörü görüntülenir.

Bu içgörü, bazı özet görünümlerde "Eşler" olarak kısaltılır.

> [!div class="mx-imgBorder"]
> ![Göreli ağ performansı.](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a>Bu ne anlama geliyor?

Bu içgörü, bu ofis konumuyla aynı şehirde bulunan Microsoft 365 müşterilerinin toplam performansını inceler. Bu içgörü, kullanıcılarınızın ortalama gecikme süresi komşu kiracıların ortalama gecikme süresinden %10 daha fazlaysa görüntülenir.

### <a name="what-should-i-do"></a>Ne yapmalıyım?

Bu durumun şirket ağınızdaki veya ISS'nizdeki gecikme süresi, performans sorunları veya mimari tasarımı sorunları gibi birçok nedeni olabilir. Ofis ağınız ile geçerli Microsoft 365 ön kapısı arasındaki rotadaki her atlama arasındaki gecikme süresini inceleyin. Daha fazla bilgi için bkz. [Microsoft 365 Ağ Bağlantısı İlkeleri](microsoft-365-network-connectivity-principles.md).

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a>En uygun olmayan Exchange Online hizmeti ön kapı kullanımı

Ağ içgörüleri hizmeti belirli bir konumdaki kullanıcıların en uygun Exchange Online hizmeti ön kapısına bağlanmadığını algılarsa bu içgörü görüntülenir.

Bu içgörü, bazı özet görünümlerde "Yönlendirme" olarak kısaltılır.

> [!div class="mx-imgBorder"]
> ![En uygun olmayan EXO ön kapı.](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a>Bu ne anlama geliyor?

Ofis konumu şehrinden kullanıma uygun Exchange Online servis ön kapıları listeledik. Geçerli test, bu listede olmayan bir Exchange Online hizmeti ön kapısının kullanımını gösteriyorsa, bu öneriyi dikkate alıyoruz.

### <a name="what-should-i-do"></a>Ne yapmalıyım?

En uygun olmayan Exchange Online hizmeti ön kapısının kullanılması ağ geri taslağından kaynaklanabilir. Bu durumda yerel ve doğrudan ağ çıkışı öneririz. Uzak bir DNS Özyinelemeli Çözümleyici sunucusu uyguladıysanız, sunucu yapılandırmasını ağ çıkışıyla hizalamanızı öneririz.

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a>En uygun olmayan SharePoint Online hizmeti ön kapısı kullanımı

Ağ içgörüleri hizmeti belirli bir konumdaki kullanıcıların en yakın SharePoint Online hizmeti ön kapısına bağlanmadığını algılarsa bu içgörü görüntülenir.

Bu içgörü, bazı özet görünümlerde "Afd" olarak kısaltılır.

> [!div class="mx-imgBorder"]
> ![En uygun olmayan SPO ön kapı.](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a>Bu ne anlama geliyor?

Test istemcisinin bağlandığını SharePoint Online hizmeti ön kapısını tanımlarız. Ardından, ofis konumu şehri için bu şehri beklenen SharePoint Online hizmeti ön kapısıyla karşılaştırıyoruz. Eşleşmiyorsa bu öneriyi yaparız.

### <a name="what-should-i-do"></a>Ne yapmalıyım?

En uygun olmayan bir SharePoint Online hizmeti ön kapısının kullanılması, şirket ağ çıkışından önce ağ geri akışından kaynaklanabilir. Bu durumda yerel ve doğrudan ağ çıkışı öneririz. Bunun nedeni uzak DNS Özyinelemeli Çözümleyici sunucusunun kullanılması olabilir. Bu durumda DNS Özyinelemeli Çözümleyici sunucusunu ağ çıkışıyla hizalamanızı öneririz.

## <a name="low-download-speed-from-sharepoint-front-door"></a>SharePoint ön kapısından düşük indirme hızı

Ağ içgörüleri hizmeti belirli bir ofis konumu ile SharePoint Online arasındaki bant genişliğinin 1 MB/sn'den az olduğunu algılarsa bu içgörü görüntülenir.

Bu içgörü, bazı özet görünümlerde "Aktarım Hızı" olarak kısaltılır.

### <a name="what-does-this-mean"></a>Bu ne anlama geliyor?

Bir kullanıcının SharePoint Online ve OneDrive İş hizmeti ön kapılarından alabildiği indirme hızı saniyede megabayt (MB/sn) cinsinden ölçülür. Bu değer 1 MB/sn'den küçükse bu içgörüleri sağlarız.

### <a name="what-should-i-do"></a>Ne yapmalıyım?

İndirme hızlarını artırmak için bant genişliğinin artırılması gerekebilir. Alternatif olarak, ofis konumundaki bilgisayarlar ile SharePoint Online hizmeti ön kapısı arasında ağ tıkanıklığı olabilir. Bu koşul, yeterli bant genişliği sağlansa bile kullanıcılar için kullanılabilir indirme hızını kısıtlar.

## <a name="china-user-optimal-network-egress"></a>Çin kullanıcı en uygun ağ çıkışı

Kuruluşunuzun Çin'de microsoft 365 kiracınıza diğer coğrafi konumlarda bağlanan kullanıcıları varsa bu içgörü görüntülenir.

### <a name="what-does-this-mean"></a>Bu ne anlama geliyor?

Kuruluşunuzun özel WAN bağlantısı varsa, Çin'deki ofis konumlarınızdan aşağıdaki konumlardan herhangi birinde İnternet'e ağ çıkışı olan bir ağ WAN bağlantı hattı yapılandırmanızı öneririz:

- Hong Kong
- Japonya
- Tayvan
- Güney Kore
- Singapur
- Malezya

İnternet çıkışı, kullanıcılardan bu konumlardan daha uzaktayken performansı düşürür ve Çin'de çıkış, sınır ötesi tıkanıklık nedeniyle yüksek gecikme süresine ve bağlantı sorunlarına neden olabilir.

### <a name="what-should-i-do"></a>Ne yapmalıyım?

Bu içgörüyle ilgili performans sorunlarını azaltma hakkında daha fazla bilgi için bkz. [Çin kullanıcıları için Microsoft 365 genel kiracı performansı iyileştirmesi](microsoft-365-networking-china.md).

## <a name="exchange-sampled-connections-affected-by-connectivity-issues"></a>Bağlantı sorunlarından etkilenen exchange örnekli bağlantıları

Bu içgörü, örneklenen bağlantıların %50'sinin veya daha fazlasının ne zaman etkilendiğini gösterir. Etki, Exchange değerlendirmesinin her örnek için %60'ın altında olmasıyla tanımlanır.

### <a name="what-does-this-mean"></a>Bu ne anlama geliyor?

Bu, kullanıcılarınızın çoğunun Outlook'un Exchange Online'a bağlanırken büyük olasılıkla sorun yaşadığını gösterir. Örneklerin yüzdesi, 60'ın altında puan gösteren kullanıcıların yüzdesini temsil eder.  

### <a name="what-should-i-do"></a>Ne yapmalıyım?

Henüz yapmadıysanız office konumu ağ bağlantısı görünürlüğünü etkinleştirin. Zayıf ağ bağlantısından hangi ofislerin etkilendiğini belirleyin ve kullanıcıları Microsoft'un ağına bağlayan ağ çevresini geliştirmenin yollarını bulun.

## <a name="sharepoint-sampled-connections-affected-by-connectivity-issues"></a>Bağlantı sorunlarından etkilenen SharePoint örnekli bağlantılar

Bu içgörü, örneklenen bağlantıların %50'sinin veya daha fazlasının ne zaman etkilendiğini gösterir. Etki, SharePoint değerlendirmesinin her örnek için %40'ın altında olmasıyla tanımlanır.

### <a name="what-does-this-mean"></a>Bu ne anlama geliyor?

Bu, kullanıcılarınızın çoğunun SharePoint ve OneDrive ile ilgili sorunlar yaşadığını gösterir. Örneklerin yüzdesi, 40'ın altında puan gösteren kullanıcıların yüzdesini temsil eder.  

### <a name="what-should-i-do"></a>Ne yapmalıyım?

Henüz yapmadıysanız office konumu ağ bağlantısı görünürlüğünü etkinleştirin. Zayıf ağ bağlantısından hangi ofislerin etkilendiğini belirleyin ve kullanıcıları Microsoft'un ağına bağlayan ağ çevresini geliştirmenin yollarını bulun.

## <a name="related-topics"></a>İlgili konular

[Microsoft 365 Yönetici Merkezi'nde ağ bağlantısı](office-365-network-mac-perf-overview.md)

[Microsoft 365 ağ değerlendirmesi](office-365-network-mac-perf-score.md)

[Microsoft 365 ağ bağlantısı test aracı](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Ağ Bağlantısı Konum Hizmetleri](office-365-network-mac-location-services.md)
