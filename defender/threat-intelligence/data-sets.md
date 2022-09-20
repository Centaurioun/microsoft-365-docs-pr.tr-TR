---
title: Microsoft Defender Tehdit Analizi (Defender TI) Veri Kümeleri
description: Bu genel bakış makalesinde Microsoft Defender Tehdit Analizi (Defender TI) veri kümeleri özelliği hakkında bilgi edinin.
author: alexroland24
ms.author: aroland
manager: dolmont
ms.service: threat-intelligence
ms.topic: conceptual
ms.date: 08/02/2022
ms.custom: template-concept
ms.openlocfilehash: 908d50e2fbf39bb953abbbcf7d004e78e836dd30
ms.sourcegitcommit: 078149c9645ce220911ccd6ce54f984a4c92ce53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67811208"
---
# <a name="data-sets"></a>Veri kümeleri

Microsoft, çok sayıda veri kümesini tek bir platformda (Microsoft Defender Tehdit Analizi (Defender TI) merkezileştirerek Microsoft topluluğunun ve müşterilerinin altyapı analizi gerçekleştirmesini kolaylaştırır. Microsoft'un birincil odak noktası, çeşitli güvenlik kullanım örneklerini desteklemek için İnternet altyapısı hakkında mümkün olduğunca çok veri sağlamaktır.

Microsoft, kullanıcıların tehditleri algılamasına ve yanıtlamasına, olayları önceliklendirmesine ve erkenden harekete geçerek kullanıcıların kuruluşlarını hedefleyen aktör gruplarıyla ilişkili saldırganların altyapılarını belirlemesine yardımcı olmak için İnternet verilerini toplar, analiz eder ve dizinler. Microsoft, İnternet verilerini toplamak için PDNS algılayıcı ağı, sanal kullanıcılardan oluşan genel ara sunucu ağı, bağlantı noktası taramalarını kullanırken kötü amaçlı yazılım ve eklenen Etki Alanı Adı Sistemi (DNS) verileri için üçüncü taraf kaynaklardan yararlanır.

Bu internet verileri iki ayrı gruba ayrılır: geleneksel ve gelişmiş. Geleneksel veri kümeleri Çözümler, Whois, SSL Sertifikaları, Alt Etki Alanları, DNS, Ters DNS ve Hizmetler'i içerir. Gelişmiş veri kümeleri grubunda İzleyiciler, Bileşenler, Konak Çiftleri ve Tanımlama Bilgileri bulunur. İzleyiciler, Bileşenler, Konak Çiftleri ve Tanımlama Bilgileri veri kümeleri, gezinilen web sayfalarının Belge Nesne Modelinin (DOM) gözlemlenmesi ile toplanır. Bileşenler ve İzleyiciler veri kümeleri ayrıca, bağlantı noktası taramalarından veya SSL Sertifikası ayrıntılarından gelen başlık yanıtlarına göre tetiklenen algılama kurallarından da gözlemlenir.

![Veri Kümeleri Edge Ekran Görüntüsü](media/dataSetsEdgeScreenshot.png)

## <a name="resolutions"></a>Çözünürlük

Pasif DNS (PDNS), belirli bir konum, kayıt ve zaman çerçevesi için DNS çözümleme verilerini depolayan bir kayıt sistemidir. Bu geçmiş çözümleme veri kümesi, kullanıcıların ip adresine çözümlenen etki alanlarını (veya tam tersini) görüntülemesine olanak tanır. Bu veri kümesi, etki alanı veya IP çakışmasına dayalı zamana dayalı bağıntıya olanak tanır.
PDNS, önceden bilinmeyen veya yeni öne çıkan tehdit aktörü altyapısının tanımlanmasını etkinleştirebilir. Blok listelerine göstergelerin proaktif olarak eklenmesi, kampanyalar gerçekleşmeden önce iletişim yollarını kesebilir. Kullanıcılar Çözünürlükler veri kümesi sekmesinde A kayıt çözümleme verilerini bulur ve DNS veri kümesi sekmesinde daha fazla DNS kaydı türü bulur.

PDNS çözümleme verilerimiz şunları içerir:

- **Çözümle:** Çözümlenen varlığın adı (IP Adresi veya Etki Alanı)
- **Konum:** IP adresinin barındırılıyor olduğu konum.
- **Ağ:** IP adresiyle ilişkili netblock veya alt ağ.
- **ASN:** Otonom sistem numarası ve kuruluş adı
- **İlk Görüldü:** Bu çözümlemeyi ilk gözlemlediğimiz tarihi gösteren bir zaman damgası.
- **Son Görülme:** Bu çözümlemeyi en son gözlemlediğimiz tarihi gösteren bir zaman damgası.
- **Kaynak:** İlişkinin algılanması etkinleştirilen kaynak.
- **Etiketler:** Defender TI sisteminde bu yapıta uygulanan tüm etiketler.

![Veri Sekmesi Çözünürlükleri](media/dataTabResolutions.png)

## <a name="questions-this-data-set-may-help-answer"></a>Bu veri kümesinin yanıtlamaya yardımcı olabileceği sorular:

### <a name="domains"></a>Etki alanları
- Etki alanı, Defender TI tarafından bir IP adresine çözümlenirken ilk ne zaman gözlemlendi?

    ![Veri Kümeleri Etki Alanı İlk Kez Görüldü](media/dataSetsDomainFirstSeen.png)

- Defender TI tarafından bir IP adresine etkin bir şekilde çözümlendiğinde en son ne zaman görüldü?
    ![Veri Kümeleri Etki Alanı Son Görülme](media/dataSetsDomainLastSeen.png)

- Şu anda hangi IP adreslerine çözümleniyor?
    ![Veri Kümeleri Etki Alanı Etkin Re çözümleri](media/dataSetsDomainActiveResolutions.png)
  
### <a name="ip-addresses"></a>IP Adresleri
- IP adresi yönlendirilebilir mi?

    ![Yönlendirilebilir Veri Kümeleri IP'leri](media/dataSetsRoutableIPs.png)

- Hangi alt ağın parçası?

    ![Veri Kümeleri IP Alt Ağı](media/dataSetsIPSubnet.png)

- Alt ağ ile ilişkilendirilmiş bir sahip var mı?
  
    ![Veri Kümeleri IP Sahibi](media/dataSetsIPOwner.png)

- Hangi AS'nin parçası?

    ![Veri kümeleri IPASN](media/dataSetsIPASN.png)

- Hangi coğrafi konum var?
    ![Veri Kümeleri IP Coğrafi konumu](media/dataSetsIPGeolocation.png)

## <a name="whois"></a>Whois

Günde binlerce kez, etki alanları kişiler ve kuruluşlar arasında satın alınıyor ve/veya aktarılıyor. Tüm bunların gerçekleşmesini sağlama işlemi kolaydır ve kayıt şirketi sağlayıcısına bağlı olarak yalnızca birkaç dakika ve yaklaşık 7 ABD doları sürer. Ödeme ayrıntılarının yanı sıra, etki alanı ayarlandıktan sonra bazıları Whois kaydının bir parçası olarak depolanan kendiniz hakkında ek bilgiler sağlamanız gerekir. Bu, genel etki alanı kaydı olarak kabul edilir. Ancak, kişisel bilgilerinizi etki alanınızın Whois kaydından gizleyebileceğiniz özel etki alanı kayıt hizmetleri vardır. Bu durumlarda etki alanı sahibinin bilgileri güvenlidir ve kayıt şirketinin bilgileriyle değiştirilir. Analistlerin sahip oldukları diğer etki alanlarını bulmasını zorlaştırmak için daha fazla aktör grubu özel etki alanı kayıtları gerçekleştiriyor. Defender TI, Whois kayıtları müşteri adayı sağlamadığında aktörlerin paylaşılan altyapısını bulmak için çeşitli veri kümeleri sağlar.

Whois, herkesin bir etki alanı, IP adresi veya alt ağ hakkındaki bilgileri sorgulamasına olanak tanıyan bir protokoldür. Tehdit altyapısı araştırmalarında Whois için en yaygın işlevlerden biri, Whois kayıtlarında paylaşılan benzersiz verileri temel alarak farklı varlıkları tanımlamak veya bağlamaktır. Dikkatle okuyorsanız veya bir etki alanı satın aldıysanız kayıt şirketlerinden istenen içeriğin hiçbir zaman doğrulanmamış olduğunu fark etmiş olabilirsiniz. Aslında, kayıtlara her şeyi koyabilirdiniz (ve birçok insan bunu yapar) ve bu da dünyaya gösterilebilirdi.

Her Whois kaydının farklı bölümleri vardır ve bunların tümü farklı bilgiler içerebilir. Yaygın olarak bulunan bölümler arasında "kayıt şirketi", "kayıt şirketi", "yönetici" ve her birinde kayıt için farklı bir kişiye karşılık gelen "teknik" yer alır. Bu veriler çoğu zaman bölümler arasında çoğaltılır, ancak bazı durumlarda, özellikle bir aktör hata yaptıysa hafif tutarsızlıklar olabilir. Defender TI'da Whois bilgilerini görüntülerken, verilerin yinelenenlerini kaldıran ve kaydın hangi bölümünden geldiğini belirten sıkıştırılmış bir kayıt görürsünüz. Bu sürecin analist iş akışını büyük ölçüde hızlandırıp verilerin gözden kaçmasını önlemektedir. Defender TI'nin Whois bilgileri WhoisIQ™ veritabanı tarafından desteklenir.

Whois verilerimiz şunları içerir:
- **Kayıt Güncelleştirildi:** Whois kaydının son güncelleştirildiği günü gösteren bir zaman damgası.
- **Son Taranan:** Defender TI sisteminin kaydı en son taramış olduğu tarih.
- **Süre sonu:** Varsa kaydın son kullanma tarihi.
- **Oluşturuldu:** Geçerli Whois kaydının yaşı.
- **Whois Server:** Sunucu, ICANN onaylı bir kayıt şirketi tarafından, içinde kayıtlı etki alanları hakkında güncel bilgiler almak için ayarlanır. 
- **Kayıt şirketi:** Yapıtı kaydetmek için kullanılan kayıt şirketi hizmeti.
- **Etki Alanı Durumu:** Etki alanının geçerli durumu. "Etkin" bir etki alanı İnternet'te canlı olarak bulunur. 
- **Email:** Whois kaydında bulunan tüm e-posta adresleri ve her birinin ilişkili olduğu kişi türü (örneğin yönetici, teknik).
- **Ad:** Kayıttaki herhangi bir kişinin adı ve her birinin ilişkili olduğu kişi türü.
- **Kuruluş:** Kayıttaki herhangi bir kuruluşun adı ve her birinin ilişkili olduğu kişi türü.
- **Sokak:** Kayıtla ilişkilendirilmiş tüm sokak adresleri ve ilişkili olduğu kişi türü.
- **Şehir:** Kayıtla ilişkilendirilmiş bir adreste listelenen herhangi bir şehir ve ilişkili olduğu kişi türü.
- **Durum:** Kayıtla ilişkilendirilmiş bir adreste listelenen tüm durumlar ve ilişkili olduğu kişi türü.
- **Posta Kodu:** Kayıtla ilişkilendirilmiş bir adreste listelenen tüm posta kodları ve ilişkili olduğu kişi türü.
- **Ülke:** Kayıtla ilişkilendirilmiş bir adreste listelenen tüm ülkeler ve ilişkili olduğu kişi türü.
- **Telefon:** Kayıtta listelenen tüm telefon numaraları ve ilişkili olduğu kişi türü.
- **Ad Sunucuları:** Kayıtlı varlıkla ilişkilendirilmiş tüm ad sunucuları.

## <a name="current-whois-lookups"></a>Geçerli Whois aramaları

![Veri Sekmesi WHOIS](media/dataTabWHOIS.png)

Defender TI'nin geçerli Whois deposu, Microsoft'un Whois koleksiyonunda şu anda kayıtlı ve ilgi çekici Whois özniteliğiyle ilişkili tüm etki alanlarını vurgular. Bu veriler, etki alanını kaydetmek için kullanılan e-posta adresiyle birlikte etki alanının kaydını ve sona erme tarihini vurgular. Bu veriler platformun Whois Search sekmesinde görüntülenir.

## <a name="historical-whois-lookups"></a>Geçmiş Whois aramaları

![Whois GeçmişiNde Ara](media/searchWhoisHistory.png)

Defender TI'nin Whois Geçmişi deposu, kullanıcılara sistemin gözlemlerine göre Whois öznitelikleriyle bilinen tüm geçmiş etki alanı ilişkilendirmelerine erişim sağlar. Bu veri kümesi, kullanıcının sorgulanan etki alanı ve öznitelik arasındaki ilişkiyi ilk kez ve son gözlemlediğimizde görüntülenmesini özetlediği bir öznitelikle ilişkili tüm etki alanlarını vurgular. Bu veriler, geçerli Whois Arama sekmesinin yanındaki ayrı bir sekmede görüntülenir.

**Bu veri kümesinin yanıtlamaya yardımcı olabileceği sorular:**

- Etki alanı kaç yaşında?

    ![Veri Kümeleri Whois Etki Alanı Yaşı](media/dataSetsWhoisDomainAge.png)

- Bilgiler gizlilikle korunuyor gibi görünüyor mu?

    ![Veri Kümeleri Whois Gizlilik Korumalı](media/dataSetsWhoisPrivacyProtected.png)

- Verilerden herhangi biri benzersiz görünüyor mu?

    ![Veri Kümeleri Whois Benzersiz](media/dataSetsWhoisUnique.png)

- Hangi ad sunucuları kullanılır?

    ![Veri Kümeleri Whois Ad Sunucuları](media/dataSetsWhoisNameServers.png)

- Bu bir çukur etki alanı mı?

    ![Veri Kümeleri Whois Sinkhole](media/dataSetsWhoisSinkhole.png)

- Burası park edilmiş bir alan mı?

    ![Whois Parked Etki Alanı Veri Kümeleri](media/dataSetsWhoisParkedDomain.png)

- Bu bir baldanlık etki alanı mı?

    ![Veri Kümeleri Whois Honeypot Etki Alanı](media/dataSetsWhoisHoneypotDomain.png)

- Bir geçmişi var mı?

    ![Veri Kümeleri Whois Geçmişi](media/dataSetsWhoisHistory.gif)

- Sahte gizlilik koruma e-postaları var mı?

    ![Veri Kümeleri Whois Sahte Gizlilik E-postaları](media/dataSetsWhoisFakePrivacyEmails.png)

- Whois kayıtlarında sahte isimler var mı?

- Etki alanları arasında paylaşılmış olabilecek Whois değerlerine karşı arama yaparak ilgili ek GÇ'leri belirlediniz mi?

    ![Veri Kümeleri Whois Paylaşılan Değer Araması](media/dataSetsWhoisSharedValueSearch.gif)

## <a name="certificates"></a>Sertifika
SSL Sertifikaları, verilerinizin güvenliğini sağlamanın ötesinde, kullanıcıların farklı ağ altyapısına bağlanması için harika bir yoldur. Modern tarama teknikleri, İnternet'teki her düğüme yönelik veri isteklerini birkaç saat içinde gerçekleştirmemize olanak tanır, bu da bir sertifikayı düzenli aralıklarla barındıran bir IP adresiyle kolayca ilişkilendirebileceğimiz anlamına gelir.

Whois kaydı gibi SSL sertifikaları da son ürünü oluşturmak için kullanıcı tarafından bilgi sağlanmasını gerektirir. Etki alanının yanı sıra, SSL sertifikası için oluşturulur (otomatik olarak imzalanmadığı sürece), ek bilgilerden herhangi biri kullanıcı tarafından oluşturulabilir. Microsoft kullanıcılarının SSL sertifikalarından en fazla değeri gördüğü durumlarda, sertifikayı oluştururken birinin kullanabileceği benzersiz veriler değil, barındırıldığı yer olması gerekir.

Ssl sertifikasına erişmek için bir web sunucusuyla ilişkilendirilmesi ve belirli bir bağlantı noktası üzerinden (en sık 443) kullanıma sunulmaları gerekir. Toplu İnternet taramalarını haftalık olarak kullanarak tüm IP adreslerini taramak ve sertifika verilerinin geçmiş bir deposunu oluşturmak için barındırılan tüm sertifikaları almak mümkündür. SSL sertifika eşlemelerine yönelik IP adresleri veritabanına sahip olmak, kullanıcılara altyapıdaki çakışmaları tanımlamanın bir yolunu sağlar.

Bu kavramı daha fazla göstermek için, bir aktörün otomatik olarak imzalanan SSL sertifikasına sahip bir sunucu ayarladığını düşünün. Birkaç gün sonra, savunucular altyapılarına alışıp kötü amaçlı içerik barındıran web sunucusunu engeller. Aktör, tüm sıkı çalışmalarını yok etmek yerine yalnızca tüm içeriği (SSL sertifikası dahil) kopyalar ve bunları yeni bir sunucuya yerleştirir. Kullanıcı olarak, artık sertifikanın benzersiz SHA-1 değeri kullanılarak her iki web sunucusuna da (biri engellenmiş, biri bilinmeyen) bir şekilde bağlandığını söylemek için bir bağlantı oluşturulabilir.

SSL sertifikalarını daha değerli kılan şey, pasif DNS veya Whois verilerinin kaçırabileceği bağlantılar oluşturabilmeleridir. Bu, olası kötü amaçlı altyapıyı ilişkilendirmenin ve aktörlerin olası operasyonel güvenlik hatalarını belirlemenin daha fazla yolu anlamına gelir. Defender TI, 2013'ten bugüne kadar 30 milyondan fazla sertifika toplayarak kullanıcılara sertifika içeriği ve geçmişi üzerinde bağıntılar yapma araçları sağlar.

SSL sertifikaları, şifreleme anahtarını kullanıcı tarafından sağlanan bir dizi ayrıntıya dijital olarak bağlayan dosyalardır. Defender TI, internet tarama tekniklerini kullanarak çeşitli bağlantı noktalarındaki IP adreslerinden SSL sertifika ilişkilendirmeleri toplar. Bu sertifikalar yerel bir veritabanının içinde depolanır ve belirli bir SSL sertifikasının İnternet'te göründüğü yer için bir zaman çizelgesi oluşturmamıza olanak tanır.

Sertifika verilerimiz şunları içerir:

- **Sha1:** BIR SSL Sertifikası varlığı için SHA1 algoritma karması.
- **İlk Görüldü:** Bir yapıtta bu sertifikayı ilk gözlemlediğimiz tarihi gösteren bir zaman damgası.
- **Son Görülme:** Bir yapıtta bu sertifikayı en son gözlemlediğimiz tarihi gösteren bir zaman damgası.
- **Altyapı:** Sertifikayla ilişkili tüm ilgili altyapılar.

![Veri Sekmesi Sertifika Listesi](media/dataTabCertificatesList.png)

Kullanıcı SHA1 karması üzerinde genişlediğinde aşağıdakiler hakkındaki ayrıntıları görebilir: **
- **Seri Numarası:** SSL sertifikasıyla ilişkili seri numarası.
- **Verilen:** Sertifikanın verildiği tarih.
- **Sona eri -yor:** Sertifikanın süresinin dolacağı tarih.
- **Konu Ortak Adı:** İlişkili SSL Sertifikaları için Konu Ortak Adı.
- **Verenin Ortak Adı:** İlişkili SSL Sertifikaları için VerenIn Ortak Adı.
- **Konu Alternatif Adları:** SSL Sertifikası için herhangi bir alternatif ortak ad.
- **VerenIn Alternatif Adları:** Verenin ek adları.
- **Konu Kuruluş Adı:** SSL sertifika kaydına bağlı kuruluş.
- **Veren Kuruluş Adı:** Sertifika sorununu düzenleyen kuruluşun adı.
- **SSL Sürümü:** Sertifikanın kayıtlı olduğu SSL sürümü.
- **Konu Kuruluş Birimi:** Sertifikadan sorumlu kuruluştaki departmanı gösteren isteğe bağlı meta veriler.
- **Veren Kuruluş Birimi:** Sertifikayı veren kuruluş hakkında ek bilgi.
- **Konu Sokak Adresi:** Kuruluşun bulunduğu sokak adresi.
- **VerenIn Sokak Adresi:** Veren kuruluşun bulunduğu sokak adresi.
- **Konu Yerelliği:** Kuruluşun bulunduğu şehir.
- **VerenIn Konumu:** Veren kuruluşun bulunduğu şehir.
- **Konu Eyalet/İl:** Kuruluşun bulunduğu eyalet veya il.
- **Veren Eyalet/İl:** Veren kuruluşun bulunduğu eyalet veya il.
- **Konu Ülke:** Kuruluşun bulunduğu ülke.
- **Veren Ülke:** Veren kuruluşun bulunduğu ülke.
- **İlgili Altyapı:** Sertifikayla ilişkili tüm ilgili altyapılar.

![Veri Sekmesi Sertifika Ayrıntıları](media/dataTabCertificateDetails.png)

**Bu veri kümesinin yanıtlamaya yardımcı olabileceği sorular:**

- Bu sertifikanın başka hangi altyapıyla ilişkilendirildiği gözlemlendi?

    ![Veri Kümeleri Sertifikayla İlgili Altyapı](media/dataSetsCertificateRelatedInfrastructure.png)

- Sertifikada iyi pivot noktaları görevi görecek benzersiz veri noktaları var mı?

    ![Veri Kümeleri Sertifika Özet Noktaları](media/dataSetsCertificatePivotPoints.png)

- Sertifika otomatik olarak imzalandı mı?

    ![Veri Kümeleri Sertifikası Otomatik İmzalı](media/dataSetsCertificateSelfSigned.png)

- Sertifika ücretsiz bir sağlayıcıdan mı geliyor?

    ![Veri Kümeleri SertifikasıFree Sağlayıcısı](media/dataSetsCertificateFreeProvider.png)

- Sertifika hangi zaman diliminde kullanımda gözlemlendi?

    ![Veri Kümeleri Sertifikaları Gözlem Tarihleri](media/dataSetsCertificatesObservationDates.png)

## <a name="subdomains"></a>Alt

Alt etki alanı, birincil etki alanının parçası olan bir internet etki alanıdır. Alt etki alanları "konak" olarak da adlandırılır. Örneğin,`learn.microsoft.com` bir alt etki alanıdır `microsoft.com`. Her alt etki alanı için, etki alanının çözümlendiği yeni bir IP adresleri kümesi olabilir ve bu, ilgili altyapıyı bulmak için harika bir veri kaynağı olabilir.

Alt etki alanı verilerimiz şunları içerir:

- **Ana bilgisayar adı:** Aranan etki alanıyla ilişkili alt etki alanı.
- **Etiketler:** Defender TI sisteminde bu yapıta uygulanan tüm etiketler.

![Veri Sekmesi Alt etki alanları](media/dataTabSubdomains.png)

**Bu veri kümesinin yanıtlamaya yardımcı olabileceği sorular:**

- Üst düzey etki alanıyla ilişkili daha fazla alt etki alanı var mı?

    ![Veri Kümeleri Alt etki alanları](media/dataSetsSubdomains.png)

- Kötü amaçlı etkinliklerle ilişkili alt etki alanları var mı?

    ![Veri Kümeleri Alt Etki Alanları Kötü Amaçlı](media/dataSetsSubdomainsMalicious.png)

- Bu etki alanınızsa, herhangi bir alt etki alanı yabancı görünüyor mu?

- Diğer kötü amaçlı etki alanlarıyla ilişkili olarak listelenen alt etki alanlarında herhangi bir desen var mı?

- Her alt etki alanını özetleyerek hedefle daha önce ilişkilendirilmemiş yeni IP alanı ortaya çıkıyor mu?

- Kök etki alanıyla eşleşmeyen başka hangi ilgisiz altyapıyı bulabilirsiniz?

## <a name="trackers"></a>Izci

İzleyiciler, web sayfalarında bulunan ve genellikle kullanıcı etkileşimini izlemek için kullanılan benzersiz kodlar veya değerlerdir. Bu kodlar, farklı bir web sitesi grubunu merkezi bir varlıkla ilişkilendirmek için kullanılabilir. Aktörler genellikle kimlik avı kampanyası için kimliğine bürünmek istedikleri bir kurbanın web sitesinin kaynak kodunu kopyalar. Kullanıcılar, Microsoft İzleyicileri veri kümesini kullanarak bu sahte siteleri tanımlamalarına olanak sağlayan bu kimlikleri kaldırmak için nadiren zaman ayıracaktır. Aktörler ayrıca siber saldırı kampanyalarının ne kadar başarılı olduğunu görmek için izleyici kimlikleri dağıtabilir. Bu, pazarlama kampanyalarının başarısını izlemek için Google Analytics İzleyici Kimliği gibi SEO kimliklerinden yararlanan pazarlamacılara benzer.

Microsoft'un İzleyici veri kümesi Google, Yandex, Mixpanel, New Relic, Clicky gibi sağlayıcılardan gelen kimlikleri içerir ve düzenli aralıklarla büyümeye devam etmektedir.

İzleyici verilerimiz şunları içerir:

- **Ana bilgisayar adı:** İzleyicinin algılandığı altyapıyı barındıran konak adı.
- **İlk Görüldü:** Yapıt üzerinde bu izleyiciyi ilk gözlemlediğimiz tarihi gösteren bir zaman damgası.
- **Son Görülme:** Yapıt üzerinde bu izleyiciyi en son gözlemlediğimiz tarihi gösteren bir zaman damgası.
- **Tür:** Algılanan izleyici türü (ör. GoogleAnalyticsID, JarmHash).
- **Değer:** izleyicinin tanımlama değeri.
- **Etiketler:** Defender TI sisteminde bu yapıta uygulanan tüm etiketler.

![Veri Sekmesi İzleyicileri](media/dataTabTrackers.png)

**Bu veri kümesinin yanıtlamaya yardımcı olabileceği sorular:**

- Aynı analiz kimliklerini kullanan başka kaynaklar var mı?

    ![Veri Kümeleri İzleyicileri Pivot Analytics Hesabı](media/dataSetsTrackersPivotAnalyticsAccount.gif)

- Bu kaynaklar kuruluşla ilişkili mi yoksa ihlal saldırısı gerçekleştirmeye mi çalışıyorsunuz?

- İzleyiciler arasında çakışma var mı? Bunlar diğer web siteleriyle paylaşılıyor mu?

- Web sayfasında bulunan izleyici türleri nelerdir?

    ![Veri Kümeleri İzleyici Türleri](media/dataSetsTrackersTypes.png)

- İzleyiciler için süre nedir?

    ![Veri Kümeleri İzleyicileri UzunlukSaylık](media/dataSetsTrackersLengthOfTime.png)

- İzleyici değerleri için değişiklik sıklığı nedir? Bunlar geliyor mu, gidiyor mu yoksa kalıyor mu?

- Web sitesi kopyalama yazılımına (MarkOfTheWeb veya HTTrack) bağlanan izleyiciler var mı?

    ![Veri Kümeleri İzleyicileriHt Track](media/dataSetsTrackersHtTrack.png)

- Kötü amaçlı C2 sunucusu kötü amaçlı yazılımlarına (JARM) bağlanan izleyiciler var mı?

    ![Veri Kümeleri İzleyicileri JARM](media/dataSetsTrackersJARM.png)

## <a name="components"></a>Bileşen

Web bileşenleri, Web gezinmesi veya taraması yapan Microsoft'tan alınan bir web sayfasını veya sunucu altyapısını açıklayan ayrıntılardır. Bu bileşenler, kullanıcının bir web sayfasının yapısını veya belirli bir altyapı parçasını yönlendiren teknoloji ve hizmetleri anlamasına olanak tanır.
Benzersiz bileşenler üzerinde özetleme, aktörlerin altyapısını veya güvenliği aşılmış diğer siteleri bulabilir. Kullanıcılar ayrıca, bir web sitesinin çalıştırdığı teknolojilere bağlı olarak belirli bir saldırıya veya güvenlik açığına karşı savunmasız olup olmadığını da anlayabilir.

Bileşen verilerimiz şunları içerir:

- **Konak adı:** Bileşenin algılandığı altyapıyı barındıran konak adı.
- **İlk Görüldü:** Yapıt üzerinde bu bileşeni ilk kez gözlemlediğimiz tarihin zaman damgası.
- **Son Görülme:** Yapıt üzerinde bu bileşeni son gözlemlediğimiz tarihin zaman damgası.
- **Kategori:** Algılanan bileşenin türü (örneğin İşletim Sistemi, Çerçeve, Uzaktan Erişim, Sunucu).
- **Ad + Sürüm:** bileşen adı ve yapıt üzerinde çalışan sürüm (örneğin, Microsoft IIS (v8.5).
- **Etiketler:** Defender TI sisteminde bu yapıta uygulanan tüm etiketler.

![Veri Sekmesi Bileşenleri](media/dataTabComponents.png)

**Bu veri kümesinin yanıtlamaya yardımcı olabileceği sorular:**

- Hangi savunmasız altyapıyı kullanıyorsunuz?

    ![Veri Kümeleri Bileşenleri Savunmasız Bileşenler](media/dataSetsComponentsVulnerableComponents.png)

    ![Veri Kümeleri Bileşenleri Prototip J'leri Güvenlik Açığı Olan Sürüm](media/dataSetsComponentsPrototypeJsVulnerableVersion.png)

    Magento v1.9, Microsoft'un bu sürüm için güvenilir belgeleri bulamadığı kadar tarihlidir.

- Hangi benzersiz web bileşenlerini kullanan tehdit aktörü bunları diğer etki alanlarına kadar izleyebilir?

- Kötü amaçlı olarak işaretlenmiş bileşenler var mı?

- Tanımlanan web bileşeni sayısı nedir?

    ![Veri Kümeleri Bileşen Sayısı Bileşen Sayısı](media/dataSetsComponentsNumberOfComponents.png)

- Sık sık görülmeyen benzersiz veya garip teknolojiler var mı?

    ![Veri Kümeleri Bileşenleri Benzersiz Bileşenleri](media/dataSetsComponentsUniqueComponents.png)

- Belirli teknolojilerin sahte sürümleri var mı?

- Web bileşenlerinde sıklıkla veya nadiren yapılan değişikliklerin sıklığı nedir?

- Kötüye kullanılması bilinen şüpheli kitaplıklar var mı?

- Bunlarla ilişkili güvenlik açıklarına sahip teknolojiler var mı?

## <a name="host-pairs"></a>Konak çiftleri

Konak çiftleri, sanal kullanıcının web gezinmesinden gözlemlenen bir bağlantıyı paylaşan iki altyapı parçasıdır (üst ve alt öğe). Bağlantı, en üst düzey yeniden yönlendirmeden (HTTP 302) iframe veya betik kaynağı başvurusu gibi daha karmaşık bir şeye kadar değişebilir.

Konak çifti verilerimiz şunları içerir:

- **Üst Konak Adı:** Bir varlığa başvuran veya alt konağa "ulaşan" konak
- **Alt Konak Adı:** Üst konak tarafından çağrılan konak
- **İlk Görüldü:** Konakla ilk kez bir ilişki gözlemlediğimiz tarihin zaman damgası.
- **Son Görülme:** Konakla bir ilişkiyi en son gözlemlediğimiz tarihin zaman damgası.
- **Neden:** Üst ve alt konak adı arasındaki bağlantının türü. Olası nedenler script.src, link.href, redirect, img.src, unknown, xmlhttprequest, a.href, finalRedirect, css.import veya parentPage bağlantılarıdır.
- **Etiketler:** Defender TI sisteminde bu yapıta uygulanan tüm etiketler.

![Veri Sekmesi Konak Çiftleri](media/dataTabHostPairs.png)

**Bu veri kümesinin yanıtlamaya yardımcı olabileceği sorular:**

- Bağlantılı yapıtlardan herhangi biri engellendi mi?
- Bağlı yapıtlardan herhangi biri etiketlendi mi (Kimlik Avı, APT, Kötü Amaçlı, Şüpheli, Tehdit Aktörü Adı)?
- Bu konak kullanıcıları kötü amaçlı içeriğe yönlendiriyor mu?

    ![Veri Kümeleri Konak Çiftleri Kötü Amaçlı Yeniden Yönlendirme](media/dataSetsHostPairsMaliciousRedirect.png)

- İhlal saldırılarını ayarlamak için kaynaklar CSS'de mi yoksa görüntülerde mi çekiliyor?

    ![Veri Kümeleri Konak Çiftleri İhlali Saldırısı](media/dataSetsHostPairsInfringementAttack.png)

- Kaynaklar bir betiği çekiyor mu yoksa Magecart veya skimming saldırısı ayarlamak için link.href'e mi başvuruyor?
    ![Veri Kümeleri Ana Bilgisayar Çiftleri Skimmer Başvurusu](media/dataSetsHostPairsSkimmerReference.png)

- Kullanıcılar nereden/nereye yönlendiriliyor?

- Ne tür bir yeniden yönlendirme gerçekleştirilmektedir?

## <a name="cookies"></a>Tanımlama bilgileri

Tanımlama bilgileri, kullanıcı İnternet'e göz atarken sunucudan istemciye gönderilen küçük veri parçalarıdır. Bu değerler bazen uygulamanın durumunu veya izleme verilerinin küçük bitlerini içerir. Defender TI, bir web sitesinde gezinirken gözlemlenen tanımlama bilgisi adlarını vurgular ve dizinler ve kullanıcıların gezinme ve veri toplama işlemlerinde belirli tanımlama bilgisi adlarını gözlemlediğimiz her yeri incelemelerine olanak tanır. Tanımlama bilgileri, kötü amaçlı aktörler tarafından virüslü kurbanları izlemek veya daha sonra kullanılacak verileri depolamak için de kullanılır.

Tanımlama bilgisi verilerimiz şunları içerir:

- **Ana bilgisayar adı:** tanımlama bilgisi ile ilişkili konak altyapısı.
- **İlk Görüldü:** Yapıt üzerinde bu tanımlama bilgisini ilk kez gözlemlediğimiz tarihin zaman damgası.
- **Son Görülme:** Yapıt üzerinde bu tanımlama bilgisini en son gözlemlediğimiz tarihin zaman damgası.
- **Ad:** Tanımlama bilgisinin adı (ör. JSESSIONID, SEARCH_NAMESITE).
- **Etki alanı:** Tanımlama bilgisi ile ilişkili etki alanı.
- **Etiketler:** Defender TI sisteminde bu yapıta uygulanan tüm etiketler.

![Veri Sekmesi Tanımlama Bilgileri](media/dataTabCookies.png)

**Bu veri kümesinin yanıtlamaya yardımcı olabileceği sorular:**

- Aynı tanımlama bilgilerini başka hangi web siteleri kullanıyor?

    ![Aynı Tanımlama Bilgisini Veren Veri Kümeleri Tanımlama Bilgileri Etki Alanları](media/dataSetsCookiesDomainsIssuingSameCookie.png)

- Aynı tanımlama bilgilerini başka hangi web siteleri izliyor?
    ![Veri Kümeleri Tanımlama Bilgileri Etki Alanları Aynı Tanımlama Bilgisini İzleme](media/dataSetsCookiesDomainsTrackingSameCookie.png)

- Tanımlama bilgisi etki alanı sorgunuzla eşleşmiyor mu?

- Yapıtla ilişkili tanımlama bilgilerinin sayısı nedir?

    ![Yapıtla İlişkili Veri Kümeleri Tanımlama Bilgileri Numarası](media/dataSetsCookiesNumberAssociatedwithArtifact.png)

- Benzersiz tanımlama bilgisi adları veya etki alanları var mı?

- Tanımlama bilgileriyle ilişkili zaman aralıkları nelerdir?

- Yeni gözlemlenen tanımlama bilgilerinin veya tanımlama bilgileriyle ilişkili değişikliklerin sıklığı nedir?

## <a name="services"></a>Hizmetleri

Hizmet adları ve bağlantı noktası numaraları TCP, UDP, DCCP ve SCTP gibi aktarım protokolleri üzerinden çalışan farklı hizmetleri ayırt etmek için kullanılır. Bağlantı noktası numaraları, belirli bir bağlantı noktasında çalışan uygulama türünü önerebilir. Ancak uygulamalar veya hizmetler, bir IP adresinde hizmeti veya uygulamayı karartmak veya gizlemek için farklı bir bağlantı noktası kullanacak şekilde değiştirilebilir. Bağlantı noktası ve üst bilgi/başlık bilgilerini bilmek, gerçek uygulamayı/hizmeti ve kullanılan bağlantı noktalarının birleşimini tanımlayabilir. Defender TI, Hizmetler sekmesinde 14 günlük geçmişi ortaya kaldırarak gözlemlenen bir bağlantı noktasıyla ilişkili son başlık yanıtını görüntüler.

Hizmetler verilerimiz şunları içerir:

- Gözlemlenen açık bağlantı noktaları
- Bağlantı noktası numaraları
- Bileşen
- Hizmetin gözlemlenme sayısı
- Bağlantı noktasının en son ne zaman tarandığını
- Protokol bağlantısı
- Bağlantı noktasının durumu
  - Açık
  - Filtre
  - Kapatıldı
- Başlık yanıtı

![Veri Sekmesi Hizmetleri](media/dataTabServices.png)

**Bu veri kümesinin yanıtlamaya yardımcı olabileceği sorular:**

- Belirli bir IP adresi için belirli bir bağlantı noktasında hangi uygulamalar çalışıyor?

    ![Çalışan Veri Kümeleri Hizmetleri Uygulamaları](media/dataSetsServicesApplicationsRunning.png)

- Hangi uygulama sürümü kullanılıyor?

    ![Veri Kümeleri Hizmetleri Sürümü Çalışıyor](media/dataSetsServicesVersionRunning.png)

- Belirli bir bağlantı noktası için açık, filtrelenmiş veya kapalı durumunda son değişiklikler yapıldı mı?

    ![Veri Kümeleri Hizmetleri Bağlantı Noktası Durumları](media/dataSetsServicesPortStatuses.png)

- Bağlantıyla ilişkili bir sertifika var mıydı?

    ![Veri Kümeleri Hizmetleri Sertifika İlişkilendirmeleri](media/dataSetsServicesCertificateAssociations.png)

- Belirli bir varlıkta güvenlik açığı olan veya kullanım dışı bırakılan teknolojiler kullanılıyor mu?

    ![Çalışan Veri Kümeleri Hizmetleri Uygulamaları](media/dataSetsServicesApplicationsRunning.png)

    ![Veri Kümeleri Hizmetleri Güvenlik Açığı Olan Hizmet](media/dataSetsServicesVulnerableService.png)

- Bilgiler, kötü amaçlarla kullanılabilecek çalışan bir hizmet tarafından kullanıma sunuldu mu?

- En iyi güvenlik uygulamaları izleniyor mu?

## <a name="dns"></a>DNS

Microsoft, yıllardır DNS kayıtlarını toplayarak kullanıcılara posta değişimi (MX) kayıtları, ad sunucusu (NS) kayıtları, metin (TXT) kayıtları, yetki başlangıcı (SOA) kayıtları, kurallı ad (CNAME) kayıtları ve işaretçi (PTR) kayıtları hakkında içgörü sağlar. DNS kayıtlarını gözden geçirmek, sahip oldukları etki alanları genelinde aktörler tarafından kullanılan paylaşılan altyapıyı tanımlamak için yararlı olabilir. Örneğin aktör grupları, komut ve denetimlerini yönetmek için altyapılarını veya aynı posta değişim sunucularını segmentlere ayırmak için aynı ad sunucularını kullanma eğilimindedir.

DNS verilerimiz şunları içerir:

- **Değer:** Konakla ilişkilendirilmiş DNS kaydı.
- **İlk Görüldü:** Yapıtta bu kaydı ilk kez gözlemlediğimiz tarihi gösteren bir zaman damgası.
- **Son Görülme:** Yapıt üzerinde bu kaydı en son gözlemlediğimiz tarihi gösteren bir zaman damgası.
- **Tür:** Kayıtla ilişkilendirilmiş altyapının türü. Olası seçenekler Posta Sunucuları (MX), metin dosyaları (TXT), ad sunucuları (NS), CNAMES ve Yetki Başlangıcı (SOA) kayıtlarını içerir.
- **Etiketler:** Defender TI sisteminde bu yapıta uygulanan tüm etiketler.

![Veri Sekmesi DNS](media/dataTabDNS.png) 

**Bu veri kümesinin yanıtlamaya yardımcı olabileceği sorular:**

- Başka hangi altyapı parçaları, aradığım göstergeyle doğrudan ilişkilidir?
- Altyapı zaman içinde nasıl değişti?
- Etki alanı sahibi bir içerik teslim ağının veya marka koruma hizmetinin hizmetlerini kullanıyor mu?
- İlişkili kuruluş kendi ağı içinde başka hangi teknolojileri kullanıyor olabilir?

## <a name="reverse-dns"></a>DNS'i ters çevir

İleriye doğru DNS araması belirli bir ana bilgisayar adının IP adresini sorgularken, ters DNS araması bir IP adresinin belirli bir ana bilgisayar adını sorgular. Bu veri kümesi, DNS veri kümesiyle benzer sonuçlar gösterir. DNS kayıtlarını gözden geçirmek, sahip oldukları etki alanları genelinde aktörler tarafından kullanılan paylaşılan altyapıyı tanımlamak için yararlı olabilir. Örneğin aktör grupları, komut ve denetimlerini yönetmek için altyapılarını veya aynı posta değişim sunucularını segmentlere ayırmak için aynı ad sunucularını kullanma eğilimindedir.

Ters DNS verilerimiz şunları içerir:

- **Değer:** Ters DNS kaydının değeri.
- **İlk Görüldü:** Yapıt üzerinde bu kaydı ilk kez gözlemlediğimiz tarihin zaman damgası.
- **Son Görülme:** Yapıtta bu kaydı ilk kez gözlemlediğimiz tarihin zaman damgası.
- **Tür:** Kayıtla ilişkilendirilmiş altyapının türü. Olası seçenekler Posta Sunucuları (MX), metin dosyaları (TXT), ad sunucuları (NS), CNAMES ve Yetki Başlangıcı (SOA) kayıtlarını içerir.
- **Etiketler:** Defender TI sisteminde bu yapıta uygulanan tüm etiketler.

![Veri Sekmesi TERS DNS](media/dataTabReverseDNS.png)

**Bu veri kümesinin yanıtlamaya yardımcı olabileceği sorular:**

- Bu ana bilgisayarı hangi DNS kayıtları gözlemledi?
- Bu konağı gözlemleyen altyapı zaman içinde nasıl değişti?

## <a name="next-steps"></a>Sonraki adımlar

Daha fazla bilgi için bkz.:

- [Arama ve özetleme](searching-and-pivoting.md)
- [Verileri sıralama, filtreleme ve indirme](sorting-filtering-and-downloading-data.md)
- [Altyapı zincirleme](infrastructure-chaining.md)
- [Öğretici: Tehdit bilgilerini ve altyapı zincirini toplama](gathering-threat-intelligence-and-infrastructure-chaining.md)
