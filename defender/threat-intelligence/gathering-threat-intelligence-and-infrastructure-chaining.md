---
title: 'Öğretici: Microsoft Defender Tehdit Analizi kullanarak Tehdit Bilgileri ve Altyapı ZinciriNi Toplama (Defender TI)'
description: Bu öğreticide, tehdit zekası ve altyapı zincirini Microsoft Defender Tehdit Analizi 'de (Defender TI) tehlikeye ilişkin göstergeleri birlikte toplamayı öğrenin. Bu makalede MyPillow Magecart ihlaliyle ilgili geçmişe dönük bir araştırma ele alınacaktır.
author: alexroland24
ms.author: aroland
ms.service: threat-intelligence
ms.topic: tutorial
ms.date: 08/02/2022
ms.custom: template-tutorial
ms.openlocfilehash: 7cdb70d72253164b24cb55d57b20cc3edb7c5a7c
ms.sourcegitcommit: 7e551fa4e9b8b25ed62b5f406143b6b1dae08cbf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2022
ms.locfileid: "67172861"
---
# <a name="tutorial-gathering-threat-intelligence-and-infrastructure-chaining"></a>Öğretici: Tehdit bilgilerini ve altyapı zincirini toplama

Bu öğreticide şunları nasıl yapacağınızı öğreneceksiniz:
- Çeşitli türlerde gösterge aramaları gerçekleştirin ve tehdit ve saldırgan zekayı toplayın

  ![ti Genel BakışHome Sayfası Chrome Ekran Görüntüsü](media/tiOverviewHomePageChromeScreenshot.png)

## <a name="prerequisites"></a>Önkoşullar

- Bir Azure Active Directory veya kişisel Microsoft hesabı. [Oturum açma veya hesap oluşturma](https://signup.microsoft.com/)
- Microsoft Defender Tehdit Analizi (Defender TI) Premium lisansı.

    > [!NOTE]
    > Defender TI Premium lisansı olmayan kullanıcılar Defender Tehdit Bilgileri Portalı'na giriş yapmaya ve ücretsiz Defender TI teklifimize erişmeye devam edebilir.

## <a name="disclaimer"></a>Feragatname

Microsoft Defender Tehdit Analizi (Defender TI), kötü amaçlı altyapı ve saldırgan tehdit araçları da dahil olmak üzere canlı, gerçek zamanlı gözlemleri ve tehdit göstergelerini içerebilir. Defender TI platformumuzdaki tüm IP ve etki alanı aramalarının arama yapmak güvenlidir.

Microsoft, açık ve mevcut bir tehlike oluşturan gerçek tehditler olarak kabul edilmesi gereken çevrimiçi kaynakları (ÖRNEĞIN, IP adresleri, etki alanı adları) paylaşacaktır.

Kullanıcıların en iyi kararlarını kullanmasını ve aşağıdaki öğreticiyi gerçekleştirirken kötü amaçlı sistemlerle etkileşim kurarken gereksiz riski en aza indirmesini istiyoruz. Microsoft'un kötü amaçlı IP adreslerini, konakları ve etki alanlarını kötüleyerek riski en aza indirmek için çalıştığını lütfen unutmayın.

## <a name="before-you-begin"></a>Başlamadan Önce
Yukarıdaki bildirimde belirtildiği gibi, şüpheli ve kötü amaçlı göstergeler güvenliğiniz için lekelenmiştir. Defender TI'de arama yaparken IP'lerden, etki alanlarından ve konaklardan köşeli ayraçları kaldırın. Bu göstergeleri doğrudan tarayıcınızda aramayın.

## <a name="perform-several-types-of-indicator-searches-and-gather-threat-and-adversary-intelligence"></a>Çeşitli türlerde gösterge aramaları gerçekleştirin ve tehdit ve saldırgan zekayı toplayın

Bu öğreticide, Bir Magecart ihlaliyle ilgili güvenlik ihlali (ICS) göstergelerini birlikte [altyapı zincirine](infrastructure-chaining.md) almak için bir dizi adım gerçekleştirecek ve bu yolda tehdit ve saldırgan zeka toplayacağız. Altyapı zincirleme, çakışan ayrıntılara veya paylaşılan özelliklere göre bir IOC'yi birçok IOC'ye genişletmek için İnternet'in yüksek oranda bağlı doğasından yararlanıyor. Altyapı zincirleri oluşturmak, tehdit avcılarının veya olay yanıtlayıcılarının bir saldırganın dijital varlığının profilini oluşturmasına olanak tanıyarak bir olay veya araştırma çerçevesinde bağlam oluşturmak için bu veri kümelerinde hızla özetlemelerine olanak tanıyarak bir kuruluştaki olayların uyarı ve eyleme konularının daha etkili bir şekilde önceliklendirmesini sağlar.

![Altyapı Zincirleme](media/infrastructureChaining.png)

**İlgili Kişilikler:** Tehdit Analizi Analisti, Tehdit Avcısı, Olay Yanıtlayıcısı, Güvenlik Operasyonları Analisti

### <a name="magecart-breach"></a>Magecart İhlali

Microsoft, güvenliği aşılmış e-ticaret sitelerine dijital skimmer'lar yerleştirerek çevrimiçi perakende platformlarının yüzlerce ihlalinin ardındaki suçlu siber grupların bir parçası olan Magecart'ın profillerini oluşturup takip ediyor.

Bunu, tüketicilerin doğrudan e-ticaret web sitelerindeki çevrimiçi ödeme formlarına girdiği hassas verileri çalmak için tasarlanmış bir betik ekleyerek veya web sitelerinin çalışmasını sağlamak için güvenebileceği güvenliği aşılmış üçüncü taraf tedarikçiler aracılığıyla eklerler.

Ekim 2018'de MyPillow'un çevrimiçi web sitesine sızarak mypillow.com, web mağazalarına, mypiltow.com skimmer'ı içeren bir yazım hatası etki alanında barındırılan bir betik ekleyerek ödeme bilgilerini çaldılar.

MyPillow ihlali iki aşamalı bir saldırıydı ve ilk skimmer yasadışı olarak tanımlanıp kaldırılmadan önce kısa bir süre etkindi, ancak saldırganlar MyPillow'un ağına hala erişime sahiplerdi ve 26 Ekim 2018'de Microsoft, livechatinc adlı yeni bir etki alanı kaydettiklerini gözlemlemişti[.] Org

Magecart aktörleri genellikle bir etki alanı ihlali kaydederek yasal etki alanına mümkün olduğunca benzer olmasını sağlar, böylece JavaScript koduna bakıyorsanız, gerçekten dikkatli bakmadığınız sürece, kredi kartı ödeme bilgilerini yakalayan ve kendi altyapılarına gönderen kendi betiklerini eklediklerini fark edemeyebilirsiniz.  temelde saklanmak için bir yol olarak.
Ancak sanal kullanıcılarımız DOM'u yakalayıp JavaScript tarafından yapılan tüm dinamik bağlantıları ve değişiklikleri arka uçta gezinmelerden bulduklarından, bu etkinliği algılayıp eklenen betiği barındıran sahte etki alanını MyPillow web deposuna sabitledik.

1. [Defender Tehdit Bilgileri portalına](https://ti.defender.microsoft.com/) erişin.
2. Portala erişmek için Microsoft kimlik doğrulamasını tamamlayın.
3. Defender TI'nın Tehdit Bilgileri Giriş Sayfasında 'mypillow.com' araması.
    a. Bu etki alanıyla ilişkili makaleler nelerdir?
    - Tüketiciler bu iki Magecart ihlali yüzünden uykularını kaybedebilir

      ![Öğretici Infra Chain My Pillowcom Makalesi](media/tutorialInfraChainMyPillowcomArticle.png)

4. 'Tüketiciler bu iki Magecart İhlali üzerinden uyku kaybına neden olabilir' makalesini seçin.
    a. Bu ilgili kampanya hakkında hangi bilgileri kullanabilirsiniz?
      - Bu makale 20 Mart 2019'da yayımlanmıştır ve Ekim 2018'de Magecart tehdit aktör grubu tarafından MyPillow'un nasıl ihlal edildiğine ilişkin içgörüler sağlar. Makalede saldırının nasıl yürütülür olduğu ayrıntılı olarak anlatılır.
5. Genel Göstergeler sekmesini seçin. a. Bu kampanyayla ilgili olarak hangi GÇ'ler listeleniyor?
      - amerisleep.github[.] ıo
      - cmytuok[.] Sayfanın Üstü
      - livechatinc[.] Org
      - mypiltow[.] Com
6. Arama çubuğunun açılan menüsünde Tümü'ne tıklayın ve 'mypillow.com' sorgusunu sorgulatın. Ardından Veri sekmesine gidin. a. Betik ekleme kanıtını bulmada hangi veri kümesi yararlı olabilir?
     - Konak çiftleri, geleneksel veri kaynaklarının ortaya çıkarmayacağı (pDNS, Whois) web siteleri arasındaki bağlantıları ortaya çıkarmakta ve kaynaklarınızın nerede kullanıldığını görmenizi ve bunun tersini görmenizi sağlar.
7. Konak Çiftleri Veri dikey penceresini seçin, İlk Görüldü ölçütüne göre sıralayın ve neden olarak script.src dosyasına göre filtreleyin. Ekim 2018'de gerçekleşen konak çifti ilişkilerini bulana kadar sayfayı kapatın.
    a. Herhangi bir yazım hatası mypillow etki alanı fark ettin mi?
      - mypillow[.] com, yazım hatasından bir betik aracılığıyla içerik çekiyor, mypiltow.com (3-5 Ekim) betik ekleme ihlalinin kanıtı olarak

          ![Öğretici Infra Chain My Pillowcom Konak Çiftleri Canlı Sohbet Betiği Src](media/tutorialInfraChainMyPillowcomHostPairsLiveChatScriptSrc.gif)
8. 'mypiltow[.] üzerinde özet com'.
    a. İlk bakışta, bu etki alanında mypillow.com'un etki alanıyla karşılaştırıldığında ne farklı görünür?
      - Saygınlık: Kötü amaçlı, mypillow.com'un itibarı bilinmiyor

        ![Öğretici InfraChain My Piltowcom Reputation](media/tutorialInfraChainMyPiltowcomReputation.png)

        ![Öğretici Infra Chain My Pillowcom Saygınlığı](media/tutorialInfraChainMyPillowcomReputation.png)
9. Veri sekmesine gidin ve Çözümler sonuçlarından mypiltow[.] ip adresini özetleyin com, Ekim 2018'de çözümlendi. Bu adımı mypillow.com için de yineleyin.
    a. mypillow.com ile mypiltow arasındaki IP adresleri arasındaki farklar hakkında ne fark edeceksiniz[.] com Ekim 2018 sırasında?
      - IP adresi, 195.161.41[.] 65, mypiltow[.] com çözümlendi, Rusya'da barındırılıyor.
      - Kullanılan farklı ASN.

          ![Öğretici Infra Chain My Piltow IP Özeti](media/tutorialInfraChainMyPiltowIpSummary.png)

          ![Öğretici Infra Chain My Pillow IP Özeti](media/tutorialInfraChainMyPillowIpSummary.png)
10. Makaleler bölümüne gidin.
    a. mypiltow.com ile ilgili başka hangi Makaleler yayımlandı?
    - RiskIQ: Magecart Eklenen URL'ler ve C2 Etki Alanları, 3-14 Haziran 2022
    - RiskIQ: Magecart eklenmiş URL'ler ve C2 Etki Alanları, 20-27 Mayıs 2022
    - Emtia Kayağı & 2022'nin İlk Çeyreğindeki Magecart Eğilimleri
    - RiskIQ: 2022'nin Başlarında Magecart Grup 8 Etkinliği
    - Magecart Group 8 Emlak: Skimming Grubu ile İlişkili Barındırma Desenleri
    - Homoglif Saldırılarında Kullanılan Inter Skimming Kit
    - Magecart Group 8, Büyüyen Kurban Listesine Ekleme NutriBullet.com Harmanlar

     ![Öğretici Infra Chain My Piltowcom Makaleleri](media/tutorialInfraChainMyPiltowcomArticles.gif)
11. 9. Adım'da yer alan ek makalelerin her birini gözden geçirin.
    a. Magecart tehdit aktörü grubu hakkında hangi ek bilgileri bulabilirsiniz? (hedefler, TTP'ler, ek GÇ'ler vb.)
12. Veri sekmesine gidin ve Whois Verileri dikey penceresini seçin ve 'mypillow.com' ile 'mypiltow[.] arasındaki Whois bilgilerini karşılaştırın com' a. Whois değerleri nelerden farklıdır?
      - mypillow.com
        1. Ekim 2011'den Whois kaydını seçerseniz etki alanının My Pillow Inc.'e ait olduğunu göreceksiniz.

            ![Öğretici Infra Chain My Piltowcom 2 Whois](media/tutorialInfraChainMyPiltowcom2Whois.png)
        2. mypiltow[.] Com
        3. Ekim 2018'den Whois kaydını seçerseniz bu mypiltow[.] com Hong Kong, Çin'de kayıtlıdır ve Domain ID Shield Service CO tarafından korunan gizliliktir.
        4. mypiltow[.] com'un kayıt şirketi OnlineNIC, Inc.

            ![Öğretici Infra Chain My Piltowcom 2 Whois](media/tutorialInfraChainMyPiltowcom2Whois.png)

    b. Mypiltow hakkında şu ana kadar şüpheli görünenler[.] com'da analiz ettiğimiz A kayıtları ve Whois ayrıntıları verilmiş mi?
      - Mypiltow'un olup olmadığını değerlendirirken[.] com meşru bir şirket altyapısı olabilir, bir analist Rus IP'lerinin öncelikli olarak ABD merkezli bir şirket için Çin gizlilik hizmeti tarafından korunmasını garip bulmalıdır.
13. Arama 'livechatinc[.] kuruluş'un Defender TI'nin Tehdit Bilgileri Giriş Sayfası'nda.
    a. Bölüm 1'de mypillow.com ararken görmediğimiz bu etki alanıyla ilişkili yeni makaleler nelerdir?
      - Magecart Group 8, Büyüyen Kurban Listesine Ekleme NutriBullet.com Harmanlar
14. Magecart Group 8 Blends into NutriBullet.com Adding to The Growing List of Victims makalesini seçin.
    a. Bu ilgili kampanya hakkında hangi bilgileri kullanabilirsiniz?
      - 'Magecart Group 8 Blends into NutriBullet.com Adding To The Growing Victims' makalesi 18 Mart 2020'de yayımlandı. Bu makalede Nutribullet, Amerisleep, ABS-CBN'nin de Magecart tehdit aktör grubunun kurbanı olduğunu öğreniyoruz.
15. Genel Göstergeler sekmesini seçin. a. Bu kampanyayla ilgili olarak hangi GÇ'ler listeleniyor?
      - URL'ler
        1. hxxps://coffemokko[.] com/tr/, hxxps://freshdepor[.] com/tr/, hxxps://prodealscenter[.] com/tr/, hxxps://scriptoscript[.] com/tr/, hxxps://swappastore[.] com/tr/
        2. Etki alanları
            - 3lift[.] org, abtasty[.] net, adaptivecss[.] org, adorebeauty[.] org, all-about-sneakers[.] org, amerisleep.github[.] io, ar500arnor[.] com, authorizecdn[.] com, bannerbuzz[.] bilgi, pil gücü[.] org, batterynart[.] com, blackriverimaging[.] org, braincdn[.] org, btosports[.] net, cdnassels[.] com, cdnmage[.] com, chicksaddlery[.] net, childsplayclothing[.] org, christohperward[.] org, citywlnery[.] org, closetlondon[.] org, cmytuok[.] top, coffemokko[.] com, coffetea[.] org, configsysrc[.] info, dahlie[.] org, davidsfootwear[.] org, dobell[.] su, elegrina[.] com, energycoffe[.] org, energytea[.] org, etradesupply[.] org, exrpesso[.] org, foodandcot[.] com, freshchat[.] info, freshdepor[.] com, greatfurnituretradingco[.] org, info-js[.] link, jewsondirect[.] com, js-cloud[.] com, kandypens[.] net, kikvape[.] org, labbe[.] biz, lamoodbighats[.] net, link js[.] link, livechatinc[.] org, londontea[.] net, mage-checkout[.] org, magejavascripts[.] com, magescripts[.] pw, magesecuritys[.] com, majsurplus[.] com, map-js[.] link, mcloudjs[.] com, mechat[.] info, melbounestorm[.] com, misshaus[.] org, mylrendyphone[.] com, mypiltow[.] com, nililotan[.] org, oakandfort[.] org, ottocap[.] kuruluş, parklar[.] su, paypaypay[.] org, pmtonline[.] su, prodealscenter[.] com, replacemyremote[.] org, sagecdn[.] org, scriptoscript[.] com, güvenlik ödemesi[.] su, shop-rnib[.] org, slickjs[.] org, slickmin[.] com, smart-js[.] link, swappastore[.] com, teacoffe[.] net, top5value[.] com, track-js[.] link, ukcoffe[.] com, verywellfitnesse[.] com, walletgear[.] org, webanalyzer[.] net, zapaljs[.] com, zoplm[.] Com

16. Defender TI'nin Tehdit Bilgileri Giriş Sayfasında mypillow.com arayın ve Veri sekmesini seçin. Konak Çiftleri Veri dikey penceresini seçin. İlk Görülene göre sıralayın ve Ekim 2018'de gerçekleşen Konak Çifti ilişkilerini bulun.

    a. mypillow.com ile secure.livechatinc[.] arasında benzer bir betik ilişkisi farkeder misiniz? mypiltow ile mypillow.com aynı ilişkiyi yansıtan kuruluş[.] Com?
      - www.mypillow.com ilk olarak secure.livechatinc adresine ulaşırken nasıl gözlemlendiğine dikkat edin[.] 26.10.2018 tarihinde kuruluş, çünkü www.mypillow.com'den secure.livechatinc'e bir GET isteği gözlemlendi[.] Org. Bu ilişki 19.11.2018'e kadar sürdü.

           ![Öğretici Infra Chain My Pillowcom Konak Çiftleri Canlı Sohbet ScriptSrc](media/tutorialInfraChainMyPillowcomHostPairsLiveChatScriptSrc.gif) ii. Ayrıca secure.livechatinc[.] kuruluş www.mypillow.com sunucusuna (xmlhttprequest) erişmek için www.mypillow.com ulaştı.
17. mypillow.com'un Konak Çifti ilişkilerini daha fazla gözden geçirin.
    a. mypillow.com secure.livechatinc ile benzer bir etki alanı adına sahip konak çifti ilişkileri var mı[.] Org?
      - Evet. Konakların aşağıdaki etki alanlarıyla mypillow.com gözlemlenen ilişkilerin birden çok türü vardır:
        1. cdn.livechatinc[.] com, secure.livechatinc[.] com, api.livechatinc[.] Com
     - İlişkinin nedenleri şunlardır:
        1. script.src
        2. iframe.src
        3. bilinmeyen
        4. topLevelRedirect
        5. img.src
        6. xmlhttprequest
      - Livechat, çevrimiçi perakendecilerin web sitelerine ekleyebileceği bir canlı destek sohbet hizmetidir, bu nedenle üçüncü taraf bir kaynaktır ve MyPillow da dahil olmak üzere birçok e-ticaret platformu tarafından kullanılır. Bu sahte etki alanı biraz daha ilginç çünkü resmi sitesi aslında livechatinc.com. Bu nedenle, bu durumda, MyPillow web sitesine ikinci bir skimmer yerleştirdiklerini gizlemek için üst düzey etki alanı yazım hatası kullandılar.
18. Geri dön ve 'secure.livechatinc[.] ile bir konak çifti ilişkisi bulun öğesini seçin ve bu ana bilgisayar adını özetler.
    a. Bu ana bilgisayar Ekim 2018'de hangi IP adresine çözümlandı?
      - 212.109.222[.] 230

        ![Öğretici Infra Chain Secure Live Chat Inc Kuruluş Çözümleri](media/tutorialInfraChainSecureLiveChatIncOrgResolutions.png)
      - Bu IP adresinin Rusya'da da barındırılıp ASN Kuruluşunun JSC IOT olduğuna dikkat edin.

        ![Öğretici Infra Chain Secure Live Chat Inc Kuruluş IP Özeti](media/tutorialInfraChainSecureLiveChatIncOrgIpSummary.png)
19. 'secure.livechatinc[.] araması kuruluş'a tıklayın, Defender TI'nin Tehdit Bilgileri Giriş Sayfası'nda Veri sekmesini seçin ve Whois dikey penceresine tıklayın. 25.12.2018'den kaydı seçin.
    a. Bu kayıt için hangi Kayıt Şirketi kullanıldı?
      - OnlineNIC Inc.
            1. Bu, mypiltow'un kaydedilmesi için kullanılan Kayıt Şirketi[.]. aynı kampanya sırasında com.
                2. Kaydı 25.12.2018'den seçerseniz etki alanının aynı Çince gizlilik koruma hizmeti olan Etki Alanı Kimliği Kalkan Hizmeti'ni de kullandığını fark edeceksiniz[.] com da kullanılmıştı.
    b. Bu kayıt için hangi ad sunucuları kullanıldı?
      - ns1.jino.ru
      - ns2.jino.ru
      - ns3.jino.ru
      - ns4.jino.ru
        1. Bunlar, mypiltow için 10/01/2018 kaydında kullanılan ad sunucularıyla aynıydı[.] Com. Saldırganlar genellikle altyapılarını segmentlere ayırmak için aynı ad sunucularını kullanır.

            ![Öğretici Infra Chain Secure Live Chat Inc Org Whois](media/tutorialInfraChainSecureLiveChatIncOrgWhois.png)

            ![Öğretici Infra Chain My Piltowcom 2 Whois](media/tutorialInfraChainMyPiltowcom2Whois.png)
20. Konak Çiftleri Veri dikey penceresini seçin.
    a. Ekim ve Kasım 2018'den hangi konak çifti ilişkilerini görüyorsunuz?
      - secure.livechatinc[.] kuruluş kullanıcıları 19.11.2022 tarihinde secure.livechatinc.com yönlendirdi. Bu büyük olasılıkla algılamadan kaçınmaya yönelik bir karartma tekniğidir.
      - www.mypillow.com secure.livechatinc üzerinde barındırılan bir betiği çekiyordu[.] kuruluş (sahte LiveChat sitesi) 26.10.2018 ile 19.11.2022 arasında. Bu zaman çerçevesi boyunca www.mypillow.com'un kullanıcı satın alma işlemleri tehlikeye girmiş olabilir.
      - secure.livechatinc[.] kuruluş, 27.10.2018 ile 29.10.2018 tarihleri arasında gerçek MyPillow web sitesini (xmlhttprequest) barındıran www.mypillow.com sunucudan veri talep ediyor.

          ![Öğretici Infra Chain Secure Live Chat Inc Kuruluş Konak Çiftleri](media/tutorialInfraChainSecureLiveChatIncOrgHostPairs.png) b. Bu ilişkilerin ne anlama geldiğine inanıyorsunuz?

## <a name="clean-up-resources"></a>Kaynakları temizleme
Bu bölümde temizecek kaynak yok.

## <a name="next-steps"></a>Sonraki Adımlar
Bu öğreticide tehdit zekası ve altyapı zincirini bir araya getirerek güvenliği tehlikeye atabileceğinizi öğrendiniz.