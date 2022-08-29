---
title: '&amp; Microsoft Defender Tehdit Analizi ile özet arama (Defender TI)'
description: Microsoft Defender Tehdit Analizi (Defender TI) kullanarak İnternet veri kümelerini, tehdit makalelerini, güvenlik açığı makalelerini ve projeleri aramayı ve özetlemeyi öğrenin.
author: alexroland24
ms.author: aroland
ms.service: threat-intelligence
ms.topic: how-to
ms.date: 08/02/2022
ms.custom: template-how-to
ms.openlocfilehash: e5c621eaf22b00a8d0c29aa17063882e2873be2b
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2022
ms.locfileid: "67387209"
---
# <a name="searching-and-pivoting"></a>Arama ve özetleme

Microsoft Defender Tehdit Analizi (Defender TI), araştırma sürecini kolaylaştırmak için sağlam ve esnek bir arama motoru sunar. Platform, kullanıcıların farklı veri kaynaklarından çok çeşitli göstergeler arasında özet oluşturmasına olanak tanıyarak farklı altyapı arasındaki ilişkileri keşfetmeyi her zamankinden daha kolay hale getirmek için tasarlanmıştır. Bu makale, kullanıcıların farklı yapıtlar arasındaki ilişkileri keşfetmek için farklı veri kümelerinde arama yapmayı ve özetlemeyi anlamasına yardımcı olur.

![Giriş Sayfası Chrome'da Arama Ekran Görüntüsü](media/searchHomePageChromeScreenshot.png)

## <a name="prerequisites"></a>Önkoşullar

- Bir Azure Active Directory veya kişisel Microsoft hesabı. [Oturum açma veya hesap oluşturma](https://signup.microsoft.com/)
- Microsoft Defender Tehdit Analizi (Defender TI) Premium lisansı.
    > [!Note]
    > Defender TI Premium lisansı olmayan kullanıcılar Defender Tehdit Bilgileri Portalı'na giriş yapmaya ve ücretsiz Defender TI teklifimize erişmeye devam edebilir.

## <a name="open-defender-tis-threat-intelligence-home-page"></a>Defender TI'nin Tehdit Bilgileri Giriş Sayfasını açın

1. [Defender Tehdit Bilgileri Portalı'na](https://ti.defender.microsoft.com/) erişin.
2. Portala erişmek için Microsoft kimlik doğrulamasını tamamlayın.

## <a name="performing-threat-intelligence-searches-and-pivots"></a>Tehdit bilgileri aramaları ve özetleri gerçekleştirme

Defender TI'nin Tehdit Bilgileri araması hem basit hem de güçlüdür ve kullanıcıların bu içgörüleri oluşturan veri kümeleriyle doğrudan etkileşim kurmasına olanak tanıyacak şekilde tasarlanmıştır. Arama çubuğu çok çeşitli girişleri destekler; kullanıcılar hem belirli yapıtları hem de Makale veya Proje adlarını arayabilir.

### <a name="search-artifact-types"></a>Arama yapıt türleri
1. **IP adresi:** Arama '195.161.141[.] Tehdit Bilgileri Arama çubuğunda 65'. Bu eylem bir IP Adresi araması ile sonuçlar.

    ![Ip Adresi Ara](media/searchIpAddress.png)

2. **Etki alanı:** Tehdit Bilgileri Arama `fabrikam.com` çubuğunda arama yapın. Bu eylem bir Etki Alanı araması ile sonuçlandır.

    ![Arama Etki Alanı](media/searchDomain.png)

3. **Ana bilgisayar:** Tehdit Bilgileri Arama `canary.fabrikam.com` çubuğunda arama yapın. Bu eylem bir Konak araması ile sonuçlar.

    ![Arama Ana Bilgisayarı](media/searchHost.png)

4. **Anahtar kelime:** Tehdit Bilgileri Arama çubuğunda 'apt29' araması yapın. Bu eylem bir Anahtar Sözcük araması ile sonuçlar. Anahtar sözcük aramaları terim, e-posta adresi vb. içerebilen herhangi bir anahtar sözcük türünü kapsar. Anahtar sözcük aramaları makalelerle, projelerle ve veri kümeleriyle ilişkilendirmelerle sonuçlanır.

    ![Arama Anahtar Sözcüğü](media/searchKeyword.png)

5. **CVE Kimliği:** Tehdit Bilgileri Arama çubuğunda 'CVE-2021-40444' araması yapın. Bu eylem BIR CVE-ID Anahtar Sözcük araması ile sonuç verir.

6. **Makale:** Tehdit Bilgileri Arama çubuğunda 'Emtia Kayağı & 2022'nin İlk Çeyreğindeki Magecart Eğilimleri' ifadesini arayın. Bu eylem bir Makale araması ile sonuçlar.

    ![Arama Ti Makalesi](media/searchTiArticle.png)

7. **Etiket:** Tehdit Bilgileri Araması açılan listesinden 'Etiket'i seçin ve Tehdit Bilgileri Arama çubuğuna 'magecart' yazın. Aramayı gerçekleştirmek için Enter tuşuna basın veya sağ oku seçin. Bu eylem bir Etiket araması ile sonuçlar.

    > [!NOTE]
    > Bu, bu etiket değerini paylaşan makaleleri döndürmez.

    ![Arama Etiketi](media/searchTag.png)

8. **Bileşen:** Tehdit Bilgileri Araması açılan listesinden 'Bileşen'i seçin ve Tehdit Bilgileri Arama çubuğuna 'cobalt strike' yazın. Aramayı gerçekleştirmek için Enter tuşuna basın veya sağ oku seçin. Bu eylem bir Bileşen araması ile sonuçlar.

    ![Arama Bileşeni](media/searchComponent.png)

9. **Takibi:** Tehdit Bilgileri Araması açılan listesinden 'İzleyiciler'i seçin ve Tehdit Bilgileri Arama çubuğuna '07d14d16d21d00042d41d00041d47e4e0ae17960b2a5b4fd6107fbb0926' yazın. Aramayı gerçekleştirmek için Enter tuşuna basın veya sağ oku seçin. Bu eylem bir İzleyici araması ile sonuçlar. Not: Bu örnekte bu bir JarmHash İzleyici türü idi.

    > [!NOTE]
    > Bu örnekte bu bir JarmHash İzleyici türü idi.

    ![Arama İzleyicileri](media/searchTrackers.png)

10. **WHOIS Email:** Tehdit Bilgileri Arama açılan listesinden 'WHOIS' > 'Email' öğesini seçin ve Tehdit Bilgileri Arama çubuğuna domains@microsoft.com yazın. Aramayı gerçekleştirmek için Enter tuşuna basın veya sağ oku seçin. Bu eylem, WHOIS Email aramayla sonuçlanan bir işlemdir.

    ![Whois Email arama](media/searchWhoisEmail.png)

11. **WHOIS Adı:** Tehdit Bilgileri Arama açılan listesinden 'WHOIS' > 'Ad' öğesini seçin ve Tehdit Bilgileri Arama çubuğuna 'MSN Hostmaster' yazın. Aramayı gerçekleştirmek için Enter tuşuna basın veya sağ oku seçin. Bu eylem, WHOIS Adı araması ile sonuçlanan bir eylemdir.

    ![Arama Whois Adı](media/searchWhoisName.png)

12. **WHOIS Kuruluşu:** Tehdit Bilgileri Araması açılan listesinden 'WHOIS' > 'Kuruluş' öğesini seçin ve Tehdit Bilgileri Arama çubuğuna 'Microsoft Corporation' yazın. Aramayı gerçekleştirmek için Enter tuşuna basın veya sağ oku seçin. Bu eylem bir WHOIS Kuruluş aramasıyla sonuçlanan bir eylemdir.

    ![Whois Kuruluşunda Ara](media/searchWhoisOrganization.png)

13. **WHOIS Adresi:** Tehdit Bilgileri Araması açılan listesinden 'WHOIS' > 'Adres' öğesini seçin ve Tehdit Bilgileri Arama çubuğuna 'One Microsoft Way' yazın. Aramayı gerçekleştirmek için Enter tuşuna basın veya sağ oku seçin. Bu eylem, WHOIS Adresi aramasıyla sonuçlanan bir eylemdir.

    ![Whois Adresini Ara](media/searchWhoisAddress.png)

14. **WHOIS Şehri:** Tehdit Bilgileri Araması açılan listesinden 'WHOIS' > 'City' öğesini seçin ve Tehdit Bilgileri Arama çubuğuna 'Redmond' yazın. Aramayı gerçekleştirmek için Enter tuşuna basın veya sağ oku seçin. Bu eylem bir WHOIS City araması ile sonuçlanan bir eylemdir.

    ![Whois City'de Arama](media/searchWhoisCity.png)

15. **WHOIS Durumu:** Tehdit Bilgileri Araması açılan listesinden 'WHOIS' > 'State' öğesini seçin ve Tehdit Bilgileri Arama çubuğuna 'WA' yazın. Aramayı gerçekleştirmek için Enter tuşuna basın veya sağ oku seçin. Bu eylem bir WHOIS Durumu aramasıyla sonuçlanan bir eylemdir.

    ![Whois Durumunu Ara](media/searchWhoisState.png)

16. **WHOIS Posta Kodu:** Tehdit Bilgileri Arama açılan listesinden 'WHOIS' > 'Posta Kodu' öğesini seçin ve Tehdit Bilgileri Arama çubuğuna '98052' yazın. Aramayı gerçekleştirmek için Enter tuşuna basın veya sağ oku seçin. Bu eylem, WHOIS Posta Kodu aramasıyla sonuçlanan bir eylemdir.

    ![Whois Posta Kodunu Ara](media/searchWhoisPostalCode.png)

17. **WHOIS Ülke:** Tehdit Bilgileri Araması açılan listesinden 'WHOIS' > 'Ülke' öğesini seçin ve Tehdit Bilgileri Arama çubuğuna 'ABD' yazın. Aramayı gerçekleştirmek için Enter tuşuna basın veya sağ oku seçin. Bu eylem, WHOIS Ülke aramasıyla sonuçlanan bir eylemdir.

    ![Whois Ülkesini Ara](media/searchWhoisCountry.png)

18. **WHOIS Telefon:** Tehdit Bilgileri Arama açılan listesinden 'WHOIS' > 'Phone' öğesini seçin ve Tehdit Bilgileri Arama çubuğuna '+1.4258828080' yazın. Aramayı gerçekleştirmek için Enter tuşuna basın veya sağ oku seçin. Bu eylem, WHOIS Telefon araması ile sonuçlanan bir işlemdir.

    ![Whois Phone'da arama](media/searchWhoisPhone.png)

19. **WHOIS Ad Sunucusu:** Tehdit Bilgileri Araması açılan listesinden 'WHOIS' > 'Nameserver' öğesini seçin ve Tehdit Bilgileri Arama çubuğuna yazın `ns1-03.azure-dns.com` . Aramayı gerçekleştirmek için Enter tuşuna basın veya sağ oku seçin. Bu eylem bir WHOIS Ad Sunucusu aramasıyla sonuçlanan bir eylemdir.

    ![Whois Name sunucusunda arama](media/searchWhoisNameserver.png)

20. **SERTIFIKA SHA-1:** Tehdit Bilgileri Arama açılan listesinden 'SHA-1' > 'Sertifika' öğesini seçin ve Tehdit Bilgileri Arama çubuğuna '35cd04a03ef86664623581cbd56e45ed07729678' yazın. Aramayı gerçekleştirmek için Enter tuşuna basın veya sağ oku seçin. Bu eylem bir Sertifika SHA-1 araması ile sonuçlandı.

    ![Arama Sertifikası Sha1](media/searchCertificateSha1.png)

21. **Sertifika Seri Numarası:** Tehdit Bilgileri Araması açılan listesinden 'Sertifika' > 'Seri Numarası' öğesini seçin ve Tehdit Bilgileri Arama çubuğuna '1137354899731266880939192213383415094395905558' yazın. Aramayı gerçekleştirmek için Enter tuşuna basın veya sağ oku seçin. Bu eylem bir Sertifika Seri Numarası araması ile sonuç verir.

    ![Arama Sertifikası Seri Numarası](media/searchCertificateSerialNumber.png)

22. **Sertifika Veren ortak adı:** Tehdit Bilgileri Arama açılan listesinden 'Sertifika' > 'Veren Ortak Adı' öğesini seçin ve Tehdit Bilgileri Arama çubuğuna 'Microsoft Azure TLS Veren CA 05' yazın. Aramayı gerçekleştirmek için Enter tuşuna basın veya sağ oku seçin. Bu eylem, Sertifika Veren Ortak Adı araması ile sonuçlar.

    ![Arama Sertifikası Veren CommonName](media/searchCertificateIssuerCommonName.png)

23. **Sertifika VerenIn Alternatif Adı:** Tehdit Bilgileri Arama açılan listesinden 'Sertifika' > 'VerenIn Alternatif Adı'nı seçin ve Tehdit Bilgileri Arama çubuğuna bir sertifika veren alternatif adı yazın. Aramayı gerçekleştirmek için Enter tuşuna basın veya sağ oku seçin. Bu eylem bir Sertifika Veren Alternatif Ad araması ile sonuçlar.

24. **Sertifika Konusu Ortak Adı:** Tehdit Bilgileri Arama açılan listesinden 'Konu Ortak Adı' > 'Sertifika' öğesini seçin ve Tehdit Bilgileri Arama çubuğuna yazın `*.oneroute.microsoft.com` . Aramayı gerçekleştirmek için Enter tuşuna basın veya sağ oku seçin. Bu eylem bir Sertifika Konusu Ortak Adı aramasıyla sonuçılır.

    ![Arama Sertifikası Konu CommonName](media/searchCertificateSubjectCommonName.png)

25. **Sertifika Konusu Alternatif Adı:** Tehdit Bilgileri Araması açılan listesinden 'Konu Alternatif Adı' > 'Sertifika' öğesini seçin ve Tehdit Bilgileri Arama çubuğuna yazın `oneroute.microsoft.com` . Aramayı gerçekleştirmek için Enter tuşuna basın veya sağ oku seçin. Bu eylem, Bir Sertifika Konusu Alternatif Adı araması ile sonuçlar.

    ![Arama Sertifikası Konu Diğer Adı](media/searchCertificateSubjectAlternativeName.png)

26. **Tanımlama Bilgisi Adı:** Tehdit Bilgileri Araması açılan listesinden 'Tanımlama Bilgisi' > 'Ad' öğesini seçin ve Tehdit Bilgileri Arama çubuğuna 'ARRAffinity' yazın. Aramayı gerçekleştirmek için Enter tuşuna basın veya sağ oku seçin. Bu eylem bir Tanımlama Bilgisi Adı araması ile sonuçlar.

    ![Arama Tanımlama Bilgisi Adı](media/searchCookieName.png)

27. **Tanımlama Bilgisi Etki Alanı:** Tehdit Bilgileri Araması açılan listesinden 'Cookie' > 'Domain' öğesini seçin ve Tehdit Bilgileri Arama çubuğuna yazın `portal.fabrikam.com` . Aramayı gerçekleştirmek için Enter tuşuna basın veya sağ oku seçin. Bu eylem, Tanımlama Bilgisi Etki Alanı araması ile sonuçlandır.

    ![Arama Tanımlama Bilgisi Etki Alanı](media/searchCookieDomain.png)

28. **Miller:** Yukarıdaki adımlarda gerçekleştirilen aramalardan herhangi biri için, bu göstergelerle ilişkili daha zenginleştirilmiş sonuçları bulmak için özetleyebileceğiniz köprülere sahip yapıtlar vardır. Bununla kendi başınıza denemeler yapmaktan çekinmeyin.

## <a name="search-results"></a>Arama sonuçları

### <a name="key-insights"></a>Önemli içgörüler

Sayfanın en üstünde, platform yapıt hakkında bazı temel bilgiler sağlar. Bu bilgiler, yapıt türüne bağlı olarak aşağıdakileri içerebilir:  

- **Ülke:** IP Adresinin yanındaki bayrak, yapıtın kaynak ülkesini gösterir ve bu da saygınlığını veya güvenlik duruşunu belirlemeye yardımcı olabilir. Bu IP Adresi, Birleşik Devletler içindeki altyapıda barındırılır.
- **Saygınlık:** Bu örnekte IP Adresi, platformun bu yapıt ve bilinen danışmanlık altyapısı arasında bağlantılar algıladığını gösteren "Kötü Amaçlı" olarak etiketlendi. Yapıtlar "Şüpheli", "Nötr" veya "Bilinmeyen" olarak da etiketlenebilir.
- **İlk Görüldü:** Bu zaman damgası yapıtın platformun algılama sistemi tarafından ilk gözlemlendiği zamanı gösterir. Bir yapıtın kullanım ömrünü anlamak, yapıtın saygınlığını belirlemeye yardımcı olabilir.
- **Son Görülme:** Bu zaman damgası, yapıtın platformun algılama sistemi tarafından en son ne zaman gözlemlendiği gösterir. Bu, yapıtın hala etkin olarak kullanılıp kullanılmadığını belirlemeye yardımcı olur.
- **IP Bloğu:** Sorgulanan IP adresi yapıtını içeren IP bloğu.
- **Kayıt şirketi:** Sorgulanan etki alanı yapıtı için WHOIS kaydıyla ilişkilendirilmiş kayıt şirketi.
- **Kayıt yapan:** Bir yapıtın WHOIS verileri içindeki kayıt yapanın adı.
- **ASN:** Yapıtla ilişkilendirilmiş ASN.
- **İşletim sistemi:** yapıtla ilişkilendirilmiş işletim sistemi.
- **Konak:** Yapıtın barındırma sağlayıcısı. Bazı barındırma sağlayıcıları diğerlerinden daha saygındır, bu nedenle bu değer bir yapıtın geçerliliğini belirtmeye yardımcı olabilir.

![IP Anahtarı İçgörüleri'ne arama yapma](media/searchIPKeyInsights.png)

Bu bölümde yapıta uygulanan etiketler veya bunu içeren projeler de gösterilir. Kullanıcılar ayrıca bir etiket ekleyebilir veya yapıtı projeye ekleyebilir.

## <a name="summary-tab"></a>Özet sekmesi

### <a name="overview"></a>Genel bakış

Tehdit Bilgileri aramasının sonuçları iki sekmede gruplandırılır: "Özet" ve "Veri." Özet sekmesi, platformun geniş veri kümelerimizden türetdiği yapıt hakkında önemli içgörüler sağlar. Bu bölüm, araştırma başlatmaya yardımcı olabilecek önemli bulguları ortaya atmak için tasarlanmıştır.

### <a name="reputation"></a>Itibar

Defender TI tüm Konaklar, Etki Alanları veya IP Adreslerine yönelik özel itibar puanları sağlar. Bu puan, bilinen veya bilinmeyen bir varlığın itibarını doğrulayarak kullanıcıların kötü amaçlı veya şüpheli altyapıyla ilgili algılanan tüm bağları hızla anlamasına yardımcı olur. Saygınlık Puanları, 0 ile 100 arasında bir aralığa sahip sayısal puan olarak görüntülenir. Puanı "0" olan bir varlığın şüpheli etkinlikle veya bilinen risk göstergeleriyle bilinen bir ilişkisi yoktur; "100" puanı varlığın kötü amaçlı olduğunu gösterir. Platform, açıklama ve önem derecesi içeren kuralların listesini sağlar. Aşağıdaki örnekte, bu etki alanı için geçerli olan dört "yüksek önem derecesi" kuralı görüyoruz.

Daha fazla bilgi için bkz. [İtibar puanlaması](reputation-scoring.md).

![Özet Sekmesi Saygınlığı](media/summaryTabReputation.png)

### <a name="analyst-insights"></a>Çözümleyici içgörüleri

Analist İçgörüleri bölümü, bir araştırmanın sonraki adımını belirlemeye yardımcı olabilecek yapıt hakkında hızlı içgörüler sağlar. Bu bölümde yapıt için geçerli olan içgörüler ve ek görünürlük için geçerli olmayan içgörüler listelenecektir. Aşağıdaki örnekte, IP Adresinin yönlendirilebilir olduğunu, bir web sunucusu barındırdığını ve son beş gün içinde açık bir bağlantı noktasına sahip olduğunu hızla belirleyebiliriz. Ayrıca, sistem tetiklenmeyen kurallar görüntüler ve bu da bir araştırma başlatırken aynı derecede yararlı olabilir.

Daha fazla bilgi için bkz. [Çözümleyici içgörüleri](analyst-insights.md).

![Özet Sekmesi Çözümleyici İçgörüleri](media/summaryTabAnalystInsights.png)

### <a name="articles"></a>Makaleler

Makaleler bölümünde, etkilenen yapıtı en iyi şekilde araştırma ve nihai olarak etkisiz hale getirmek hakkında içgörü sağlayabilen tüm makaleler görüntülenir. Bu makaleler, bilinen tehdit aktörlerinin ve altyapılarının davranışını inceleyen araştırmacılar tarafından yazılır ve diğer kişilerin kuruluşlarında riski azaltmasına yardımcı olabilecek önemli bulgular ortaya konur. Bu örnekte, arama yapılan IP Adresi makaledeki bulgularla ilgili bir IOC olarak tanımlanmıştır.

Daha fazla bilgi için bkz. [Microsoft Defender Tehdit Analizi (Defender TI) nedir?](index.md)

![Özet Sekmesi Makaleleri](media/summaryTabArticles.png)

### <a name="services"></a>Hizmetleri

Bu bölümde, IP adresi yapıtı üzerinde çalışan algılanan hizmetler listelenir. Bu, varlığın amaçlanan kullanımını anlamaya çalışırken yararlıdır. Kötü amaçlı altyapıyı araştırırken, bu bilgiler bir yapıtın özelliklerini belirlemeye yardımcı olabilir ve kullanıcıların bu bilgilere dayanarak kuruluşlarını proaktif olarak savunmasına olanak tanır

![Özet Sekme Hizmetleri](media/summaryTabServices.png)

### <a name="resolutions"></a>Çözünürlük

Çözümler, dünya çapında dağıtılan pasif algılayıcılar kullanılarak yakalanan tek tek DNS kayıtlarıdır. Bu değerler, bir Etki Alanı veya IP adresinin zaman içinde altyapıyı nasıl değiştiryişinin geçmişini gösterir. Bunlar ek altyapıyı keşfetmek ve bağlantı düzeylerine göre riski ölçmek için kullanılabilir. Her çözünürlük için, çözümlerin yaşam döngüsünü göstermek için "ilk görülen" ve "son görülen" zaman damgaları sağlarız.

![Özet Sekmesi Yeniden çözümleri](media/summaryTabResolutions.png)

### <a name="certificates"></a>Sertifika

SSL Sertifikaları, verilerinizin güvenliğini sağlamanın ötesinde, kullanıcıların farklı ağ altyapısına bağlanması için harika bir yoldur. SSL sertifikaları, pasif DNS veya WHOIS verilerinin kaçırabileceği bağlantılar oluşturabilir. Bu, olası kötü amaçlı altyapıyı ilişkilendirmenin ve aktörlerin olası operasyonel güvenlik hatalarını belirlemenin daha fazla yolu anlamına gelir. Her SSL sertifikası için sertifika adını, son kullanma tarihini, konu ortak adını ve konu kuruluş adını sağlarız.

![Özet Sekmesi Sertifikaları](media/summaryTabCertificates.png)

### <a name="projects"></a>Projeler

Defender TI platformu, kullanıcıların ilgi çekici göstergeleri düzenlemek veya araştırmadan ödün vermek için projeler oluşturmasına olanak tanır. Daha iyi görünürlük için bağlantı yapıtlarını izlemek için projeler de oluşturulur. Projeler, tüm ilişkili yapıtların listesini ve adları, açıklamaları, ortak çalışanları ve izleme profillerini koruyan ayrıntılı bir geçmiş içerir.

Kullanıcı bir IP adresini, etki alanını veya konağı ararsa, bu gösterge kullanıcının erişimi olan bir projede listeleniyorsa, diğer veri kümelerini daha fazla bilgi için gözden geçirmeden önce, gösterge hakkında daha fazla bağlam için Projeler sekmesini seçebilir ve projenin ayrıntılarına gidebilir.

Daha fazla bilgi için bkz. [Projeleri kullanma](using-projects.md).

![Özet Sekmesi Projeleri](media/summaryTabProjects.png)

### <a name="hashes"></a>Karmalar

Microsoft, karma veri kümesini doldurmak üzere sorgulanan altyapıyla eşleştirmek için çeşitli ticari ve açık kaynak kötü amaçlı yazılım veri depolarıyla iş ortağıdır. Günümüzde kötü amaçlı yazılım depoları Proofpoint'in Yeni Ortaya Çıkan Tehditleri, Hibrit Analizi ve VirusTotal'ı içerir. Bu veriler, kullanıcıların bir saldırganın aktör özelliklerini, amacını ve motivasyonlarını anlamasına yardımcı olurken altyapının birbirine bağlanmasına da yardımcı olur. Her sonuç benzersiz bir karma içerir. Karma verilerimiz algılama kaynağını, örneğini ve toplama tarihini içerir.

![Özet Sekmesi Karmaları](media/summaryTabHashes.png)

## <a name="data-tab"></a>Veri sekmesi

### <a name="overview"></a>Genel bakış

Veri sekmesi, kullanıcıların Defender TI platformu tarafından gözlemlenen somut bağlantıları ayrıntılı olarak incelemelerine yardımcı olur. Özet sekmesi bir yapıt hakkında hemen bağlam sağlamak için önemli bulguları ortaya çıkarken, Veri sekmesi analistlerin bu bağlantıları çok daha ayrıntılı bir şekilde incelemesine olanak tanır. Kullanıcılar döndürülen herhangi bir değere tıklayarak ilgili meta veriler arasında özetleyebilir.

![Veri Kümeleri Edge Ekran Görüntüsü](media/dataSetsEdgeScreenshot.png)

### <a name="data-types"></a>Veri türleri

Aşağıdaki veri kümeleri Defender TI'de kullanılabilir:

- Çözünürlük
- WHOİS
- Sertifika
- Izci
- Alt
- Bileşen
- Konak Çiftleri
- Karmalar
- Tanımlama bilgileri
- Hizmetleri
- DNS
- DNS'i ters çevir

Bu ayrı veri kümeleri, arama gönderdikten sonra ayrı sekmelerde görünür. Sonuçlar tıklanabilir olduğundan, kullanıcının geleneksel araştırma yöntemleriyle kaçırılmış olabilecek içgörüleri ortaya çıkarabilmesi için ilgili altyapıda hızla özetlenebilir.

### <a name="resolutions"></a>Çözünürlük

Pasif DNS, belirli bir konum, kayıt ve zaman çerçevesi için DNS çözümleme verilerini depolayan bir kayıt sistemidir. Bu geçmiş çözümleme veri kümesi, kullanıcıların ip adresine çözümlenen etki alanlarını (veya tam tersini) görüntülemesine olanak tanır. Bu veri kümesi, etki alanı veya IP çakışmasına dayalı zamana dayalı bağıntıya olanak tanır.

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

![Veri Sekmesi Yeniden çözümleri](media/dataTabResolutions.png)

### <a name="whois"></a>WHOİS

WHOIS, herkesin bir etki alanının, IP adresinin veya alt ağın sahipliği hakkında bilgi sorgulamasına olanak tanıyan bir protokoldür. Tehdit altyapısı araştırmalarında WHOIS için en yaygın işlevlerden biri, WHOIS kayıtlarında paylaşılan benzersiz verilere göre farklı varlıkları tanımlamak veya bağlamaktır.

Her WHOIS kaydının farklı bölümleri vardır ve bunların tümü farklı bilgiler içerebilir. Yaygın olarak bulunan bölümler arasında "kayıt şirketi", "kayıt şirketi", "yönetici" ve her birinde kayıt için farklı bir kişiye karşılık gelen "teknik" yer alır. Bu veriler çoğu zaman bölümler arasında çoğaltılır, ancak bazı durumlarda, özellikle bir aktör hata yaptıysa hafif tutarsızlıklar olabilir. Defender TI'da WHOIS bilgilerini görüntülerken, verilerin yinelenenlerini kaldıran ve kaydın hangi bölümünden geldiğini belirten sıkıştırılmış bir kayıt görürsünüz.

Kullanıcılar, kayıt verilerinin zaman içinde nasıl değiştiğini anlamak için geçmiş WHOIS kayıtlarını da görüntüleyebilir.

WHOIS verilerimiz şunları içerir:

- **Kayıt Güncelleştirildi:** WHOIS kaydının son güncelleştirildiği günü gösteren bir zaman damgası.
- **Son Taranan:** Defender TI sisteminin kaydı en son taramış olduğu tarih.
- **Süre sonu:** Varsa kaydın son kullanma tarihi.
- **Oluşturuldu:** Geçerli WHOIS kaydının yaşı.
- **WHOIS Sunucusu:** Sunucu, içinde kayıtlı etki alanları hakkında güncel bilgileri almak için ICANN onaylı bir kayıt şirketi tarafından ayarlanır.
- **Kayıt şirketi:** Yapıtı kaydetmek için kullanılan kayıt şirketi hizmeti.
- **Etki Alanı Durumu:** Etki alanının geçerli durumu. "Etkin" bir etki alanı İnternet'te canlı olarak bulunur.
- **Email:** WHOIS kaydında bulunan tüm e-posta adresleri ve her birinin ilişkili olduğu kişi türü (örneğin yönetici, teknik).
- **Ad:** Kayıttaki herhangi bir kişinin adı ve her birinin ilişkili olduğu kişi türü.
- **Kuruluş:** Kayıttaki herhangi bir kuruluşun adı ve her birinin ilişkili olduğu kişi türü.
- **Sokak:** Kayıtla ilişkilendirilmiş tüm sokak adresleri ve ilişkili olduğu kişi türü.
- **Şehir:** Kayıtla ilişkilendirilmiş bir adreste listelenen herhangi bir şehir ve ilişkili olduğu kişi türü.
- **Durum:** Kayıtla ilişkilendirilmiş bir adreste listelenen tüm durumlar ve ilişkili olduğu kişi türü.
- **Posta Kodu:** Kayıtla ilişkilendirilmiş bir adreste listelenen tüm posta kodları ve ilişkili olduğu kişi türü.
- **Ülke:** Kayıtla ilişkilendirilmiş bir adreste listelenen tüm ülkeler ve ilişkili olduğu kişi türü.
- **Telefon:** Kayıtta listelenen tüm telefon numaraları ve ilişkili olduğu kişi türü.
- **Ad Sunucuları:** Kayıtlı varlıkla ilişkilendirilmiş tüm ad sunucuları.

![Veri Sekmesi WHOIS](media/dataTabWHOIS.png)

### <a name="certificates"></a>Sertifika

SSL Sertifikaları, verilerinizin güvenliğini sağlamanın ötesinde, kullanıcıların farklı ağ altyapısına bağlanması için harika bir yoldur. Modern tarama teknikleri, İnternet'teki her düğüme yönelik veri isteklerini birkaç saat içinde gerçekleştirmemize olanak tanır, bu da bir sertifikayı düzenli aralıklarla barındıran bir IP adresiyle kolayca ilişkilendirebileceğimiz anlamına gelir.

WHOIS kaydı gibi SSL sertifikaları da son ürünü oluşturmak için kullanıcı tarafından bilgi sağlanmasını gerektirir. Etki alanının yanı sıra, SSL sertifikası için oluşturulur (otomatik olarak imzalanmadığı sürece), ek bilgilerden herhangi biri kullanıcı tarafından oluşturulabilir. Kullanıcılarımızın SSL sertifikalarından en çok değer gördüğü yer, sertifikayı oluştururken birinin kullanabileceği benzersiz veriler değil, barındırıldığı yerdir.

SSL sertifikalarını daha değerli kılan şey, pasif DNS veya WHOIS verilerinin kaçırabileceği bağlantılar oluşturabilmesidir. Bu, olası kötü amaçlı altyapıyı ilişkilendirmenin ve aktörlerin olası operasyonel güvenlik hatalarını belirlemenin daha fazla yolu anlamına gelir. Microsoft, 2013'ten bugüne kadar 30 milyondan fazla sertifika toplayarak kullanıcılara sertifika içeriği ve geçmişiyle ilgili bağıntılar yapma araçları sunmaktadır.

Sertifika verilerimiz şunları içerir:

- **Sha1:** BIR SSL Sertifikası varlığı için SHA1 algoritma karması.
- **İlk Görüldü:** Bir yapıtta bu sertifikayı ilk gözlemlediğimiz tarihi gösteren bir zaman damgası.
- **Son Görülme:** Bir yapıtta bu sertifikayı en son gözlemlediğimiz tarihi gösteren bir zaman damgası.
- **Altyapı:** Sertifikayla ilişkili tüm ilgili altyapılar.

![Veri Sekmesi Sertifika Listesi](media/dataTabCertificatesList.png)

Kullanıcı bir Sha1 karması üzerine tıkladığında, sertifikayla ilgili ayrıntıları sağ bölmede görebilir ve bunlar şunları içerir:

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

### <a name="subdomains"></a>Alt

Alt etki alanı, birincil etki alanının parçası olan bir internet etki alanıdır. Alt etki alanları "konak" olarak da adlandırılır. Örneğin, `docs.microsoft.com` bir alt etki alanıdır `microsoft.com`. Her alt etki alanı için, etki alanının çözümlendiği yeni bir IP adresleri kümesi olabilir ve bu, ilgili altyapıyı bulmak için harika bir veri kaynağı olabilir.

Alt etki alanı verilerimiz şunları içerir:

- **Ana bilgisayar adı:** Aranan etki alanıyla ilişkili alt etki alanı.
- **Etiketler:** Defender TI sisteminde bu yapıta uygulanan tüm etiketler.

![Veri Sekmesi Alt etki alanları](media/dataTabSubdomains.png)

### <a name="trackers"></a>Izci

İzleyiciler, web sayfalarında bulunan ve genellikle kullanıcı etkileşimini izlemek için kullanılan benzersiz kodlar veya değerlerdir. Bu kodlar, farklı bir web sitesi grubunu merkezi bir varlıkla ilişkilendirmek için kullanılabilir. Aktörler genellikle kimlik avı kampanyası için kimliğine bürünmek istedikleri bir kurbanın web sitesinin kaynak kodunu kopyalar. Kullanıcılar, İzleyiciler veri kümelerimizi kullanarak bu sahte siteleri tanımlamalarına olanak sağlayan bu kimlikleri kaldırmak için nadiren zaman ayıracaktır.

Microsoft'un İzleyici veri kümesi Google, Yandex, Mixpanel, New Relic, Clicky gibi sağlayıcılardan gelen kimlikleri içerir ve düzenli aralıklarla büyümeye devam etmektedir.

İzleyici verilerimiz şunları içerir:

- **Ana bilgisayar adı:** İzleyicinin algılandığı altyapıyı barındıran konak adı.
- **İlk Görüldü:** Yapıt üzerinde bu izleyiciyi ilk gözlemlediğimiz tarihi gösteren bir zaman damgası.
- **Son Görülme:** Yapıt üzerinde bu izleyiciyi en son gözlemlediğimiz tarihi gösteren bir zaman damgası.
- **Tür:** Algılanan izleyici türü (ör. GoogleAnalyticsID, JarmHash).
- **Değer:** izleyicinin tanımlama değeri.
- **Etiketler:** Defender TI sisteminde bu yapıta uygulanan tüm etiketler.

![Veri Sekmesi İzleyicileri](media/dataTabTrackers.png)

### <a name="components"></a>Bileşen

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

### <a name="host-pairs"></a>Konak çiftleri

Konak çiftleri, Microsoft'un sanal kullanıcı web gezinmesinden gözlemlenen bir bağlantıyı paylaşan iki altyapı parçasıdır (üst ve alt öğe). Bağlantı, en üst düzey yeniden yönlendirmeden (HTTP 302) iframe veya betik kaynağı başvurusu gibi daha karmaşık bir şeye kadar değişebilir.

Konak çifti verilerimiz şunları içerir:

- **Üst Konak Adı:** Herhangi bir alt konak adına yeniden yönlendiren veya başka bir şekilde bağlanan ana bilgisayar adı.
- **Alt Konak Adı:** Üst konak adına bağlanan ana bilgisayar adı. Bu değer, yeniden yönlendirmenin veya daha karmaşık başka bir bağlantının sonucudur.
- **İlk Görülen:** Yapıt üzerinde bu konak çifti ilişkisini ilk gözlemlediğimiz tarih.
- **Last Seen:** Yapıt üzerinde bu konak çifti ilişkisini son gözlemlediğimiz tarih.
- **Neden:** Üst ve alt konak adı arasındaki bağlantının türü. Olası nedenler arasında yeniden yönlendirmeler, img.src, css.import veya script.src bağlantıları bulunur.
- **Etiketler:** Defender TI sisteminde bu yapıta uygulanan tüm etiketler.

![Veri Sekmesi Konak Çiftleri](media/dataTabHostPairs.png)

### <a name="hashes"></a>Karmalar

Microsoft, karma veri kümesini doldurmak üzere sorgulanan altyapıyla eşleştirmek için çeşitli ticari ve açık kaynak kötü amaçlı yazılım veri depolarıyla iş ortağıdır. Günümüzde kötü amaçlı yazılım depoları Proofpoint'in Yeni Ortaya Çıkan Tehditleri, Hibrit Analizi ve VirusTotal'ı içerir. Bu veriler, kullanıcıların bir saldırganın aktör özelliklerini, amacını ve motivasyonlarını anlamasına yardımcı olurken altyapının birbirine bağlanmasına da yardımcı olur. Her sonuç benzersiz bir karma içerir.

Karma verilerimiz şunları içerir:

1. **Kaynak:** Karmayı algılamak için kullanılan kaynak.
2. **Örnek:** Algılanan karma için benzersiz tanımlama kodu.
3. **Toplama Tarihi:** Karma örneğin belirlenen kaynak tarafından toplandığı gün.

![Veri Sekmesi Karmaları](media/dataTabHashes.png)

### <a name="cookies"></a>Tanımlama bilgileri

Tanımlama bilgileri, kullanıcı İnternet'e göz atarken sunucudan istemciye gönderilen küçük veri parçalarıdır. Bu değerler bazen uygulamanın durumunu veya izleme verilerinin küçük bitlerini içerir. Bir web sitesinde gezinirken gözlemlenen tanımlama bilgisi adlarını vurgular ve dizinleriz ve kullanıcıların sistemin gezinme ve veri toplama işlemlerinden belirli tanımlama bilgisi adlarını gözlemlediği her yeri incelemelerine olanak sağlarız.

Tanımlama bilgisi verilerimiz şunları içerir:

- **Ana bilgisayar adı:** tanımlama bilgisi ile ilişkili konak altyapısı.
- **İlk Görüldü:** Yapıt üzerinde bu tanımlama bilgisini ilk kez gözlemlediğimiz tarihin zaman damgası.
- **Son Görülme:** Yapıt üzerinde bu tanımlama bilgisini en son gözlemlediğimiz tarihin zaman damgası.
- **Ad:** Tanımlama bilgisinin adı (ör. JSESSIONID, SEARCH_NAMESITE).
- **Etki alanı:** Tanımlama bilgisi ile ilişkili etki alanı.
- **Etiketler:** Defender TI sisteminde bu yapıta uygulanan tüm etiketler.

![Veri Sekmesi Tanımlama Bilgileri](media/dataTabCookies.png)

### <a name="services"></a>Hizmetleri
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

### <a name="dns"></a>DNS

Microsoft, yıllardır DNS kayıtlarını toplayarak kullanıcılara posta değişimi (MX) kayıtları, ad sunucusu (NS) kayıtları, metin (TXT) kayıtları, yetki başlangıcı (SOA) kayıtları, kurallı ad (CNAME) kayıtları ve işaretçi (PTR) kayıtları hakkında içgörü sağlar. DNS kayıtlarını gözden geçirmek, sahip oldukları etki alanları genelinde aktörler tarafından kullanılan paylaşılan altyapıyı tanımlamak için yararlı olabilir. Örneğin aktör grupları, komut ve denetimlerini yönetmek için altyapılarını veya aynı posta değişim sunucularını segmentlere ayırmak için aynı ad sunucularını kullanma eğilimindedir. 

DNS verilerimiz şunları içerir:

- **Değer:** DNS kaydının değeri.
- **İlk Görüldü:** Yapıt üzerinde bu kaydı ilk kez gözlemlediğimiz tarihin zaman damgası.
- **Son Görülme:** Yapıtta bu kaydı en son gözlemlediğimiz tarihin zaman damgası.
- **Tür:** Kayıtla ilişkilendirilmiş altyapının türü. Olası seçenekler Posta Sunucuları (MX), metin dosyaları (TXT), ad sunucuları (NS), CNAMES ve Yetki Başlangıcı (SOA) kayıtlarını içerir.
- **Etiketler:** Defender TI sisteminde bu yapıta uygulanan tüm etiketler.

![Veri Sekmesi DNS](media/dataTabDNS.png)

### <a name="reverse-dns"></a>DNS'i ters çevir

İleriye doğru DNS araması belirli bir ana bilgisayar adının IP adresini sorgularken, ters DNS araması bir IP adresinin belirli bir ana bilgisayar adını sorgular. Bu veri kümesi, DNS veri kümesiyle karşılaştırılabilir sonuçlar gösterir. DNS kayıtlarını gözden geçirmek, sahip oldukları etki alanları genelinde aktörler tarafından kullanılan paylaşılan altyapıyı tanımlamak için yararlı olabilir. Örneğin aktör grupları, komut ve denetimlerini yönetmek için altyapılarını veya aynı posta değişim sunucularını segmentlere ayırmak için aynı ad sunucularını kullanma eğilimindedir.

Ters DNS verilerimiz şunları içerir:

- **Değer:** Ters DNS kaydının değeri.
- **İlk Görüldü:** Yapıt üzerinde bu kaydı ilk kez gözlemlediğimiz tarihin zaman damgası.
- **Son Görülme:** Yapıtta bu kaydı en son gözlemlediğimiz tarihin zaman damgası.
- **Tür:** Kayıtla ilişkilendirilmiş altyapının türü. Olası seçenekler Posta Sunucuları (MX), metin dosyaları (TXT), ad sunucuları (NS), CNAMES ve Yetki Başlangıcı (SOA) kayıtlarını içerir.
- **Etiketler:** Defender TI sisteminde bu yapıta uygulanan tüm etiketler.

![Veri Sekmesi TERS DNS](media/dataTabReverseDNS.png)

### <a name="intelligence"></a>Zeka

Zeka bölümü, Ister Makaleler aracılığıyla Araştırma Ekibimizden ister Projeler aracılığıyla kendi ekibinizden türetilmiş olsun, Defender TI platformunda seçilmiş içgörüleri vurgular. Zeka bölümü, kullanıcıların sorgulanan bir yapıtın arkasındaki temel ek bağlamı anlamasına yardımcı olur; analistler, daha büyük güvenlik topluluğunun araştırma çabalarından kendi araştırmalarını başlatabilir.

![Veri Sekmesi Zekası](media/dataTabIntelligence.png)

### <a name="articles"></a>Makaleler

Makaleler bölümünde, etkilenen yapıtı en iyi şekilde araştırma ve nihai olarak etkisiz hale getirmek hakkında içgörü sağlayabilen tüm makaleler görüntülenir. Bu makaleler, bilinen tehdit aktörlerinin ve altyapılarının davranışını inceleyen araştırmacılar tarafından yazılır ve diğer kişilerin kuruluşlarında riski azaltmasına yardımcı olabilecek önemli bulgular ortaya konur. Bu örnekte, arama yapılan IP Adresi makaledeki bulgularla ilgili bir IOC olarak tanımlanmıştır.

Daha fazla bilgi için bkz. [Microsoft Defender Tehdit Analizi (Defender TI) nedir?](index.md)

![Veri Sekmesi Yönetim Bilgileri Makaleleri](media/dataTabIntelligenceArticles.png)

### <a name="projects"></a>Projeler

Altyapı analizinin birincil yan üretimlerinden biri, neredeyse her zaman bir tehdit aktörü veya aktör grubuyla bağlantılı bir gösterge kümesidir. Bu göstergeler, bir saldırı kampanyası başlattıklarında tehdit aktörlerini tanımlamanın bir yoludur. Saldırganların tehdit aktörlerinin nasıl çalıştığına ilişkin taktikleri, teknikleri ve yordamları (TTP' ler) hakkında içgörü geliştirme. Projeler, TTP'lerine göre saldırganları tanımlamak ve saldırgan altyapısının zaman içinde nasıl değiştiğini izlemek için bir yöntem sağlar.

Kullanıcı Defender TI'da bir IP adresini, etki alanını veya konağı ararken, bu gösterge kullanıcının erişimi olan bir projede listeleniyorsa, kullanıcı Zeka bölümündeki Projeler dikey penceresini seçebilir ve daha fazla bilgi için diğer veri kümelerini gözden geçirmeden önce gösterge hakkında daha fazla bağlam için projenin ayrıntılarına gidebilir.

Bir projenin ayrıntılarını ziyaret etmeniz, tüm ilişkili yapıtların listesini ve yukarıda açıklanan tüm bağlamı koruyan ayrıntılı bir geçmişi gösterir. Aynı kuruluştaki kullanıcıların artık iletişim kurmak için zaman harcaması gerekmez. Tehdit aktörü profilleri Defender TI içinde oluşturulabilir ve "canlı" bir gösterge kümesi görevi görebilir. Yeni bilgiler bulunduğunda veya bulunduğunda bu projeye eklenebilir.

Defender TI platformu, kullanıcıların ilgi çekici göstergeleri ve bir araştırmadan ödün verme göstergelerini düzenlemek için birden çok proje türü geliştirmesine olanak tanır.

Daha fazla bilgi için bkz. [Projeleri kullanma](using-projects.md).

![Veri Sekmesi Akıllı Projeleri](media/dataTabIntelligenceProjects.png)

## <a name="next-steps"></a>Sonraki adımlar

Daha fazla bilgi için bkz.:

- [Verileri sıralama, filtreleme ve indirme](sorting-filtering-and-downloading-data.md)
- [Veri kümeleri](data-sets.md)
- [İtibar puanlaması](reputation-scoring.md)
- [Çözümleyici içgörüleri](analyst-insights.md)
- [Microsoft Defender Tehdit Bilgileri (Defender TI) nedir?](index.md)
- [Projeleri kullanma](using-projects.md)
