---
title: Dikkate alınacak SharePoint 2007 geçiş seçenekleri
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPS150
- OSU140
- SPO160
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: 66325a43-5816-4f8e-81ba-c11b71345b7c
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: Bu makale, sharepoint server 2007 kullanan kullanıcıların yükseltmelerini planlamalarına yardımcı olacak bilgiler içerir.
ms.openlocfilehash: 99ac785f85892ad4cd6a9ac65a9fe822b109d743
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68187789"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a>Dikkate alınacak SharePoint 2007 geçiş seçenekleri

*Bu makale hem Microsoft 365 Kurumsal hem de Office 365 Kurumsal için geçerlidir.*

Microsoft SharePoint 2007 ve SharePoint Server 2007 destek sonuna ulaştı. Yükseltme zamanı! Bu makalede geçiş seçenekleriniz hakkında bilgi sağlanır.
  
## <a name="common-upgrade-strategies-for-sharepoint"></a>SharePoint için yaygın yükseltme stratejileri

SharePoint Server ortamını yükseltmek için birden çok yöntem vardır. Microsoft Office SharePoint Server 2007 grubunuz varsa, yükseltme yöntemlerine bazı örnekler aşağıda verilmiştir:
  
- Veritabanı ekleme
    
- Yan yana yükseltme
    
- Yerinde yükseltme
    
- Karma yükseltme (ayrılmış veritabanları / ayrı veritabanı ekleme ile yerinde)
    
- SharePoint karmaları (çevrimiçi olarak şirket içi SharePoint'e bağlanın)
    
- Site koleksiyonları veya kitaplıkları arasında verileri el ile taşıma
    
- FastTrack Sihirbazı'nı Microsoft 365'e yükseltme ([SharePoint Online dağıtım danışmanı](https://aka.ms/spoguidance))
    
- Microsoft 365'te SharePoint Online'a (SPO) geçiş API'si
    
Sizin için en uygun olan nedir?
  
Çiftliğinizin ne yaptığına ve ne için kullanıldığına ilişkin bilginiz, yükseltme söz konusu olduğunda taktiksel bir güçtür. Kişilerin SharePoint Grubu'nı kullanma şekli, seçeneklerinizden birini belirlemenize yardımcı olur.
  
> [!TIP]
> Microsoft Office SharePoint Server 2007'de de aşamalı yükseltme burada ele alınmamıştır. Adıma özgü yükseltme makalelerinin listesini görmek için [SharePoint Server 2007 destek sonu Yol Haritası'na](sharepoint-2007-end-of-support.md) bakın. 
  
Yükseltme yaptığınız SharePoint sürümü için [Ürün Yaşam Döngüsü](https://support.microsoft.com/lifecycle/search) ve Sistem Gereksinimleri'ni denetlemeyi unutmayın. Bu, bir sonraki yükseltmenin ne zaman gerekli olacağını (örneğin, daha fazla yükseltmeyi planlamak için SharePoint Server 2010 gibi eski bir üründe duraklarsanız, destek sonu tarihini bildiğinizden emin olmanız) ve planınızı destekleyen donanıma sahip olduğunuzdan emin olmanız için bunu bilmeniz için geçerlidir. 
  
SharePoint sitelerinizin bazılarını veya tümünü Bulutta Microsoft 365'e geçişi planlıyorsanız, [Microsoft 365 ve Office 365 hizmet açıklamalarının](/office365/servicedescriptions/office-365-service-descriptions-technet-library) bağlantısının yer işaretini eklemenin tam zamanıdır. SharePoint Online özellikleri ve bunların şirket içi SharePoint Server'dan nasıl farklı olabileceği hakkında bilgi edinmek için Hizmet Açıklamaları'na ihtiyacınız olacaktır. İşlevsel Microsoft Office SharePoint Server 2007 gruplarını yükseltin. Yüklemenizde bozuk siteler varsa, yükseltmeden önce bunları düzeltin.
  
## <a name="a-note-about-managing-risk"></a>Riski yönetme hakkında bir not

Yükseltme mantığının düzeninde 'yan yana' gibi yöntemler önemlidir. Yan yana yükselttiğinizde, Microsoft Office SharePoint Server 2007 grubunuzun bakımını yaparsınız, ancak yeni donanımda bundan sonraki sürümü (SharePoint Server 2010) bir grup oluşturursunuz. Bu üç şekilde yardımcı olur:
  
1. Microsoft Office SharePoint Server 2007 veritabanlarınızın yedeklerini almak için veritabanı eklemeyi kullanarak bunları ayrı olarak yükseltebilirsiniz.
    
2. Microsoft Office SharePoint Server 2007 grubunuzda yalnızca birkaç kritik belge kitaplığının ve diğer bilgilerin kullanımda olduğunu görürseniz, verileri Microsoft Office SharePoint Server 2007'den SharePoint Server 2010'a el ile taşımayı veya yalnızca belirli siteleri ve web'leri sonraki sürüme taşımayı seçebilirsiniz (işinizi kolaylaştırabilir).
    
3. Microsoft Office SharePoint Server 2007 sunucu grubuna ne kadar az işlem yaparsanız, yükseltme işlemi yapılırken grup içindeki veriler o kadar güvenli olur.
    
In-Place yükseltmesi gibi yöntemler doğrudan Microsoft Office SharePoint Server 2007 grubunuzda çalışır ve bir yoldan vazgeçmeniz ve el değmemiş ortamınızla yeniden başlamanız için daha az kolay seçenek sağlar. Mümkün olduğunca, bazı güvenlik önlemleri (özgün ortamın yedeklerini alma ve test etme gibi) oluşturun. Örneğin, Microsoft Office SharePoint Server 2007 grubunuz sanalsa ve yedekleme ve geri yükleme amacıyla yineleniyorsa, yükseltme için hizmet pencerenizden önce en güncel veritabanlarını yedekleyin ve geri yükleyin. Veritabanı yedeklemelerini geri yükleme seçeneğine sahip olduğunuzu bilmek size yalnızca bir hata güvenliği sağlamakla kalmaz, size içinizi rahatlatabilir.
  
> [!TIP]
> [Microsoft Office SharePoint Server 2007, SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc261992(v=office.12)), [SharePoint Server 2013](/previous-versions/office/sharepoint-server-2010/cc261992(v=office.14)) ve [SharePoint Server 2016](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013) için yükseltmeye yönelik en [](/SharePoint/upgrade-and-update/best-practices-for-upgrade)iyi yöntemler belgeleri mevcuttur. Yükseltmeler veya Microsoft 365 geçişleriyle ilgili deneyimi olan Microsoft [İş Ortaklarını](https://partnercenter.microsoft.com/pcv/search) da arayabilirsiniz. 
  
## <a name="make-your-plan"></a>Planınızı yapma

Yükseltmeniz gerekiyorsa, bir plana ihtiyacınız vardır ve bu durumlarda tek boyutlu bir boyut tümüne uymaz. Planınız 'SharePoint Online ile Bir Microsoft 365 aboneliği oluşturun, bir etki alanı kaydedin ve kişileri dosyalarını kaydetmeleri için oraya yönlendirin' kadar basit olabilir. Ve olmayabilir. Bu karar sizindir ve sizin ve kullanıcılarınızın gerçekten ihtiyaç duyduğu şeye kadar uzanır.
  
> [!NOTE]
> Yaşam döngüsü sona eren yazılımlarda çalıştırmak risklidir. Destek dışı olan ürünlere artık sorun bulunduğunda düzeltme eki uygulanmaz. Bu, yeni güvenlik tehditleri ortaya çıkarsa yaşam döngüsü sonu ürünleri artık desteklenmediğinden güvenlik düzeltme ekleri veya düzeltmeler olmayacağı anlamına da gelir. Lütfen bu durumdan kaçının! 
  
### <a name="first-know-your-farm"></a>İlk olarak, çiftliğinizi tanıyin

Yükseltme sırasında karar verme sürecinizin, grubunuzun kuruluşunuz için yaptıklarına bağlı olması gerekir. Neleri karşılar? Rolü nedir? Şirketinizdeki her grup farklı bir role sahip olabilir. SharePoint gruplarınızdan bazıları  *kritik öneme* sahip olabilir, bazıları dosya arşivleri olabilir; burada güvenli bir şekilde tutulabilir. Öte yandan, grubunuz aynı anda birçok rolü dolduruyorsa site koleksiyonlarının, web'lerin, hatta belge kitaplıklarının ne yaptığını, özelleştirmeleri ve bunların ne kadar önemli olduğunu bilmeniz gerekebilir. Verilerinizi bu düzeyde çözümlemek çok fazla iş gibi görünebilir, ancak yükseltmeden veya geçirmeden önce etki alanınızda ustalaşarak zaman ve çabadan tasarruf etmenizi sağlar. Tüm hareketli parçaları ve en önemli parçaları öğrendikten sonra, neleri geride bıraktığınızı da anlarsınız. Bu bilgi sadece ileriye dönük olarak size fayda sağlayacaktır. 
  
Peki, kullanıcılar SharePoint Server grubunuzda en önemli olan şeyin ne olduğunu söylüyor?
  
- Yerleşik SharePoint özellikleri
    
- Büyük veri corpus (dosyaların arşivi gibi)
    
- Kullanılabilirlik
    
- Grup içindeki kritik uygulamalar, web bölümleri veya belgeler (Görev açısından kritik grup)
    
- Uyumluluk standartları karşılanmıştır
    
- Özelleştirme
    
SharePoint grubunuzdan işletmeniz için önemli bir şey çalıştırıyorsanız, bunun istemci hizmeti gereksinimleriyle ilgili büyük bir kritik veri kataloğu gibi çalıştığını varsayarak , 'Kritik uygulamalar'ın yanı sıra 'Kullanılabilirlik' seçeneğinin yanına bir onay işareti koyabilirsiniz; yani, SharePoint'i bir süre kullanamasanız işletmeniz etkilenecektir. Aynı şekilde, grubunuzun sunduğu kritik hizmetler özel koda, site tanımlarına veya birlikte çalışan birçok özelleştirmeye dayandığından 'Özelleştirmeler'i de de kontrol edebilirsiniz.
  
SharePoint, yazılımda yerleşik olarak bulunanların dışında sizin katılımınız olmadan bu gereksinimleri karşılıyorsa ve bunu genel olarak güncelleştirip normal yönetim ve bakım gerçekleştirdiyseniz ,'Yerleşik SharePoint'i seçmiş olabilirsiniz; bu, SharePoint'in eski bir sürümünde oturmanızın nedeni de olabilir. Başka bir deyişle, microsoft Office SharePoint Server 2007 destek sonu'nda zaten ihtiyacınız olanı yapar ve yükseltmeniz gerekmeyen bir hizmettir.
  
Bu öğeleri madde işaretiyle listelediğinizde, yükseltmeniz için ölçütler oluşturursunuz. Başka bir deyişle, tüm yükseltmelerin dikkate alınması için bu çubuğu karşılaması gerekir. Bu, şu anda gereksinimlerinize uymayan yöntemleri eleyebilirsiniz.
  
### <a name="a-simple-sample-plan"></a>Basit bir örnek plan

SharePoint Yükseltmenizin izleyeceği yolda liderlik ve diğer yöneticilerle daha geniş bir fikir birliği olması gerekebilir. SharePoint Server Yöneticileri genellikle Microsoft SQL Server yöneticileriyle işbirliği yapmak, Ağ ve Güvenlik ekipleriyle çalışmak ve daha fazlası. Birçok proje katılımcısı olduğunda yükseltme ve geçiş planınız için sözleşme oluşturmanız veya bunu ayarlamanız gerekebilir. Örneğin, verilerinizi şirketinizin bir bölümünün Microsoft 365'te SharePoint Online kullanması için geçirirseniz, büyük olasılıkla ağınızda performans ayarlaması veya test edilmesi gerekir. Etkilenen ekipler önceden bilgilendirilmelidir.
  
Basit örneğimde bir SharePoint yöneticisinin teklifini gösteriyorum ve ardından tüm paydaşların üzerinde anlaşmaya varan planı listeliyorum. Netlik için sözleşmelerinizi ve kararlarınızı belgele.
  
Plan, bir çiftliğin derinlemesine analizinden sonra başlar ve bazı yükseltme seçeneklerini daraltmaya yol açacak olan çiftliğin rolünü, sorun noktalarını ve diğer önemli bilgileri belirlemeye çalışır. Daha sonra SharePoint yöneticisi tarafından bir yükseltme teklifi yapılır ve proje katılımcıları bir eylem planı üzerinde anlaşmaya varılır.
  
'En önemli' madde işareti listem:
  
- Kullanılabilirlik, SharePoint'te yerleşik özellikler ve Uyumluluk standartları.
    
- Verilerin çoğu üç site koleksiyonundadır ve bir Geliştirme ekibi tarafından kullanılan bir Toplantı Çalışma Alanı dünya çapında birden çok saat diliminde önemli ve yoğun kullanımdadır.
    
- Yaygın olarak kullanılan 17 site daha vardır.
    
- İki belge kitaplığı (Toplantı Çalışma Alanı ve Kök site koleksiyonundaki Belgeler) en büyüktür (her birinde 8000'den fazla belge). Elektronik tablo ekleri içeren çok sayıda arşivlenmiş belgemiz ve listemiz var.
    
- Uyumlulukta kalması GEREKEN hassas verilere sahip 14 kitaplık listesi vardır.
    
- Nereye gidersek gidelim tutma ve e-keşif yapma yeteneğine sahip olmamız GEREKİR.
    
- InfoSec kuralları nedeniyle bu verilerden bazıları şirket içinde kalmalıdır.
    
 **Yükseltme ve geçiş seçeneklerim:**
  
| Evet | Hayır |
|:-----|:-----|
|Veritabanı ekleme ile veritabanlarını yükseltme  <br/> |Yerinde yükseltme  <br/> |
|Yan yana gruplarla yükseltme  <br/> |Karma Yükseltme  <br/> |
|Microsoft 365'te SPO'ya geçiş API'si (kişisel site verileri için)  <br/> |SharePoint Karma (henüz gerekli değil)  <br/> |
|Kritik veriler için SharePoint Online'a bazı el ile veri geçişleri  <br/> |FastTrack sihirbazı Microsoft 365'e yükseltme  <br/> |
   
 **Önerilen planım:**
  
Önce veritabanlarını yükseltebilmemiz için sharepoint sürümlerinin yan yana, bazıları sanallaştırılmış olarak şirket içinde yükseltin. SharePoint 2007'den SharePoint 2010'a gidin. Yöneticiler ve Geliştirmeler sonuçta elde edilen grubu test eder. Kullanıcılar sonuçta elde edilen grubu test ediyor. Bu süre boyunca gösteri durdurma sorunlarını düzeltin. Yine yan yana, SharePoint 2010 veritabanlarını SharePoint 2013'e yükseltin. Test. Kullanıcı testi/pilot. Bu süre boyunca gösteri durdurma sorunlarını düzeltin.
  
- SPO ile Bir Arama Federasyon Karması'nın gereksinimlerinizi karşılayıp karşılamadiğini düşünün.
    
- Buradan SharePoint Online'a yükseltmek istiyorsanız [FastTrack yardımını](https://fasttrack.microsoft.com) göz önünde bulundurun. 
    
- Herhangi bir site koleksiyonlarının Microsoft 365 Aboneliğine yüklenip yüklenemediğini belirleyin. (Microsoft 365 birçok [Uyumluluk standartlarını karşılar](/compliance/regulatory/offering-home). Microsoft [365,eKeşif'e](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) sahiptir ve Uyumluluk Merkezi aracılığıyla [Tutmalar](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E) yapabilir.) 
    
Aksi takdirde, SharePoint Server 2016'ya yan yana yükseltme ile devam edin.
  
> [!NOTE]
> Yükseltmeyi planlayan yöneticiler tarafından yapılan öneriler ile gerçek işlem arasında, yükseltmenin bağlı olduğu diğer paydaşlarla yapılan konuşmalar yer alır. Örneğin, bazen ekonomi yöneticileri planlarını değiştirmeye zorlar. Son karar ne olursa olsun, üzerinde anlaşmaya varılan planın ne olduğunu belgelemelisiniz. Şuna benzer olabilir: 
  
 **Eylem planım:**
  
Şirket içinde, varsayılan SharePoint Server 2010 ve 2013'i oluşturmak için bir sanal ortam kullanırız. SharePoint Server 2016, 2016 için sistem gereksinimlerini karşılayan yeni donanımlar üzerinde derlenecektir. Veritabanlarını SharePoint 2007'den SharePoint Server 2016 ile arasındaki tüm sürümlere yükseltmek için veritabanı eklemeleri yapacağız. Yerel özellikler gereksinimlerimizi karşılamıyorsa, çekirdek özelleştirmeler şu anda SharePoint Server 2016 ortamında yeniden oluşturuluyor ve test ediliyor. Başarılı olursak, yükseltilen veritabanları ve daha az özelleştirme içeren yeni donanım üzerinde bir şirket içi grubumuz olur. Yükseltilen içerik veritabanlarını SharePoint Server 2013'teki yeni site koleksiyonlarına ekleyeceğiz, test edeceğiz, kullanıcı testi/pilot yapacağız ve ardından canlı kullanım için yeni SharePoint Server 2016 ortamına bir DNS kesme işlemi yapacağız.
  
- Şu anda SharePoint Server 2016 ile SharePoint Online arasında Federasyon Karma'nın kullanılmasını göz önünde bulundurmayacağız.
    
- Sitelerimizin tahmini %35'i, gösterişli etki alanları olan yeni SPO sitelerine dönüştürülebilir veya sonuçta OneDrive İş depolama alanına dönüşebilir. Siteleri dönüştürmek veya yeni siteleri SPO'ya yönlendirmek için başka fırsatlar arıyorsunuz.
    
- Geçişin bu bölümünden bazıları kişisel OneDrive İş sitelere sürükleyip bırakarak ve bazıları da geçiş API'sine göre el ile yapılır.
    
Daha ayrıntılı adımlar veya belirli yükseltme yönergelerine yönelik bir dizi bağlantı bir planı izlemelidir. MOSS 2007 bilgisayarı kullanımdan kaldırılmamalı ve karşılaştırma amacıyla sanal ortamlar korunmalıdır; ancak, kullanıcılar SharePoint Server 2016'ya yeniden yönlendirildiğinde yükseltme tamamlanır.
  
Genellikle yöntem seçerken önemli faktörler, yükseltmenin toplam maliyeti ve zaman içindeki maliyettir (SharePoint Geçiş Yol Haritası makalesinde bu konuda daha fazla bilgi bulabilirsiniz). Ancak, önceden planlamak beklentileri ayarlama, akıllıca seçim ve başarının nasıl görüneceğini çerçeveleme konusunda size büyük fayda sağlayacaktır.
  
## <a name="related-links"></a>İlgili bağlantılar

[Office 2007 sunucularından ve istemcilerinden yükseltmenize yardımcı olacak kaynaklar](upgrade-from-office-2007-servers-and-products.md)
  
[Microsoft Yaşam Döngüsü İlkesi ve Yaşam Döngüsü araması](https://support.microsoft.com/lifecycle)
  
[Yükseltme veya geçiş konusunda yardımcı olabilecek Microsoft İş Ortaklarını arayın](https://partnercenter.microsoft.com/pcv/search)
