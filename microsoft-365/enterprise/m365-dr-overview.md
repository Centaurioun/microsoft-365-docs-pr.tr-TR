---
title: Genel Bakış ve Tanımlar
description: Data Residency özelliğine Genel Bakış ve Tanımlar hakkında bilgi edinin
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.service: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: ''
ms.reviewer: dmwmsft
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: c73910350027ff90fa54208e4e11c53b04538969
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806317"
---
# <a name="overview-and-definitions"></a>Genel Bakış ve Tanımlar

## <a name="definitions"></a>Tanımlar

Veri yerleşimi işlevselliği ve davranışı hakkında aşağıdaki açıklamalara netlik sağlamak için, Microsoft'un bu alanda sağladığı özellikleri daha iyi anlamak için net terimlere ve tanımlara sahip olmak gerekir.

**Tablo 1: Tanımlar ve Terimler**

| **Terim** | **Tanım** |
|:-----|:-----|
|Makro Bölgesi Coğrafyası  <br/> |Makro Bölgesi Coğrafyası 1 – EMEA, Makro Bölgesi Coğrafyası – Asya Pasifik, Makro Bölgesi Coğrafyası - Amerika  <br/> |
|Makro Bölgesi Coğrafya 1 - EMEA  <br/> |Avusturya, Finlandiya, Fransa, İrlanda, Hollanda, İsveç'teki veri merkezleri  <br/> |
|Makro Bölgesi Coğrafya 2 - Asya Pasifik  <br/> |Hong Kong, Japonya, Malezya, Singapur, Güney Kore'deki veri merkezleri  <br/> |
|Makro Bölgesi Coğrafya 3 - Amerika  <br/> |Brezilya, Şili, Birleşik Devletler'deki veri merkezleri  <br/> |
|Yerel Bölge Coğrafyası  <br/> |Avustralya, Brezilya, Kanada, Fransa, Almanya, Hindistan, Japonya, Katar, Güney Kore, Norveç, Güney Afrika, İsveç, İsviçre, Birleşik Arap Emirlikleri, Birleşik Krallık  <br/> |
|Genişletilmiş Yerel Bölge Coğrafyası  <br/> |Polonya, İtalya, Endonezya, İsrail, İspanya, Meksika, Malezya, Avusturya, Şili, Yeni Zelanda, Danimarka, Yunanistan, Tayvan  <br/> |
|Coğrafya  <br/> |_Yerel Bölge Coğrafyası, Genişletilmiş Yerel Bölge Coğrafyası_ veya _Makro Bölgesi Coğrafyası_  <br/> |
|Uydu Coğrafya  <br/> |Müşteri Çoklu Coğrafi Hizmete abone olursa, tanımlı kullanıcı müşteri verilerinin _Kiracı_ _Birincil Sağlanan Coğrafyası_ dışındaki diğer Coğrafyalarda depolanmasına neden olabilir  <br/> |
|Acar  <br/> |Azure Active Directory  <br/> |
|Kiracı  <br/> |_Kiracı_, Azure Active Directory'deki bir kuruluşu temsil eder. Bir kuruluşun Azure veya Microsoft 365 gibi bir Microsoft bulut hizmetine kaydolduğunda aldığı ve sahip olduğu ayrılmış bir Azure AD hizmet örneğidir. Her Azure AD _Kiracısı_ ayrıdır ve diğer Azure AD _Kiracı'nın_ kiracılarından ayrıdır  <br/> |
|Varsayılan Coğrafya  <br/> |_AAD Kiracısı_ oluşturulduğunda, kayıt işlemi sırasında müşteri tarafından bir ülke sağlanır.  Bu ülke, tüm Microsoft 365 hizmetleri için varsayılan Coğrafyayı belirler.  Bazı durumlarda, tüm hizmetler bu tek _Varsayılan Coğrafyada_ sağlayamaz. Açıklama için aşağıdaki _Microsoft 365 Hizmeti sağlama eşlemesi_ bölümüne bakın.  <br/> |
|Microsoft 365 Hizmeti sağlama eşlemesi  <br/> |Tüm Microsoft 365 Hizmetleri, belirli bir _Kiracının_ belirtilen verilerinin nerede sağlanıp depolanacağına karar vermek için _Varsayılan Coğrafyayı_ kullanır.  <br/> |
|Microsoft 365 Hizmeti sağlama ülke eşlemesi  <br/> |Belirli bir hizmetin _Kiracı Varsayılan Coğrafyası'na_ göre belirtilen müşteri verilerini nerede sağladığını öğrenmek için lütfen [veri eşlemelerine](https://aka.ms/datamaps) bakın.  <br/> |
|Birincil Sağlanan Coğrafya  <br/> |Belirli bir Microsoft 365 hizmeti, müşteri verilerinin hangi _Coğrafyaya_ sağlanacağına karar vermek için _Kiracı Varsayılan Coğrafyası'nı_ _Microsoft 365 Hizmeti sağlama ülke eşlemesiyle_ birlikte kullanır.   <br/> |
|Microsoft 365 Yönetici Merkezi Veri Konumu  <br/> |Exchange Online için _Birincil Sağlanan Coğrafya'yı_ görmek için SharePoint Online ve Microsoft Teams Ayarlar'daki Office 365 Admin Merkezi'ne bakın; Kuruluş ayarları; Kuruluş profili; Veri konumu kartı.  <br/> |
|Microsoft 365 Multi-Geo Özellikleri  <br/> |Microsoft 365 Multi-Geo Özellikleri, tek bir _Kiracının_ müşteri verilerini tek _bir Birincil Sağlanan Coğrafya_ ile sınırlı olmak yerine birden çok coğrafyada bekleyen olarak depolamasına olanak tanır. Daha fazla ayrıntı için lütfen Multi-Geo açıklamasına bakın.  <br/> |
|Tercih Edilen Veri Konumu (PDL)  <br/> |Multi-Geo aboneliği olan _Kiracılar_ için kullanılır.  Yönetici tarafından ayarlanan ve kullanıcının veya paylaşılan kaynağın verilerinin bekleyen konumda nerede depolanması gerektiğini belirten bir özellik.  Daha fazla ayrıntı için lütfen Multi-Geo açıklamasına bakın.  <br/> |
|Gelişmiş Data Residency (ADR)  <br/> |Tanımlanmış bir hizmet kümesi için müşteri verilerinin yerleşimini garanti eden yeni bir Microsoft 365 eklenti hizmeti. Bkz. bölüm 3  <br/> |
|Gizlilik ve Güvenlik Ürün Koşulları  <br/> |Microsoft 365 hizmetleri için Gizlilik ve Güvenlik Koşulları, müşteri verileri konumuyla ilgili bazı taahhütler sağlar.  Belge <a href="https://www.microsoft.com/licensing/terms/en-US/product/PrivacyandSecurityTerms/EAEAS" target="_blank">burada</a> bulunabilir. İlgili bölümün (1 Kasım 2022'de) ayıklanması:<br>**Office 365 Hizmetleri.** Müşteri Avustralya, Brezilya, Kanada, Avrupa Birliği, Fransa, Almanya, Hindistan, Japonya, Norveç, Katar, Güney Afrika, Güney Kore, İsveç, İsviçre, Birleşik Krallık, Birleşik Arap Emirlikleri veya Birleşik Devletler _kiracısını_ sağlarsa, Microsoft şu Müşteri Verilerini yalnızca bu Coğrafi Bölge içinde depolar: (1) Exchange Online  posta kutusu içeriği (e-posta gövdesi, takvim girdileri ve e-posta eklerinin içeriği), (2) SharePoint Online site içeriği ve bu sitede depolanan dosyalar, (3) OneDrive İş yüklenen dosyalar ve (4) Microsoft Teams sohbet iletileri (özel iletiler, kanal iletileri, toplantı iletileri ve sohbetlerde kullanılan görüntüler dahil) ve Microsoft Stream kullanan müşteriler için  (SharePoint'te), toplantı kayıtları.
|İş yükleri  <br/> |Genellikle Exchange Online, SharePoint Online, Microsoft Teams vb. gibi ancak bunlarla sınırlı olmamak üzere bir Microsoft 365 hizmetine başvurmak için kullanılır.|

## <a name="overview-of-data-residency"></a>Data Residency genel bakış

Microsoft 365 Bulut hizmetleri dünyanın dört bir yanındaki veri merkezlerimizde çalışır ve dünyanın dört bir yanındaki müşterilere hizmet sağlar.  Müşteri verileri birden çok veri merkezinde depolanabilir.  Veri yerleşimi, müşteri verilerinin bekleyen konumda depolandığı coğrafi konumu ifade eder. Kişisel ve/veya hassas bilgilerin korunmasına yardımcı olmak için kamu, kamu sektörü, eğitim ve düzenlenmiş ticari varlıklar için veri yerleşimi önemlidir.  Birçok ülkede müşterilerin veri depolamanın konumunu açıkça yöneten yasalara, düzenlemelere veya endüstri standartlarına uyması beklenir.

Microsoft, müşteri verilerini kalıcı olarak depolamak için iki faktöre göre karar verir:

1. _Kiracının_ _Varsayılan Coğrafyası_
1. Belirli bir hizmet için kullanılabilir _Coğrafyalar_

### <a name="_default-geography_-of-the-aad-_tenant_"></a>AAD _Kiracısının_ _Varsayılan Coğrafyası_

Müşteri yeni bir AAD _Kiracısı_ oluşturduğunda, oluşturma işlemi sırasında bir ülkeye girer.  _Kiracı_ için _Varsayılan Coğrafyayı_ tanımlayan ülke bu ülkedir.  Kiracı oluşturmanın birden çok yolu _vardır_.  Bunlar AAD formları aracılığıyla oluşturulabilir, yeni Microsoft 365 hizmetleri (denemeler) denenirken oluşturulabilir.  _Kiracı_ oluşturulduktan sonra _Varsayılan Coğrafya_ değiştirilemez.

### <a name="available-geographies-for-a-given-service"></a>Belirli bir hizmet için kullanılabilir Coğrafyalar

Microsoft 365 hizmetleri tüm Microsoft veri merkezlerine küresel olarak dağıtılmaz.  Exchange Online, SharePoint Online ve Microsoft Teams gibi daha büyük hizmetler tüm _Coğrafyalara_ evrensel olarak dağıtılır.   Diğer hizmetler müşteri sayısına, bölgesel ilişkilerine ve yazılım mimarilerine göre hizmetlerinin nereye dağıtılacağına karar verir.  Bir müşteri bu kategorideki bir hizmeti ilk kez kullandığında, sağlama mantığı belirli bir müşterinin sağlanacağı yeri belirlemek için _Varsayılan Coğrafya'yı_ ve desteklenen _Coğrafyaları_ kullanır.

Zaman içinde, belirli bir hizmet yazılımlarını ek _Coğrafyalara_ dağıtabilir, böylece yeni müşteriler için sağlama konumları zaman içinde değişebilir ve bu durum müşteri verilerinin yeni bir _Coğrafyaya_ taşınmasına neden olmayabilir.

Belirli bir hizmet için verilerinizin nerede depolandığını anlamak için öncelikle bunu anlama aracınız _Kiracı_ Yönetici Merkezi'ndedir.  _Kiracı_ yöneticisi olarak, Yönetici->Ayarları->Kuruluş Ayarları->Kuruluş Profili->Veri Konumu'na giderek gerçek veri konumunu bulabilirsiniz.  Şu anda veri konumu Exchange Online, SharePoint Online ve Microsoft Teams için kullanılabilir.  Bu kaynağa ek olarak lütfen [Veri Eşlemeleri sayfasına](o365-data-locations.md) bakın.

Bazı örnekler:

**Örnek 1:** Exchange Online, SharePoint Online ve Microsoft Teams'i içeren yeni bir aboneliğe sahip olan kayıt ülkesi "Fransa" olan bir _Kiracı_ için, söz konusu hizmetlerin müşteri verileri Fransız _Yerel Bölge Coğrafyası'na_ sağlanacaktır. Neden mi?  Bu hizmetler Fransız veri merkezlerine dağıtıldığından ve _Kiracının_ Fransa'ya kaydolma ülkesi olduğundan.

**Örnek 2:**  Exchange Online, SharePoint Online ve Microsoft Teams'i içeren yeni bir aboneliği olan "Belçika" olarak kaydolan bir _Kiracı_ için, söz konusu hizmetlerin müşteri verileri _Makro Bölgesi Coğrafya 1 – EMEA'ya_ sağlanacaktır.  Neden mi?  Belçika'da Microsoft 365 veri merkezi olmadığından ve en yakın Coğrafya _Makro Bölgesi Coğrafya 1 - EMEA_ olduğundan.

**Örnek 3:** Microsoft Forms içeren yeni bir aboneliğe sahip kaydolma ülkesi "Japonya" olan bir _Kiracı_ için, Formlar için müşteri verileri _Makro Bölgesi Coğrafyası 3 - Amerika'ya_ sağlanacaktır.  Neden mi?  Formlar yalnızca _Makro Bölgesi Coğrafya 3 - Amerika_ ve _Makro Bölgesi Coğrafya 1 – EMEA'da_ dağıtıldığından (yalnızca AB _Kiracıları_ ).

**Örnek 4a:** Microsoft Yammer'ı içeren yeni bir aboneliği olan ve kaydolma ülkesi "İsveç" olan bir _Kiracı_ için, Yammer için müşteri verileri _Makro Bölgesi Coğrafya 1 - EMEA'ya_ sağlanır.  Neden mi?  Yammer _Makro Bölgesi Coğrafyası 1 - EMEA'da_ dağıtıldığından ve İsveç _Kiracıları_ bu _Coğrafyanın_ dışında en iyi şekilde sunulur.

**Örnek 4b:** Kaydolma ülkesi "İsveç" olan ve _Yammer'ın Makro Bölgesel Coğrafya 1 - EMEA'ya_ dağıtılmadan önce Microsoft Yammer'ı içeren bir aboneliği olan bir _Kiracı_ için, Yammer için müşteri verileri _Makro Bölgesi Coğrafya 3 - Amerika'da_ bulunur.  Neden mi?  Çünkü o sırada Yammer, _Makro Bölgesi Coğrafyası 3 - Amerika'da_ o sırada tüm müşteriler için yalnızca tek bir dağıtıma sahipti.

### <a name="migrationsmoves"></a>Geçişler/Taşımalar

Bir Microsoft 365 hizmeti belirli bir _Coğrafyaya_ _Kiracı_ sağladıktan sonra, bu verilerin başka bir _Coğrafyaya_ taşınmasının beş yolu vardır:

1. Microsoft 365 hizmeti, taşımayı engelleyecek başka ilkeler yoksa, hizmet işlemleri nedeniyle verileri yeni bir _Coğrafyaya_ taşımaya karar verir.
1. Microsoft veri merkezleri olan _Yerel Coğrafyalar_ ve aynı ülkeye sahip _kiracılar_ için _, Verileri Bölgesel Coğrafyalardan Yerel Coğrafyalara_ geçirme seçenekleri vardır.  Bu seçenek genellikle _Yerel Bölge Coğrafyası_ oluşturulduktan sonra yalnızca 6 ay boyunca kullanılabilir.
1. _Bir Kiracı_ _Multi-Geo_ hizmetine abone olursa, _Kiracı kullanıcısının_ Exchange Online, SharePoint Online ve Microsoft Teams verileri _Uydu Coğrafyalarına_ atanabilir.
1. _Kiracının_ ülkeye _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası_ olarak kaydolması ve _Gelişmiş Data Residency_ hizmeti eklentisi aboneliği olması durumunda, eklenen hizmetlerin _Kiracı_ verileri _Bölgesel Coğrafya'dan_ ilgili _Yerel Bölge Coğrafyasına_ geçirilecektir.
1. Bazen Microsoft, _Bölgesel Coğrafya'dan ilgili_ _Yerel Coğrafyalara veya Genişletilmiş Yerel Coğrafyalara_ Geçiş seçeneğini yeniden _açar_.

### <a name="durable-commitments-on-data-location"></a>Veri konumuyla ilgili dayanıklı taahhütler

Belirli bir hizmet için _Kiracı_ veri konumunun değişmediğinden emin olmak için üç yöntem vardır.

1. Ürün Koşulları: herhangi bir _Yerel Bölge Coğrafyasında_ sağlanan Exchange Online, SharePoint Online, OneDrive İş ve Microsoft Teams ya da Avrupa Birliği ya da Birleşik Devletler [, Ürün Koşulları'nda](https://www.microsoft.com/licensing/terms/product/PrivacyandSecurityTerms/all) belirtilen müşteri veri yerleşimi taahhüdüne sahiptir.  Daha fazla bilgi için [Ürün Koşulları Data Residency sayfasına bakın](m365-dr-product-terms-dr.md).
1. _Multi Geo_ aboneliği: Müşterilerin desteklenen tüm _Coğrafyalara_ Exchange Online, SharePoint Online, OneDrive İş ve Microsoft Teams için veri konumu atamasına olanak tanır.  Daha fazla bilgi için bkz[. Multi Geo Data Residency](microsoft-365-multi-geo.md).
1. _Gelişmiş Data Residency_ aboneliği, herhangi bir _Yerel Bölge Coğrafyası veya Genişletilmiş Yerel Bölge Coğrafyası'nda_ genişletilmiş bir Microsoft 365 hizmetleri kümesi için veri yerleşimini garanti eder.  Daha fazla bilgi için [Gelişmiş Data Residency sayfasına](advanced-data-residency.md) bakın.

**Tablo 2: İş Yüküne Göre Kullanılabilir Data Residency**

|**Hizmet Adı**|**Ürün Koşulları**|**Multi-Geo**|**Adr**|
|:-----|:-----|:-----|:-----|
|Exchange Online <br/> |X<sup>1</sup>  <br/> |X<sup>2</sup>  <br/> |X<sup>3</sup>  <br/> |
| SharePoint Online / OneDrive İş <br/> |X<sup>1</sup>  <br/> |X<sup>2</sup>  <br/> |X<sup>2</sup>  <br/> |
| Microsoft Teams <br/> |X<sup>1</sup>  <br/> |X<sup>2</sup>  <br/> |X<sup>2</sup>  <br/> |
| Office P1 için Microsoft Defender <br/> |-  <br/> |-  <br/> |X<sup>2</sup>  <br/> |
| Web için Office <br/> |-  <br/> |-  <br/> |X<sup>2</sup>  <br/> |
| Viva Connections <br/> |-  <br/> |-  <br/> |X<sup>2</sup>  <br/> |
| Viva Topics <br/> |-  <br/> |-  <br/> |X<sup>2</sup>  <br/> |
| Microsoft Purview <br/> |-  <br/> |-  <br/> |X<sup>2</sup>  <br/> |

1. Yalnızca _Yerel Bölge Coğrafya_ ülkeleri, Avrupa Birliği ve Birleşik Devletler için kullanılabilir.
1. _Yerel Bölge Coğrafyası_, _Genişletilmiş Yerel Bölge Coğrafyası_ ve _Bölgesel Coğrafya ülkelerinde/bölgelerinde_ kullanılabilir
1. Yalnızca _Yerel Bölge Coğrafyası_ ve _Genişletilmiş Yerel Bölge Coğrafyası_ ülkeleri için kullanılabilir.

>[!NOTE]
>Bu konularla ilgili diğer ayrıntılar için [İş Yükü Data Residency Özellikleri bölümüne](m365-dr-workload-exo.md) bakın.

**Tablo 3: Ülkeye göre kullanılabilir Data Residency**

| Ülke    | Exchange Online  | SharePoint Online  | Teams  | MDO P1  | Web için Office  | Viva Connections  | Viva Topics  |  Amaç  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Avustralya  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Brezilya  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Kanada  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Avrupa Birliği  | P-M  | P-M  | P-M  | -  | -  | -  | -  | -  |
| Fransa  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Almanya  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Hindistan  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Japonya  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Katar  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Güney Kore  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Norveç  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| South Africa  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| İsveç  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| İsviçre  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Birleşik Arap Emirlikleri  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Birleşik Krallık  | P-M-A  | P-M-A  | P-M-A  | A  | A  | A  | A  | A  |
| Amerika Birleşik Devletleri  | P-M  | P-M  | P-M  | -  | -  | -  | -  | -  |

P: Ürün Koşulları Data Residency<br>
M: Multi-Geo Data Residency<br>
Y: Gelişmiş Data Residency

### <a name="countryregion-specific-data-center-city-locations"></a>Ülkeye/Bölgeye özgü Veri Merkezi şehir konumları

Aşağıdaki Bölgesel Coğrafyalar bekleyen verileri depolayabilir.

**Tablo 4: Bölgesel Coğrafyalar**

|**Bölgesel Coğrafyalar** |**Müşteri verilerinin depolanabileceği konumlar**  |
|---------|---------|
|Makro Bölgesi Coğrafyası 1 - EMEA (Avrupa, Orta Doğu ve Afrika) |  Avusturya, Finlandiya, Fransa, İrlanda, Hollanda, İsveç  |
|Makro Bölgesi Coğrafya 2 - Asya Pasifik |  Hong Kong, Japonya, Malezya, Singapur, Güney Kore  |
|Makro Bölgesi Coğrafya 3 - Amerika | Brezilya, Şili, Birleşik Devletler  |

**Tablo 5: Geçerli Yerel Coğrafyalar ve Bölgeye özgü Veri merkezi konumları**

|Ülke |Veri Merkezi Konumu  |
|---------|---------|
|Avustralya   |Sidney, Melbourne   |
|Brezilya   |Rio, Campinas   |
|Kanada      |Quebec City, Toronto    |
|Avrupa Birliği      |Avusturya (Viyana), Finlandiya (Helsinki), Fransa (Paris, Marsilya), İrlanda (Dublin), Hollanda (Amsterdam), İsveç (Gävle, Sandviken, Staffanstorp)     |
|Fransa      |Paris, Marsilya     |
|Almanya     |Frankfurt, Berlin       |
|Hindistan   |Chennai, Mumbai, Pune        |
|Japonya     |Osaka, Tokyo      |
|Güney Kore   |Busan, Seul        |
|Norveç     |Oslo, Stavanger       |
|Katar     |Doha          |
|South Africa       |Cape Town, Johannesburg        |
|İsveç     |Gävle, Sandviken, Staffanstorp      |
|İsviçre           |Geneva, Zürih     |
|Birleşik Arap Emirlikleri    |Dubai, Abu Dabi        |
|Birleşik Krallık       |Durham, Londra, Cardiff      |
|Amerika Birleşik Devletleri    |Boydton, Cheyenne, Chicago, Des Moines, Quincy, San Antonio, Santa Clara, San Jose       |

### <a name="faq"></a>SSS

#### <a name="how-does-microsoft-define-data"></a>Microsoft verileri nasıl tanımlar?
<details><summary>Genişletmek için tıklayın</summary>

Microsoft Güven Merkezi'nden [farklı müşteri verileri türleri için tanımlarımızı](https://go.microsoft.com/fwlink/p/?linkid=864390) gözden geçirin. [Gizlilik & Güvenlik Koşulları'nda](https://www.microsoft.com/licensing/terms/product/PrivacyandSecurityTerms/all) Microsoft, müşteri verileri/_Kiracınız_ ve kullanıcı verilerinizle ilgili sözleşmeye dayalı taahhütlerde bulunur. Müşteri verilerini, [Gizlilik & Güvenlik Koşullarına](https://www.microsoft.com/licensing/terms/product/PrivacyandSecurityTerms/all) göre _yalnızca kiracının_ bölgesinde bekleyen olarak depolanacak şekilde taahhüt edilen müşteri verileri olarak adlandırıyoruz.

</details>

#### <a name="where-are-the-exact-addresses-of-the-data-centers"></a>Veri merkezlerinin tam adresleri nerede?

<details><summary>Genişletmek için tıklayın</summary>

Microsoft, veri merkezlerinin tam adreslerini açıklamaz. Veri merkezi tesislerimizin güvenliğini sağlamaya yardımcı olmak için bu ilkeyi oluşturduk. Ancak, şehir konumlarını listeleyeceğiz. Daha fazla bilgi edinmek için lütfen Genel Bakış ve Tanımlar sayfasındaki [Ülkeye/Bölgeye Özgü Veri Merkezi Şehir Konumları'ndaki](m365-dr-overview.md#countryregion-specific-data-center-city-locations) Tablo 5'e bakın.

</details>

#### <a name="does-the-location-of-your-customer-data-have-a-direct-impact-on-your-end-users-experience"></a>Müşteri verilerinizin konumunun son kullanıcılarınızın deneyimi üzerinde doğrudan bir etkisi var mı?
<details><summary>Genişletmek için tıklayın</summary>

Microsoft 365'in performansı yalnızca _Kiracı_ kullanıcısının veri merkezi konumlarına olan uzaklığıyla orantılı değildir. Microsoft'un küresel bulut ağına, küresel bulut altyapısına ve Microsoft 365 hizmetleri mimarisine yaptığı yatırımlar, kullanıcılara bekleyen müşteri verilerinin depolandığı konumdan bağımsız olarak tekil ve tutarlı bir deneyim sağlamaya yardımcı olur. Kullanıcılarınız performans sorunlarıyla karşılaşıyorsa, bunları ayrıntılı olarak gidermeniz gerekir. Microsoft, [Office Desteği web sitesinde](network-planning-and-performance.md) son kullanıcı performansını planlamak ve iyileştirmek için Microsoft 365 müşterilerine yönelik yönergeler yayımladı.

</details>

#### <a name="how-does-microsoft-help-me-comply-with-my-national-regional-and-industry-specific-regulations"></a>Microsoft ulusal, bölgesel ve sektöre özgü düzenlemelerime uymama nasıl yardımcı olur?
<details><summary>Genişletmek için tıklayın</summary>

Microsoft 365, bir _Kiracının_ bireylerin verilerinin toplanması ve kullanılmasını yöneten ulusal, bölgesel ve sektöre özgü gereksinimlere uymasına yardımcı olmak için tüm küresel bulut üretkenlik sağlayıcılarının en kapsamlı uyumluluk tekliflerini sunar. Microsoft Güven Merkezi'ndeki [Microsoft Purview](https://go.microsoft.com/fwlink/p/?linkid=862317) bölümünde [uyumluluk tekliflerimizi](/compliance/regulatory/offering-home) ve diğer ayrıntıları gözden geçirin. Ayrıca bazı Microsoft 365 planları, _Kiracının_ verilerini yönetmesine, yasal ve mevzuat gereksinimlerine uymasına ve verileri üzerinde gerçekleştirilen eylemleri izlemesine yardımcı olmak için daha fazla uyumluluk çözümü sunar.

</details>

#### <a name="who-can-access-your-data-and-according-to-what-rules"></a>Verilerinize kimler erişebilir ve hangi kurallara göre erişebilir?
<details><summary>Genişletmek için tıklayın</summary>

 Microsoft, _kiracının_ müşteri verilerinin yetkisiz kişiler tarafından uygunsuz erişime veya kullanıma karşı korunmasına yardımcı olmak için güçlü önlemler uygular. Bu, Microsoft personeli ve alt yüklenicilerinin erişimini kısıtlamayı ve kamu tarafından müşteri verilerine yönelik istekleri yanıtlamaya yönelik gereksinimleri dikkatle tanımlamayı içerir. Ancak _kiracınızın müşteri_ verilerine istediğiniz zaman ve herhangi bir nedenle erişebilirsiniz. [Diğer ayrıntılar Microsoft Güven Merkezi'nden](https://go.microsoft.com/fwlink/p/?linkid=864392) edinilebilir.

</details>

#### <a name="does-microsoft-access-your-data"></a>Microsoft verilerinize erişıyor mu?
<details><summary>Genişletmek için tıklayın</summary>

Microsoft, microsoft 365 işlemlerinin çoğunu otomatikleştirirken kendi müşteri verilerine erişimini kasıtlı olarak sınırlar. Bu, Microsoft 365'i büyük ölçekte yönetmemize ve müşteri verilerine yönelik iç tehdit risklerini ele almamıza yardımcı olur. Varsayılan olarak Microsoft mühendislerinin, Microsoft 365'teki müşteri verilerine yönelik yönetim ayrıcalıkları ve ayakta erişimleri yoktur. Bir Microsoft mühendisinin müşteri verilerine sınırlı bir süre için sınırlı ve günlüğe kaydedilmiş erişimi olabilir, ancak yalnızca normal hizmet işlemleri için gerekli olduğunda ve yalnızca Microsoft'taki üst düzey bir yönetim üyesi tarafından onaylandığında (ve müşteri tarafından Müşteri Kasası özelliği için lisanslanan müşteriler için).

</details>

#### <a name="how-does-microsoft-secure-your-data"></a>Microsoft verilerinizin güvenliğini nasıl sağlar?
<details><summary>Genişletmek için tıklayın</summary>

Microsoft, bilgilerinizin güvende kalmasına yardımcı olmak için Microsoft 365'e yerleşik olarak sağlam ilkeler, denetimler ve sistemler sunar. Daha fazla bilgi edinmek için Microsoft Güven Merkezi'nin Microsoft [365 güvenlik bölümünü](https://go.microsoft.com/fwlink/p/?linkid=864393) gözden geçirin.

</details>

#### <a name="does-microsoft-365-encrypt-your-data"></a>Microsoft 365 verilerinizi şifreler mi?
<details><summary>Genişletmek için tıklayın</summary>

Microsoft 365, bekleyen ve aktarılan müşteri verilerini şifreleyen hizmet tarafı teknolojileri kullanır. Bekleyen müşteri verileri için Microsoft 365, birim düzeyinde ve dosya düzeyinde şifreleme kullanır. Aktarımdaki müşteri verileri için Microsoft 365, veri merkezleri ile istemciler ve sunucular arasındaki iletişimler için Aktarım Katmanı Güvenliği (TLS) ve İnternet Protokolü Güvenliği (IPsec) gibi birden çok şifreleme teknolojisi kullanır. Microsoft 365, müşteri tarafından yönetilen şifreleme özelliklerini de içerir.

</details>

#### <a name="where-can-i-find-data-residency-information-for-microsoft-azure"></a>Microsoft Azure için veri yerleşimi bilgilerini nerede bulabilirim?
<details><summary>Genişletmek için tıklayın</summary>

Microsoft Azure'a ilişkin veri yerleşimi bilgilerini bulmak için [bölgeye göre kullanılabilir ürünler](https://go.microsoft.com/fwlink/p/?linkid=2093451) sayfasını gözden geçirin.

</details>

#### <a name="why-do-i-see-my-microsoft-365-service-requests-for-my-data-at-rest-connecting-to-servers-in-countries-outside-of-my-region"></a>Bekleyen verilerim için Microsoft 365 hizmet isteklerimi neden bölgemin dışındaki ülkelerdeki sunuculara bağlanırken görüyorum?
<details><summary>Genişletmek için tıklayın</summary>

Bazen müşteri isteği, _Kiracının_ müşteri verilerinin bekleyen konumda depolandığı konumdan farklı bir bölgedeki sunucular tarafından işlenebilir. Bu durum ağ yönlendirme kararlarının istek işleme için farklı bir sunucu seçmesi, ancak bu gibi durumlarda _Kiracının_ müşteri verilerinin bekleyen konumda yeni bir konuma taşınmaması durumunda gerçekleşebilir.

</details>
