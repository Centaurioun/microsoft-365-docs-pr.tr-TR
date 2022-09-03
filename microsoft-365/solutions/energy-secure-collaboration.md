---
title: Enerji Sektörü için Temel Uyumluluk ve Güvenlik Konuları
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.service: microsoft-365-enterprise
ms.localizationpriority: high
description: Microsoft 365, enerji kuruluşlarının modern bir işbirliği platformuna geçmesine yardımcı olurken, verilerin ve sistemlerin güvenli ve yönetmeliklerle uyumlu kalmasına yardımcı olur.
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: f0e4bdf1111dfd530a5cba71484ea90449ea73c6
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67580497"
---
# <a name="key-compliance-and-security-considerations-for-the-energy-industry"></a>Enerji Sektörü için Temel Uyumluluk ve Güvenlik Konuları

![Bulutu kullanan çeşitli sektörlerin küresel görünümüne yönelik çizim metaforu.](../media/solution-arch-center/MSC17_global_016.png)

## <a name="introduction"></a>Giriş

Enerji endüstrisi, topluma insanların her gün güvendiği yakıt ve kritik altyapı sağlar. Yasal makamlar, toplu güç sistemleriyle ilgili altyapının güvenilirliğini sağlamak için enerji endüstrisi kuruluşlarına katı standartlar uygular. Bu mevzuat standartları yalnızca enerjinin üretilmesi ve iletilmesiyle değil, aynı zamanda enerji şirketlerinin günlük operasyonları için kritik öneme sahip olan veri ve iletişimlerle de ilgilidir. 

Enerji sektöründeki kuruluşlar, düzenli operasyonlarının bir parçası olarak birçok bilgi türüyle çalışır ve bilgi alışverişinde bulunur. Buna müşteri verileri, sermaye mühendisliği tasarım belgeleri, kaynak konum haritaları, proje yönetimi yapıtları, performans ölçümleri, saha hizmeti raporları, çevresel veriler ve performans ölçümleri dahildir. Bu kuruluşlar, operasyon ve işbirliği sistemlerini modern dijital platformlara dönüştürmeyi denerken, güvenilir bir Bulut Hizmeti Sağlayıcısı (CSP) olarak Microsoft'u ve en iyi iş birliği platformları olarak Microsoft 365'i arıyor. Microsoft 365, Microsoft Azure platformunda oluşturulduğundan, kuruluşlar Buluta geçerken uyumluluk ve güvenlik denetimlerini dikkate aldıklarında her iki platformu da incelemelidir.

Kuzey Amerika'da Kuzey Amerika Electric Reliability Corporation (NERC), NERC [Kritik Altyapı Koruması (CIP)](https://www.nerc.com/pa/Stand/Pages/CIPStandards.aspx) standartları olarak adlandırılan güvenilirlik standartlarını zorunlu kılmaktadır. NERC, ABD Federal Enerji Düzenleme Komisyonu (FERC) ve Kanada'daki hükümet yetkilileri tarafından gözetime tabidir. Tüm toplu güç sistemi sahipleri, operatörleri ve kullanıcıları NERC'ye kaydolmalı ve NERC CIP standartlarına uymalıdır. Bulut Hizmeti Sağlayıcıları ve Microsoft gibi üçüncü taraf satıcılar NERC CIP standartlarına tabi değildir. Ancak CIP standartları, Kayıtlı Varlıklar Toplu Elektrik Sistemi'nin (BES) işleyişinde satıcılar kullandığında dikkate alınması gereken hedefleri içerir. Toplu Elektrik Sistemleri çalıştıran Microsoft müşterileri, NERC CIP standartlarına kendi uyumluluklarını sağlamakla tamamen sorumludur. 

Microsoft bulut hizmetleri ve NERC hakkında bilgi için aşağıdaki kaynaklara bakın:

- [NERC CIP Standartları ve Bulut Bilişim](https://aka.ms/AzureNERC)
- [NERC Denetimleri için Bulut Uygulama Kılavuzu](https://aka.ms/AzureNERCGuide)

Enerji kuruluşları tarafından dikkate alınması önerilen mevzuat standartları, NIST SP 800-53 Rev 4 standardını (Ulusal Standartlar ve Teknoloji Enstitüsü) temel alan ve geliştiren FedRAMP (ABD Federal Risk ve Yetkilendirme Yönetimi Programı) içerir.

- Microsoft Office 365 ve Office 365 ABD Hükûmeti'ne Orta Düzeyde FedRAMP ATO (Çalışma Yetkisi) verilmiştir. 
- Azure ve Azure Kamu her birine, en yüksek FedRAMP yetkilendirme düzeyini temsil eden bir FedRAMP High P-ATO (Çalışmak için Geçici Yetkilendirme) verilmiştir. 

Microsoft bulut hizmetleri ve FedRAMP hakkında bilgi için aşağıdaki kaynaklara bakın:

- [Microsoft FedRAMP'ye genel bakış](/compliance/regulatory/offering-FedRAMP)
- [FedRAMP raporlarını Office 365](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_FedRAMP_Reports)

FedRAMP Moderate kontrol kümesi ile NERC CIP gereksinimleri arasındaki karşılaştırma FedRAMP Moderate denetimlerinin tüm NERC CIP gereksinimlerini kapsadığını gösterdiğinden bu başarılar enerji sektörü için önemlidir. Ek bilgi için Microsoft, NIST 800-53 Rev 4'te belgelendiği gibi geçerli NERC CIP standartları kümesi ile FedRAMP Moderate denetim kümesi arasında bir denetim eşlemesi içeren NERC [Denetimleri için Bulut Uygulama Kılavuzu](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=68df41b2-873d-4e4b-a7c8-8a0d4fdefb88&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides) geliştirdi.

Enerji sektörü işbirliği platformlarını modernleştirmeyi ararken, işbirliği araçlarının ve güvenlik denetimlerinin yapılandırılması ve dağıtımı için dikkat edilmesi gereken noktalar şunlardır:

- Ortak işbirliği senaryolarının değerlendirilmesi
- Çalışanların üretken olması için gereken verilere erişim
- Mevzuat uyumluluğu gereksinimleri
- Veriler, müşteriler ve kuruluş için ilişkili riskler

Microsoft 365, modern bir çalışma alanı bulut ortamıdır. En sıkı mevzuat uyumluluk çerçevelerine uymaya yönelik denetimler ve ilke uygulama da dahil olmak üzere kuruluş genelinde güvenli ve esnek işbirliği sağlar. Aşağıdaki konular aracılığıyla, bu makalede Microsoft 365'in enerji sektörünün modern bir işbirliği platformuna geçişine nasıl yardımcı olduğu açıklanırken veri ve sistemlerin hem güvenli hem de yönetmeliklerle uyumlu tutulmasına yardımcı olur:

- Microsoft Teams ile Kapsamlı bir İşbirliği Platformu Sağlama
- Enerji Sektöründe Güvenli ve Uyumlu İşbirliği Sağlama
- Hassas Verileri Tanımlama ve Veri Kaybını Önleme
- Kayıtları Etkili Bir Şekilde Yöneterek Verileri Yönetme
- Enerji Piyasaları için FERC ve FTC Yönetmeliklerine Uyma
- Veri Sızdırma ve Insider Riskine Karşı Koruma

Bir Microsoft iş ortağı olarak Protiviti bu makaleye katkıda bulundu ve bu makaleye önemli geri bildirimler sağladı.

## <a name="provide-a-comprehensive-collaboration-platform-with-microsoft-teams"></a>Microsoft Teams ile Kapsamlı bir İşbirliği Platformu Sağlama

İşbirliği genellikle birden çok iletişim biçimi, belgeleri depolama ve erişme ve diğer uygulamaları gerektiği gibi tümleştirme olanağı gerektirir. İster küresel ister yerel şirketler olsun, enerji sektöründeki çalışanların genellikle diğer departmanların üyeleriyle veya ekipler arasında işbirliği yapıp iletişim kurmaları gerekir. Ayrıca genellikle dış iş ortakları, satıcılar veya istemcilerle iletişim kurmaları gerekir. Sonuç olarak silo oluşturan veya bilgi paylaşımını zorlaştıran sistemlerin kullanılması genellikle önerilmez. Ancak yine de çalışanların bilgileri güvenli bir şekilde ve ilkeye göre paylaştığını güvence altına almak istiyoruz. 

Çalışanlara, en üretken olmalarını sağlayan araçları seçmelerini ve kolayca tümleştirmelerini sağlayan modern ve bulut tabanlı bir işbirliği platformu sağlamak, çalışma ve işbirliği yapmanın en iyi yollarını bulmalarını sağlar. Microsoft Teams'i, kuruluşu korumak için güvenlik denetimleri ve idare ilkeleriyle birlikte kullanmak, iş gücünüzün bulutta kolayca işbirliği yapmasına yardımcı olabilir.

Microsoft Teams, kuruluşunuz için ortak girişimler veya projeler üzerinde birlikte çalışmak ve işbirliği yapmak üzere kişileri bir araya getirmek için bir işbirliği merkezi sağlar. Ekip üyelerinin konuşmalar yürütmesine, işbirliği yapmasına ve belgeleri birlikte yazmasına olanak tanır. Kişilerin dosyaları ekip üyeleriyle veya ekip dışındaki kişilerle depolamasına ve paylaşmasına olanak tanır. Ayrıca, tümleşik kurumsal ses ve video ile canlı toplantılar düzenlemelerine de olanak tanır. Microsoft Teams Planner, Dynamics 365, Power BI ve diğer üçüncü taraf iş kolu uygulamaları gibi Microsoft uygulamalarına kolay erişimle özelleştirilebilir. Teams, kuruluşun işbirliği ve iletişim gereksinimlerini merkezi hale getirmek için Office 365 hizmetlerine ve üçüncü taraf uygulamalara erişimi basitleştirir.

Her Microsoft Ekibi bir Office 365 Grubu tarafından yedeklenmiştir. Office 365 Grubu, Microsoft Teams dahil olmak üzere Office 365 hizmetleri için üyelik sağlayıcısı olarak kabul edilir. Office 365 Grupları, hangi kullanıcıların üye olarak kabul edildiğini ve hangilerinin grubun sahibi olduğunu güvenli bir şekilde denetlemek için kullanılır. Bu sayede Teams'de hangi kullanıcıların farklı özelliklere erişimi olduğunu kolayca denetleyebiliyoruz. Sonuç olarak, Ekip üyeleri ve sahipleri yalnızca kullanmalarına izin verilen özelliklere erişebilir.

Microsoft Teams'in enerji kuruluşlarından yararlanabileceği yaygın bir senaryo, bitki örtüsü yönetimi gibi bir saha hizmeti programının parçası olarak yüklenicilerle veya dış firmalarla işbirliği yapmaktır. Yükleniciler genellikle bitki örtüsünü yönetmek veya güç sistemi yüklemelerinin etrafındaki ağaçları kaldırmakla uğraşır. Genellikle iş yönergelerini almaları, dağıtıcılar ve diğer saha servis personeliyle iletişim kurmaları, dış çevrenin fotoğraflarını çekmeleri ve paylaşmaları, iş tamamlandığında oturumu kapatmaları ve verileri merkez ofisle yeniden paylaşmaları gerekir. Geleneksel olarak, bu programlar telefon, metin, kağıt iş siparişleri veya özel uygulamalar kullanılarak çalıştırılırdı. Bu, aşağıdakiler de dahil olmak üzere birçok zorluk sunabilir:

- İşlemler el ile veya analog olduğundan ölçümlerin izlenmesi zorlaşır
- İletişimlerin tümü tek bir yerde yakalanmaz
- Veriler silolanır ve ihtiyaç duyan tüm çalışanlarla paylaşılmaz
- Çalışma tutarlı veya verimli bir şekilde gerçekleştirilemeyebilir
- Özel uygulamalar işbirliği araçlarıyla tümleştirilmediğinden verileri ayıklamayı ve paylaşmayı veya performansı ölçmeyi zorlaştırır

Microsoft Teams, bilgileri güvenli bir şekilde paylaşmak ve ekip üyeleriyle dış saha hizmeti yüklenicileri arasında konuşmalar yürütmek için kullanımı kolay bir işbirliği alanı sağlayabilir. Ekipler toplantılar yürütmek, sesli aramalar yapmak, iş siparişlerini merkezi olarak depolamak ve paylaşmak, alan verilerini toplamak, fotoğraf yüklemek, iş süreci çözümleriyle tümleştirmek (Power Apps ve Power Automate ile oluşturulmuş) ve iş kolu uygulamalarını tümleştirmek için kullanılabilir. Bu tür saha hizmeti verileri düşük etki olarak kabul edilebilir; ancak bu senaryolarda çalışanlar ve saha hizmeti personeli arasındaki iletişim ve erişim verileri merkezileştirilerek verimlilik elde edilebilir.

Microsoft Teams'in enerji sektörüne fayda sağlayabildiği bir diğer örnek de saha hizmeti personelinin kesinti sırasında hizmeti geri yüklemek için çalışmasıdır. Saha personeli genellikle alt istasyonlar, istasyon oluşturma veya alandaki varlıklar için mavi baskılar için şema verilerine hızlı erişim gerektirir. Bu veriler yüksek etki olarak kabul edilir ve NERC CIP düzenlemelerine göre korunmalıdır. Kesintiler sırasında saha hizmeti çalışması, saha personeli ve ofis çalışanları arasında ve sırayla son müşterilerle iletişim gerektirir. Microsoft Teams'de iletişimleri ve veri paylaşımını merkezi hale getirmek, saha personeline hem kritik verilere erişmek hem de bilgileri ya da durumu merkeze geri iletmek için kolay bir yöntem sağlar. Örneğin Microsoft Teams, saha personelinin kesintiye giderken konferans aramalarına katılmasını sağlar. Saha personeli ayrıca ortamlarının fotoğraflarını veya videolarını alabilir ve saha ekipmanı şemalarla eşleşmediğinde özellikle önemli olan merkez ofisiyle paylaşabilir. Daha sonra alandan toplanan veriler ve durum, Power BI gibi veri görselleştirme araçları aracılığıyla ofis çalışanlarına ve liderlik ekibine ortaya çıkarılabilir. Sonuç olarak, Microsoft Teams bu kritik durumlarda saha personelini daha verimli ve üretken hale getirir.

### <a name="teams-improve-collaboration-and-reduce-compliance-risk"></a>Teams: İşbirliğini geliştirme ve uyumluluk riskini azaltma

Microsoft 365, temel üyelik sağlayıcısı olarak Office 365 Gruplarını kullanarak Microsoft Teams için ortak ilke özellikleri sağlar. Bu ilkeler işbirliğini geliştirmeye ve uyumluluk gereksinimlerini karşılamaya yardımcı olabilir.

**Office 365 Grup Adlandırma İlkeleri**, Office 365 Grupların ve dolayısıyla Microsoft Teams'in şirket ilkesine göre adlandırılmasını sağlamaya yardımcı olur. Bir Ekibin adı, uygun şekilde adlandırılmadıysa güçlükler sunabilir. Örneğin, çalışanlar yanlış adlandırılıyorsa hangi ekiplerin çalışabileceğini veya içinde bilgi paylaşacaklarını bilmiyor olabilir. Grup adlandırma ilkeleri iyi bir hijyen sağlamaya yardımcı olur ve ayrılmış sözcükler veya uygunsuz terimler gibi belirli sözcüklerin kullanımını da engelleyebilir. 

**Office 365 Grup Süre Sonu İlkeleri**, Office 365 Grupların ve dolayısıyla Microsoft Teams'in kuruluşun gerektirdiğinden daha uzun süre saklanmamasını sağlamaya yardımcı olur. Bu özellik, iki önemli bilgi yönetimi sorununu önlemeye yardımcı olur:

- Microsoft Teams'in gerekli olmayan veya kullanılmayan çoğalması
- Kuruluş tarafından artık gerekli olmayan verilerin fazla tutulması

Yöneticiler Office 365 Grupları (90, 180 veya 365 gün gibi) için gün cinsinden bir süre sonu belirtebilir. bir Office 365 grubu tarafından yedeklenen bir hizmet süre sonu boyunca etkin değilse, grup sahiplerine bildirilir. Hiçbir işlem yapılmazsa, Office 365 Grubu ve Microsoft Teams dahil olmak üzere ilgili tüm hizmetler silinir. 

Microsoft Ekibi'nde verilerin fazla tutulması kuruluşlar için dava riskleri oluşturabilir. Süre sonu ilkelerinin kullanılması, kuruluşun korunması için önerilen bir yöntemdir. Yerleşik saklama etiketleri ve ilkeleriyle birlikte Microsoft 365, kuruluşların yalnızca mevzuat uyumluluğu yükümlülüklerini karşılamak için gereken verileri saklamasına yardımcı olur.

### <a name="teams-integrate-custom-requirements-with-ease"></a>Teams: Özel gereksinimleri kolayca tümleştirme

Microsoft Teams varsayılan olarak Teams'in self servis oluşturulmasını sağlar. Ancak, düzenlemeye tabi olan birçok kuruluş, çalışanlar tarafından şu anda hangi işbirliği alanlarının kullanıldığını, hangi alanların hassas veriler içerdiğini ve kuruluş genelindeki alanların sahiplerinin kim olduğunu denetlemek ve anlamak ister. Microsoft 365, bu denetimleri kolaylaştırmak için kuruluşların self servis Teams oluşturmayı devre dışı bırakmasına olanak tanır. Ayrıca Power Apps ve Power Automate gibi yerleşik Microsoft 365 iş süreci otomasyon araçlarının kullanılması, kuruluşların yeni bir Ekip istemek için basit süreçler oluşturmasına olanak tanır. Kullanımı kolay bir form tamamlanarak, yönetici tarafından otomatik olarak onay istenebilir. Onaylandıktan sonra Ekip otomatik olarak sağlanabilir ve istek sahibine yeni Ekibine bir bağlantı gönderilir. Kuruluşlar, bu tür süreçler oluşturarak diğer iş süreçlerini kolaylaştırmak için özel gereksinimleri de tümleştirebilir.

## <a name="provide-secure-and-compliant-collaboration-in-the-energy-industry"></a>Enerji Sektöründe Güvenli ve Uyumlu İşbirliği Sağlama

Belirtildiği gibi, Microsoft Office 365 ve Office 365 ABD Hükümeti her biri Orta Düzeyde FedRAMP ATO'ya ulaşmış. Azure ve Azure Kamu, en yüksek FedRAMP yetkilendirme düzeyini temsil eden bir FedRAMP High P-ATO elde etti. Buna ek olarak, FedRAMP orta denetim kümesi tüm NERC CIP gereksinimlerini kapsar ve böylece enerji endüstrisi kuruluşlarının ("kayıtlı varlıklar") NERC denetim gereksinimlerini ele almak için ölçeklenebilir ve verimli bir yaklaşım olarak mevcut FedRAMP yetkilendirmelerinden yararlanmasına olanak sağlar. Bununla birlikte, FedRAMP'nin belirli bir noktaya sertifikasyon değil [, sürekli izleme](https://www.fedramp.gov/assets/resources/documents/CSP_Continuous_Monitoring_Strategy_Guide.pdf) için sağlamalar içeren bir değerlendirme ve yetkilendirme programı olduğunu unutmayın. Bu hüküm öncelikli olarak CSP için geçerli olsa da, Bulk Electric Systems'ı işletir Microsoft müşterileri NERC CIP standartlarına kendi uyumluluklarını sağlamakla sorumludur. Düzenlemelerle sürekli uyumluluk sağlanmasına yardımcı olmak için kuruluşun uyumluluk duruşunu sürekli izlemek genellikle önerilen bir uygulamadır.

Microsoft, zaman içinde düzenlemelere uyumluluğun izlenmesine yardımcı olmak için önemli bir araç sağlar:

- **Microsoft Purview Uyumluluk Yöneticisi** , kuruluşun geçerli uyumluluk duruşunu ve bu duruşu geliştirmeye yardımcı olmak için gerçekleştirebileceği eylemleri anlamasına yardımcı olur. Uyumluluk Yöneticisi, veri koruma ve mevzuat standartlarıyla ilgili riskleri azaltmaya yardımcı olan eylemleri tamamlamadaki ilerlemeyi ölçen risk tabanlı bir puan hesaplar. Uyumluluk Yöneticisi, Microsoft 365 veri koruma temeli temelinde bir başlangıç puanı sağlar. Bu temel, ortak endüstri düzenlemelerini ve standartlarını içeren bir dizi denetimdir. Bu puan iyi bir başlangıç noktası olsa da, bir kuruluş kendi sektörüyle daha ilgili değerlendirmeler ekledikten sonra Uyumluluk Yöneticisi daha güçlü hale gelir. Uyumluluk Yöneticisi [, FedRAMP Orta Denetim Kümesi](https://www.fedramp.gov/documents/), [NIST 800-53 Rev. 4](https://go.microsoft.com/fwlink/?linkid=2109075) ve [AICPA SOC 2](https://go.microsoft.com/fwlink/?linkid=2115184) dahil olmak üzere NERC CIP uyumluluk yükümlülükleriyle ilgili bir dizi mevzuat standartlarını destekler. Enerji endüstrisi kuruluşları da gerekirse özel denetim kümeleri oluşturabilir veya içeri aktarabilir.

Compliance Manager'da yerleşik olarak bulunan iş akışı özellikleri, enerji kuruluşlarının mevzuat uyumluluğu süreçlerini dönüştürmesine ve dijitalleştirmesine olanak tanır. Geleneksel olarak, enerji sektöründeki uyumluluk ekipleri aşağıdaki zorluklarla karşı karşıya kalır:

- Düzeltme eylemlerinde tutarsız raporlama veya ilerleme durumunu izleme
- Verimli olmayan veya etkisiz işlemler
- Yetersiz kaynak veya sahiplik eksikliği
- Gerçek zamanlı bilgi eksikliği ve insan hatası

Uyumluluk Yöneticisi'nin kullanımı aracılığıyla mevzuat uyumluluğu süreçlerinin yönlerini otomatikleştirerek, kuruluşlar yasal ve uyumluluk işlevleri üzerindeki yönetim yükünü azaltabilir. Bu araçlar düzeltme eylemleri, daha tutarlı raporlama ve eylemlerin belgelenmiş sahipliği (eylemlerin uygulanmasına bağlı) hakkında daha güncel bilgiler sağlayarak bu zorlukların giderilmesine yardımcı olabilir. Kuruluşlar zaman içinde düzeltme eylemlerini otomatik olarak izleyebilir ve genel verimlilik artışlarını görebilir. Bu, personelin riskte daha etkili gezinmeye yardımcı olmak için içgörü elde etmeye ve strateji geliştirmeye daha fazla çaba harcamasına olanak tanır.

Uyumluluk Yöneticisi, herhangi bir standart veya düzenleme ile kurumsal uyumluluğun mutlak bir ölçüsünü ifade etmez. Kişisel veriler ve bireysel gizlilik risklerini azaltabilecek denetimleri ne ölçüde benimsediğinizi ifade eder. Uyumluluk Yöneticisi'nden gelen öneriler, uyumluluk garantisi olarak yorumlanmamalıdır. Uyumluluk Yöneticisi'nde sağlanan müşteri eylemleri önerilerdir. Uygulamadan önce yasal yükümlülüklerini yerine getirmek için bu önerilerin etkinliğini değerlendirmek her kuruluşa bağlı olur. Uyumluluk Yöneticisi'nde bulunan öneriler, uyumluluk garantisi olarak yorumlanmamalıdır.

Siber güvenlikle ilgili birçok denetim [FedRAMP Orta Denetim Kümesi](https://www.fedramp.gov/documents/) ve [NERC CIP standartlarına](https://www.nerc.com/pa/Stand/Pages/CIPStandards.aspx) dahildir. Ancak Microsoft 365 platformuyla ilgili temel denetimler arasında güvenlik yönetimi denetimleri (CIP-003-6), hesap ve erişim yönetimi/erişim iptali (CIP-004-6), elektronik güvenlik çevresi (CIP-005-5), güvenlik olayı izleme ve olay yanıtı (CIP-008-5) bulunur. Aşağıdaki temel Microsoft 365 özellikleri, bu konularda yer alan riskleri ve gereksinimleri gidermeye yardımcı olur.

### <a name="secure-user-identities-and-control-access"></a>Güvenli Kullanıcı Kimlikleri ve Denetim Erişimi

Belgelere ve uygulamalara erişimi koruma, kullanıcı kimliklerinin güvenliğini güçlü bir şekilde sağlamakla başlar. Temel olarak bu, kuruluşun kimlikleri depolaması ve yönetmesi için güvenli bir platform sağlamayı ve güvenilir bir kimlik doğrulama aracı sağlamayı gerektirir. Ayrıca bu uygulamalara erişimi dinamik olarak denetlemeyi de gerektirir. Çalışanlar çalışırken, uygulamadan uygulamaya veya birden çok konum ve cihaz arasında geçiş yapabilir. Sonuç olarak, her adımda verilere erişimin kimliği doğrulanmalıdır. Ayrıca kimlik doğrulaması işleminin kimliklerin gizliliğinin ihlal edilmediğinden emin olmak için güçlü bir protokolü ve birden çok kimlik doğrulama faktörünün (tek seferlik SMS geçiş kodu, kimlik doğrulayıcı uygulaması, sertifika vb.) desteklemesi gerekir. Son olarak, risk tabanlı erişim ilkelerini zorunlu tutma, verileri ve uygulamaları içeriden gelen tehditlere, yanlışlıkla veri sızıntılarına ve veri sızdırmaya karşı korumaya yönelik önemli bir öneridir.

Microsoft 365, kimliklerin merkezi olarak depolandığı ve güvenli bir şekilde yönetildiği **Azure Active Directory (Azure AD)** ile güvenli bir tanımlama platformu sağlar. Azure Active Directory, bir çok ilgili Microsoft 365 güvenlik hizmetiyle birlikte, çalışanlara güvenli bir şekilde çalışması için gereken erişimi sağlamanın yanı sıra kuruluşu tehditlere karşı korumanın temelini oluşturur.

**Azure AD Multi-Factor Authentication (MFA)** platformda yerleşiktir ve kullanıcıların hassas verilere ve uygulamalara erişirken söyledikleri kişiler olmasını sağlamaya yardımcı olmak için ek bir koruma katmanı sağlar. Azure MFA için parola ve bilinen mobil cihaz gibi en az iki kimlik doğrulaması biçimi gerekir. Microsoft Authenticator uygulaması, SMS ile teslim edilen tek seferlik geçiş kodu, kullanıcının PIN girmesi gereken bir telefon araması alma ve akıllı kartlar veya sertifika tabanlı kimlik doğrulaması gibi birkaç ikinci faktörlü kimlik doğrulama seçeneğini destekler. Parolanın gizliliğinin ihlal edilmesi durumunda, potansiyel bir korsanın kuruluş verilerine erişmek için kullanıcının telefonuna ihtiyacı vardır. Buna ek olarak, Microsoft 365 modern kimlik doğrulamasını temel protokol olarak kullanır ve web tarayıcılarından Microsoft Outlook ve Microsoft Office uygulamaları gibi işbirliği araçlarına aynı güçlü kimlik doğrulama deneyimini getirir.

**Azure AD Koşullu Erişim**, erişim denetimi kararlarını otomatikleştirmek ve şirket varlıklarını korumak için ilkeler uygulamak için sağlam bir çözüm sağlar. Yaygın bir örnek, bir çalışanın hassas müşteri verileri içeren bir uygulamaya erişmeye çalışması ve çok faktörlü kimlik doğrulaması gerçekleştirmek için otomatik olarak gerekli olmasıdır. Azure Koşullu Erişim, kullanıcının erişim isteğinden gelen sinyalleri (kullanıcı, cihazı, konumu, ağı ve erişmeye çalıştığı uygulama veya depo gibi) bir araya getirir. Uygulamaya erişmeye yönelik her girişimi yapılandırdığınız ilkelere göre dinamik olarak değerlendirir. Kullanıcı veya cihaz riski yükseltilmişse veya başka koşullar karşılanmazsa, Azure AD ilkeyi otomatik olarak zorlar (örneğin, dinamik olarak MFA gerektirme, erişimi kısıtlama ve hatta engelleme). Bu, hassas varlıkların dinamik olarak değişen ortamlarda korunmasına yardımcı olur. 

**Office 365 için Microsoft Defender**, kuruluşları e-posta yoluyla gönderilen kötü amaçlı bağlantılardan ve kötü amaçlı yazılımlardan korumak için tümleşik bir hizmet sağlar. Kullanıcıları etkileyen en yaygın saldırı vektörlerinden biri e-posta kimlik avı saldırılarıdır. Bu saldırılar, belirli yüksek profilli çalışanları dikkatle hedefleyebilir ve çok ikna edici olacak şekilde oluşturulabilir. Bunlar genellikle kullanıcının kötü amaçlı bir bağlantıya tıklamasını veya kötü amaçlı yazılım içeren bir eki açmasını gerektiren bir eylem çağrısı içerir. Virüs bulaştıktan sonra saldırgan bir kullanıcının kimlik bilgilerini çalabilir ve kuruluş genelinde yaya olarak hareket edebilir. Ayrıca hassas bilgiler arayan e-postaları ve verileri de yok edebilir. Office 365 için Microsoft Defender, tıklama zamanında bağlantıları kötü amaçlı olabilecek siteler için değerlendirir ve engeller. Email ekler, kullanıcının posta kutusuna teslim edilmesi için korumalı bir korumalı alanda açılır. 

**Microsoft Defender for Cloud Apps**, kuruluşlara ilkeleri ayrıntılı düzeyde zorunlu kılma olanağı sağlar. Bu, Machine Learning kullanılarak otomatik olarak tanımlanan bireysel kullanıcı profillerini temel alan davranış anomalilerini algılamayı içerir. Cloud Apps için Defender, erişilen belgelerin kullanıcı davranışı ve özellikleriyle ilgili ek sinyalleri değerlendirerek Azure Koşullu Erişim ilkelerini kullanır. Zaman içinde, Bulut Uygulamaları için Defender her çalışan için tipik davranışı (erişen veriler ve kullandıkları uygulamalar) öğrenir. Öğrenilen davranış düzenlerine bağlı olarak, bir çalışan bu davranış profilinin dışına çıkarsa ilkeler güvenlik denetimlerini otomatik olarak zorunlu kılabilir. Örneğin, bir çalışan genellikle saat 9:00'dan itibaren bir muhasebe uygulamasına erişiyorsa. pazartesiden cumaya saat 17:00'ye kadar, ancak aynı kullanıcı pazar akşamı bu uygulamaya yoğun bir şekilde erişmeye başlar. Bulut Uygulamaları için Defender, kullanıcının yeniden kimlik doğrulamasını zorunlu kılmak için ilkeleri dinamik olarak zorunlu kılabilir. Bu, kimlik bilgilerinin gizliliğinin ihlal edilmediğinden emin olmanıza yardımcı olur. Ayrıca Cloud Apps için Defender, kuruluştaki Gölge BT'yi keşfetmeye ve tanımlamaya yardımcı olabilir. Bu, InfoSec ekiplerinin hassas verilerle çalışırken çalışanların tasdikli araçlar kullanmasını sağlamasına yardımcı olur. Son olarak, Bulut Uygulamaları için Defender, Hassas verileri Microsoft 365 platformunun dışında bile Bulutun herhangi bir yerinde koruyabilir. Kuruluşların belirli dış Bulut uygulamalarını tasdik etmesine (veya tasdikini kaldırmasına) olanak tanır ve kullanıcılar bu uygulamalarda çalışırken erişimi ve izlemeyi denetler.

**Azure Active Directory** ve ilgili Microsoft 365 güvenlik hizmetleri, enerji endüstrisi kuruluşlarına modern bir bulut işbirliği platformunun dağıtılacağı temeli sağlar. Azure Active Directory, verilere ve uygulamalara erişimi korumaya yönelik denetimler içerir. Bu denetimler, güçlü güvenlik sağlamanın yanı sıra kuruluşların mevzuat uyumluluğu yükümlülüklerini karşılamasına da yardımcı olur. 

Azure Active Directory ve Microsoft 365 hizmetleri ile tümleşiktir ve aşağıdaki önemli özellikleri sağlar:

- Kullanıcı kimliklerini merkezi olarak depolama ve güvenli bir şekilde yönetme
- Erişim isteklerinde kullanıcıların kimliğini doğrulamak için çok faktörlü kimlik doğrulaması da dahil olmak üzere güçlü bir kimlik doğrulama protokolü kullanın
- Tüm uygulamalarda tutarlı ve sağlam bir kimlik doğrulama deneyimi sağlama
- İlke karar verme sürecine birden çok sinyal ekleyerek (kimlik, kullanıcı/grup üyeliği, uygulama, cihaz, ağ, konum ve gerçek zamanlı risk puanı dahil) tüm erişim isteklerinde ilkeleri dinamik olarak doğrulayın
- Kullanıcı davranışına ve dosya özelliklerine göre ayrıntılı ilkeleri doğrulayın ve gerektiğinde ek güvenlik önlemlerini dinamik olarak zorunlu kılın
- Kuruluştaki gölge BT'yi belirleyin ve InfoSec ekiplerinin bulut uygulamalarını tasdik etmelerine veya engellemelerine izin verin
- Microsoft ve Microsoft dışı bulut uygulamalarına erişimi izleme ve denetleme
- E-posta kimlik avı ve fidye yazılımı saldırılarına karşı proaktif koruma

## <a name="identify-sensitive-data-and-prevent-data-loss"></a>Hassas Verileri Tanımlama ve Veri Kaybını Önleme

FedRAMP Orta Denetim Kümesi ve NERC CIP standartları, temel denetim gereksinimi olarak bilgi korumasını da içerir (CIP-011-2). Bu gereksinimler özellikle BES (Toplu Elektrik Sistemi) Siber Sistem Bilgileri ile ilgili bilgileri ve bu bilgilerin korunması ve güvenli bir şekilde işlenmesi (depolama, ulaşım ve kullanım dahil) ile ilgili bilgileri tanımlama gereksinimini ele alır. BES Siber Sistem Bilgileri'ne özel örnekler, genel kullanıma açık olmayan ve yetkisiz erişime veya yetkisiz dağıtıma izin vermek için kullanılabilen toplu elektrik sisteminin (BES Siber Sistemler, Fiziksel Access Control Sistemleri ve Elektronik Access Control veya izleme sistemleri) çalıştırılması için temel olan sistemler hakkında güvenlik yordamları veya güvenlik bilgilerini içerebilir. Bununla birlikte, enerji kuruluşlarının günlük operasyonları için kritik öneme sahip müşteri bilgilerini tanımlamak ve korumak için de aynı ihtiyaç vardır.

Microsoft 365, aşağıdakiler gibi güçlü özelliklerin bir birleşimiyle hassas verilerin kuruluş içinde tanımlanmasını ve korunmasını sağlar:

- **Hem** kullanıcı tabanlı sınıflandırma hem de hassas verilerin otomatik sınıflandırması için Microsoft Purview Bilgi Koruması

- Hassas veri türleri (ör. normal ifadeler) ve anahtar sözcükler kullanarak hassas verilerin otomatik olarak tanımlanması için **Microsoft Purview Veri Kaybı Önleme (DLP**) ve ilke zorlama

**Microsoft Purview Bilgi Koruması**, çalışanların belgeleri ve e-postaları duyarlılık etiketleriyle sınıflandırmasına olanak tanır. Duyarlılık etiketleri, kullanıcılar tarafından Microsoft Office uygulamalarındaki belgelere ve Microsoft Outlook içindeki e-postalara el ile uygulanabilir. Duyarlılık etiketleri belge işaretlerini, şifreleme yoluyla korumayı ve hak yönetimini zorunlu kılmayı otomatik olarak uygulayabilir. Duyarlılık etiketleri, anahtar sözcükleri ve hassas veri türlerini (kredi kartı numaraları, sosyal güvenlik numaraları, kimlik numaraları vb.) kullanan ilkeler yapılandırılarak da otomatik olarak uygulanabilir. 

Microsoft ayrıca eğitilebilir sınıflandırıcılar da sağlar. Bunlar makine öğrenmesi modellerini kullanarak, yalnızca desen eşleştirme veya içerik içindeki öğelerle değil, içeriğin ne olduğuna bağlı olarak hassas verileri tanımlar. Sınıflandırıcı, sınıflandırılacak içeriğin birçok örneğine bakarak bir içerik türünü tanımlamayı öğrenir. Sınıflandırıcıyı eğiterek başlar ve belirli bir kategori içindeki içerik örnekleri sağlanır. Örnekleri işledikten sonra model, hem eşleşen hem de eşleşmeyen örneklerin bir karışımını sağlayarak test edilir. Sınıflandırıcı daha sonra belirli bir örneğin kategoriye girip girmediğini tahmin eder. Ardından bir kişi sonuçları doğrular, sınıflandırıcının tahminlerinin doğruluğunu artırmaya yardımcı olmak için pozitifleri, negatifleri, hatalı pozitifleri ve hatalı negatifleri sıralar. Eğitilen sınıflandırıcı yayımlandığında SharePoint Online, Exchange Online ve OneDrive İş içeriği işler ve otomatik olarak sınıflandırır.

Belgelere ve e-postalara duyarlılık etiketleri uygulamak, seçilen duyarlılığı tanımlayan nesnenin içine meta veriler ekler ve böylece duyarlılık verilerle birlikte hareket eder. Sonuç olarak, etiketli bir belge kullanıcının masaüstünde veya şirket içi bir sistemde depolanmış olsa bile, yine de korunur. Bu, Microsoft Defender for Cloud Apps veya ağ uç cihazları gibi diğer Microsoft 365 çözümlerinin hassas verileri tanımlamasına ve güvenlik denetimlerini otomatik olarak zorlamasına olanak tanır. Duyarlılık etiketleri, çalışanları bir kuruluştaki hangi verilerin hassas olarak kabul edildiği ve bu verilerin nasıl işlendiği konusunda eğitmek gibi ek bir avantaja sahiptir.

**Microsoft Purview Veri Kaybı Önleme (DLP),** hassas veriler içeren belgeleri, e-postaları ve konuşmaları otomatik olarak tanımlar. Bunu, hassas veri türleri için bunları tarayarak ve ardından bu nesnelere ilke uygulayarak yapar. İlkeler SharePoint ve OneDrive İş içindeki belgelere uygulanır. İlkeler, kullanıcılar e-posta gönderdiğinde ve Microsoft Teams'de sohbet ve kanal konuşmaları içinde de uygulanır. İlkeler anahtar sözcükleri, hassas veri türlerini, bekletme etiketlerini ve verilerin kuruluş içinde mi yoksa dışarıdan mı paylaşıldığını aramak için yapılandırılabilir. Kuruluşların hatalı pozitif sonuçları daha iyi önlemek için DLP ilkelerine ince ayar yapmalarına yardımcı olmak için denetimler sağlanır. Hassas veriler bulunduğunda, Microsoft 365 uygulamalarındaki kullanıcılara özelleştirilebilir ilke ipuçları görüntülenebilir. İlke ipuçları, kullanıcılara içeriklerinin hassas veriler içerdiğini ve düzeltici eylemler önerebileceğini bildirir. İlkeler ayrıca kullanıcıların belgelere erişmesini, belgeleri paylaşmasını veya belirli türde hassas veri içeren e-postalar göndermesini engelleyebilir. Microsoft 365, 100'den fazla yerleşik hassas veri türünü destekler. Kuruluşlar özel hassas veri türlerini ilkelerine uyacak şekilde yapılandırabilir.

kuruluşlara Microsoft Purview Bilgi Koruması ve DLP ilkelerinin dağıtlanması için dikkatli bir planlama gerekir. Ayrıca, çalışanların kuruluşun veri sınıflandırma şemasını ve hangi veri türlerinin hassas olduğunu anlaması için kullanıcı eğitimi gerektirir. Çalışanlara hassas verileri tanımlamalarına ve bunları nasıl işleyebileceklerini anlamalarına yardımcı olacak araçlar ve eğitim programları sağlamak, onları bilgi güvenliği risklerini azaltmaya yönelik çözümün bir parçası haline getirir.

## <a name="govern-data-by-effectively-managing-records"></a>Kayıtları Etkili Bir Şekilde Yöneterek Verileri Yönetme

Düzenlemeler, birçok kuruluşun, yönetilen kurumsal saklama zamanlamasına göre temel kuruluş belgelerinin saklamasını yönetmesini gerektirir. Kuruluşlar, veriler yetersiz tutulursa (çok erken silinirse) mevzuat uyumluluğu riskleriyle veya veriler fazla tutulursa (çok uzun tutulursa) yasal risklerle karşı karşıya kalır. Etkili kayıt yönetimi stratejileri, kuruluş belgelerinin kuruluş için riski en aza indirmek için tasarlanmış önceden belirlenmiş saklama sürelerine göre tutulmasına yardımcı olur. Bekletme süreleri, merkezi olarak yönetilen bir kuruluş kaydı bekletme zamanlaması içinde belirlenmiştir. Saklama süreleri, her belge türünün doğasına, belirli veri türlerinin korunmasına yönelik mevzuat uyumluluğu gereksinimlerine ve kuruluşun tanımlı ilkelerine bağlıdır. 

Kuruluş belgeleri arasında kayıt saklama dönemlerinin doğru bir şekilde atandığı durumlarda, tek tek belgelere benzersiz olarak saklama süreleri atayan ayrıntılı bir işlem gerekebilir. Kayıt saklama ilkelerini büyük ölçekte uygulamak birçok nedenden dolayı zor olabilir. Bu nedenler, birçok durumda elde tutma sürelerinin kurumsal olaylarla (süresi dolan sözleşmeler veya kuruluştan ayrılan bir çalışan gibi) tetiklenebileceği gerçeğiyle birlikte enerji endüstrisi kuruluşları içindeki çok sayıda belgeyi içerir.

Microsoft 365, kayıt yönetimi gereksinimlerini kolayca uygulamak için bekletme etiketleri ve ilkeleri tanımlamaya yönelik özellikler sağlar. Kayıt yöneticisi, geleneksel bekletme zamanlamasında "kayıt türünü" temsil eden bir bekletme etiketi tanımlar. Bekletme etiketi şunları tanımlayan ayarları içerir:

- Kaydın ne kadar süreyle tutuldu
- Eşzamanlılık gereksinimleri veya saklama süresi dolduğunda ne olur (belgeyi silin, bir değerlendirme gözden geçirmesi başlatın veya hiçbir işlem gerçekleştirmeyin)
- Bekletme süresinin başlatılmasını tetikleyen işlemler (oluşturulma tarihi, son değiştirme tarihi, etiketli tarih veya olay) ve
- Belge veya e-posta bir kayıtsa (yani düzenlenemez veya silinemez)

Bekletme etiketleri daha sonra SharePoint veya OneDrive sitelerinde, Exchange posta kutularında ve Office 365 Gruplarında yayımlanır. Kullanıcılar daha sonra belgelere ve e-postalara bekletme etiketlerini el ile uygulayabilir. Veya kayıt yöneticileri bekletme etiketlerini otomatik olarak uygulamak için kuralları kullanabilir. Otomatik uygulama kuralları, kredi kartı numaraları, sosyal güvenlik numaraları veya diğer kişisel bilgiler (PII) gibi belgelerde veya e-postalarda bulunan anahtar sözcükleri veya hassas verileri temel alabilir. Otomatik uygulama kuralları SharePoint meta verilerini de temel alabilir.

FedRAMP Orta Denetim Kümesi ve NERC CIP standartları, temel kontrol gereksinimi olarak Varlık Yeniden Kullanımı ve Elden Çıkarma 'yı da içerir (CIP-011-2). Bu gereksinimler bir kez daha ÖZELLIKLE BES (Toplu Elektrik Sistemi) Siber Sistem Bilgilerini ele alır. Ancak, diğer yargı düzenlemeleri, enerji endüstrisi kuruluşlarının birçok bilgi türü için kayıtları etkili bir şekilde yönetmesini ve atmalarını gerektirecektir. Bu bilgiler finansal tabloları, sermaye proje bilgilerini, bütçeleri, müşteri verilerini vb. içerir. Her durumda, enerji kuruluşlarının sağlam kayıt yönetimi programları ve kurumsal kayıtların savunulabilir bir şekilde dağıtılmasıyla ilgili kanıt tutmaları gerekir.

Microsoft 365, her bekletme etiketiyle kayıt yöneticilerinin bir değerlendirme gözden geçirmesi gerekip gerekmediğini belirlemesine olanak tanır. Ardından bu kayıt türleri edat için geldiğinde, saklama süreleri dolduktan sonra, içerik silinmeden önce belirlenen değerlendirme gözden geçirenleri tarafından bir gözden geçirme yapılmalıdır. Değerlendirme gözden geçirmesi onaylandıktan sonra içerik silme işlemi devam eder. Ancak, silmenin kanıtı (silme işlemini gerçekleştiren kullanıcı ve gerçekleştiği tarih/saat) bir yok etme sertifikası olarak birden çok yıl boyunca korunur. Kuruluşlar yok etme sertifikalarının daha uzun veya kalıcı bir şekilde saklanmasını gerektiriyorsa Microsoft Sentinel, günlük ve denetim verilerinin uzun süreli bulut tabanlı depolanması için kullanılabilir. Microsoft Sentinel kuruluşlara etkinlik verilerinin, günlük verilerinin ve saklama/bırakma verilerinin uzun süreli depolanması ve saklanması üzerinde tam denetim sağlar.

## <a name="comply-with-ferc-and-ftc-regulations-for-energy-markets"></a>Enerji Piyasaları için FERC ve FTC Yönetmeliklerine Uyma

ABD Federal Enerji Düzenleme Komisyonu (FERC), [enerji piyasaları ve elektrik enerjisi ve doğal gaz pazarları için ticaretle ilgili düzenlemeleri](https://www.ferc.gov) denetler. ABD Federal Ticaret Komisyonu (FTC) [petrol piyasasındaki benzer düzenlemeleri](https://www.ftc.gov/sites/default/files/documents/rules/prohibition-energy-market-manipulation-rule/091113mmrguide.pdf) denetler. Her iki durumda da bu düzenleyici kurumlar enerji piyasalarının manipülasyonunu yasaklama kuralları ve rehberliği belirlemektedir. Örneğin FERC, enerji kuruluşlarının ticareti, tüccar iletişimlerini ve iç denetimlerle uyumluluğu izlemek için teknoloji kaynaklarına yatırım yapmalarını önerir. Düzenleyiciler ayrıca enerji kuruluşlarının kuruluşun uyumluluk programının sürekli etkinliğini düzenli aralıklarla değerlendirmelerini de önerir.

Geleneksel olarak, iletişim izleme çözümleri maliyetlidir ve yapılandırmak ve yönetmek karmaşık olabilir. Ayrıca kuruluşlar, çalışanların kullanımına sunulan birçok farklı iletişim kanalını izleme konusunda zorluklar yaşayabilir. Microsoft 365, çalışan iletişimlerini izlemek, çalışan etkinliklerini denetlemek ve enerji pazarları için FERC düzenlemelerine uymaya yardımcı olmak için çeşitli yerleşik sağlam özellikler sağlar.

### <a name="implement-supervisory-control"></a>Denetim Denetimi Uygulama

Microsoft 365, kuruluşların çalışanların iletişimlerini yakalayan (yapılandırılmış koşullara göre) denetim ilkeleri yapılandırmalarına ve bunların belirlenen gözetmenler tarafından gözden geçirilmesine olanak tanır. Denetim ilkeleri iç/dış e-posta ve ekleri, Microsoft Teams sohbeti ve kanal iletişimlerini, Skype Kurumsal Çevrimiçi sohbet iletişimlerini ve eklerini ve üçüncü taraf hizmetleri (Facebook veya Dropbox gibi) aracılığıyla yapılan iletişimleri yakalayabilir. 

Bir kuruluş içinde yakalanıp gözden geçirilebilen iletişimlerin kapsamlı doğası ve ilkelerin yapılandırılabileceği kapsamlı koşullar, kuruluşların FERC enerji pazarı düzenlemelerine uymasına yardımcı olmak için Microsoft 365 Denetim İlkeleri'ne olanak sağlar. Denetim ilkeleri, kişilerin veya grupların iletişimlerini gözden geçirmek üzere yapılandırılabilir. Ayrıca, gözetmenler kişi veya grup olarak yapılandırılabilir. Gelen veya giden iletileri, etki alanlarını, bekletme etiketlerini, anahtar sözcükleri veya tümcecikleri, anahtar sözcük sözlüklerini, hassas veri türlerini, ekleri, ileti boyutunu veya ek boyutunu temel alan iletişimleri yakalamak için kapsamlı koşullar yapılandırılabilir. Gözden geçirenlere bayrak eklenmiş iletişimleri gözden geçirebilecekleri, ilkeleri ihlal eden iletişimler üzerinde işlem yapabilecekleri veya bayrak eklenmiş öğeleri çözümlendi olarak işaretleyebilecekleri bir pano sağlanır. Ayrıca, önceki incelemelerin ve çözümlenen öğelerin sonuçlarını da gözden geçirebilirler. 

Microsoft 365, denetim ilkesi gözden geçirme etkinliklerinin ilkeye ve gözden geçirene göre denetlenebilmesini sağlayan raporlar sağlar. Kullanılabilir raporlar, denetim ilkelerinin kuruluşların yazılı denetim ilkeleri tarafından tanımlandığı şekilde çalıştığını doğrulamak için kullanılabilir. Raporlar, şirket ilkesiyle uyumlu olmayan iletişimler de dahil olmak üzere gözden geçirme gerektiren iletişimleri tanımlamak için de kullanılabilir. Son olarak, denetim ilkelerini yapılandırma ve iletişimleri gözden geçirmeyle ilgili tüm etkinlikler birleşik Office 365 denetim günlüğünde denetlenir. 

Microsoft 365 Denetim İlkeleri, kuruluşların insan kaynakları taciz ihlalleri ve şirket iletişimlerinde rahatsız edici dil gibi kurumsal ilkelerle uyumluluk için iletişimleri izlemesine olanak tanır. Ayrıca kuruluşların birleşmeler ve devralmalar veya liderlik değişiklikleri gibi hassas kuruluş değişikliklerine maruz kaldıklarında iletişimleri izleyerek riski azaltmalarına da olanak tanır. 

### <a name="communication-compliance"></a>İletişim uyumluluğu

Çalışanların kullanımına sunulan birçok iletişim kanalıyla kuruluşlar, enerji ticaret piyasaları gibi düzenlenmiş sektörlerde iletişimleri algılamak ve araştırmak için giderek daha etkili çözümlere ihtiyaç duyuyor. Bu zorluklar arasında iletişim kanallarının sayısının ve ileti hacminin artırılması ve ilke ihlalleri için olası para cezası riski bulunabilir.

[Microsoft Purview İletişim Uyumluluğu](/microsoft-365/compliance/communication-compliance), kuruluşunuzdaki uygunsuz iletileri algılamanıza, araştırmanıza ve üzerinde işlem yapmanıza yardımcı olarak iletişim risklerini en aza indirmenize yardımcı olan bir uyumluluk çözümüdür. Önceden tanımlanmış ve özel ilkeler, belirlenen gözden geçirenler tarafından incelenebilmeleri için ilke eşleşmeleri için iç ve dış iletişimleri taramanıza olanak sağlar. Gözden geçirenler kuruluşunuzdaki taranmış e-postayı, Microsoft Teams'i, Yammer'ı veya üçüncü taraf iletişimlerini araştırabilir ve kuruluşunuzun ileti standartlarıyla uyumlu olduklarından emin olmak için uygun eylemleri gerçekleştirebilir.

İletişim Uyumluluğu, uyumluluk ekiplerinin olası ihlaller için iletileri etkili ve verimli bir şekilde gözden geçirmesine yardımcı olur:

- kabul edilebilir kullanım, etik standartlar ve şirkete özgü ilkeler gibi kurumsal ilkeler 
- yaklaşan alımlar, birleşmeler, kazançların açığa çıkması, yeniden düzenleme veya liderlik ekibi değişiklikleri gibi hassas projeler hakkında yetkisiz iletişimler gibi hassas veya hassas iş açıklamaları
- bir kuruluşun enerji pazarları için FERC düzenlemelerine uygun olarak faaliyette bulunduğu işletme türleri veya işlemler ile ilgili çalışan iletişimleri gibi mevzuat uyumluluğu gereksinimleri

İletişim uyumluluğu, iletişimleri gözden geçirirken hatalı pozitif sonuçları azaltmaya yardımcı olmak için yerleşik tehdit, taciz ve küfür sınıflandırıcıları sağlar. Bu, inceleme ve düzeltme işlemi sırasında gözden geçirenlere zaman kazandırır. Gözden geçirenlerin, ilke uyarıları tarafından vurgulanmış uzun iş parçacıkları içindeki belirli iletilere odaklanmalarına yardımcı olur. Bu, uyumluluk ekiplerinin riskleri daha hızlı bir şekilde belirlemelerine ve düzeltmelerine yardımcı olur. Uyumluluk ekiplerine ilkeleri kolayca yapılandırma ve ince ayar yapma, çözümü kuruluşun belirli gereksinimlerine göre ayarlama ve hatalı pozitif sonuçları azaltma olanağı sağlar. İletişim uyumluluğu, riskli davranış veya ilke ihlallerindeki olası desenleri vurgulayarak zaman içinde riskli olabilecek kullanıcı davranışını belirlemeye de yardımcı olabilir. Son olarak esnek yerleşik düzeltme iş akışları sağlar. Bu iş akışları, gözden geçirenlerin tanımlanan kurumsal süreçlere göre yasal veya insan kaynakları ekiplerine yükseltmeye yönelik hızlı bir şekilde harekete geçmelerine yardımcı olur.

## <a name="protect-against-data-exfiltration-and-insider-risk"></a>Veri sızdırma ve şirket içi risklere karşı koruma

Kuruluşlar için yaygın bir tehdit, veri sızdırma veya bir kuruluştan veri ayıklama eylemidir. Çalışanlar veya saha hizmeti personeli tarafından her gün erişilebilen bilgilerin hassas doğası nedeniyle bu durum enerji kuruluşları için önemli bir endişe kaynağı olabilir. Bu veriler hem BES (Toplu Elektrik Sistemi) Siber Sistem bilgilerini hem de işle ilgili bilgileri ve müşteri verilerini içerir. Artan iletişim yöntemleri ve veri taşımaya yönelik birçok araçla, veri sızıntıları, ilke ihlalleri ve iç risk risklerinin risklerini azaltmak için genellikle gelişmiş araçlar gerekir.

### <a name="insider-risk-management"></a>İçeriden risk yönetimi

Çalışanların doğası gereği her yerden erişilebilen çevrimiçi işbirliği araçlarıyla etkinleştirilmesi kuruluşa risk getirir. Çalışanlar yanlışlıkla veya kötü amaçlı olarak saldırganlara veya rakiplere veri sızdırabilir. Alternatif olarak, kişisel kullanım için verileri dışarı aktarabilir veya verileri gelecekteki bir işverene götürebilirler. Bu senaryolar, kuruluşlar için güvenlik ve uyumluluk açısından ciddi riskler sunar. Bu riskleri ortaya çıktığında belirlemek ve bunları hızla azaltmak için hem veri toplamaya yönelik akıllı araçlar hem de yasal, insan kaynakları ve bilgi güvenliği gibi departmanlar arasında işbirliği gerekir.

[Microsoft Purview İçeriden Risk Yönetimi](/microsoft-365/compliance/insider-risk-management), kuruluşunuzdaki kötü amaçlı ve yanlışlıkla etkinlikleri algılamanıza, araştırmanıza ve eyleme geçirmenize olanak tanıyarak iç riskleri en aza indirmenize yardımcı olan bir uyumluluk çözümüdür. Insider risk ilkeleri, kuruluşunuzda tanımlanması ve algılanması gereken risk türlerini tanımlamanıza olanak sağlar. Örneğin, olaylar üzerinde işlem yapmak ve gerekirse servis taleplerini Microsoft eKeşif'e (Premium) yükseltmek de buna dahildir. Kuruluşunuzdaki risk analistleri, kullanıcıların kuruluşunuzun uyumluluk standartlarıyla uyumlu olduğundan emin olmak için hızlı bir şekilde uygun eylemler gerçekleştirebilir.

Örneğin, insider risk yönetimi kullanıcının cihazlarından gelen sinyalleri (usb sürücüsüne dosya kopyalama veya kişisel e-posta hesabına e-posta gönderme gibi) veri sızdırma desenlerini tanımlamak için çevrimiçi hizmetler (Office 365 e-posta, SharePoint Online, Microsoft Teams OneDrive İş gibi) etkinliklerle ilişkilendirebilir. Ayrıca bu etkinlikleri, veri sızdırmayla ilişkili ortak bir davranış düzeni olan bir kuruluşta çalışanlarla ilişkilendirebilir. Zaman içinde riskli olabilecek birden çok etkinliği ve davranışı algılayabilir. Yaygın desenler ortaya çıktığında uyarılar oluşturabilir ve araştırmacıların ilke ihlalini yüksek düzeyde güvenle doğrulamak için önemli etkinliklere odaklanmasına yardımcı olabilir. Insider risk yönetimi ayrıca araştırmacıların verilerini karartarak veri gizliliği düzenlemelerinin yerine getirilmelerine yardımcı olurken aynı zamanda araştırma gerçekleştirmelerine yardımcı olan önemli etkinliklere de yardımcı olabilir. Hazır olduğunda, araştırmacıların düzeltme eylemine yönelik vakaları oluşturmaya yönelik yaygın yükseltme iş akışlarının ardından önemli etkinlik verilerini paketlemesine ve insan kaynaklarına ve hukuk departmanlarına güvenli bir şekilde göndermesine olanak tanır.

Insider risk yönetimi, Microsoft 365'te kuruluşların veri gizliliği düzenlemelerini karşılamasına ve daha üst düzey eylemler gerektirdiğinde yerleşik yükseltme yollarını izlemesine izin verirken, insider risklerini algılamaya ve araştırmaya yönelik özelliklerde önemli bir artıştır.

## <a name="conclusion"></a>Sonuç

Microsoft 365, Microsoft Teams ile kuruluş genelinde kullanımı kolay bulut tabanlı işbirliği sağlayan tümleşik ve kapsamlı bir çözüm sunar. Microsoft Teams ayrıca saha hizmeti personeliyle daha iyi iletişim ve işbirliğine olanak sunarak enerji kuruluşlarının daha verimli ve etkili olmasını sağlar. Kurum genelinde ve saha personeliyle daha iyi işbirliği yapmak, enerji kuruluşlarının müşterilere daha iyi hizmet vermelerine yardımcı olabilir.

Enerji endüstrisi kuruluşları, operasyonları ve müşterileri ile ilgili bilgileri nasıl depoladıkları, güvenlik altına aldıkları, yönetdikleri ve sakladığıyla ilgili katı düzenlemelere uymalıdır. Ayrıca, enerji piyasalarının manipülasyonunu nasıl izledikleri ve engelledikleriyle ilgili düzenlemelere uymaları gerekir. Microsoft 365, verileri, kimlikleri, cihazları ve uygulamaları risklerden korumak ve katı enerji endüstrisi düzenlemelerine uymak için güçlü güvenlik denetimleri sağlar. Enerji kuruluşlarının uyumluluklarını değerlendirmesine yardımcı olmak ve zaman içinde eyleme geçmek ve düzeltme etkinliklerini izlemek için yerleşik araçlar sağlanır. Bu araçlar ayrıca iletişimleri izlemek ve denetlemek için kullanımı kolay yöntemler sağlar. Microsoft 365 platformu, Microsoft Azure ve Azure Active Directory gibi temel bileşenler üzerine kurulmuştur ve platformun genel güvenliğinin sağlanmasına yardımcı olur ve kuruluşun FedRAMP Orta ve Yüksek denetim kümeleri için uyumluluk gereksinimlerini karşılamasına yardımcı olur. Bu da enerji kuruluşunun NERC CIP standartlarını karşılama becerisine katkıda bulunur.

Genel olarak Microsoft 365, enerji kuruluşlarının kuruluşu daha iyi korumalarına, daha sağlam uyumluluk programlarına sahip olmasını ve personelin daha iyi içgörüler elde etmeye ve riski daha iyi azaltmaya yönelik stratejiler uygulamaya odaklanmasına olanak tanır.
