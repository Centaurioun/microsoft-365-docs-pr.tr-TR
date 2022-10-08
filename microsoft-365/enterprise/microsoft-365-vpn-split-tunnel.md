---
title: 'Genel bakış: Microsoft 365 için VPN bölünmüş tüneli'
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 3/3/2022
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
- remotework
- m365initiative-coredeploy
f1.keywords:
- NOCSH
description: Uzak kullanıcılar için bağlantıyı iyileştirmek için Microsoft 365 ile VPN bölünmüş tüneline genel bakış.
ms.openlocfilehash: ab719109756da721ac46a1ecba069a02ce85fb68
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68200989"
---
# <a name="overview-vpn-split-tunneling-for-microsoft-365"></a>Genel bakış: Microsoft 365 için VPN bölünmüş tüneli

>[!NOTE]
>Bu makale, uzak kullanıcılar için Microsoft 365 iyileştirmesini ele alan bir makale kümesinin parçasıdır.

>- VPN bölünmüş tüneli uygulama hakkında ayrıntılı yönergeler için bkz. [Microsoft 365 için VPN bölünmüş tüneli uygulama](microsoft-365-vpn-implement-split-tunnel.md).
>- VPN bölünmüş tünel senaryolarının ayrıntılı listesi için bkz. [Microsoft 365 için yaygın VPN bölünmüş tünel senaryoları](microsoft-365-vpn-common-scenarios.md).
>- VPN bölünmüş tünel ortamlarında Teams medya trafiğinin güvenliğini sağlama yönergeleri için bkz. [VPN bölünmüş tüneli için Teams medya trafiğinin güvenliğini sağlama](microsoft-365-vpn-securing-teams.md).
>- VPN ortamlarında Stream ve canlı etkinlikleri yapılandırma hakkında bilgi için bkz. [VPN ortamlarında Akış ve canlı etkinlikler için dikkat edilmesi gereken özel noktalar](microsoft-365-vpn-stream-and-live-events.md).
>- Çin'deki kullanıcılar için Microsoft 365 dünya çapında kiracı performansını iyileştirme hakkında bilgi için bkz. [Çin kullanıcıları için Microsoft 365 performans iyileştirmesi](microsoft-365-networking-china.md).

Kuruluşlar, kullanıcıları için güvenli uzak deneyimleri desteklemek için geleneksel olarak VPN'leri kullanır. Çekirdek iş yükleri şirket içinde kalırken, uzak istemciden gelen ve şirket ağındaki bir veri merkezinden yönlendirilen VPN, uzak kullanıcıların şirket kaynaklarına erişmesi için birincil yöntemdi. Kuruluşlar, bu bağlantıları korumak için VPN yolları boyunca ağ güvenlik çözümleri katmanları oluşturur. Bu güvenlik, iç altyapıyı korumak ve trafiği VPN'ye ve ardından şirket içi İnternet çevresi üzerinden dışarı yönlendirerek dış web sitelerinin mobil taramasını korumak için oluşturulmuştu. VPN'ler, ağ çevreleri ve ilişkili güvenlik altyapısı genellikle amaç doğrultusunda oluşturulmuş ve tanımlanmış bir trafik hacmi için ölçeklendirilmiştir; genellikle bağlantının çoğu şirket ağı içinden başlatılır ve çoğu iç ağ sınırları içinde kalır.

Uzak kullanıcı cihazının tüm bağlantılarının şirket içi ağa ( _zorlamalı tünel_ olarak bilinir) geri yönlendirildiği VPN modelleri, uzak kullanıcıların eşzamanlı ölçeği mütevazı olduğu ve VPN'den geçen trafik birimlerinin düşük olduğu sürece büyük ölçüde sürdürülebilirdi.  Bazı müşteriler, uygulamaları kurumsal çevreden genel SaaS bulutlarına taşındıktan sonra bile durum quo olarak VPN zorlamalı tünel kullanmaya devam etti.

Dağıtılmış ve performansa duyarlı bulut uygulamalarına bağlanmak için zorlamalı tünelli VPN'lerin kullanılması yetersizdir, ancak güvenlik durumunu korumak için bazı kuruluşlar tarafından olumsuz etkiler kabul edilmiştir. Bu senaryonun örnek diyagramı aşağıda görülebilir:

![Zorlamalı Tünel VPN yapılandırması.](../media/vpn-split-tunneling/enterprise-network-traditional.png)

_Şekil 1: Geleneksel bir Zorlamalı Tünel VPN çözümü._

Bu sorun uzun yıllardır artmaktadır ve birçok müşteri ağ trafiği desenlerinin önemli bir değişimini bildirmektedir. Eskiden şirket içinde kalan trafik artık dış bulut uç noktalarına bağlanıyor. Birçok Microsoft müşterisi, daha önce ağ trafiğinin yaklaşık %80'inin bir iç kaynağa (yukarıdaki diyagramdaki noktalı çizgiyle gösterilir) olduğunu bildirmektedir. 2020'de büyük iş yüklerini buluta kaydıran bu sayı yaklaşık %20'ye veya daha düşük bir sayıya düştü. Bu eğilimler diğer kuruluşlarda sık rastlanmayan bir durumdur. Zaman içinde, bulut yolculuğu ilerledikçe yukarıdaki model giderek daha hantal ve sürdürülebilir hale gelir ve kuruluşun bulut öncelikli bir dünyaya geçerken çevik olmasını önler.

Dünya genelindeki COVID-19 krizi, hemen düzeltilmesini gerektirmek için bu sorunu daha da ilerletmektedir. Çalışanların güvenliğini sağlama ihtiyacı, büyük ölçekte evden çalışma üretkenliğini desteklemek için kurumsal BT'de eşi görülmemiş talepler oluşturdu. Microsoft 365, müşterilerin bu talebi karşılamasına yardımcı olmak için iyi bir konuma sahiptir, ancak evden çalışan kullanıcıların yüksek eşzamanlılığı, zorlamalı tünel VPN ve şirket içi ağ çevreleri üzerinden yönlendirilirse hızlı doygunluğa neden olan ve VPN altyapısını kapasite dışında çalıştıran büyük miktarda Microsoft 365 trafiği oluşturur. Bu yeni gerçeklikte, Microsoft 365'e erişmek için VPN kullanmak artık yalnızca bir performans engeli değil, yalnızca Microsoft 365'i değil, aynı zamanda çalışmak için VPN'ye güvenmesi gereken kritik iş operasyonlarını da etkileyen bir sabit duvardır.

Microsoft, bu sorunlara kendi hizmetlerimizin içinden etkili, modern çözümler sunmak ve sektörün en iyi uygulamalarıyla uyum sağlamak için müşterilerle ve daha geniş bir sektörle yakın bir şekilde çalışmaktadır. Microsoft 365 hizmeti için [bağlantı ilkeleri](./microsoft-365-network-connectivity-principles.md), uzak kullanıcılar için verimli bir şekilde çalışacak şekilde tasarlanmıştır ve bir yandan da bir kuruluşun kendi bağlantıları üzerinde güvenlik ve denetim sağlamasına olanak sağlar. Bu çözümler, sınırlı çalışma ile hızlı bir şekilde uygulanabilir, ancak yukarıda özetlenen sorunlar üzerinde önemli bir olumlu etki sağlar.

Uzak çalışan cihazlarını VPN üzerinden şirket ağına veya bulut altyapısına bağlayan müşteriler için Microsoft, Microsoft Teams, **SharePoint Online** ve **Exchange Online** temel **Microsoft** 365 senaryolarının _BIR VPN bölünmüş tünel_ yapılandırması üzerinden yönlendirildiğini önerir. Bu, COVID-19 krizi gibi büyük ölçekli evden çalışma olayları sırasında çalışanların sürekli üretkenliğini kolaylaştırmaya yönelik ilk hat stratejisi olarak özellikle önemlidir.

![Bölünmüş Tünel VPN yapılandırması.](../media/vpn-split-tunneling/vpn-model-2.png)

_Şekil 2: Doğrudan hizmete gönderilen tanımlı Microsoft 365 özel durumlarına sahip bir VPN bölünmüş tünel çözümü. Diğer tüm trafik, hedef ne olursa olsun VPN tünelinden geçer._

Bu yaklaşımın özü, kuruluşlara VPN altyapısı doygunluğu riskini azaltmak ve Microsoft 365 performansını mümkün olan en kısa zaman diliminde önemli ölçüde geliştirmek için basit bir yöntem sunmaktır. VPN istemcilerini VPN tünelini atlamak için en kritik, yüksek hacimli Microsoft 365 trafiğine izin verecek şekilde yapılandırmak aşağıdaki avantajları sağlar:

- Microsoft 365 kullanıcı deneyimini etkileyen kurumsal VPN mimarilerinde müşteri tarafından bildirilen performans ve ağ kapasitesi sorunlarının çoğunun kök nedenini hemen azaltır
  
  Önerilen çözüm özellikle Microsoft 365 [URL'leri ve IP adresi aralıkları](./urls-and-ip-address-ranges.md) konusunda **İyileştir** olarak kategorilere ayrılmış Microsoft 365 hizmet uç noktalarını hedefler. Bu uç noktalara gelen trafik gecikme süresine ve bant genişliği azaltmaya karşı son derece hassastır ve VPN tünelini atlamasına olanak tanıyarak son kullanıcı deneyimini önemli ölçüde geliştirebilir ve kurumsal ağ yükünü azaltabilir. Bant genişliğinin veya kullanıcı deneyimi ayak izinin çoğunu oluşturmayan Microsoft 365 bağlantıları, İnternet'e bağlı trafiğin geri kalanıyla birlikte VPN tüneli üzerinden yönlendirilmeye devam edebilir. Daha fazla bilgi için bkz. [VPN bölünmüş tünel stratejisi](#the-vpn-split-tunnel-strategy).

- Müşteriler tarafından hızlı bir şekilde ve ek altyapı veya uygulama gereksinimleri olmadan yapılandırılabilir, test edilebilir ve uygulanabilir

  VPN platformuna ve ağ mimarisine bağlı olarak uygulama birkaç saat kadar sürebilir. Daha fazla bilgi için bkz. [VPN bölünmüş tüneli uygulama](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling).

- İnternet'e giden trafik de dahil olmak üzere diğer bağlantıların yönlendirilme şeklini değiştirmeyerek müşteri VPN uygulamalarının güvenlik duruşunu korur

  Önerilen yapılandırma, VPN trafiği özel durumları için **en düşük ayrıcalık** ilkesini izler ve müşterilerin kullanıcıları veya altyapıyı ek güvenlik risklerine maruz bırakmadan bölünmüş tünel VPN'i uygulamasına olanak tanır. Doğrudan Microsoft 365 uç noktalarına yönlendirilen ağ trafiği şifrelenir, Office istemci uygulama yığınları tarafından bütünlük için doğrulanır ve hem uygulama hem de ağ düzeyinde sağlamlaştırılmış Microsoft 365 hizmetlerine ayrılmış IP adresleri kapsamına alınır. Daha fazla bilgi için bkz [. Günümüzün benzersiz uzaktan çalışma senaryolarında modern güvenlik denetimleri elde etmek için güvenlik uzmanları ve BT için alternatif yollar (Microsoft Güvenlik Ekibi blogu)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/).

- Çoğu kurumsal VPN platformu tarafından yerel olarak desteklenir

  Microsoft, iş ortaklarının yukarıdaki önerilere uygun olarak çözümleri için hedefli rehberlik ve yapılandırma şablonları geliştirmelerine yardımcı olmak için ticari VPN çözümleri üreten sektör iş ortaklarıyla işbirliği yapmaya devam ediyor. Daha fazla bilgi için bkz. [Yaygın VPN platformları için HOWTO kılavuzları](microsoft-365-vpn-implement-split-tunnel.md#howto-guides-for-common-vpn-platforms).

>[!TIP]
>Microsoft, Bölünmüş tünel VPN yapılandırmasının Microsoft 365 hizmetleri için belgelenmiş ayrılmış IP aralıklarına odaklanmasını önerir. FQDN veya AppID tabanlı bölünmüş tünel yapılandırmaları, bazı VPN istemci platformlarında mümkün olsa da önemli Microsoft 365 senaryolarını tam olarak kapsamayabilir ve IP tabanlı VPN yönlendirme kurallarıyla çakışabilir. Bu nedenle Microsoft, bölünmüş tünel VPN'sini yapılandırmak için Microsoft 365 FQDN'lerinin kullanılmasını önermez. FQDN yapılandırmasının kullanılması, .pac dosyası özelleştirmeleri gibi diğer ilgili senaryolarda veya ara sunucu atlama uygulamak için yararlı olabilir.

Tam uygulama kılavuzu için bkz. [Microsoft 365 için VPN bölünmüş tüneli uygulama](microsoft-365-vpn-implement-split-tunnel.md).

Uzaktan çalışanlar için Microsoft 365'i yapılandırmaya yönelik adım adım bir işlem için bkz. [Uzaktan çalışma için altyapınızı ayarlama](..\solutions\empower-people-to-work-remotely.md)

## <a name="the-vpn-split-tunnel-strategy"></a>VPN bölünmüş tünel stratejisi

Geleneksel kurumsal ağlar genellikle en önemli verilerin, hizmetlerin, uygulamaların şirket içinde barındırıldığı ve kullanıcıların çoğu gibi doğrudan iç şirket ağına bağlı olduğu bulut öncesi bir dünyada güvenli bir şekilde çalışacak şekilde tasarlanmıştır. Bu nedenle, şube ofislerinin merkez ofise _Multiprotocol Label Switching (MPLS)_ ağları aracılığıyla bağlandığını ve uzak kullanıcıların hem şirket uç noktalarına hem de İnternet'e erişmek için bir VPN üzerinden şirket ağına bağlanması gereken bu öğelerin etrafında ağ altyapısı oluşturulmuştur. Bu modelde, uzak kullanıcılardan gelen tüm trafik şirket ağından geçer ve ortak bir çıkış noktası üzerinden bulut hizmetine yönlendirilir.

![Zorlamalı VPN yapılandırması.](../media/vpn-split-tunneling/vpn-model-1.png)

_Şekil 2: Hedef ne olursa olsun tüm trafiğin şirket ağına geri zorlandığı uzak kullanıcılar için yaygın bir VPN çözümü_

Kuruluşlar verileri ve uygulamaları buluta taşıdıkça, bu model hızla hantal, pahalı ve hesaplanamaz hale geldiğinden, kullanıcıların ağ performansını ve verimliliğini önemli ölçüde etkilediğinden ve kuruluşun değişen gereksinimlere uyum sağlama becerisini kısıtladıkça daha az etkili olmaya başlamıştır. Çok sayıda Microsoft müşterisi, birkaç yıl önce ağ trafiğinin %80'inin bir iç hedefe olduğunu, ancak 2020'de trafiğin %80'inin harici bulut tabanlı bir kaynağa bağlandığını bildirdi.

COVID-19 krizi, kuruluşların büyük çoğunluğu için acil çözümler gerektirmek için bu sorunu daha da ağırlaştırdı. Birçok müşteri, zorlanan VPN modelinin bu krizin gerektirdiği gibi %100 uzaktan çalışma senaryoları için yeterince ölçeklenebilir veya performanslı olmadığını tespit etti. Bu kuruluşların verimli bir şekilde çalışmaya devam etmesi için hızlı çözümler gerekir.

Microsoft 365 hizmeti için Microsoft, hizmete erişen kullanıcılar için yüksek performans sunmak ve VPN altyapısının yükünü azaltmak ve hala gerektiren trafik tarafından kullanılabilmesi için odaklanmış, sıkı denetimli ve görece statik bir hizmet uç noktası kümesinin çok basit ve hızlı bir şekilde iyileştirilebileceği bu sorunu göz önünde bulundurarak hizmet için bağlantı gereksinimlerini tasarlamıştır.

Microsoft 365, Microsoft 365 için gerekli uç noktaları üç kategoriye ayırır: **İyileştir**, **İzin Ver** ve **Varsayılan**. **En iyi duruma getirme** uç noktaları burada odak noktamızdır ve aşağıdaki özelliklere sahiptir:

- Microsoft'un sahip olduğu ve yönetilen uç noktaları, Microsoft altyapısında barındırılıyor mu?
- Exchange Online, SharePoint Online, Skype Kurumsal Online ve Microsoft Teams gibi temel Microsoft 365 iş yüklerine ayrılmıştır
- IP'ler sağlandı mı?
- Düşük değişiklik oranı ve sayı olarak küçük kalması beklenir (şu anda 20 IP alt ağı)
- Yüksek hacim ve/veya gecikme süresine duyarlıdır
- Ağdaki satır içi öğeler yerine hizmette gerekli güvenlik öğelerinin sağlanmasına sahip olabilir
- Microsoft 365 hizmetine yönelik trafik hacminin yaklaşık %70-80'ini oluşturur

Bu sıkı kapsamlı uç nokta kümesi, zorlamalı VPN tünelinden ayrılabilir ve kullanıcının yerel arabirimi aracılığıyla güvenli bir şekilde ve doğrudan Microsoft 365 hizmetine gönderilebilir. Bu, **bölünmüş tünel** olarak bilinir.

DLP, AV koruması, kimlik doğrulaması ve erişim denetimi gibi güvenlik öğelerinin tümü hizmet içindeki farklı katmanlarda bu uç noktalara karşı çok daha verimli bir şekilde teslim edilebilir. Ayrıca trafik hacminin büyük bir kısmını VPN çözümünden uzaklaştırdığımız için bu, VPN kapasitesini hala buna bağlı olan iş açısından kritik trafik için boşaltır. Ayrıca, bu yeni çalışma yöntemiyle başa çıkmak için uzun ve maliyetli bir yükseltme programından geçmek için birçok durumda gereksinimi ortadan kaldırmalıdır.

![Bölünmüş Tünel VPN yapılandırma ayrıntıları.](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

_Şekil 3: Tanımlı Microsoft 365 özel durumlarının doğrudan hizmete gönderildiği bir VPN bölünmüş tünel çözümü. Diğer tüm trafik, hedef ne olursa olsun şirket ağına geri dönmeye zorlanır._

Güvenlik açısından bakıldığında, Microsoft'un şirket içi güvenlik yığınları tarafından satır içi inceleme ile sunulana benzer, hatta gelişmiş güvenlik sağlamak için kullanılabilecek bir dizi güvenlik özelliği vardır. Microsoft Güvenlik ekibinin blog gönderisi [Güvenlik uzmanları ve BT'nin günümüzün benzersiz uzaktan çalışma senaryolarında modern güvenlik denetimlerine ulaşmanın alternatif yolları](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) , sağlanan özelliklerin net bir özetini içerir ve bu makalede daha ayrıntılı yönergeler bulabilirsiniz. Microsoft'un VPN'de çalışan bölünmüş tünel uygulaması hakkında bilgi edinmek için [bkz. Microsoft uzak iş gücünü nasıl bağlı tutuyor](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)?

Çoğu durumda, bu uygulama birkaç saat içinde gerçekleştirilebilir ve bu sayede kuruluşların karşılaştığı en acil sorunlardan birinin hızlı bir şekilde tam ölçekli uzaktan çalışmaya geçişini sağlar. VPN bölünmüş tünel uygulama kılavuzu için bkz. [Microsoft 365 için VPN bölünmüş tüneli uygulama](microsoft-365-vpn-implement-split-tunnel.md).

## <a name="faq"></a>SSS

Microsoft Güvenlik Ekibi, [günümüzün benzersiz uzaktan çalışma senaryolarında modern güvenlik denetimleri elde etmek için güvenlik uzmanları ve BT için alternatif yollar](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) yayımladı. Bu gönderi, güvenlik uzmanları için temel yolları özetleyen bir blog gönderisi ve BT günümüzün benzersiz uzaktan çalışma senaryolarında modern güvenlik denetimleri elde edebilir. Ayrıca, bu konuyla ilgili sık sorulan müşteri sorularından ve yanıtlarından bazıları aşağıdadır.

### <a name="how-do-i-stop-users-accessing-other-tenants-i-do-not-trust-where-they-could-exfiltrate-data"></a>Nasıl yaparım? kullanıcıların verileri çıkarabilecekleri yere güvenmediğim diğer kiracılara erişmesini durdurmak mı?

Yanıt, [kiracı kısıtlamaları adlı bir özelliktir](/azure/active-directory/manage-apps/tenant-restrictions). Kimlik doğrulama trafiği yüksek hacimli veya özellikle gecikmeye duyarlı olmadığından, VPN çözümü aracılığıyla özelliğin uygulandığı şirket içi ara sunucuya gönderilebilir. Güvenilen kiracıların izin verme listesi burada tutulur ve istemci güvenilir olmayan bir kiracıya belirteç almayı denerse, proxy yalnızca isteği reddeder. Kiracıya güveniliyorsa, kullanıcı doğru kimlik bilgilerine ve haklara sahipse belirteç erişilebilir.

Bu nedenle, bir kullanıcı yukarıdaki İşaretli uç noktaları iyileştir'e TCP/UDP bağlantısı oluşturabilse de, söz konusu kiracıya erişmek için geçerli bir belirteç olmadan oturum açamaz ve verilere erişemez/veri taşıyamaz.

### <a name="does-this-model-allow-access-to-consumer-services-such-as-personal-onedrive-accounts"></a>Bu model kişisel OneDrive hesapları gibi tüketici hizmetlerine erişime izin verir mi?

Hayır, etmez, Microsoft 365 uç noktaları tüketici hizmetleriyle aynı değildir (örnek olarak Onedrive.live.com), bu nedenle bölünmüş tünel kullanıcının tüketici hizmetlerine doğrudan erişmesine izin vermez. Tüketici uç noktalarına yönelik trafik VPN tünelini kullanmaya devam eder ve mevcut ilkeler uygulanmaya devam eder.

### <a name="how-do-i-apply-dlp-and-protect-my-sensitive-data-when-the-traffic-no-longer-flows-through-my-on-premises-solution"></a>Nasıl yaparım? şirket içi çözümüm üzerinden trafik akışı olmadığında DLP uygulamak ve hassas verilerimi korumak mı?

Microsoft 365, hassas bilgilerin yanlışlıkla açığa çıkmasını önlemenize yardımcı olmak için zengin bir [yerleşik araçlar](../compliance/information-protection.md) kümesine sahiptir. Uygun olmayan şekilde depolanan veya paylaşılan hassas bilgileri algılamak için Teams ve SharePoint'in yerleşik [DLP özelliklerini](../compliance/dlp-learn-about-dlp.md) kullanabilirsiniz. Uzaktan çalışma stratejinizin bir bölümü kendi cihazını getir (KCG) ilkesini içeriyorsa, hassas verilerin kullanıcıların kişisel cihazlarına indirilmesini önlemek için [uygulama tabanlı Koşullu Erişim'i](/azure/active-directory/conditional-access/app-based-conditional-access) kullanabilirsiniz

### <a name="how-do-i-evaluate-and-maintain-control-of-the-users-authentication-when-they-are-connecting-directly"></a>Nasıl yaparım? doğrudan bağlanırken kullanıcının kimlik doğrulaması denetimini değerlendirmek ve korumak?

Q1'de belirtilen kiracı kısıtlamaları özelliğine ek olarak, kimlik doğrulama isteğinin riskini dinamik olarak değerlendirmek ve uygun şekilde tepki vermek için [koşullu erişim ilkeleri](/azure/active-directory/conditional-access/overview) uygulanabilir. Microsoft[, Sıfır Güven modelinin](https://www.microsoft.com/security/zero-trust?rtc=1) zaman içinde uygulanmasını önerir ve mobil ve bulut öncelikli bir dünyada denetimi korumak için Azure AD koşullu erişim ilkelerini kullanabiliriz. Koşullu erişim ilkeleri, kimlik doğrulama isteğinin başarılı olup olmadığına ilişkin gerçek zamanlı bir karar vermek için aşağıdakiler gibi çeşitli faktörlere göre kullanılabilir:

- Cihaz, cihaz biliniyor mu/güvenilen/Etki alanına katılmış mı?
- IP – Kimlik doğrulama isteği bilinen bir kurumsal IP adresinden mi geliyor? Yoksa güvenmediğimiz bir ülkeden mi?
- Uygulama – Kullanıcı bu uygulamayı kullanma yetkisine sahip mi?

Daha sonra bu ilkelere göre onaylama, MFA'yı tetikleme veya kimlik doğrulamasını engelleme gibi ilkeler tetikleyebiliriz.

### <a name="how-do-i-protect-against-viruses-and-malware"></a>Virüslere ve kötü amaçlı yazılımlara karşı koruma Nasıl yaparım??

Microsoft 365, hizmetin kendisindeki çeşitli katmanlarda işaretlenen uç noktaları en iyi duruma getirme için [bu belgede açıklanan](/office365/Enterprise/office-365-malware-and-ransomware-protection) korumayı da sağlar. Belirtildiği gibi, bu güvenlik öğelerini protokolleri/trafiği tam olarak anlamayabilecek cihazlara uygun olarak yapmaya çalışmak yerine hizmetin kendisinde sağlamak çok daha verimlidir. Varsayılan olarak, SharePoint Online bilinen kötü amaçlı yazılım için [dosya yüklemelerini otomatik olarak tarar](../security/office-365-security/virus-detection-in-spo.md)

Yukarıda listelenen Exchange uç noktaları [için, Microsoft 365 için Exchange Online Protection ve Microsoft Defender](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) hizmet trafiğinin güvenliğini sağlamak için mükemmel bir iş yapar. [](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

### <a name="can-i-send-more-than-just-the-optimize-traffic-direct"></a>Yalnızca Trafiği en iyi duruma getirme doğrudanından fazlasını gönderebilir miyim?

Düşük çalışma düzeyi için en yüksek avantajı sağlayacağından, işaretlenen uç noktaları **iyileştir'e** öncelik verilmelidir. Ancak isterseniz, hizmetin çalışması için İşaretli uç noktalara izin ver ve gerekirse kullanılabilecek uç noktalar için IP adreslerinin sağlanması gerekir.

Genel web tarama için merkezi güvenlik, denetim ve şirket ilkesi uygulaması sağlayan _güvenli web ağ geçitleri_ olarak adlandırılan bulut tabanlı ara sunucu/güvenlik çözümleri sunan çeşitli satıcılar da vardır. Bu çözümler, yüksek oranda kullanılabilirse, yüksek oranda kullanılabilir, yüksek performanslı ve kullanıcılarınızın yakınında sağlanmış bulut tabanlı bir konumdan güvenli İnternet erişiminin kullanıcıya yakın bir konumdan teslim edilmesine izin vererek bulut öncelikli bir dünyada iyi çalışabilir. Bu, genel göz atma trafiği için VPN/kurumsal ağ üzerinden bir saç tokası gereksinimini ortadan kaldırırken, merkezi güvenlik denetimine de izin verir.

Ancak bu çözümler geçerli olsa bile, Microsoft işaretlenen Microsoft 365 trafiğini en iyi duruma getirmenin doğrudan hizmete gönderilmesini kesinlikle önerir.

Azure Sanal Ağ doğrudan erişime izin verme yönergeleri için bkz. Noktadan [siteye Azure VPN Gateway kullanarak uzaktan çalışma](/azure/vpn-gateway/work-remotely-support).

### <a name="why-is-port-80-required-is-traffic-sent-in-the-clear"></a>Bağlantı noktası 80 neden gereklidir? Trafik temiz mi gönderildi?

80 numaralı bağlantı noktası yalnızca bağlantı noktası 443 oturumuna yeniden yönlendirme, hiçbir müşteri verisi gönderilmez veya 80 numaralı bağlantı noktası üzerinden erişilebilir olması gibi işlemler için kullanılır. [Şifreleme](../compliance/encryption.md) , Microsoft 365 için aktarımdaki ve bekleyen veriler için şifrelemeyi özetler ve [Trafik türleri](/microsoftteams/microsoft-teams-online-call-flows#types-of-traffic) , Teams medya trafiğini korumak için SRTP'yi nasıl kullandığımızı özetler.

### <a name="does-this-advice-apply-to-users-in-china-using-a-worldwide-instance-of-microsoft-365"></a>Bu öneri, Microsoft 365'in dünya çapında bir örneğini kullanan Çin kullanıcıları için geçerli mi?

**Hayır**, etmiyor. Yukarıdaki önerilerden biri, PRC'deki microsoft 365'in dünya çapındaki bir örneğine bağlanan kullanıcılardır. Bölgede sınır ötesi ağ tıkanıklığının yaygın olarak ortaya çıkması nedeniyle, doğrudan İnternet çıkış performansı değişken olabilir. Bölgedeki müşterilerin çoğu trafiği kurumsal ağa getirmek için VPN kullanarak çalışır ve iyileştirilmiş bir yol aracılığıyla yetkili MPLS devrelerini veya ülke dışına çıkışa benzer bir şekilde kullanır. Bu, [Çin kullanıcıları için Microsoft 365 performans iyileştirme](microsoft-365-networking-china.md) makalesinde daha ayrıntılı olarak açıklanmıştır.

### <a name="does-split-tunnel-configuration-work-for-teams-running-in-a-browser"></a>Bölünmüş tünel yapılandırması tarayıcıda çalışan Teams için çalışır mı?

Evet, uyarılarla. Teams işlevlerinin çoğu [, Microsoft Teams için istemcileri alma](/microsoftteams/get-clients#web-client) bölümünde listelenen tarayıcılarda desteklenir.

Ayrıca Microsoft Edge **96 ve üzeri** , Edge [WebRtcRespectOsRoutingTableEnabled](/deployedge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) ilkesini etkinleştirerek eşler arası trafik için VPN bölünmüş tünel oluşturmayı destekler. Şu anda diğer tarayıcılar eşler arası trafik için VPN bölünmüş tünel oluşturmayı desteklemeyebilir.

## <a name="related-articles"></a>İlgili makaleler

[Microsoft 365 için VPN bölünmüş tüneli uygulama](microsoft-365-vpn-implement-split-tunnel.md)

[Microsoft 365 için yaygın VPN bölünmüş tünel senaryoları](microsoft-365-vpn-common-scenarios.md)

[VPN bölünmüş tüneli için Teams medya trafiğinin güvenliğini sağlama](microsoft-365-vpn-securing-teams.md)

[VPN ortamlarında Akış ve canlı etkinlikler için özel dikkat edilmesi gerekenler](microsoft-365-vpn-stream-and-live-events.md)

[Çin kullanıcıları için Microsoft 365 performans iyileştirmesi](microsoft-365-networking-china.md)

[Microsoft 365 Ağ Bağlantı İlkeleri](microsoft-365-network-connectivity-principles.md)

[Microsoft 365 ağ bağlantısını değerlendirme](assessing-network-connectivity.md)

[Microsoft 365 ağ ve performans ayarlama](network-planning-and-performance.md)

[Günümüzün benzersiz uzaktan çalışma senaryolarında modern güvenlik denetimleri elde etmek için güvenlik uzmanları ve BT için alternatif yollar (Microsoft Güvenlik Ekibi blogu)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Microsoft'ta VPN performansını geliştirme: otomatik bağlantılara izin vermek için Windows 10 VPN profillerini kullanma](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[VPN üzerinde çalıştırma: Microsoft uzak iş gücünü nasıl bağlı tutuyor?](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Microsoft küresel ağı](/azure/networking/microsoft-global-network)
