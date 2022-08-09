---
title: Microsoft Defender Tehdit Analizi kullanarak verileri sıralama, filtreleme ve indirme (Defender TI)
description: Microsoft Defender Tehdit Analizi (Defender TI) kullanarak verileri sıralamayı, filtrelemeyi ve indirmeyi öğrenin.
author: alexroland24
ms.author: aroland
ms.service: threat-intelligence
ms.topic: how-to
ms.date: 08/02/2022
ms.custom: template-how-to
ms.openlocfilehash: 36648d50033cb00893e9f973641f421274e6e3d8
ms.sourcegitcommit: 414682b9bf42dc19a89c893d3c515aee9765b6e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2022
ms.locfileid: "67280387"
---
# <a name="sorting-filtering-and-downloading-data"></a>Verileri sıralama, filtreleme ve indirme

Microsoft Defender Tehdit Analizi (Defender TI) platformu, analistlerin geniş gezinme verileri koleksiyonumuza dizinlenmiş ve özet tablo biçiminde erişmesini sağlar.  Bu veri kümeleri çok büyük olabilir ve çok fazla miktarda geçmiş ve son veri döndürebilir. Böylece analistlerin verileri uygun şekilde sıralamasına ve filtrelemesine izin vermek, ilgi çekici bağlantıları kolayca ortaya çıkarabilme olanağı sağlar.

![DataSets Chrome'da Sıralama Ekran Görüntüsü](media/sortingDataSetsChromeScreenshot.png)

Bu nasıl yapılır makalesinde, aşağıdaki veri kümeleri için verileri sıralamayı ve filtrelemeyi öğreneceksiniz:

- Çözünürlük
- WHOİS
- Sertifika
- Alt
- Izci
- Bileşen
- Konak Çiftleri
- Karmalar
- Tanımlama bilgileri
- Hizmetleri
- DNS
- DNS'i ters çevir

Daha fazla bilgi için bkz. [Veri kümeleri](data-sets.md).

Bu nasıl yapılır makalesinde aşağıdaki özelliklerden göstergeleri/yapıtları indirmeyi de öğreneceksiniz:

- Projeler
- Makaleler
- Veri Kümeleri

## <a name="prerequisites"></a>Önkoşullar

- Bir Azure Active Directory veya kişisel Microsoft hesabı. [Oturum açma veya hesap oluşturma](https://signup.microsoft.com/)
- Microsoft Defender Tehdit Analizi (Defender TI) Premium lisansı.
    > [!NOTE]
    > Defender TI Premium lisansı olmayan kullanıcılar Defender Tehdit Bilgileri Portalı'na giriş yapmaya ve ücretsiz Defender TI teklifimize erişmeye devam edebilir.

## <a name="open-defender-tis-threat-intelligence-home-page"></a>Defender TI'nin Tehdit Bilgileri Giriş Sayfasını açın

1. [Defender Tehdit Bilgileri Portalı'na](https://ti.defender.microsoft.com/) erişin.
2. Portala erişmek için Microsoft kimlik doğrulamasını tamamlayın.

## <a name="sorting-data"></a>Verileri sıralama

Veri sekmesindeki sıralama işlevi, kullanıcıların veri kümelerimizi sütun değerlerine göre hızla sıralamasını sağlar. Varsayılan olarak, çoğu sonuç "Son Görülme" (azalan) ölçütüne göre sıralanır, böylece en son gözlemlenen sonuçlar listenin en üstünde görünür; bu, bir yapıtın geçerli altyapısı hakkında hemen içgörü sağlamak için en son verileri ortaya getirir. Şu anda tüm veri kümeleri aşağıdaki "İlk Görüldü" ve "Son Görülen" değerlerine göre sıralanabilir:

- Son Görülen Azalan (Varsayılan)
- Son Görülen Artan
- İlk Kez Artan Görülüyor
- İlk Görülen Azalan

Veriler, aranan veya özetlenen her IP, etki alanı veya konak varlığı için Veri sekmesindeki her veri kümesi dikey penceresinde sıralanabilir.

1. Defender TI Tehdit Bilgileri arama çubuğunda bir etki alanı, IP adresi veya konak arayın ve Veri sekmesine gidin.
2. Çözümleme Verileri dikey penceresindeki İlk Görülen ve Son Görülen sütunlara sıralama tercihleri uygulayın.

![Çözümlemeleri Sıralama](media/sortingResolutions.gif)

## <a name="filtering-data"></a>Verileri filtreleme

Veri filtreleme, analistlerin belirli bir meta veri değerine göre belirli bir veri grubuna erişmesini sağlar. Örneğin, bir analist yalnızca belirli bir kaynaktan veya belirli bir türe (sunucular, çerçeveler) ait bileşenlerden bulunan IP çözümlemelerini görüntülemeyi seçebilir. Bu, kullanıcıların sorgu sonuçlarını belirli bir ilgi alanına ait öğelere daraltmalarına olanak tanır. Tehdit Bilgileri platformu belirli veri türleriyle çakışan belirli meta veriler sağladığından, filtre seçenekleri her veri kümesi için farklı olacaktır.

## <a name="resolution-filters"></a>Çözünürlük filtreleri

Çözümleme verileri için aşağıdaki filtreler geçerlidir:

- **Sistem Etiketi**: Bu etiketler, araştırma ekibimiz tarafından bulunan içgörüler temelinde Tehdit Analizi sistemi tarafından oluşturulur.
- **Etiket**: Tehdit Bilgileri kullanıcıları tarafından uygulanan etiketler.
- **ASN**: Belirlenen Otonom Sistem Numarası (ASN) ile ilgili sonuçlar.
- **Ağ**: Belirlenen ağ ile ilgili sonuçlar.
- **Kaynak**: Sonucu oluşturan veri kaynağı (örn. riskq, emerging_threats).

1. Defender TI Tehdit Bilgileri arama çubuğunda bir etki alanı, IP adresi veya konak arayın ve Veri sekmesine gidin.
2. Çözünürlük Verileri dikey penceresinde yukarıda belirtilen filtre seçenekleri türlerinin her birine filtre uygulayın.

![Filtrelerin Çözünürlükleri](media/filtersResolutions.gif)

## <a name="tracker-filters"></a>İzleyici filtreleri

aşağıdaki filtreler izleyici verileri için geçerlidir:

- **Tür**: Her yapıt için tanımlanan izleyici türü (örn. JarmFuzzyHash, GoogleAnalyticsID).
- **Adres**: İzleyiciyi doğrudan gözlemleyen veya izleyiciyi gözlemleyen bir çözümleyici konağı olan IP adresi. (IP adresi aranırken görüntülenir)
- **Hostname**: Bu izleyici değerini gözlemleyen konak. (Bir etki alanı veya konak aranırken görüntülenir)

1. Defender TI Tehdit Bilgileri arama çubuğunda bir etki alanı, IP adresi veya konak arayın ve Veri sekmesine gidin.
2. İzleyici verileri dikey penceresine gidin.
3. İzleyici Verileri dikey penceresinde yukarıda belirtilen filtre seçenekleri türlerinin her birine filtre uygulayın.

![Filtreler İzleyicileri](media/filtersTrackers.gif)

## <a name="component-filters"></a>Bileşen filtreleri

Aşağıdaki filtreler bileşen verilerine uygulanır:

- **Ipaddressraw:** Döndürülen ana bilgisayar adıyla çakışan IP adresi.
- **Tür:** Belirlenen bileşen türü (örneğin, uzaktan erişim, işletim sistemi).
- **Ad:** Algılanan bileşenin adı (örn. Cobalt Strike, PHP).

1. Defender TI Tehdit Bilgileri arama çubuğunda bir etki alanı, IP adresi veya konak arayın ve Veri sekmesine gidin.
2. Bileşenler Verileri dikey penceresine gidin.
3. Bileşenler Verileri dikey penceresinde yukarıda belirtilen filtre seçenekleri türlerinin her birine filtre uygulayın.

![Filtreler Bileşenleri](media/filtersComponents.gif)

## <a name="host-pair-filters"></a>Konak çifti filtreleri

Konak çifti verileri için aşağıdaki filtreler geçerlidir:

- **Yön:** gözlemlenen bağlantının yönü. Bu, üst öğenin alt öğeye mi yoksa tersine mi yönlendirdiğini gösterir.
- **Üst Konak Adı:** Üst yapıtın ana bilgisayar adı.
- **Neden:** Konak üst /alt ilişkisinin algılanan nedeni (örn. yeniden yönlendirme, iframe.src).
- **Alt Konak Adı:** Alt yapıtın ana bilgisayar adı.

1. Defender TI Tehdit Bilgileri arama çubuğunda bir etki alanı, IP adresi veya konak arayın ve Veri sekmesine gidin.
2. Konak Çiftleri Verileri dikey penceresine gidin.
3. Konak Çiftleri Veri dikey penceresinde yukarıda belirtilen filtre seçenekleri türlerinin her birine filtre uygulayın.

![Filtreler Konak Çiftleri](media/filtersHostPairs.gif)

## <a name="dns--reverse-dns-filters"></a>DNS & DNS filtrelerini ters çevirme

DNS ve Ters DNS verileri için aşağıdaki filtreler geçerlidir:

- **Kayıt Türü:** DNS kaydında algılanan kayıt türü (ör. NS, CNAME).
- **Değer:** Kaydın belirlenen değeri (örneğin, nameserver.host.com).

1. Defender TI Tehdit Bilgileri arama çubuğunda bir etki alanı, IP adresi veya konak arayın ve Veri sekmesine gidin.
2. DNS ve sonraki sürümlerde Ters DNS Verileri dikey pencerelerine gidin.
3. DNS ve Ters DNS Verileri dikey pencerelerinde yukarıda belirtilen filtre seçenekleri türlerinin her birine filtre uygulayın.

![DNS'ye filtre uygulama](media/filtersDNS.gif)

## <a name="downloading-data"></a>Verileri indirme

Defender TI'de, bir kullanıcının csv dışarı aktarma olarak veri indirebileceği çeşitli bölümler vardır.   Kullanıcıların verileri csv olarak dışarı aktarmak için indirme simgesine dikkat etmeleri gerekir.

![İndir Simgesi](media/downloadIcon.png)

Veriler aşağıdaki bölümlerde indirilebilir:

- Çoğu Veri Kümesi dikey penceresi
- Project
- Tehdit Bilgileri Makalesi

Aşağıdaki üst bilgiler Çözünürlükler, DNS ve ters DNS verilerinin indirilmesi sonucu dışarı aktarılır:

| &nbsp;                     | &nbsp;                     |
|----------------------------|----------------------------|
| **Gidermek**                | Bir IP adresi arandığında, arama yapılan etki alanıyla (IP Adresini çözümleme) veya bir IP adresine çözümlenen etki alanıyla ilişkilendirilmiş bir kayıt |
| **Konum**               | IP adresinin barındırılıyor olduğu ülke |
| **Ağ**                | Netblock veya alt ağ |
| **autonomousSystemNumber** | Otonom Sistem Numarası |
| **firstSeen**              | Microsoft'un çözünürlüğü ilk gözlemlediği Tarih /Saat (biçim: aa/gg/yyyy ss:mm) |
| **lastSeen**               | Microsoft'un çözünürlüğü en son gözlemlediği tarih /saat (biçim: aa/gg/yyyy ss:mm) |
| **Kaynak**                 | Bu çözümü gözlemleyen kaynak |
| **Etiketler**                   | Yapıtla ilişkilendirilmiş özel veya sistem etiketleri |

Alt Etki Alanları verilerinin indirilmesi sonucunda aşağıdaki üst bilgiler dışarı aktarılır:

| &nbsp;                     | &nbsp;                     |
|----------------------------|----------------------------|
| **Hostname**               | Arama yapılan etki alanının alt etki alanı |
| **Etiketler**                   | Yapıtla ilişkilendirilmiş özel veya sistem etiketleri |

İzleyiciler verilerinin indirilmesi sonucunda aşağıdaki üst bilgiler dışarı aktarılır:

| &nbsp;                     | &nbsp;                     |
|----------------------------|----------------------------|
| **Hostname**               | İzleyiciyi gözlemleyen veya şu anda gözlemleyen ana bilgisayar adı |
| **firstSeen**              | Microsoft'un konak adının izleyiciyi kullandığını ilk gözlemlediği tarih /saat (biçim: aa/gg/yyyy ss:mm) |
| **lastSeen**               | Microsoft'un konak adının izleyiciyi kullandığını ilk gözlemlediği tarih /saat (biçim: aa/gg/yyyy ss:mm) |
| **Attributetype**          | İzleyici türü |
| **attributeValue**         | İzleyici değeri |
| **Etiketler**                   | Yapıtla ilişkilendirilmiş özel veya sistem etiketleri |

Bileşenler verilerinin indirilmesi sonucunda aşağıdaki üst bilgiler dışarı aktarılır:

| &nbsp;                     | &nbsp;                     |
|----------------------------|----------------------------|
| **Hostname**               | Bileşeni gözlemleyen veya şu anda gözlemleyen ana bilgisayar adı |
| **firstSeen**              | Microsoft'un konak adının izleyiciyi kullandığını ilk gözlemlediği tarih /saat (biçim: aa/gg/yyyy ss:mm |
| **lastSeen**               | Microsoft'un ana bilgisayar adının bileşeni kullandığını en son gözlemlediği tarih /saat (biçim: aa/gg/yyyy ss:mm |
| **Kategori**               | Bileşen türü |
| **Adı**                   | Bileşenin adı |
| **Sürüm**                | Bileşenin sürümü |
| **Etiketler**                   | Yapıtla ilişkilendirilmiş özel veya sistem etiketleri |

Konak Çiftleri verilerinin indirilmesi sonucunda aşağıdaki üst bilgiler dışarı aktarılır:

| &nbsp;                     | &nbsp;                     |
|----------------------------|----------------------------|
| **parentHostname**         | Alt konak adına ulaşan ana bilgisayar adı |
| **childHostname**          | Barındırdıkları varlıkları üst konak adına besleyen konak adı. |
| **firstSeen**              | Microsoft'un üst ve alt konak adı arasındaki ilişkiyi ilk gözlemlediği tarih /saat (biçim: aa/gg/yyyy ss:mm) |
| **lastSeen**               | Microsoft'un üst ve alt konak adı arasındaki ilişkiyi en son gözlemlediği tarih /saat (biçim: aa/gg/yyyy ss:mm) |
| **attributeCause**         | Üst ve alt konak adı arasındaki ilişkinin nedeni |
| **Etiketler**                   | Yapıtla ilişkilendirilmiş özel veya sistem etiketleri |

Karmalar verilerinin indirilmesi sonucunda aşağıdaki üst bilgiler dışarı aktarılır:

| &nbsp;             | &nbsp;                     |
|--------------------|----------------------------|
| **Kaynak**         | MD5 karma örneğini gözlemleyen kaynak |
| **Örnek**                  | MD5 karması |
| **koleksiyon tarihi**         | Kaynak tarafından yakalanan koleksiyon tarihi |

Tanımlama bilgileri verilerinin indirilmesi sonucunda aşağıdaki üst bilgiler dışarı aktarılır:

| &nbsp;                     | &nbsp;                     |
|----------------------------|----------------------------|
| **Hostname**               | Tanımlama bilgisi adını gözlemleyen ana bilgisayar adı |
| **firstSeen**              | Tanımlama Bilgisi adı, Tanımlama Bilgisi Etki Alanından kaynaklanan ana bilgisayar adına ilk kez gözlemlendiğinde (biçim: aa/gg/yyyy ss:mm) |
| **lastSeen**               | Tanımlama Bilgisi adının tanımlama bilgisi etki alanından kaynaklanan ana bilgisayar adına son gözlemlendiği tarih/saat (biçim: aa/gg/yyyy ss:mm) |
| **Cookiename**             | Tanımlama bilgisinin adı |
| **cookieDomain**           | Tanımlama bilgisi adının kaynaklandığı etki alanı adının sunucusu |
| **Etiketler**                   | Yapıtla ilişkilendirilmiş özel veya sistem etiketleri |

Aşağıdaki üst bilgiler, benim, ekibim ve paylaşılan projelerim için proje listelerinin indirilmesi sonucunda dışarı aktarılır:

| &nbsp;                     | &nbsp;                     |
|----------------------------|----------------------------|
| **Adı**                   | Projenin adı |
| **yapıtlar (sayı)**      | Proje içindeki yapıtların sayısı |
| **oluşturan (kullanıcı)**      | Projeyi oluşturan kullanıcı |
| **tarihinde oluşturuldu**             | Proje oluşturulduğunda |
| **Etiketler**                   | Yapıtla ilişkilendirilmiş özel veya sistem etiketleri |
| **Işbirlikçi**          | Projeye ortak çalışanlar olarak eklenen kişiler. Bu yalnızca Projelerim ve Paylaşılan Projeler sayfalarından indirilen projeler için görünür. |

Proje ayrıntılarının (yapıtlar) bir projeden indirilmesi sonucunda aşağıdaki üst bilgiler dışarı aktarılır:

| &nbsp;                     | &nbsp;                     |
|----------------------------|----------------------------|
| **Artifakı**               | Yapıt değeri (örneğin IP adresi, etki alanı, konak, WHOIS değeri, sertifika SHA-1 vb.) |
| **Türü**                   | Yapıt türü (ör. IP, etki alanı, konak, WHOIS Kuruluşu, WHOIS Telefonu, Sertifika SHA-1 vb.) |
| **Oluşturulan**                | Yapıtın projeye eklendiği tarih /saat (biçim: aa/gg/yyyy ss:mm) |
| **Yaratıcısı**                | Yapıtı ekleyen kullanıcının Email adresi |
| **Bağlam**                | Yapıtın projeye nasıl eklendiği |
| **Etiketler**                   | Yapıtla ilişkilendirilmiş özel veya sistem etiketleri |
| **Işbirlikçi**          | Projeye ortak çalışanlar olarak eklenen kişiler. Bu yalnızca Projelerim ve Paylaşılan Projeler sayfalarından indirilen projeler için görünür. |

Aşağıdaki üst bilgiler, tehdit bilgileri genel veya riskq göstergelerini indirmenin bir sonucu olarak dışarı aktarılır:

| &nbsp;                     | &nbsp;                     |
|----------------------------|----------------------------|
| **Türü**                | Gösterge türü (ör. ip, sertifika, etki alanı, hash_sha256) |
| **Değer**               | Göstergenin değeri (ör. IP adresi, etki alanı, ana bilgisayar adı) |
| **Kaynak**              | Gösterge kaynağı (RiskIQ veya OSINT) |

## <a name="next-steps"></a>Sonraki adımlar

Daha fazla bilgi için bkz. [Veri kümeleri](data-sets.md).
