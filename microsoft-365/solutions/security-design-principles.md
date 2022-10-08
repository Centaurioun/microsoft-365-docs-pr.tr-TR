---
title: Microsoft 365 Kurumsal kaynak planlaması - Siber güvenlik mimarisi
description: Microsoft'un Siber Güvenlik Mimarı Kozeta Garrett'tan Microsoft Kurumsal mimarisindeki güvenlik güçlüklerinin nasıl aşılacağını öğrenin.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-identity-device-management
- M365-security-compliance
- M365solutions
ms.custom: seo-marvel-jun2020
f1.keywords: NOCSH
ms.openlocfilehash: aefce57eb633f028768ee5a4a2ae8591e6dc9c13
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67983134"
---
# <a name="security-hurdles-you-can-sail-overone-architects-viewpoint"></a>Üzerinden geçiş yapabileceğiniz güvenlik engelleri— Bir mimara bakış açısı

Bu makalede, Microsoft'ta Siber Güvenlik Mimarı [Kozeta Garrett](https://www.linkedin.com/in/kozeta-garrett-53013a6/), kurumsal kuruluşlarda karşılaştığı en önemli güvenlik zorluklarını açıklar ve bu engelleri aşmak için yaklaşımlar önerir.

## <a name="about-the-author"></a>Yazar hakkında

![Kozeta Garrett fotoğrafı.](../media/solutions-architecture-center/kozeta-garrett-security.jpg)

Bulut Güvenliği Mimarı rolümde, Microsoft 365 ve Azure'a geçiş yapmış müşteriler için güvenlik mimarisi tasarlamaya ve uygulamaya odaklanan stratejik ve teknik rehberlik sağlamak, kurumsal güvenlik çözümleri geliştirmek ve iş dayanıklılığı için güvenlik mimarisini ve kültürünü dönüştürmeye yardımcı olmak için birden çok kuruluşla birlikte çalıştım. Deneyimim arasında olay algılama ve yanıt, kötü amaçlı yazılım analizi, sızma testi ve BT güvenliği ve savunma duruşuna yönelik iyileştirmeler öneriliyor. Modernleştirme çalışmaları da dahil olmak üzere işletme için bir etkinleştirici olarak güvenliğin neden olduğu dönüşümlerin öncüleri konusunda tutkuluyum.

Son birkaç yıl içinde güvenlik modernleştirme anlayışını benimseyen kuruluşların son COVID-19 durumuna rağmen güvenli bir şekilde uzaktan çalışmaya devam etmelerine olanak sağlayan harika bir konumda olduğunu görmek en tatmin edici olmuştur. Ne yazık ki bu koşullar, bu acil ihtiyaç için hazır olmayan bazı müşteriler için uyandırma çağrısı olarak da hizmet vermektedir. Birçok kuruluş, bu son derece olağan dışı koşullarda çalışabilmeleri için hızlı bir şekilde modernleştirmeleri, birikmiş BT güvenlik borçlarını devre dışı bırakmaları ve güvenlik duruşlarını bir gecede geliştirmeleri gerektiğini fark ediyor.

İyi haber, Microsoft'un kuruluşların güvenlik duruşlarını hızla artırmalarına yardımcı olmak için harika kaynaklar sunmuş olmasıdır. Bu kaynaklara ek olarak, bu engelleri aşmanız umuduyla her gün müşterilerle karşılaştığım en önemli zorlukları paylaşmak istiyorum.

Şu anda Kuzey Virginia'da, ülkemizin başkenti Washington DC'ye yakın bir bölgede yaşıyorum. Koşu, bisiklet, yürüyüş ve yüzme gibi açık hava etkinliklerinin ve egzersizlerin hemen her biçimini seviyorum. Bunlara karşı koymak için yemek pişirmeyi, gurme yemeği ve seyahati seviyorum.

## <a name="partner-with-the-security-team-from-the-start-of-cloud-adoption"></a>Bulut benimsemesinin başlangıcından itibaren Güvenlik ekibiyle iş ortağı olun

Başlamak için, kuruluşunuzdaki ekiplerin başlangıçtan itibaren koordine etmelerinin ne kadar önemli olduğunu yeterince vurgulamıyorum. Güvenlik ekipleri, bulut benimseme ve tasarımının ilk aşamalarında kritik iş ortakları olarak benimsenmelidir. Bu, yalnızca işletmeye eklenen özellikler (güvenli mobil cihazlardan harika bir kullanıcı deneyimi, tam işlevsellik uygulamaları veya sınırlı işlevsellik e-postası ve üretkenlik uygulamalarının ötesinde kurumsal verilerde değer oluşturmak gibi) için değil, aynı zamanda yeni ve eski güvenlik güçlüklerinin çözülmesine yardımcı olan depolama, yapay zeka ve bilgi işlem analizi özelliklerinden yararlanmak için güvenlik ekiplerinin bulut benimsemesini desteklemek anlamına gelir. Güvenlik ekiplerinin başarılı olması için kişiler (kültür), süreçler (eğitim) ve teknoloji dahil olmak üzere bu vardiyanın tüm yönlerini yönetmeye dahil edilmesi gerekir. Ayrıca Güvenlik Operasyonları Merkezi'nin (SOC) modernizasyonuna ve sürekli geliştirilmesine yatırım yapmak anlamına gelir. Dijital dönüşümün güvenli bir şekilde yapıldığından emin olmak için güvenlik stratejinizi iş stratejinizle ve ortam eğilimlerinizle uyumlu hale getirmek için birlikte çalışın. Bu iyi yapıldığında kuruluşlar, iş, BT ve güvenlik değişiklikleri dahil olmak üzere değişikliklere daha hızlı uyum sağlama yeteneği geliştirir.

Müşterilerin engelleri aşmalarını en çok gördüğüm yer, operasyonlar ile SOC ekipleri arasında gerçek bir ortaklık olmamasıdır. Operasyon ekibi, bulutu benimsemek için zorlayıcı son tarihlerle zorlanır ve zorunlu tutulurken, güvenlik ekipleri her zaman kapsamlı bir güvenlik stratejisini gözden geçirme ve planlama sürecine erken dahil değildir. Bu, şirket içinde farklı bulut bileşenlerini ve bileşenlerini tümleştirmeyi içerir. Bu ortaklık eksikliği, belirli bileşenlerine yönelik denetimleri uygulamak için silolarda çalışan farklı ekiplere daha da zorlayarak uygulama, sorun giderme ve tümleştirmenin karmaşıklığının artmasına neden olur.

Bu engelleri aşan müşteriler, hibrit bulut iş yüklerini korumaya yönelik güvenlik stratejisini ve gereksinimlerini yenilemek için Operasyonlar ve İdare ile Güvenlik ve Risk yönetimi ekipleri arasında iyi ortaklıklara sahiptir. Siber güvenlik idaresi, risk ve uyumluluk gereksinimlerine uygun olarak veri koruma ve sistemler ve hizmetlerin kullanılabilirliği gibi nihai güvenlik hedeflerine ve sonuçlarına lazerle odaklanır. Bu kuruluşlar, Operasyon ve İdare ekibi ile SOC arasında güvenlik tasarımı yaklaşımı açısından kritik öneme sahip olan ve yatırımlarının değerini en üst düzeye çıkaracak erken aşama ortaklıklar geliştirmektedir.

## <a name="build-a-modern-identity-based-security-perimeter"></a>Modern (kimlik tabanlı) bir güvenlik çevresi oluşturma

Ardından, Sıfır Güven mimarisi yaklaşımını benimseyin. Bu, modern, kimlik tabanlı bir güvenlik çevresi oluşturmakla başlar. İster şirket içi ister bulut olsun, her erişim girişiminin doğrulanana kadar güvenilmeyen olarak kabul edildiği güvenlik mimarisini tasarlayın; "asla güvenme, her zaman doğrula." Bu tasarım yaklaşımı yalnızca güvenliği ve üretkenliği artırmakla kalmaz, aynı zamanda kullanıcıların herhangi bir cihaz türüyle her yerden çalışmasına da olanak tanır. Microsoft 365'te bulunan gelişmiş bulut denetimleri, kullanıcı risk düzeyine göre değerli kaynaklara erişimi denetlerken kullanıcıların kimliklerini korumanıza yardımcı olur.

Önerilen yapılandırma için bkz. [Kimlik ve cihaz erişim yapılandırmaları](../security/office-365-security/microsoft-365-policies-configurations.md).

## <a name="transition-security-controls-to-the-cloud"></a>Güvenlik denetimlerini buluta geçiş

Birçok güvenlik ekibi, "ağ çevre güvenliğini" korumak ve şirket içi güvenlik araçlarını ve denetimlerini bulut çözümlerine "zorlamak" da dahil olmak üzere tüm şirket içi dünya için oluşturulan geleneksel en iyi güvenlik uygulamalarını kullanmaya devam etmektedir. Bu tür denetimler bulut için tasarlanmamıştır, etkisizdir ve modern bulut özelliklerinin benimsenmesini engeller. Ağ çevresi güvenlik yaklaşımı için çalışan süreçler ve araçların verimsiz, bulut özelliklerine engel olduğu kanıtlanmıştır ve modern ve otomatik güvenlik özelliklerinden yararlanmaya izin vermez.

Savunma stratejilerini bulut tarafından yönetilen koruma, otomatik araştırma ve düzeltme, otomatik kalem testi, Office 365 için Defender ve olay analizine geçirerek bu engeli aşabilirsiniz. Modern cihaz yönetimi çözümleri kullanan müşteriler tüm cihazlarda (akıllı telefon, kişisel bilgisayar, dizüstü bilgisayar veya tablet) otomatik yönetim, standart yama uygulama, virüsten koruma, ilke uygulama ve uygulama koruması uygulamışlardır. Bu, VPN, Microsoft System Center Configuration Manager (SCCM) ve Active Directory grup ilkeleri gereksinimini ortadan kaldırır. Bu, koşullu erişim ilkeleriyle birlikte güçlü denetim ve görünürlüğün yanı sıra kullanıcılarının nerede çalıştığına bakılmaksızın kaynaklara kolay erişim sağlar.

## <a name="strive-for-best-together-security-tools"></a>'Birlikte en iyi' güvenlik araçları için çabalayın

Müşterilerin tökezlediğini gördüğüm bir diğer engel de güvenlik araçlarına "türünün en iyisi" yaklaşımını kullanmak. Yeni ortaya çıkan güvenlik gereksinimlerini karşılamak için sürekli olarak 'en iyi tür' noktası çözümlerinin katmanlanması kurumsal güvenliğin bozulmasına neden olur. En iyi niyetle bile, çoğu ortamdaki araçlar çok pahalı ve karmaşık hale geldiği için tümleştirilemez. Bu da ekibin kaldırabileceğinden daha fazla önceliklendirme uyarısı olduğundan görünürlükte boşluklar oluşturur. SecOps ekibini yeni araçlar üzerinde yeniden eğitme de sürekli bir zorluk haline gelir.

'Basit daha iyidir' yaklaşımı da güvenlik için çalışır. 'En iyi cins' araçların peşinden gitmek yerine, varsayılan olarak birlikte çalışan araçlarla 'birlikte en iyi' stratejisini benimseyerek bu engelin üzerinden geçin. Microsoft güvenlik özellikleri uygulamaları, kullanıcıları ve bulutları kapsayan tümleşik tehdit koruması ile kuruluşunuzun tamamını korur. Tümleştirme, bir kuruluşun girişte saldırganları içererek ve saldırıları hızla düzelterek daha dayanıklı olmasını ve riski azaltmasını sağlar.

## <a name="balance-security-with-functionality"></a>İşlevsellikle güvenliği dengeleme

Uzun bir siber güvenlik geçmişinden ve deneyiminden geldikçe, en güvenli yapılandırmayla başlamayı ve kuruluşların operasyonel ve güvenlik gereksinimlerine göre güvenlik yapılandırmalarını gevşetmelerine izin verme eğilimindeyim. Ancak bu, kayıp işlevselliğin ve kötü kullanıcı deneyiminin ağır bir fiyatına gelebilir. Birçok kuruluşun öğrendiği gibi, güvenlik kullanıcılar için çok zorsa, yönetilmeyen bulut hizmetlerini kullanmak da dahil olmak üzere sizin için bir çözüm yolu bulur. Kabul etmek ne kadar zor olsa da, hassas işlevsellik-güvenlik dengesinin sağlanması gerektiğini fark ettim.

Kullanıcıların işlerini yapmak için ne gerekiyorsa yapacağını fark eden kuruluşlar, "Gölge BT savaşının" mücadele etmeye değdiğini kabul eder. İş Gölge BT ve işleri için onaylanmamış SaaS uygulamalarının kullanımı söz konusu olduğunda EN büyük suçluların BT çalışanları olduğunu fark ediyorlar. Bu kişiler, kullanımını teşvik etmek için (gizleme yerine) stratejilerini kaydırdı ve yaratabileceği riskleri azaltmaya odaklandı. Bu kuruluşun güvenlik ekipleri her şeyin engellenmesi, günlüğe kaydedilmesi ve ters ara sunucu veya VPN üzerinden gönderilmesinde ısrar etmez. Bunun yerine, bu güvenlik ekipleri değerli ve hassas verilerin yanlış taraflara veya kötü amaçlı uygulamalara maruz kalmalarını engelleme çabalarını ikiye katlar. Verilerin bütünlüğünü korumak için çalışır. Şifreleme, güvenli çok faktörlü kimlik doğrulaması, otomatik risk ve uyumluluk ve bulut erişim güvenlik aracısı (CASB) özellikleri dahil olmak üzere daha gelişmiş bulut bilgi koruma özelliklerinden tam olarak yararlanırken, birden çok platformda korumalı paylaşıma izin verir ve hatta teşvik eder. Gölge BT'yi yaratıcılığa, üretkenliğe ve işbirliğine dönüştürerek işlerinin rekabet avantajından uzak durmasını sağlıyorlar.

## <a name="adopt-a-methodical-approach"></a>Yöntemsel bir yaklaşımı benimseme

Sektörden bağımsız olarak farklı kuruluşlarda bulut güvenliğini uygulama konusunda karşılaştığım zorlukların çoğu birbirine çok benzerdi. Her şeyden önce, belirli özellikler ve özelliklerle ilgili birçok harika belge olsa da, kuruluş düzeyinde bunlar için nelerin geçerli olduğu, güvenlik özelliklerinin nerede çakıştığı ve özelliklerin nasıl tümleştirilmesi gerektiği konusunda bir karışıklık düzeyi vardır. Ayrıca, hangi güvenlik özelliklerinin kullanıma hazır olarak yapılandırıldığı ve kuruluş tarafından yapılandırılmasını gerektiren bir belirsizlik düzeyi de vardır. Buna ek olarak, SOC ekipleri ne yazık ki kuruluşlarının zaten geçmekte olduğu hızlı bulut benimseme ve dijital dönüşüme hazırlanmak için gereken tam açığa çıkarma, eğitim veya bütçe ayırma işlemine sahip değil.

Microsoft, bu engelleri temizlemenize yardımcı olmak için güvenlik stratejinize ve uygulamanıza yöntemli bir yaklaşım benimsemenize yardımcı olmak için tasarlanmış çeşitli kaynaklar seçkisi oluşturmuştur.

|Kaynak   |Daha fazla bilgi  |
|---------|---------|
|[Güvenlik ekiplerinin evden çalışmayı desteklemesi için en önemli görevler](../security/top-security-tasks-for-remote-work.md)      | Kendinizi aniden çoğunlukla evde çalışan bir iş gücünü desteklerken bulursanız, bu makale güvenliği hızla artırmanıza yardımcı olur. Lisanslama planınıza göre önerilen en önemli görevleri içerir.    |
|[Microsoft 365 Sıfır Güven dağıtım planı](../security/microsoft-365-zero-trust.md)    | Bu makalede, Microsoft 365 ile Sıfır Güven güvenliği oluşturmaya yönelik bir dağıtım planı sağlanmaktadır. İlerleme durumunuzu izlemek için kullanabileceğiniz indirilebilir bir poster içerir. |
|[Sıfır Güven Rehberlik Merkezi](/security/zero-trust/)  | Sıfır Güven güvenlik modeli, ilkeleri ve dağıtım planlarını kullanarak Sıfır Güven mimarisini uygulama hakkında bilgi edinin. |
|[docs.security.com/security](/security/)    | Güvenlik stratejisi ve mimarisi için Microsoft genelinde teknik rehberlik.        |
| | |

Bu kaynakların tümü başlangıç noktası olarak kullanılacak ve kuruluşunuzun ihtiyaçlarına uyarlanacak şekilde tasarlanmıştır.
