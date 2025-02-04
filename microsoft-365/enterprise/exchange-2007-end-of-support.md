---
title: Exchange 2007 end of support roadmap
ms.author: dstrome
author: dstrome
manager: scotv
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- Ent_O365
ms.assetid: c3024358-326b-404e-9fe6-b618e54d977d
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: Exchange Server 2007 desteği sona erdikten sonra seçenekleriniz hakkında bilgi edinin ve Microsoft 365, Office 365 veya Exchange 2016'ya geçişi planlamaya başlayın.
ms.openlocfilehash: 2e8b25e016d5b0040938586e75f3536bb8609cd6
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68185501"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Exchange 2007 end of support roadmap

*Bu makale hem Microsoft 365 Kurumsal hem de Office 365 Kurumsal için geçerlidir.*

Exchange Server 2007, Nisan 2017'de destek sonuna ulaşmıştır. Exchange 2007'den Microsoft 365, Office 365 veya Exchange 2016'ya geçiş işlemini başlatmadıysanız, şimdi planlamaya başlamanın tam zamanı.

## <a name="what-does-end-of-support-mean"></a>*Destek sonu* ne anlama gelir?

neredeyse tüm Microsoft ürünleri gibi Exchange Server de yeni özellikler, hata düzeltmeleri, güvenlik düzeltmeleri vb. sağladığımız bir destek yaşam döngüsüne sahiptir. Bu yaşam döngüsü genellikle ürünün ilk sürümünden itibaren 10 yıl sürer. Bu yaşam döngüsünün sonu, ürünün destek sonu olarak bilinir. Exchange 2007, 11 Nisan 2017'de destek sonuna ulaştığından, Microsoft artık şunları sağlamamaktadır:

- Oluşabilecek sorunlar için teknik destek.

- Sunucunun kararlılığını ve kullanılabilirliğini etkileyebilecek sorunlar için hata düzeltmeleri.

- Sunucuyu güvenlik ihlallerine açık hale getirebilecek güvenlik açıklarına yönelik güvenlik düzeltmeleri.

- Saat dilimi güncelleştirmeleri.

Exchange 2007 yüklemeniz destek sonu tarihinden sonra çalışmaya devam edecektir. Ancak yeni güncelleştirmeler veya destek olmadığından, exchange 2007'den en kısa sürede geçmenizi kesinlikle öneririz.

Destek sonuna yakın Office 2007 sunucuları hakkında daha fazla bilgi için bkz. [Office 2007 sunucularından ve ürünlerinden yükseltmenizi planlama](upgrade-from-office-2007-servers-and-products.md).

## <a name="what-are-my-options"></a>Seçeneklerim nelerdir?

Şunları yapabilirsiniz:

- Tam geçiş, aşamalı veya karma geçiş kullanarak Microsoft 365'e geçiş.

- Exchange 2007 sunucularınızı şirket içi sunucularınızda Exchange'in daha yeni bir sürümüne geçirin.

Aşağıdaki bölümlerde her bir seçenek daha ayrıntılı olarak incelanmıştır.

### <a name="migrate-to-microsoft-365"></a>Microsoft 365'e geçiş

E-postanızı Microsoft 365'e geçirmek, Exchange 2007 dağıtımınızı devre dışı bırakmanıza yardımcı olacak en iyi ve en basit seçenektir. Microsoft 365'e geçişle, 10 yıllık teknolojiden aşağıdakiler gibi en yeni özelliklere tek bir atlama yapabilirsiniz:

- Bekletme İlkeleri, In-Place ve Dava Tutma, yerinde eBulma ve daha fazlası gibi uyumluluk özellikleri

- Microsoft 365 Grupları

- Odaklanmış Gelen Kutusu

- MyAnalytics

- E-postaya, takvimlere, kişilere vb. program aracılığıyla erişim için REST API'leri

Microsoft 365 ayrıca ilk olarak yeni özellikler ve deneyimler alır, böylece siz ve kullanıcılarınız bunları genellikle hemen kullanmaya başlayabilirsiniz. Ayrıca şu konularda endişelenmeniz gerekmez:

- Donanım satın alma ve bakım.

- Sunucularınızı ısıtmak ve soğutmak için ödeme.

- Güvenlik, ürün ve saat dilimi düzeltmeleri hakkında güncel kalma.

- Uyumluluk gereksinimlerini desteklemek için depolama ve yazılımları koruma.

- Exchange'in yeni bir sürümüne yükseltme. Microsoft 365 ile her zaman Exchange'in en son sürümündesiniz.

#### <a name="how-should-i-migrate-to-microsoft-365"></a>Microsoft 365'e nasıl geçiş yapmalıyım?

Birkaç geçiş seçeneğiniz vardır. Aşağıdakiler de dahil olmak üzere birkaç şeyi göz önünde bulundurmanız gerekir:

- Taşımanız gereken koltuk veya posta kutularının sayısı.
- Geçişin ne kadar sürmesini istediğiniz.
- Geçiş sırasında şirket içi yüklemenizle Microsoft 365 arasında sorunsuz tümleştirmeye ihtiyacınız olup olmadığı.

Bu tablo, geçiş seçeneklerinizi ve hangi yöntemin kullanılacağını belirleyen en önemli faktörleri gösterir:

|Geçiş seçeneği|Kuruluş boyutu|Süre|
|---|---|---|
|Tam geçiş|150'den az koltuk|Bir hafta veya daha az|
|Aşamalı geçiş|150'den fazla koltuk|Birkaç hafta|
|Tam karma geçiş|Birkaç yüz binlerce koltuk|Birkaç ay veya daha fazla|

Aşağıdaki bölümlerde bu yöntemlere genel bir bakış sağlanır. Daha fazla ayrıntı için bkz. [Geçiş yoluna karar verme](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27).

#### <a name="cutover-migration"></a>Tam geçiş

Tam geçişte tüm posta kutularınızı, dağıtım gruplarınızı, kişilerinizi vb. önceden seçilmiş bir tarih ve saatte Microsoft 365'e geçirirsiniz. Geçiş tamamlandıktan sonra şirket içi Exchange sunucularınızı kapatır ve yalnızca Microsoft 365'i kullanmaya başlarsınız.

Tam geçiş, çok fazla posta kutusu olmayan, Microsoft 365'e hızlı bir şekilde ulaşmak isteyen ve diğer yöntemlerin bazı karmaşıklıklarıyla uğraşmak istemeyen küçük kuruluşlar için harikadır. Ancak bir hafta veya daha kısa bir süre içinde tamamlanmalıdır ve kullanıcıların Outlook profillerini yeniden yapılandırması gerekir. Tam geçiş en fazla 2.000 posta kutusunu işleyebilir, ancak en fazla 150 posta kutusunu geçirmek için bunu kullanmanızı kesinlikle öneririz. Daha fazla geçiş yapmaya çalışırsanız, son teslim tarihinizden önce tüm posta kutularını aktarmak için zamanınız tükenebilir ve BT destek personeliniz kullanıcıların Outlook'u yeniden yapılandırmasına yardımcı olmak için isteklere boğulabilir.

Tam geçiş yapmayı düşünüyorsanız göz önünde bulundurmanız gerekenler şunlardır:

- Microsoft 365'in 443 numaralı TCP bağlantı noktası üzerinden Outlook Anywhere kullanarak Exchange 2007 sunucularınıza bağlanması gerekir.

- Tüm şirket içi posta kutuları Microsoft 365'e taşınacaktır.

- Kullanıcılarınızın posta kutularına okuma erişimi olan bir şirket içi yönetici hesabınız olmalıdır.

- Microsoft 365'te kullanmak istediğiniz Exchange 2007 kabul edilen etki alanlarının hizmete doğrulanmış etki alanları olarak eklenmesi gerekir.

- Geçişi başlattığınızda ve tamamlama aşamasına başladığınızda Microsoft 365, Microsoft 365 ve şirket içi posta kutularını düzenli aralıklarla eşitler. Bu, şirket içi posta kutularınızda e-postanın geride bırakılması konusunda endişelenmeden geçişi tamamlamanıza olanak tanır.

- Kullanıcılar Microsoft 365 hesapları için yeni geçici parolalar alır. Posta kutularında ilk kez oturum açtıklarında parolalarını değiştirmeleri gerekir.

- Geçiş yaptığınız her kullanıcı posta kutusu için Exchange Online içeren bir Microsoft 365 lisansına sahip olmanız gerekir.

- Kullanıcıların cihazlarının her birinde yeni bir Outlook profili ayarlamaları ve e-postalarını yeniden indirmeleri gerekir. Outlook'un indireceği e-posta miktarı farklılık gösterebilir. Daha fazla bilgi için bkz. [Çevrimdışı tutulacak posta miktarını değiştirme](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).

Tam geçiş hakkında daha fazla bilgi için bkz:

- [Tam e-posta geçişi hakkında bilmeniz gerekenler](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)

- [E-postanın tam geçişini gerçekleştirme](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)

#### <a name="staged-migration"></a>Aşamalı geçiş

Aşamalı geçişte, Microsoft 365'e geçirmek istediğiniz birkaç yüz veya birkaç bin posta kutunuz vardır, geçişi tamamlamak için bir hafta veya daha uzun sürmesi gerekir ve paylaşılan Serbest/Meşgul takvim bilgileri gibi gelişmiş karma geçiş özelliklerine ihtiyacınız yoktur.

Aşamalı geçiş, posta kutularını Microsoft 365'e geçirmek için daha fazla zaman alması gereken ancak birkaç hafta içinde geçişi tamamlamayı planlayan kuruluşlar için idealdir. Posta kutularını toplu olarak geçirebilirsiniz. Belirli bir anda kaç posta kutusunun ve hangi posta kutularının geçirileceğini siz denetlersiniz. Örneğin, aynı departmandaki kullanıcıların posta kutularının tümünün aynı anda taşındığından emin olmak için toplu işlem gerçekleştirebilirsiniz. Ya da son toplu iş tarihine kadar yönetici posta kutularını bırakabilirsiniz. Tam geçişlerde olduğu gibi, kullanıcılarınızın Outlook profillerini yeniden oluşturması gerekir.

Aşamalı geçiş yapmayı düşünüyorsanız göz önünde bulundurmanız gerekenler şunlardır:

- Microsoft 365'in 443 numaralı TCP bağlantı noktası üzerinden Outlook Anywhere kullanarak Exchange 2007 sunucularınıza bağlanması gerekir.

- Kullanıcılarınızın posta kutularına okuma erişimi olan bir şirket içi yönetici hesabınız olmalıdır.

- Microsoft 365'te kullanmayı planladığınız Exchange 2007 kabul edilen etki alanlarının hizmete doğrulanmış etki alanları olarak eklenmesi gerekir.

- Toplu olarak geçirmeyi planladığınız her posta kutusunun tam adını ve e-posta adresini içeren bir CSV dosyası oluşturmanız gerekir. Ayrıca, geçirmekte olduğunuz her posta kutusu için yeni bir parola eklemeniz ve bu parolayı her kullanıcıya göndermeniz gerekir. Kullanıcıdan yeni Microsoft 365 posta kutusunda ilk kez oturum açarken parolayı değiştirmesi istenir.

- Geçiş toplu işlemini başlattığınızda ve tamamlama aşamasına başladığınızda, Microsoft 365 toplu işe dahil edilen Microsoft 365 ve şirket içi posta kutularını düzenli aralıklarla eşitler. Bu, şirket içi posta kutularınızda e-postanın geride bırakılması konusunda endişelenmeden geçişi tamamlamanıza olanak tanır.

- Geçiş yaptığınız her kullanıcı posta kutusu için Exchange Online içeren bir Microsoft 365 lisansına sahip olmanız gerekir.

- Kullanıcıların cihazlarının her birinde yeni bir Outlook profili ayarlamaları ve e-postalarını yeniden indirmeleri gerekir. Outlook'un indireceği e-posta miktarı farklılık gösterebilir. Daha fazla bilgi için bkz. [Çevrimdışı tutulacak posta miktarını değiştirme](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).

Aşamalı geçiş hakkında daha fazla bilgi için bkz:

- [Aşamalı e-posta geçişi hakkında bilmeniz gerekenler](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)

- [E-postanın aşamalı geçişini gerçekleştirme](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)

#### <a name="full-hybrid"></a>Tam karma

Tam karma geçişte, kuruluşunuzun yüzlerce, on binlerce posta kutusu vardır ve bunların bir kısmını veya tümünü Microsoft 365'e taşımak istiyorsunuz. Bu geçişler genellikle daha uzun süreli olduğundan karma geçişler şunları mümkün hale getirir:

- Şirket içi kullanıcılara Microsoft 365'teki kullanıcılar için serbest/meşgul takvim bilgilerini (veya tam tersini) gösterin.

- Hem şirket içinde hem de Microsoft 365'te alıcıları içeren birleşik bir genel adres listesine bakın.

- İster şirket içinde ister Microsoft 365'te olsun, tüm kullanıcılar için tam Outlook alıcı özelliklerini görüntüleyin.

- TLS ve sertifikalar kullanarak şirket içi Exchange sunucuları ile Microsoft 365 arasında güvenli e-posta iletişimi.

- Şirket içi Exchange sunucuları ile Microsoft 365 arasında gönderilen iletileri dahili olarak değerlendirerek şunların gerçeklestirilmesini sağlayın:

  - İç iletileri hedefleyen aktarım ve uyumluluk aracıları tarafından düzgün bir şekilde değerlendirilip işlenebilir.

  - İstenmeyen posta önleme filtrelerini atla.

Tam karma geçiş, hibrit yapılandırmada uzun aylar veya daha uzun süre kalmayı bekleyen kuruluşlar için en iyisidir. Bu bölümün önceki bölümlerinde listelenen özelliklerin yanı sıra dizin eşitlemesi, daha iyi tümleşik uyumluluk özellikleri ve çevrimiçi posta kutusu taşımalarını kullanarak posta kutularını Microsoft 365'e ve Microsoft 365'ten taşıma özelliğini alacaksınız. Microsoft 365, şirket içi kuruluşunuzun bir uzantısı haline gelir.

Tam karma geçiş yapmayı düşünüyorsanız göz önünde bulundurmanız gerekenler şunlardır:

- Tam karma geçiş, tüm kuruluş türleri için uygun değildir. Tam karma geçişlerin karmaşıklığı nedeniyle, birkaç yüzden az posta kutusu olan kuruluşlar genellikle bir tane ayarlamak için gereken çabayı ve maliyeti haklı gösteren avantajlar görmez. Bu sizin kuruluşunuz gibi görünüyorsa, bunun yerine tam geçiş veya aşamalı geçiş yapmayı göz önünde bulundurmanızı öneririz.

- "Karma sunucu" olarak görev yapmak için Exchange 2007 kuruluşunuzda en az bir Exchange 2013 sunucusu dağıtmanız gerekir. Bu sunucu, Exchange 2007 sunucularınız adına Microsoft 365 ile iletişim kurar.

- Microsoft 365'in 443 numaralı TCP bağlantı noktası üzerinden Outlook Anywhere kullanarak "karma sunucuya" bağlanması gerekir.

- şirket içi Active Directory sunucularınız ile Microsoft 365 arasında Azure Active Directory (Azure AD) Connect kullanarak dizin eşitlemesi ayarlamanız gerekir.

- Kullanıcılar, microsoft 365 posta kutularında yerel ağda oturum açarken kullandıkları kullanıcı adı ve parolayı kullanarak oturum açabilecektir. (Bu işlev, parola eşitleme ve/veya Active Directory Federasyon Hizmetleri (AD FS) ile bağlanma Azure AD gerektirir.)

- Geçiş yaptığınız her kullanıcı posta kutusu için Exchange Online içeren bir Microsoft 365 lisansına sahip olmanız gerekir.

- Kullanıcıların cihazlarının çoğunda yeni bir Outlook profili ayarlamaları gerekmez, ancak bazı eski Android telefonlarda yeni bir profile ihtiyaç duyulabilir. Kullanıcıların e-postalarını yeniden indirmeleri gerekmez.

Tam karma geçiş sizin için uygunsa, geçişinize yardımcı olması için aşağıdaki kaynaklara bakın:

- [Exchange Dağıtım Yardımcısı](/exchange/exchange-deployment-assistant)

- [Karma Dağıtımları Exchange Server](/exchange/exchange-hybrid)

- [Karma Yapılandırma sihirbazı](/exchange/hybrid-configuration-wizard)

- [Karma Yapılandırma sihirbazı hakkında SSS](/exchange/hybrid-configuration-wizard-faqs)

- [Karma dağıtım önkoşulları](/exchange/hybrid-deployment-prerequisites)

### <a name="migrate-to-a-newer-version-of-exchange-server"></a>daha yeni bir Exchange Server sürümüne geçiş

Microsoft 365'e geçiş yaparak en iyi değere ve kullanıcı deneyimine ulaşabileceğinize kesinlikle inanıyoruz. Ancak bazı kuruluşların e-postalarını şirket içinde tutmaları gerektiğini de anlıyoruz. Bunun nedeni yasal gereksinimlerin, verilerin başka bir ülkede bulunan bir veri merkezinde depolanmadığından emin olmak veya benzer bir durum olabilir. E-postanızı şirket içinde tutmayı seçerseniz, Exchange 2007 ortamınızı Exchange 2010, Exchange 2013 veya Exchange 2016'ya geçirebilirsiniz.

Microsoft 365'e geçiş yapamazsanız, Exchange 2016'ya geçmenizi öneririz. Exchange 2016, Exchange'in önceki sürümlerinin tüm özelliklerini içerir. Bazı özellikler yalnızca Microsoft 365'te kullanılabilse de, microsoft 365 ile sunulan deneyimle de en yakından eşleşir. Kaçırdığınız şeylerden yalnızca birkaçını gözden geçirin:

|Exchange sürümü|Özellikler|
|---|---|
|Exchange 2010| Role-Based Access Control (ACL'ler olmadan izinler) <br/> posta kutusu ilkelerini Outlook Web App <br/> Kuruluşlar arasında serbest/meşgul ve temsilci takvimleri paylaşma olanağı|
|Exchange 2013| *Exchange 2010 ve ...* <br/> Sunucu rollerinin sayısını üçe indiren basitleştirilmiş mimari (Posta Kutusu, İstemci Erişimi, Edge Aktarımı) <br/> Hassas bilgilerin sızmasını önlemeye yardımcı olan veri kaybı önleme ilkeleri (DLP) <br/> geliştirilmiş Outlook Web App deneyimi|
|Exchange 2016| *Exchange 2013 ve ...* <br/> Yalnızca Posta Kutusu ve Edge Aktarım için daha basitleştirilmiş sunucu rolleri <br/> SharePoint ile tümleştirme ile birlikte geliştirilmiş DLP <br/> Geliştirilmiş veritabanı dayanıklılığı <br/> Çevrimiçi belge işbirliği|

#### <a name="which-version-should-i-migrate-to"></a>Hangi sürüme geçiş yapmalıyım?

Başlangıçta Exchange 2016'ya geçiş yapacağınızı varsaymanızı öneririz. Ardından aşağıdaki bilgileri kullanarak varsayımınızı onaylayın veya Exchange 2016'yı eleyin. Bir nedenden dolayı Exchange 2016'ya geçiş yapamazsanız, exchange 2013 ile aynı işlemi vb. yapın.

|Dikkate|Daha Fazla Bilgi|
|---|---|
|Destek sonu tarihleri| Exchange 2007'de olduğu gibi, Exchange'in her sürümünün de kendi destek sonu tarihi vardır: <br/> *Exchange 2010* - Ocak 2020 <br/> *Exchange 2013* - Nisan 2023 <br/> *Exchange 2016* - Ekim 2025 <br/> Destek ne kadar erken sona ererse, o kadar erken başka bir geçiş gerçekleştirmeniz gerekir.|
|Exchange 2010 ve 2013'e geçiş yolu.|Exchange 2010 veya Exchange 2013'e geçiş için genel aşamalar şunlardır: <br/> - Exchange 2010 veya 2013'ü mevcut Exchange 2007 kuruluşunuza yükleyin. <br/>- Hizmetleri ve diğer altyapıyı Exchange 2010 veya 2013'e taşıyın.<br/>- Posta kutularını ve ortak klasörleri Exchange 2010 veya 2013'e taşıyın.<br/>- Kalan Exchange 2007 sunucularının yetkisini alın.|
|Exchange 2016'ya geçiş yolu|Exchange 2016'ya geçiş için genel aşamalar şunlardır: <br/> - Exchange 2013'ü mevcut Exchange 2007 kuruluşunuza yükleyin.<br/>- Hizmetleri ve diğer altyapıyı Exchange 2013'e taşıyın.<br/>- Posta kutularını ve ortak klasörleri Exchange 2013'e taşıyın.<br/>- Kalan Exchange 2007 sunucularının yetkisini alın.<br/>- Exchange 2016'yi mevcut Exchange 2013 kuruluşunuza yükleyin.<br/>- Posta kutularını, ortak klasörleri, hizmetleri ve diğer altyapıyı Exchange 2016'ya taşıyın (sıra önemli değildir). Kalan Exchange 2013 sunucularının yetkisini alın.<br/><br/> **Not:** Exchange 2013'ten Exchange 2016'ya geçiş basittir. İki sürüm neredeyse aynı donanım gereksinimlerine sahiptir ve bu sürümler çok uyumludur. Böylece Exchange 2013 için satın aldığınız bir sunucuyu yeniden derleyebilir ve üzerine Exchange 2016 yükleyebilirsiniz. Çevrimiçi posta kutusu taşıma işlemleri için kullanıcıların çoğu posta kutularının sunucudan taşındığını ve siz Exchange 2016 ile yeniden derledikten sonra geri döndüğünü fark etmez.|
|Sürüm bir arada bulunma| Geçiş sırasında ... <br/> **Exchange 2016:** Exchange 2016, Exchange 2007 sunucusu içeren bir kuruluşa yüklenemez. Öncelikle Exchange 2010 veya 2013'e geçmeniz (Kesinlikle Exchange 2013'e öneririz), tüm Exchange 2007 sunucularını kaldırmanız ve ardından Exchange 2016'ya geçmeniz gerekir. <br/> **Exchange 2010 veya Exchange 2013:** Exchange 2010 veya Exchange 2013'ü var olan bir Exchange 2007 kuruluşuna yükleyebilirsiniz. Bu, bir veya daha fazla Exchange 2010 veya 2013 sunucusu yüklemenizi ve geçişinizi gerçekleştirmenizi sağlar.|
|Sunucu donanımı| Sunucu donanım gereksinimleri Exchange 2007'den değiştirildi. Donanımınızın uyumlu olduğundan emin olun. Ayrıntılar için bkz: <br/> [Exchange 2016 Sistem Gereksinimleri](/Exchange/plan-and-deploy/system-requirements) <br/> [Exchange 2013 Sistem Gereksinimleri](/exchange/exchange-2013-system-requirements-exchange-2013-help) <br/> [Exchange 2010 Sistem Gereksinimleri](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141)) <br/> Exchange performansındaki önemli iyileştirmelerin yanı sıra daha yeni sunuculardaki artan bilgi işlem gücü ve depolama kapasitesinin aynı sayıda posta kutusunu desteklemek için büyük olasılıkla daha az sunucuya ihtiyacınız olduğunu göreceksiniz.|
|İşletim sistemi sürümü| Her sürüm için desteklenen en düşük işletim sistemi sürümleri şunlardır: <br/> **Exchange 2016** - Windows Server 2012 <br/> **Exchange 2013** - Windows Server 2008 R2 SP1 <br/> **Exchange 2010** - Windows Server 2008 SP2 <br/> [Exchange Desteklenebilirlik Matrisi'nde](/Exchange/plan-and-deploy/supportability-matrix) işletim sistemi desteği hakkında daha fazla bilgi bulabilirsiniz.|
|Active Directory ormanı işlev düzeyi| Her sürüm için desteklenen en düşük Active Directory ormanı işlev düzeyleri şunlardır: <br/> **Exchange 2016** Windows Server 2008 R2 SP1 <br/> **Exchange 2013** Windows Server 2003 <br/> **Exchange 2010** Windows Server 2003 <br/> Orman işlev düzeyi desteği hakkında daha fazla bilgiyi [Exchange Desteklenebilirlik Matrisi'nde](/Exchange/plan-and-deploy/supportability-matrix) bulabilirsiniz.|
|Office istemci sürümleri| Her sürüm için desteklenen en düşük Office istemci sürümleri şunlardır: <br/> **Exchange 2016** - Office 2010 (en son güncelleştirmelerle) <br/> **Exchange 2013** - Office 2007 SP3 <br/> **Exchange 2010** - Office 2003 <br/> Office istemci desteği hakkında daha fazla bilgiyi [Exchange Desteklenebilirlik Matrisi'nde](/Exchange/plan-and-deploy/supportability-matrix) bulabilirsiniz.|

#### <a name="how-do-i-migrate"></a>Geçiş Nasıl yaparım??

E-postanızı şirket içinde tutmaya karar verdiyseniz geçişinize yardımcı olması için aşağıdaki kaynakları kullanın:

- [Exchange Dağıtım Yardımcısı](/exchange/exchange-deployment-assistant)

- Exchange [2016, 2013](/Exchange/plan-and-deploy/active-directory/ad-schema-changes), [2010](/exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help) için Active Directory [](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401) şema değişiklikleri

- Exchange [2016, 2013](/Exchange/plan-and-deploy/system-requirements), [2010](/exchange/exchange-2013-system-requirements-exchange-2013-help) için [](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141)) sistem gereksinimleri

- Exchange [2016, 2013](/Exchange/plan-and-deploy/prerequisites), [2010](/previous-versions/office/exchange-server-2010/bb691354(v=exchg.141)) önkoşulları [](/exchange/exchange-2013-prerequisites-exchange-2013-help)

## <a name="get-help"></a>Yardım alın

Microsoft 365'e geçiş gerçekleştiriyorsanız Microsoft FastTrack hizmetimizi kullanmaya uygun olabilirsiniz. FastTrack, Microsoft 365'e geçişinizi mümkün olduğunca sorunsuz hale getirmek için en iyi yöntemleri, araçları ve kaynakları sağlar. En iyisi, bir destek mühendisi, planlama ve tasarımdan son posta kutunuzu geçirmeye kadar geçişinizde size yol gösterir. FastTrack hakkında daha fazla bilgi için bkz. [Microsoft FastTrack](https://fasttrack.microsoft.com/).

Microsoft 365'e geçişiniz sırasında sorunlarla karşılaşırsanız ve FastTrack kullanmıyorsanız veya daha yeni bir Exchange Server sürümüne geçiş işleminizde size yardımcı olmak için buradayız. Kullanabileceğiniz bazı kaynaklar şunlardır:

- [Teknik topluluk](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)

- [Müşteri desteği](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-topics"></a>İlgili konular

[Office 2007 sunucularınızı ve istemcilerinizi yükseltmenize yardımcı olacak kaynaklar](upgrade-from-office-2007-servers-and-products.md)
