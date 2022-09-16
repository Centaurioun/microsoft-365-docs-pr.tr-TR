---
title: Microsoft Defender Tehdit Bilgileri (Defender TI) nedir?
description: Bu genel bakış makalesinde, Microsoft Defender Tehdit Bilgileri (Defender TI) ile birlikte gelen ana özellikler hakkında bilgi edinebilirsiniz.
author: alexroland24
ms.author: aroland
manager: dolmont
ms.service: threat-intelligence
ms.topic: overview
ms.date: 08/02/2022
ms.custom: template-overview
ms.openlocfilehash: bed8b4ed1aefb1a401f61256161f6dce5c593e18
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2022
ms.locfileid: "67737256"
---
# <a name="what-is-microsoft-defender-threat-intelligence-defender-ti"></a>Microsoft Defender Tehdit Bilgileri (Defender TI) nedir?

Microsoft Defender Tehdit Bilgileri (Defender TI), tehdit altyapısı analizi gerçekleştirirken ve tehdit bilgilerini toplarken önceliklendirme, olay yanıtlama, tehdit avcılığı, güvenlik açığı yönetimi ve siber tehdit bilgilerine yönelik çözümleyici iş akışlarını kolaylaştıran bir platformdur. Çözümleyiciler, kuruluşlarının kendilerini savunmasına gerçekten yardımcı olan şeylere odaklanmak yerine veri keşfetme, toplama ve ayrıştırma işlemlerine önemli miktarda zaman harcar ve analiz ve bağıntı yoluyla aktörler hakkında içgörüler elde etmiş olur.

Çözümleyicilerin genellikle şüpheli bir etki alanını, konağı veya IP adresini değerlendirmek için ihtiyaç duydukları kritik veri kümelerini elde etmek amacıyla birden çok depoya gitmesi gerekir. DNS verileri, WHOIS bilgileri, kötü amaçlı yazılımlar ve SSL sertifikaları, güvenlik ihlali göstergelerine (IOC) yönelik önemli bağlam sağlayıcılarıdır ve bu depolar yaygın olarak dağıtıldığı için her zaman ortak bir veri yapısını sahip değillerdir. Bu sebeple çözümleyicilerin, şüpheli altyapının düzgün ve zamanında değerlendirilebilmesi için gerekli olan ilgili tüm verilere sahip olması kolay değildir.

Bu veri kümeleriyle etkileşim kurmak zahmetli olabilir ve bu depolar arasında geçiş yapmak zaman alır ve sonuç olarak güvenlik operasyonları gruplarının, yanıtlama çalışmalarını sürekli olarak yeniden önceliklendirmesi gerekeceğinden bu grupların kaynakları tükenir.

Hangi tehdit bilgilerinin kuruluşlarına ve/veya sektörlerine yönelik en büyük tehditleri oluşturduğunun analizini gerçekleştiren Siber Tehdit Bilgileri Çözümleyicileri için çok çeşitli tehdit bilgilerinin alımını içeren işlemlerde dengenin sağlanması bir zorluk teşkil eder.

Yine aynı kapsamda Güvenlik Açığı Bilgileri Çözümleyicileri için kuruluşlarıyla ilişkili olan en kritik güvenlik açıklarının araştırılmasını ve düzeltilmesini önceliklendirmek üzere varlık envanterlerini CVE bilgileriyle ilişkilendirmek bir zorluk teşkil eder.

Makalelerle ve güvenlik açıklarıyla bağlantısı bulunan göstergeleri ilişkilendirmeye, güvenlik ihlali göstergeleri (IOC) ile altyapı zincirlemesi gerçekleştirmeye ve Defender TI lisanslı kullanıcıların kiracılarındaki diğer Defender TI lisanslı kullanıcılarla araştırmalarda işbirliği yapmasını sağlamaya yönelik yenilikçi ve kullanımı kolay bir arabirimde verileri görüntüleyen ve kritik veri kaynaklarını bir araya getirerek bu kaynakları zenginleştiren Defender TI adlı bir platform geliştiren Microsoft’un buradaki amacı çözümleyici iş akışını yeniden şekillendirmektir. Güvenlik kuruluşları, ortamlarında sürekli artan miktarda bilgi ve uyarı ile meşgul oldukları için uyarıların doğru ve zamanında değerlendirilmesini sağlayan bir Tehdit Analizi ve Bilgileri Platformuna sahip olmaları önemlidir.

Aşağıda Defender TI'ın Tehdit Bilgileri Giriş Sayfası'nın ekran görüntüsü yer almaktadır. Çözümleyiciler öne çıkan yeni makaleleri hızla tarayabileceği gibi bir anahtar sözcük, yapıt veya CVE-ID araması gerçekleştirerek bilgi toplama, önceliklendirme, olay yanıtlama ve tehdit avcılığı çalışmalarını başlatabilir.

![TI’a Genel Bakış Edge Ekran Görüntüsü](media/tiOverviewEdgeScreenshot.png)

## <a name="defender-ti-articles"></a>Defender TI Makaleler
Makaleler Microsoft’un tehdit aktörleri, araçlar, saldırılar ve güvenlik açıkları hakkında içgörüler sağladığı açıklamalardır. Defender TI öne çıkanlar ve Defender TI makaleleri tehdit bilgileriyle ilgili blog gönderileri niteliğinde değildir ve farklı tehditler hakkında özetler içermelerinin yanı sıra kullanıcıların eyleme geçmelerine yardımcı olmak için eyleme dönüştürülebilir içeriklere ve güvenlik ihlali göstergelerine yönlendiren bağlantılar sunarlar. Bu teknik bilgilerin tehdit özetlerine dahil edilmesi sayesinde kullanıcıların değişen tehdit aktörlerini, araçları, saldırıları ve güvenlik açıklarını sürekli olarak izlemesi sağlanır.

## <a name="featured-articles"></a>Öne çıkan makaleler

Defender TI Tehdit Bilgileri Giriş Sayfası’nın öne çıkan makale bölümü (arama çubuğunun hemen altında) öne çıkan Microsoft içeriğini gösterir:

![TI’a Genel Bakış Öne Çıkan Makaleler](media/tiOverviewFeaturedArticles.png)

Makaleye tıklayarak temel makale içeriğine gidebilirsiniz. Kullanıcı için makale özetinde makaleyle ilgili hızlı bir bilgilendirme yer alır. Makalede vurgulanan Göstergeler bölümü, makaleyle ilişkili kaç tane Genel gösterge ve Defender TI göstergesi olduğunu gösterir.

![TI’a Genel Bakış Öne Çıkan Makale](media/tiOverviewFeaturedArticle.png)

## <a name="articles"></a>Makaleler

Tüm makaleler (öne çıkan makaleler dahil) Microsoft Defender TI Tehdit Bilgileri Giriş Sayfası makaleler bölümünde listelenir ve oluşturulma tarihlerine (azalan) göre sıralanır:

![TI’a Genel Bakış Makaleler](media/tiOverviewArticles.png)

## <a name="article-descriptions"></a>Makale açıklamaları

Makale ayrıntı ekranının açıklama bölümü, profili oluşturulan saldırı veya saldırgan hakkında bilgi içerir. İçerik çok kısa (OSINT bültenleri söz konusu olduğunda) veya oldukça uzun (özellikle Microsoft geniş içerikli bir rapor düzenlediğinde uzun süreli raporlama için) olabilir. Uzun açıklamalarda görüntüler, temel içeriğe yönlendiren bağlantılar, Defender TI içindeki aramalara yönlendiren bağlantılar, saldırgan kod parçacıkları ve saldırının engellenmesine yönelik güvenlik duvarı kuralları bulunabilir:

![TI’a Genel Bakış Makale Açıklaması](media/tiOverviewArticleDescription.png)

## <a name="public-indicators"></a>Genel göstergeler

Ekranın genel göstergeler bölümünde makaleyle ilgili daha önce yayımlanan göstergeler gösterilir. Genel göstergelerdeki bağlantılar, temel Defender TI verilerine veya ilgili dış kaynaklara (ör. karmalar için VirusTotal) yönlendirir.

![TI’a Genel Bakış Makalesi Genel Göstergeler](media/tiOverviewArticlePublicIndicators.png)

## <a name="defender-ti-indicators"></a>Defender TI göstergeleri

Defender TI göstergeleri bölümü, Defender TI'ın araştırma ekibinin bulduğu ve makalelere eklediği göstergeleri kapsar.

Bu bağlantılar ayrıca ilgili Defender TI verilerine veya ilgili dış kaynağa yönlendirir.

![TI’a Genel Bakış Makalesi Defender TI Göstergeleri](media/tiOverviewArticleDefenderTiIndicators.png)

## <a name="vulnerability-articles"></a>Güvenlik açığı makaleleri

Defender TI, kullanıcıların CVE hakkındaki kritik bilgileri tanımlamasına yardımcı olmak için CVE-ID aramaları sunar. CVE-ID aramaları sonucunda Güvenlik Açığı Makaleleri görüntülenir.

Güvenlik Açığı Makaleleri, ilgili CVE'lerin ardındaki esas bağlam hakkında bilgilendirme sağlar. Her makale CVE'nin açıklamasını, etkilenen bileşenlerin bir listesini, özel risk azaltma yordamlarını ve stratejilerini, ilgili bilgilendirme makalelerini, Deep ve Dark Web konuşmalarındaki başvuruları ve diğer önemli gözlemleri içerir. Bu makaleler her CVE'ye ilişkin daha derinlemesine bağlam ve eyleme dönüştürülebilir içgörüler sağlayarak kullanıcıların bu güvenlik açıklarını daha hızlı anlamalarına ve bu güvenlik açıklarının riskini hızla azaltmalarına olanak tanır.

Güvenlik Açığı Makaleleri ayrıca bir Defender TI Öncelik Puanı ve önem derecesi göstergesi içerir. Defender TI Öncelik Puanı, CVSS puanına, açıklardan yararlanmalara, internet konuşmalarına ve kötü amaçlı yazılım bağlantısına bağlı olarak CVE'nin önceliğini yansıtan benzersiz bir algoritmadır. Ayrıca Defender TI Öncelik Puanı, kullanıcıların önce hangi CVE'lerin düzeltilmesi gerektiğini anlayabilmesi için bu bileşenlerin güncel tarihe yakınlığını değerlendirir.

## <a name="reputation-scoring"></a>İtibar puanlaması

Defender TI tüm Konaklar, Etki Alanları veya IP Adreslerine yönelik özel itibar puanları sağlar. Bu puan, bilinen veya bilinmeyen bir varlığın itibarını doğrulayarak kullanıcıların kötü amaçlı veya şüpheli altyapıyla ilgili algılanan tüm bağları hızla anlamasına yardımcı olur. Platform, İlk ve Son Görülme zaman damgaları, ASN, ülke/bölge, ilişkili altyapı gibi bu varlıkların etkinliği hakkında hızlı bilgiler ve geçerli olduğu durumlarda ise itibar puanını etkileyen kuralların bir listesini sağlar.

![İtibar Özet Kartı](media/reputationSummaryCard.png)

IP itibarı verileri, kendi saldırı yüzeyinizin güvenilirliğini anlamak için önemlidir ve ayrıca araştırmalarda görünen bilinmeyen konakları, etki alanlarını veya IP adreslerini değerlendirirken de yararlıdır. Bu puanlar, daha önce varlığı etkilemiş kötü amaçlı veya şüpheli etkinlikleri veya dikkate alınması gereken diğer bilinen güvenlik ihlali göstergelerini ortaya çıkarır.

Daha fazla bilgi için bkz. [İtibar puanlaması](reputation-scoring.md).

## <a name="analyst-insights"></a>Çözümleyici içgörüleri

Microsoft'un geniş veri kümesinin bir özetini çıkaran çözümleyici içgörüleri böylece araştırmayı basitleştiren bir dizi gözlem sunar ve veri kümesinin tüm düzeylerdeki çözümleyiciler için daha ulaşılabilir hale gelmesini sağlar.

İçgörülerin, bir etki alanına veya IP adresine ilişkin küçük bilgi parçaları veya gözlemler olması gerekir ve Defender TI kullanıcılarının sorgulanan yapıt hakkında değerlendirme yapmalarını ve kullanıcıların araştırılan bir göstergenin kötü amaçlı, şüpheli veya zararsız olup olmadığını belirlemede daha iyi hale gelmelerini sağlar.

Daha fazla bilgi için bkz. [Çözümleyici içgörüleri](analyst-insights.md).

![Özet Sekmesi Çözümleyici İçgörüleri](media/summaryTabAnalystInsights.png)

## <a name="data-sets"></a>Veri kümeleri
Microsoft, çok sayıda veri kümesini tek bir merkezi platformda yani Defender TI'da bir araya getirerek Microsoft topluluğunun ve müşterilerinin altyapı analizi gerçekleştirmelerini kolaylaştırır. Microsoft'un birincil odak noktası, çeşitli güvenlik kullanım örneklerini desteklemek için İnternet altyapısı hakkında mümkün olduğunca çok veri sağlamaktır.

Microsoft, kullanıcıların tehditleri algılamasına ve yanıtlamasına, olayları önceliklendirmesine ve erkenden harekete geçerek kullanıcıların kuruluşlarını hedefleyen aktör gruplarıyla ilişkili saldırganların altyapılarını belirlemesine yardımcı olmak için İnternet verilerini toplar, analiz eder ve dizinler. Microsoft, İnternet verilerini toplamak için PDNS algılayıcı ağı, sanal kullanıcılardan oluşan genel ara sunucu ağı, bağlantı noktası taramalarını kullanırken kötü amaçlı yazılım ve eklenen Etki Alanı Adı Sistemi (DNS) verileri için üçüncü taraf kaynaklardan yararlanır.

Bu internet verileri iki ayrı gruba ayrılır: geleneksel ve gelişmiş. Geleneksel veri kümeleri grubunda Çözümler, WHOIS, SSL Sertifikaları, Alt Etki Alanları, Karmalar, DNS, Ters DNS ve Hizmetler yer alır. Gelişmiş veri kümeleri grubunda İzleyiciler, Bileşenler, Konak Çiftleri ve Tanımlama Bilgileri bulunur. İzleyiciler, Bileşenler, Konak Çiftleri ve Tanımlama Bilgileri veri kümeleri, gezinilen web sayfalarının Belge Nesne Modelinin (DOM) gözlemlenmesi ile toplanır. Bileşenler ve İzleyiciler veri kümeleri ayrıca, bağlantı noktası taramalarından veya SSL Sertifikası ayrıntılarından gelen başlık yanıtlarına göre tetiklenen algılama kurallarından da gözlemlenir. Bu veri kümelerinin birçoğu verileri sıralamak, filtrelemek ve indirmek için çeşitli yöntemler kullanır ve böylece belirli bir yapıt türü veya geçmiş listesindeki bir zamanla ilişkilendirilebilecek bilgilere erişimi kolaylaştırır.

Daha fazla bilgi için bkz.:

- [Verileri sıralama, filtreleme ve indirme](sorting-filtering-and-downloading-data.md)
- [Veri kümeleri](data-sets.md)

![TI’a Genel Bakış Veri Kümeleri](media/tiOverviewDataSets.png)

## <a name="tags"></a>Etiketler

Defender TI etiketleri, sistem tarafından türetilen veya diğer kullanıcılar tarafından oluşturulan bir yapıt hakkında hızlı içgörü sağlamak için kullanılır. Daha iyi analizlerin yapılması için etiketler, çözümleyicilerin güncel olaylar ve araştırmalarla bunların geçmiş bağlamları arasındaki bağlantıları kurmasına yardımcı olur.

Defender TI platformu iki tür etiket sunar: sistem etiketleri ve özel etiketler.

Daha fazla bilgi için bkz. [Etiketleri kullanma](using-tags.md).

![Özel Etiketler](media/tagsCustom.png)

## <a name="projects"></a>Projeler

Microsoft'un Defender TI platformu, kullanıcıların bir araştırmada bulunan ilgili göstergeleri ve güvenlik ihlali göstergelerini düzenlemeye yönelik birden çok proje türü geliştirmesine olanak tanır. Projeler, tüm ilişkili yapıtların listesini ve adların, açıklamaların ve ortak çalışanların saklandığı ayrıntılı bir geçmiş içerir.

Kullanıcı Defender TI'da bir IP adresini, etki alanını veya konağı aradığında eğer bu gösterge kullanıcının erişimi olan bir projede listeleniyorsa kullanıcı, Özet sekmesindeki ve Veriler sekmesindeki Projeler bölümlerinde proje bağlantısını görüntüleyebilir. Kullanıcı, daha fazla bilgi edinmek için diğer veri kümelerini gözden geçirmesine gerek kalmadan, gösterge hakkında daha fazla bağlam bilgisi edinmek için buradan projenin ayrıntılarına gidebilir. Böylece çözümleyicilerin, Defender TI kiracısı kullanıcılarından birinin çoktan başlatmış olabileceği bir araştırmayla vakit kaybetmelerinin önüne geçer ve (projenin ortak çalışanı olarak eklenmişlerse) söz konusu projeyle ilişkili yeni yapıtlar (güvenlik ihlali göstergeleri) eklemelerine yardımcı olur.

Daha fazla bilgi için bkz. [Projeleri kullanma](using-projects.md).

![Defender TI'a Genel Bakış Projeler](media/defenderTIOverviewProjects.png)

## <a name="data-residency-availability-and-privacy"></a>Veri yerleşimi, uygunluk ve gizlilik

Microsoft Defender Tehdit Bilgileri hem genel verileri hem de müşteriye özgü verileri içerir. Temel İnternet verileri genel Microsoft verileridir ve müşteriler tarafından uygulanan etiketler müşteri verileri olarak kabul edilir. Tüm müşteri verileri müşterinin seçtiği bölgede depolanır.

Microsoft, güvenlik amacıyla oturum açtıklarında kullanıcıların IP adreslerini toplar. Bu veriler 30 güne kadar saklanır, ancak ürünün olası sahte veya kötü amaçlı kullanımına yönelik bir araştırma gerekirse daha uzun süre depolanabilir.

Defender TI verileri yedekleme bölgelerine çoğaltan teknolojiler kullandığından, bir bölge kapalı olduğunda müşterilerin bu senaryoda bir kesinti süresi görüntülememesi gerekir.

Defender TI müşteri verilerini işler. Varsayılan olarak, müşteri verileri eşleştirilmiş bölgeye çoğaltılır.

## <a name="next-steps"></a>Sonraki adımlar

Daha fazla bilgi için bkz.:

- [Hızlı Başlangıç: Microsoft Defender Tehdit Bilgileri’ne erişmeyi ve portalınızda özelleştirmeler yapmayı öğrenin](learn-how-to-access-microsoft-defender-threat-intelligence-and-make-customizations-in-your-portal.md)
- [Veri kümeleri](data-sets.md)
- [Arama ve özetleme](searching-and-pivoting.md)
- [Verileri sıralama, filtreleme ve indirme](sorting-filtering-and-downloading-data.md)
- [Altyapı zincirleme](infrastructure-chaining.md)
- [İtibar puanlaması](reputation-scoring.md)
- [Çözümleyici içgörüleri](analyst-insights.md)
- [Projeleri kullanma](using-projects.md)
- [Etiketleri kullanma](using-tags.md)
