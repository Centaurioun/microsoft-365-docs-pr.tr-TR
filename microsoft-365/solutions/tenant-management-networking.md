---
title: Adım 2. Kurumsal kiracılar için Microsoft 365'iniz için en iyi ağ
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Microsoft 365 kiracılarınıza ağ erişimini iyileştirin.
ms.openlocfilehash: f9b5bd30ace8044f1c36e5a1b190ab3d6a4c6203
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67579500"
---
# <a name="step-2-optimal-networking-for-your-microsoft-365-for-enterprise-tenants"></a>Adım 2. Kurumsal kiracılar için Microsoft 365'iniz için en iyi ağ

Kuruluşlar için Microsoft 365, Teams ve Exchange Online gibi bulut üretkenlik uygulamalarını ve Microsoft Intune yanı sıra Microsoft Azure'ın birçok kimlik ve güvenlik hizmetini içerir. Bu bulut tabanlı hizmetlerin tümü, şirket içi ağınızdaki istemci cihazlardan veya İnternet'te herhangi bir konumdan gelen bağlantıların güvenliğine, performansına ve güvenilirliğine dayanır. 

Kiracınızın ağ erişimini iyileştirmek için şunları yapmanız gerekir:

- Şirket içi kullanıcılarınız ile Microsoft Global Network'e en yakın konum arasındaki yolu iyileştirin.
- Uzaktan erişim VPN çözümü kullanan uzak kullanıcılarınız için Microsoft Genel Ağı'na erişimi iyileştirin.
- Ofis konumlarınızın ağ çevresini tasarlamak için Ağ İçgörüleri'ni kullanın.
- Office 365 CDN ile SharePoint sitelerinde barındırılan belirli varlıklara erişimi iyileştirin.
- Uç noktalar listesiyle Microsoft 365 güvenilen trafiği için işlemeyi atlamak için ara sunucu ve ağ uç cihazlarını yapılandırın ve değişiklikler yapıldıkçe listenin güncelleştirilmesini otomatikleştirin.

## <a name="enterprise-on-premises-workers"></a>Kurumsal şirket içi çalışanlar

Kurumsal ağlar için, istemcilerle en yakın Microsoft 365 uç noktaları arasında en yüksek performanslı ağ erişimini etkinleştirerek son kullanıcı deneyimini iyileştirmeniz gerekir. Son kullanıcı deneyiminin kalitesi, kullanıcının kullandığı uygulamanın performansı ve yanıt hızıyla doğrudan ilgilidir. Örneğin Microsoft Teams, kullanıcı telefon aramaları, konferanslar ve paylaşılan ekran işbirliklerinin sorunsuz olması için düşük gecikme süresine dayanır.

Ağ tasarımındaki birincil hedef, istemci cihazlardan Microsoft'un tüm veri merkezlerini düşük gecikme süresi, yüksek kullanılabilirlik bulut uygulaması giriş noktalarıyla birbirine bağlayan microsoft genel ağ omurgası olan Microsoft Global Network'e gidiş dönüş süresini (RTT) azaltarak gecikme süresini en aza indirmek olmalıdır.

Burada geleneksel kurumsal ağ örneği verilmiştir.

![İnternet'e merkezi erişime sahip geleneksel bir kurumsal ağ.](../media/tenant-management-overview/tenant-management-networking-traditional.png)

Bu çizimde, şubeler geniş alan ağı (WAN) cihazları ve WAN omurgası aracılığıyla merkezi bir ofise bağlanır. İnternet erişimi, merkezi ofisin ağ kenarındaki bir güvenlik veya ara sunucu cihazı ve bir İnternet servis sağlayıcısı (ISS) üzerinden gerçekleştirilir. İnternet'te, Microsoft Global Network'ün dünyanın dört bir yanındaki bölgelerde bir dizi ön kapı vardır. Kuruluşlar ayrıca ek paket işleme ve trafik güvenliği için ara konumları da kullanabilir. Bir kuruluşun Microsoft 365 kiracısı Microsoft Global Network'ün içinde yer alır.

Microsoft 365 bulut hizmetleri için bu yapılandırmayla ilgili sorunlar şunlardır:

- Şubelerdeki kullanıcılar için trafik yerel olmayan ön kapılara gönderilerek gecikme süresini artırır.
- Ara konumlara trafik göndermek, güvenilen trafikte yinelenen paket işleme gerçekleştiren ağ saç tokaları oluşturarak gecikme süresini artırır.
- Ağ uç cihazları, güvenilir trafikte gereksiz ve yinelenen paket işleme gerçekleştirerek gecikme süresini artırır.

Microsoft 365 ağ performansını iyileştirmenin karmaşık olması gerekmez. Birkaç temel ilkeyi izleyerek mümkün olan en iyi performansı elde edebilirsiniz:

- Microsoft bulut hizmetlerine yönelik güvenilir trafik olan Microsoft 365 ağ trafiğini belirleyin.
- Kullanıcıların Microsoft 365'e bağlandığı her konumdan İnternet'e microsoft 365 ağ trafiğinin yerel dal çıkışına izin verin.
- Ağ saç tokalarından kaçının.
- Microsoft 365 trafiğinin proxy'leri ve paket denetleme cihazlarını atlamasına izin verin.

Bu ilkeleri uygularsanız Microsoft 365 için iyileştirilmiş bir kurumsal ağ elde edersiniz.

![Microsoft 365 için iyileştirilmiş bir kurumsal ağ.](../media/tenant-management-overview/tenant-management-networking-optimized.png)

Bu çizimde şubelerin, bölgesel olarak en yakın ön kapıya güvenilir Microsoft 365 trafiği gönderen yazılım tanımlı WAN cihazı (SDWAN) cihazı aracılığıyla kendi İnternet bağlantıları vardır. Merkezi ofiste güvenilen Microsoft 365 trafiği güvenlik veya ara sunucu cihazını atlar ve ara cihazlar artık kullanılmaz.

İyileştirilmiş yapılandırmanın geleneksel bir kurumsal ağın gecikme sorunlarını nasıl çözdüğü aşağıda anlatılır:

- Güvenilen Microsoft 365 trafiği WAN omurgasını atlar ve tüm ofisler için yerel ön kapılara gönderilerek gecikme süresini kısaltılır.
- Yinelenen paket işleme gerçekleştiren ağ saç tokaları Microsoft 365 güvenilen trafiği için atlanır ve gecikme süresini kısaltır.
- Gereksiz ve yinelenen paket işleme gerçekleştiren ağ uç cihazları, Microsoft 365 güvenilen trafiği için atlanır ve gecikme süresini kısaltır.

Daha fazla bilgi için bkz. [Microsoft 365 ağ bağlantısına genel bakış](../enterprise/microsoft-365-networking-overview.md).

## <a name="remote-workers"></a>Uzak çalışanlar

Uzak çalışanlarınız kuruluş ağınıza uzaktan erişim elde etmek için geleneksel bir VPN istemcisi kullanıyorsa, VPN istemcisinin bölünmüş tünel desteğine sahip olduğunu doğrulayın. Bölünmüş tünel olmadan, tüm uzaktan çalışma trafiğiniz VPN bağlantısı üzerinden gönderilir; burada kuruluşunuzun uç cihazlarına iletilmesi, işlenmesi ve ardından İnternet'e gönderilmesi gerekir. Burada bir örnek verilmiştir.

![Tünel oluşturmadan VPN istemcilerinden gelen ağ trafiği.](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

Bu çizimde, Microsoft 365 trafiğinin kuruluşunuz üzerinden dolaylı bir yol alması gerekir ve bu yol VPN istemcisinin fiziksel konumundan uzak bir Microsoft Global Network ön kapısına iletilebilir. Bu dolaylı yol ağ trafiğine gecikme ekler ve genel performansı azaltır. 

Bölünmüş tünel ile VPN istemcinizi, belirli trafik türlerinin kuruluş ağına VPN bağlantısı üzerinden gönderilmesini dışlamak üzere yapılandırabilirsiniz.

Microsoft 365 bulut kaynaklarına erişimi iyileştirmek için bölünmüş tünel VPN istemcilerinizi VPN bağlantısı üzerinden **En İyi Duruma Getir** kategorisi Microsoft 365 uç noktalarına trafiği hariç tutacak şekilde yapılandırın. Daha fazla bilgi için bkz. [uç nokta kategorilerini Office 365](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories) ve bölünmüş tünel için kategori uç noktalarını iyileştirme [listeleri](../enterprise/microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling).

Aşağıda, Microsoft 365 bulut uygulamalarına giden trafiğin çoğunun VPN bağlantısını atladığı bölünmüş tünel için ortaya çıkan trafik akışı gösterilir.

![Tünel ile VPN istemcilerinden gelen ağ trafiği.](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

Bu çizimde, VPN istemcisi önemli Microsoft 365 bulut hizmeti trafiğini doğrudan İnternet üzerinden ve en yakın ön kapıya Microsoft Global Network'e gönderir ve alır.

Daha fazla bilgi ve kılavuz için bkz[. VPN bölünmüş tünel kullanarak uzak kullanıcılar için Office 365 bağlantısını iyileştirme](../enterprise/microsoft-365-vpn-split-tunnel.md).

## <a name="using-network-insights-preview"></a>Network Insights'ı kullanma (önizleme)

Ağ içgörüleri, Microsoft 365 kiracınızdan toplanan ve ofis konumlarınız için ağ çevreleri tasarlamanıza yardımcı olan performans ölçümleridir. Her içgörü, şirket içi kullanıcıların kiracınıza eriştiği her coğrafi konum için belirtilen sorunun performans özellikleri hakkında canlı ayrıntılar sağlar.

Kiracı için gösterilebilen iki kiracı düzeyi ağ içgörüleri vardır:

- [Bağlantı sorunlarından etkilenen Exchange örnekli bağlantıları](../enterprise/office-365-network-mac-perf-insights.md#exchange-sampled-connections-affected-by-connectivity-issues)
- [Bağlantı sorunlarından etkilenen SharePoint örnekli bağlantıları](../enterprise/office-365-network-mac-perf-insights.md#sharepoint-sampled-connections-affected-by-connectivity-issues)

Her ofis konumu için belirli ağ içgörüleri şunlardır:

- [Yeniden vurgulanmış ağ çıkışı](../enterprise/office-365-network-mac-perf-insights.md#backhauled-network-egress)
- [Yakınınızda bulunan müşteriler için daha iyi performans algılandı](../enterprise/office-365-network-mac-perf-insights.md#better-performance-detected-for-customers-near-you)
- [En uygun olmayan Exchange Online hizmeti ön kapı kullanımı](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-exchange-online-service-front-door)
- [En uygun olmayan SharePoint Online hizmeti ön kapısı kullanımı](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [SharePoint ön kapısından düşük indirme hızı](../enterprise/office-365-network-mac-perf-insights.md#low-download-speed-from-sharepoint-front-door)
- [Çin kullanıcı en uygun ağ çıkışı](../enterprise/office-365-network-mac-perf-insights.md#china-user-optimal-network-egress)

> [!IMPORTANT]
> Microsoft 365 Yönetici Merkezi'ndeki ağ içgörüleri, performans önerileri ve değerlendirmeler şu anda önizleme durumundadır. Yalnızca özellik önizleme programına kaydedilmiş Microsoft 365 kiracıları için kullanılabilir.

Daha fazla bilgi için bkz. [Microsoft 365 Ağ İçgörüleri](../enterprise/office-365-network-mac-perf-insights.md).

## <a name="sharepoint-performance-with-the-office-365-cdn"></a>Office 365 CDN ile SharePoint performansı

Bulut tabanlı Content Delivery Network (CDN), yük sürelerini azaltmanıza, bant genişliğinden tasarruf etmenizi ve hızlı yanıt vermenizi sağlar. CDN, grafik veya video dosyaları gibi statik varlıkları isteyen tarayıcılara daha yakın önbelleğe alarak performansı artırır ve bu da indirmeleri hızlandırmaya ve gecikme süresini azaltmaya yardımcı olur. SharePoint sayfalarınız için daha iyi performans sağlamak üzere statik varlıkları barındırmak için Microsoft 365 E3 ve E5'te SharePoint'te bulunan yerleşik Office 365 Content Delivery Network'u (CDN) kullanabilirsiniz.

Office 365 CDN, statik varlıkları birden çok konumda veya _kaynakta_ barındırmanıza ve bunları küresel yüksek hızlı ağlardan sunmanıza olanak sağlayan birden çok CDN'den oluşur. Office 365 CDN'de barındırmak istediğiniz içerik türüne bağlı olarak, **genel** kaynaklar, **özel** kaynaklar veya her ikisini birden ekleyebilirsiniz.

Office 365 CDN dağıtıldığında ve yapılandırıldığında, varlıkları genel ve özel kaynaklardan karşıya yükler ve bunları İnternet genelinde bulunan kullanıcılara hızlı erişim için kullanılabilir hale getirir.

![Office 365 kullanıcılar için dağıtılan CDN.](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 kullanıcılar için dağıtılan CDN")

Daha fazla bilgi için bkz. [SharePoint Online ile Office 365 CDN kullanma](../enterprise/use-microsoft-365-cdn-with-spo.md).

## <a name="automated-endpoint-listing"></a>Otomatik uç nokta listesi

Şirket içi istemcilerinizin, uç cihazlarınızın ve bulut tabanlı paket analizi hizmetlerinizin güvenilir Microsoft 365 trafiğinin işlenmesini atlamasını sağlamak için, bunları Microsoft 365 hizmetlerine karşılık gelen uç nokta kümesiyle (IP adresi aralıkları ve DNS adları) yapılandırmanız gerekir. Bu uç noktalar güvenlik duvarlarında ve diğer uç güvenlik cihazlarında, proxy'leri atlayacak istemci bilgisayarlar için PAC dosyalarında veya şube ofislerindeki SD-WAN cihazlarında el ile yapılandırılabilir. Ancak, uç noktalar zaman içinde değişir ve bu konumlardaki uç nokta listelerinin sürekli el ile bakımını gerektirir.

İstemci PAC dosyalarınızda ve ağ cihazlarınızda Microsoft 365 uç noktaları için listeleme ve değişiklik yönetimini otomatikleştirmek için [Office 365 IP Adresi ve URL REST tabanlı web hizmetini](../enterprise/microsoft-365-ip-web-service.md) kullanın. Bu hizmet, Microsoft 365 ağ trafiğini daha iyi tanımlamanıza ve ayırt etmenize yardımcı olur ve en son değişiklikleri değerlendirmenizi, yapılandırmanızı ve güncel kalmanızı kolaylaştırır.

Zaman içinde uç noktalarda yapılan değişiklikleri belirlemek ve PAC dosyalarınızı ve uç ağ cihazlarınızı yapılandırmak için PowerShell, Python veya diğer dilleri kullanabilirsiniz.

Temel işlem:

1. PAC dosyalarınızı ve ağ cihazlarınızı geçerli Microsoft 365 uç noktaları kümesiyle yapılandırmak için Office 365 IP Adresi ve URL web hizmetini ve seçtiğiniz yapılandırma mekanizmasını kullanın.
2. Uç noktalarda değişiklik olup olmadığını denetlemek veya bir bildirim yöntemi kullanmak için günlük yineleme çalıştırın.
3. Değişiklikler algılandığında PAC dosyasını istemci bilgisayarlar için yeniden oluşturun ve yeniden dağıtın ve değişiklikleri ağ cihazlarınızda yapın.

Daha fazla bilgi için bkz. [OFFICE 365 IP Adresi ve URL web hizmeti](../enterprise/microsoft-365-ip-web-service.md).

## <a name="results-of-step-2"></a>2. Adımın Sonuçları

En uygun ağa sahip Microsoft 365 kiracınız için şunları belirlediniz:

- Tüm şube ofislerine İnternet bağlantıları ekleyerek ve ağ saç tokalarını ortadan kaldırarak şirket içi kullanıcılar için ağ performansını iyileştirme.
- İstemci tabanlı PAC dosyalarınız ve devam eden güncelleştirmeler (kurumsal ağlar için en uygun) dahil olmak üzere ağ cihazlarınız ve hizmetleriniz için otomatik güvenilen uç nokta listelemesi uygulama.
- Uzak çalışanların şirket içi kaynaklara erişimini destekleme.
- Ağ İçgörüleri'ni kullanma
- Office 365 CDN'yi dağıtma.

Aşağıda, kurumsal bir kuruluşa ve en uygun ağa sahip kiracısına bir örnek verilmiştir.

![En uygun ağa sahip bir kiracı örneği.](../media/tenant-management-overview/tenant-management-tenant-build-step2.png)

[Bu görüntünün daha büyük bir sürümünü görün](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-management-overview/tenant-management-tenant-build-step2.png)

Bu çizimde, bu kurumsal kuruluşun kiracısı şunları içerir:

- Güvenilen Microsoft 365 trafiğini yerel bir ön kapıya ileden bir SDWAN cihazı ile her şube ofisi için yerel İnternet erişimi.
- Ağ saç tokası yok.
- Microsoft 365 güvenilen trafiğini yerel bir ön kapıya ileten merkezi ofis güvenliği ve ara sunucu uç cihazları.

## <a name="ongoing-maintenance-for-optimal-networking"></a>En iyi ağ için sürekli bakım

Sürekli olarak şunları yapmanız gerekebilir:

- Uç noktalardaki değişiklikler için uç cihazlarınızı ve dağıtılan PAC dosyalarınızı güncelleştirin veya otomatik işleminizin düzgün çalıştığını doğrulayın.
- Office 365 CDN'deki varlıklarınızı yönetin.
- Uç noktalardaki değişiklikler için VPN istemcilerinizdeki bölünmüş tünel yapılandırmasını güncelleştirin.

## <a name="next-step"></a>Sonraki adım

[![3. Adım. Kimliklerinizi eşitleyin ve güvenli oturum açma işlemleri uygulayın.](../media/tenant-management-overview/tenant-management-step-grid-identity.png)](tenant-management-identity.md)

Şirket içi hesaplarınızı ve gruplarınızı eşitlemek ve güvenli kullanıcı oturum açma işlemleri uygulamak için [kimlikle](tenant-management-identity.md) devam edin.
