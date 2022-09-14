---
title: İçerik teslim ağları
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 07/15/2020
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 0140f704-6614-49bb-aa6c-89b75dcd7f1f
description: Office 365 performansı geliştirmek için Content Delivery Networks'i (CDN) nasıl kullandığı hakkında bilgi edinmek için bu bilgileri kullanın.
ms.openlocfilehash: a210182c150dbfc8b14a3034fbc89e9948ba482a
ms.sourcegitcommit: 37e137535c4f70702afe1a5eeaa899c75ee02cfd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2022
ms.locfileid: "67664713"
---
# <a name="content-delivery-networks-cdns"></a>İçerik Teslim Ağları (CDN'ler)

*Bu makale hem Microsoft 365 Kurumsal hem de Office 365 Kurumsal için geçerlidir.*

CDN'ler son kullanıcılar için Office 365 hızlı ve güvenilir tutmaya yardımcı olur. Office 365 gibi bulut hizmetleri, indirmeleri hızlandırmak ve algılanan son kullanıcı gecikme süresini azaltmak için statik varlıkları tarayıcılara daha yakın bir şekilde önbelleğe almak için CDN'leri kullanır. Bu konudaki bilgiler, content delivery networks (CDN) ve bunların Office 365 tarafından nasıl kullanıldığı hakkında bilgi edinmenize yardımcı olacaktır.

## <a name="what-exactly-is-a-cdn"></a>CDN tam olarak nedir?

CDN, yüksek hızlı omurga ağları tarafından bağlanan veri merkezlerindeki proxy ve dosya sunucularından oluşan coğrafi olarak dağıtılmış bir ağdır. CDN'ler, bir web sitesindeki veya hizmetteki belirli bir dosya ve nesne kümesinin gecikme süresini ve yükleme sürelerini azaltmak için kullanılır. CdN'de, herhangi bir konumdan gelen isteklerin en iyi şekilde bakımı için binlerce uç nokta bulunabilir.

CDN'ler genellikle Javascript dosyaları, simgeler ve resimler gibi bir web sitesi veya hizmet için genel içeriğin daha hızlı indirilmesi için kullanılır ve ayrıca SharePoint Online belge kitaplıklarındaki dosyalar, akış medya dosyaları ve özel kod gibi kullanıcı içeriğine özel erişim sağlayabilir.

CDN'ler çoğu kurumsal bulut hizmeti tarafından kullanılır. Office 365 gibi bulut hizmetleri, bir kerede özel içerik (e-postalar gibi) ve genel içerik (simgeler gibi) karışımını indiren milyonlarca müşteriye sahiptir. Simgeleri gibi herkesin kullandığı görüntüleri kullanıcının bilgisayarına mümkün olduğunca yaklaştırmak daha verimlidir. Her bulut hizmetinin bu genel içeriği her metropol bölgesinde, hatta dünyanın her yanındaki tüm büyük İnternet merkezlerinde depolayan CDN veri merkezleri oluşturması pratik değildir, bu nedenle bu CDN'lerden bazıları paylaşılır.

## <a name="how-do-cdns-make-services-work-faster"></a>CDN'ler hizmetlerin daha hızlı çalışmasını nasıl sağlar?

Site görüntüleri ve simgeler gibi yaygın nesneleri tekrar tekrar indirmek, e-posta veya belgeler gibi önemli kişisel içerikleri indirmek için daha iyi kullanılabilecek ağ bant genişliğini alabilir. Office 365 CDN'leri içeren bir mimari kullandığından, istemci bilgisayarlara daha yakın sunuculardan simgeler, betikler ve diğer genel içerik indirilebilir ve böylece indirmeler daha hızlı hale getirilebilir. Bu, Office 365 veri merkezlerinde güvenli bir şekilde depolanan kişisel içeriğinize daha hızlı erişim anlamına gelir.

CDN'ler bulut hizmeti performansını çeşitli yollarla iyileştirmeye yardımcı olur:

- CDN'ler ağın ve dosya indirme yükünün bir kısmını bulut hizmetinden uzaklaştırarak, statik varlıklara yönelik istekleri sunma gereksinimini azaltarak kullanıcı içeriği ve diğer hizmetleri sunmak için bulut hizmeti kaynaklarını serbest bırakabilirsiniz.
- CDN'ler, yüksek performanslı ağlar ve dosya sunucuları uygulayarak ve [HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) gibi güncelleştirilmiş ağ protokollerinden son derece verimli sıkıştırma ve istek çoğullama ile yararlanarak düşük gecikme süreli dosya erişimi sağlamak için oluşturulmuş bir amaçtır.
- CDN ağları, içeriğin kullanıcılara mümkün olduğunca yakın olmasını sağlamak için genel olarak dağıtılmış birçok uç nokta kullanır.

## <a name="the-office-365-cdn"></a>Office 365 CDN

Yerleşik Office 365 Content Delivery Network (CDN), Office 365 yöneticilerinin statik varlıkları isteyen tarayıcılara daha yakın önbelleğe alarak kuruluşlarının SharePoint Online sayfaları için daha iyi performans sağlamasına olanak tanır ve bu da indirmeleri hızlandırmaya ve gecikme süresini azaltmaya yardımcı olur. Office 365 CDN, gelişmiş sıkıştırma ve indirme hızları için [HTTP/2 protokollerini](https://en.wikipedia.org/wiki/HTTP/2) kullanır.

> [!NOTE]
> Office 365 CDN yalnızca **Üretim** (dünya çapında) bulutundaki kiracılar tarafından kullanılabilir. ABD Hükümeti, Çin ve Almanya bulutlarındaki kiracılar şu anda Office 365 CDN'yi desteklememektedir.

Office 365 CDN, statik varlıkları birden çok konumda veya _kaynakta_ barındırmanıza ve bunları küresel yüksek hızlı ağlardan sunmanıza olanak sağlayan birden çok CDN'den oluşur. Office 365 CDN'de barındırmak istediğiniz içerik türüne bağlı olarak **genel kaynaklar,** **özel** kaynaklar veya her ikisini birden ekleyebilirsiniz.

![CDN kavramsal diyagramını Office 365.](../media/O365-CDN/o365-cdn-flow-transparent.svg "CDN kavramsal diyagramını Office 365")

Office 365 CDN içindeki **genel** kaynaklardan gelen içeriğe anonim olarak erişilebilir ve barındırılan varlıklara URL'leri olan herkes erişebilir. Genel kaynaklardaki içeriğe erişim anonim olduğundan, bunları yalnızca Javascript dosyaları, betikler, simgeler ve görüntüler gibi hassas olmayan genel içerikleri önbelleğe almak için kullanmanız gerekir. Office 365 CDN, Office 365 istemci uygulamaları gibi genel kaynak varlıklarını genel bir kaynaktan indirmek için varsayılan olarak kullanılır.

Office 365 CDN içindeki **özel** kaynaklar, SharePoint Online belge kitaplıkları, siteler ve özel görüntüler gibi kullanıcı içeriğine özel erişim sağlar. Özel kaynaklardaki içeriğe erişim, dinamik olarak oluşturulan belirteçlerle güvenli hale getirildiğinden, içeriğe yalnızca özgün belge kitaplığı veya depolama konumu izinleri olan kullanıcılar tarafından erişilebilir. Office 365 CDN'deki özel kaynaklar yalnızca SharePoint Online içeriği için kullanılabilir ve varlıklara yalnızca SharePoint Online kiracınızdan yeniden yönlendirme yoluyla erişebilirsiniz.

Office 365 CDN hizmeti, SharePoint Online aboneliğinizin bir parçası olarak dahil edilir.

Office 365 CDN'yi kullanma hakkında daha fazla bilgi için bkz. [SharePoint Online ile Office 365 içerik teslim ağını kullanma](use-microsoft-365-cdn-with-spo.md).

Office 365 CDN kullanımı hakkında kavramsal ve HOWTO bilgileri sağlayan bir dizi kısa video izlemek için [SharePoint Geliştirici Desenleri ve Uygulamaları YouTube kanalını ziyaret edin](https://aka.ms/sppnp-videos).

## <a name="other-microsoft-cdns"></a>Diğer Microsoft CDN'leri

Office 365 CDN'nin bir parçası olmasa da, sharepoint geliştirme kitaplıklarına, özel koda ve Office 365 CDN kapsamının dışında kalan diğer amaçlara erişmek için bu CDN'leri Office 365 kiracınızda kullanabilirsiniz.

### <a name="azure-cdn"></a>Azure CDN

>[!NOTE]
>3. Çeyrek 2020'den itibaren SharePoint Online, geliştirilmiş video kayıttan yürütmeyi ve güvenilirliği desteklemek için Azure CDN'de videoları önbelleğe almaya başlayacaktır. Popüler videolar kullanıcıya en yakın CDN uç noktasından akışla aktarılacaktır. Bu veriler Microsoft Purview sınırı içinde kalır. Bu, tüm kiracılar için ücretsiz bir hizmettir ve yapılandırmak için herhangi bir müşteri eylemi gerektirmez.

Özel web bölümlerini, kitaplıkları ve diğer kaynak varlıklarını barındırmak üzere kendi CDN örneğinizi dağıtmak için **Azure CDN'yi** kullanabilirsiniz. Bu sayede CDN depolama alanınıza erişim anahtarları uygulayabilir ve CDN yapılandırmanız üzerinde daha fazla denetim sağlayabilirsiniz. Azure CDN kullanımı ücretsiz değildir ve bir Azure aboneliği gerektirir.

Azure CDN örneğini yapılandırma hakkında daha fazla bilgi için bkz [. Hızlı Başlangıç: Azure depolama hesabını Azure CDN ile tümleştirme](/azure/cdn/cdn-create-a-storage-account-with-cdn).

Azure CDN'nin SharePoint web bölümlerini barındırmak için nasıl kullanılabileceğini gösteren bir örnek için bkz. [SharePoint istemci tarafı web bölümünüzü Azure CDN'ye dağıtma](/sharepoint/dev/spfx/web-parts/get-started/deploy-web-part-to-cdn).

Azure CDN PowerShell modülü hakkında bilgi için bkz. [Azure CDN'yi PowerShell ile yönetme](/azure/cdn/cdn-manage-powershell).

### <a name="microsoft-ajax-cdn"></a>Microsoft Ajax CDN

**Microsoft'un Ajax CDN'si**, jQuery (ve diğer tüm kitaplıkları), ASP.NET Ajax, Bootstrap, Knockout.js ve diğerleri gibi birçok popüler geliştirme kitaplığı sunan salt okunur bir CDN'dir.
  
Bu betikleri projenize eklemek için, bu genel kullanıma açık kitaplıklara yapılan başvuruları projenize eklemek yerine CDN adresine yapılan başvurularla değiştirmeniz yeterlidir. Örneğin, jQuery'ye bağlanmak için aşağıdaki kodu kullanın:

``` html
<script src=https://ajax.aspnetcdn.com/ajax/jquery-2.1.1.js> </script>
```

Microsoft Ajax CDN'yi kullanma hakkında daha fazla bilgi için bkz. [Microsoft Ajax CDN](/aspnet/ajax/cdn/overview).

## <a name="how-does-office-365-use-content-from-a-cdn"></a>Office 365 CDN'den gelen içeriği nasıl kullanır?

Office 365 kiracınız için hangi CDN'yi yapılandırdığınızdan bağımsız olarak, temel veri alma işlemi aynıdır.

1. İstemciniz (tarayıcı veya Office istemci uygulaması) Office 365'dan veri ister.

2. Office 365 verileri doğrudan istemcinize döndürür veya veriler CDN tarafından barındırılan bir içerik kümesinin parçasıysa istemcinizi CDN URL'sine yönlendirir.

    a. Veriler zaten _genel_ bir kaynakta önbelleğe alınmışsa, istemciniz verileri doğrudan en yakın CDN konumundan istemcinize indirir.

    b. Veriler zaten _özel_ bir kaynakta önbelleğe alınmışsa CDN hizmeti, Office 365 kullanıcı hesabınızın kaynak üzerindeki izinlerini denetler. İzinleriniz varsa SharePoint Online, CDN ve iki erişim belirtecindeki varlığın yolundan oluşan özel bir URL'yi dinamik olarak oluşturur ve istemcinizin özel URL'sini döndürür. Ardından istemciniz, özel URL'yi kullanarak verileri doğrudan en yakın CDN konumundan istemcinize indirir.

3. Veriler CDN'de önbelleğe alınmadıysa, CDN düğümü verileri Office 365'dan talep eder ve istemciniz verileri indirdikten sonra verileri zaman için önbelleğe alır.

CDN, kullanıcının tarayıcısına en yakın veri merkezini görür ve yeniden yönlendirmeyi kullanarak istenen verileri oradan indirir. CDN yeniden yönlendirmesi hızlıdır ve kullanıcılara çok fazla indirme süresi kazandırabilir.

## <a name="how-should-i-set-up-my-network-so-that-cdns-work-best-with-office-365"></a>CDN'lerin Office 365 ile en iyi şekilde çalışması için ağımı nasıl ayarlamam gerekir?

Ağınızdaki istemciler ile CDN uç noktaları arasındaki gecikme süresini en aza indirmek, en iyi performansı sağlamak için dikkat edilmesi gereken önemli noktadır. Ağ yapılandırmanızın gereksiz gecikme süresinden kaçınmak için CDN trafiğini merkezi proxy'ler üzerinden yönlendirmek yerine istemci tarayıcılarının CDN'ye doğrudan erişmesine izin vermesini sağlamak için [Office 365 uç noktalarını yönetme](managing-office-365-endpoints.md) bölümünde açıklanan en iyi yöntemleri kullanabilirsiniz.

Office 365 ağ performansını iyileştirmenin ardındaki kavramları anlamak için Office 365 [Ağ Bağlantısı İlkeleri'ni](./microsoft-365-network-connectivity-principles.md) de okuyabilirsiniz.

## <a name="is-there-a-list-of-all-the-cdns-that-office-365-uses"></a>Office 365 tarafından kullanılan tüm CDN'lerin listesi var mı?

Office 365 tarafından kullanılan CDN'ler her zaman değiştirilebilir ve çoğu durumda bir cdn iş ortağının kullanılamadığı durumlarda yapılandırılmış birden çok CDN iş ortağı vardır. Office 365 tarafından kullanılan birincil CDN'ler şunlardır:

|Cdn  |Şirket  |Kullanım  |Bağlantı  |
|---------|---------|---------|---------|
|CDN Office 365     |Microsoft Azure         |Genel kaynaklarda genel varlıklar, özel kaynaklarda SharePoint kullanıcı içeriği         |[Microsoft Azure CDN](/azure/frontdoor/)         |
|Azure CDN     |Microsoft         |Özel kod, SharePoint Framework çözümleri         |[Microsoft Azure CDN](/azure/frontdoor/)         |
|Microsoft Ajax CDN (salt okunur)     |Microsoft         |Ajax, jQuery, ASP.NET, Bootstrap, Knockout.js vb. için ortak kitaplıklar.         |[Microsoft Ajax CDN](/aspnet/ajax/cdn/overview)         |

## <a name="what-performance-gains-does-a-cdn-provide"></a>CDN hangi performans kazançlarını sağlar?

Doğrudan Office 365 indirilen veriler ile belirli bir CDN'den indirilen veriler arasındaki performans farklarının ölçülmesiyle ilgili birçok faktör vardır. Örneğin, kiracınıza ve en yakın CDN uç noktasına göre konumunuz, CDN tarafından sunulan sayfadaki varlık sayısı ve ağ gecikme süresi ile bant genişliğindeki geçici değişiklikler. Ancak basit bir A/B testi, belirli bir dosya için indirme süresi farkını göstermeye yardımcı olabilir.

Aşağıdaki ekran görüntüleri, Office 365'daki yerel dosya konumu ile [Microsoft Ajax Content Delivery Network'te](/aspnet/ajax/cdn/overview) barındırılan dosya arasındaki indirme hızı farkını gösterir. Bu ekran görüntüleri Internet Explorer 11 geliştirici araçlarının **Ağ** sekmesinden alınmaktadır. Bu ekran görüntüleri popüler jQuery kitaplığındaki gecikme süresini gösterir. Bu ekranı açmak için Internet Explorer'da **F12** tuşuna basın ve Wi-Fi simgesiyle simgelenmiş **Ağ** sekmesini seçin.
  
![F12 Ağı'nın ekran görüntüsü.](../media/930541fd-af9b-434a-ae18-7bda867be128.png)
  
Bu ekran görüntüsü, SharePoint Online sitesinin kendisinde ana sayfa galerisine yüklenen kitaplığı gösterir. Kitaplığı karşıya yüklemek için geçen süre 1,51 saniyedir.
  
![Yükleme süresi 1,51'lerin ekran görüntüsü.](../media/64225c79-fa53-480f-81cd-0d351674320e.png)
  
İkinci ekran görüntüsü, Microsoft'un CDN'sinin teslim ettiği dosyanın aynısını gösterir. Bu kez gecikme süresi yaklaşık 496 milisaniyedir. Bu büyük bir geliştirmedir ve nesneyi indirmek için toplam süre boyunca bir saniyenin tıraşlandığını gösterir.
  
![469 ms içindeki yükleme sürelerinin ekran görüntüsü.](../media/6a553cc3-25a0-42c1-aae7-4aebbc2eb4c3.png)

## <a name="is-my-data-safe"></a>Verilerim güvenli mi?

İşinizi yürüten verileri korumak için büyük özen gösteririz. Office 365 CDN'de depolanan veriler hem aktarımda hem de beklemede şifrelenir ve SharePoint CDN Office 365 veri erişimi Office 365 kullanıcı izinleri ve belirteç yetkilendirmesi ile güvenli hale getirilir. Office 365 SharePoint CDN'sindeki veri isteklerinin Office 365 kiracınızdan yönlendirilmesi (yeniden yönlendirilmesi) gerekir, aksi durumda yetkilendirme belirteci oluşturulmaz.

Verilerinizin güvenli kalmasını sağlamak için, kullanıcı içeriğini veya diğer hassas verileri hiçbir zaman genel CDN'de depolamamanızı öneririz. Genel CDN'deki verilere erişim anonim olduğundan, genel CDN'ler yalnızca web betiği dosyaları, simgeler, resimler ve diğer hassas olmayan varlıklar gibi genel içeriği barındırmak için kullanılmalıdır.

> [!NOTE]
> Üçüncü taraf CDN sağlayıcıları, Office 365 Güven Merkezi tarafından belirtilen taahhütlerden farklı gizlilik ve uyumluluk standartlarına sahip olabilir. CDN hizmeti aracılığıyla önbelleğe alınan veriler Microsoft Veri İşleme Koşulları'na (DPT) uymayabilir ve Office 365 Güven Merkezi uyumluluk sınırlarının dışında olabilir.

Office 365 CDN sağlayıcıları için gizlilik ve veri koruması hakkında ayrıntılı bilgi için aşağıdakileri ziyaret edin:  

- [Microsoft Güven Merkezi'nde](https://www.microsoft.com/trustcenter) gizlilik ve veri koruması Office 365 hakkında daha fazla bilgi edinin
- Akamai [Gizlilik Güven Merkezi'nde Akamai'nin](https://www.akamai.com/us/en/about/compliance/data-protection-at-akamai.jsp) gizliliği ve veri koruması hakkında daha fazla bilgi edinin
- Azure [Güven Merkezi'nde](https://azure.microsoft.com/overview/trusted-cloud/) Azure gizliliği ve veri koruması hakkında daha fazla bilgi edinin

## <a name="how-can-i-secure-my-network-with-all-these-3rd-party-services"></a>Tüm bu üçüncü taraf hizmetleriyle ağımın güvenliğini nasıl sağlayabilirim?

Kapsamlı bir iş ortağı hizmetleri kümesi kullanmak, Office 365 kullanılabilirlik gereksinimlerini ölçeklendirmesine ve karşılamasına ve Office 365 kullanırken kullanıcı deneyimini geliştirmesine olanak tanır. Office 365 3. taraf hizmetleri, crl.microsoft.com veya sa.symcb.com gibi sertifika iptal listelerini ve r3.res.outlook.com gibi CDN'leri içerir. Office 365 tarafından oluşturulan her CDN FQDN,Office 365 için özel bir FQDN'dir. Office 365 isteği üzerine bir FQDN'ye gönderilirseniz, CDN sağlayıcısının FQDN'yi ve bu konumdaki temel içeriği denetleyeceğinden emin olabilirsiniz.
  
Bir Microsoft veya Office 365 veri merkezini hedefleyen istekleri üçüncü tarafa yönelik isteklerden ayırmak isteyen müşteriler için [Office 365 uç noktalarını yönetme](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a) yönergelerini yazdık.

## <a name="is-there-a-list-of-all-the-fqdns-that-leverage-cdns"></a>CDN'lerden yararlanan tüm FQDN'lerin listesi var mı?

FQDN'lerin listesi ve CDN'lerden nasıl yararlandıkları zaman içinde değişir. CDN'lerden yararlanan en son FQDN'lerden haberdar olmak için yayımlanan [Office 365 URL'leri ve IP adresi aralıkları](./urls-and-ip-address-ranges.md) sayfamıza bakın.

Csv veya JSON olarak biçimlendirilmiş geçerli Office 365 URL'lerini ve IP adresi aralıklarını istemek için Office 365 IP [Adresi ve URL Web hizmetini](microsoft-365-ip-web-service.md) de kullanabilirsiniz.

## <a name="can-i-use-my-own-cdn-and-cache-content-on-my-local-network"></a>Kendi CDN'mi kullanabilir ve yerel ağımda içeriği önbelleğe alabilir miyim?

Müşterilerimizin ihtiyaçlarını desteklemek için sürekli yeni yollar arıyoruz ve şu anda önbelleğe alma proxy çözümlerinin ve diğer şirket içi CDN çözümlerinin kullanımını araştırıyoruz.

Office 365 CDN'nin bir parçası olmasa da, özel web bölümlerini, kitaplıkları ve diğer kaynak varlıklarını barındırmak için **Azure CDN'yi** de kullanabilirsiniz. Bu sayede CDN depolamanıza erişim anahtarları uygulayabilir ve CDN yapılandırmanız üzerinde daha fazla denetim sağlayabilirsiniz. Azure CDN kullanımı ücretsiz değildir ve bir Azure aboneliği gerektirir. Azure CDN örneğini yapılandırma hakkında daha fazla bilgi için bkz [. Hızlı Başlangıç: Azure depolama hesabını Azure CDN ile tümleştirme](/azure/cdn/cdn-create-a-storage-account-with-cdn).

## <a name="im-using-azure-expressroute-for-office-365-does-that-change-things"></a>Office 365 için Azure ExpressRoute kullanıyorum, bu bir şeyleri değiştiriyor mu?

[Office 365 için Azure ExpressRoute](azure-expressroute.md), genel İnternet'ten ayrılmış Office 365 altyapısına ayrılmış bir bağlantı sağlar. Bu, istemcilerin ExpressRoute tarafından desteklenen hizmetler listesine açıkça dahil olmayan CDN'lere ve diğer Microsoft altyapısına bağlanmak için ExpressRoute olmayan bağlantılar üzerinden bağlanmaları gerekeceği anlamına gelir. CDN'leri hedefleyen istekler gibi belirli trafiği yönlendirme hakkında daha fazla bilgi için bkz. [ağ trafiği yönetimi Office 365](routing-with-expressroute.md).

## <a name="can-i-use-cdns-with-sharepoint-server-on-premises"></a>CDN'leri şirket içi SharePoint Server ile kullanabilir miyim?

CDN'lerin kullanılması yalnızca SharePoint Online bağlamında anlamlıdır ve SharePoint Server ile bundan kaçınılmalıdır. Bunun nedeni, sunucunun şirket içinde veya coğrafi olarak yakın olması durumunda coğrafi konumla ilgili tüm avantajların geçerli olmadığıdır. Ayrıca, barındırıldığı sunuculara bir ağ bağlantısı varsa, site İnternet bağlantısı olmadan kullanılabilir ve bu nedenle CDN dosyalarını alamaz. Aksi takdirde, siteniz için ihtiyacınız olan kitaplık ve dosyalar için kullanılabilir ve kararlı bir CDN kullanmanız gerekir.
  
İşte geri dönmek için kullanabileceğiniz kısa bir bağlantı: [https://aka.ms/o365cdns]()
  
## <a name="see-also"></a>Ayrıca bkz.

[Office 365 Ağ Bağlantı İlkeleri](./microsoft-365-network-connectivity-principles.md)

[Office 365 ağ bağlantısını değerlendirme](assessing-network-connectivity.md)

[Office 365 uç noktalarını yönetme](managing-office-365-endpoints.md)

[Office 365 URL'leri ve IP adresi aralıkları](./urls-and-ip-address-ranges.md)

[SharePoint Online ile Office 365 içerik teslim ağını kullanma](use-microsoft-365-cdn-with-spo.md)

[Microsoft Güven Merkezi](https://www.microsoft.com/trustcenter)

[Office 365 performansını ayarlama](tune-microsoft-365-performance.md)
