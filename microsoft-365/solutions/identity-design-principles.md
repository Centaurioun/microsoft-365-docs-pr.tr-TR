---
title: Kimlik ve ötesine—Mimarlardan birinin bakış açısı
description: Microsoft'un Teknik Sorumlu Mimarı Alex Shteynberg'den Microsoft Kurumsal mimarisi için en iyi tasarım stratejileri hakkında bilgi edinin.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-identity-device-management
- M365-security-compliance
- M365solutions
ms.custom: seo-marvel-jun2020
f1.keywords: NOCSH
ms.openlocfilehash: 88eec0ad7b452f0624c298ef21812dd9d8587f37
ms.sourcegitcommit: 078149c9645ce220911ccd6ce54f984a4c92ce53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67810747"
---
# <a name="to-identity-and-beyondone-architects-viewpoint"></a>Kimlik ve ötesine—Mimarlardan birinin bakış açısı

Bu makalede, Microsoft'un Baş Teknik Mimarı [Alex Shteynberg](https://www.linkedin.com/in/alex-shteynberg/), Microsoft 365 ve diğer Microsoft bulut hizmetlerini benimseyen kurumsal kuruluşlara yönelik en iyi tasarım stratejilerini ele almaktadır.

## <a name="about-the-author"></a>Yazar hakkında

![Alex Shteynberg fotoğrafı.](../media/solutions-architecture-center/identity-and-beyond-alex-shteynberg.jpg)

New York [Microsoft Teknoloji Merkezi'nde](https://www.microsoft.com/mtc?rtc=1) Baş Teknik Mimarım. Çoğunlukla büyük müşteriler ve karmaşık gereksinimlerle çalışıyorum. Bakış açım ve görüşlerim bu etkileşimleri temel alır ve her durum için geçerli olmayabilir. Ancak deneyimlerime göre, müşterilere en karmaşık zorluklar konusunda yardımcı olabilirsek, tüm müşterilere yardımcı olabiliriz.

Normalde her yıl 100'de fazla müşteriyle çalışıyorum. Her kuruluşun benzersiz özellikleri olsa da eğilimleri ve ortak noktaları görmek ilginçtir. Örneğin, bir eğilim birçok müşteri için sektörler arası ilgidir. Sonuçta, banka şubesi bir kafe ve topluluk merkezi de olabilir.

Rolümde, müşterilerin benzersiz iş hedeflerini ele almak için en iyi teknik çözüme ulaşmalarına yardımcı olmaya odaklanıyorum. Resmi olarak Kimlik, Güvenlik, Gizlilik ve Uyumluluk konularına odaklanıyorum. Bu dokunuşların yaptığımız her şeye dokunmasını seviyorum. Çoğu projeyle ilgilenmem için bana bir fırsat veriyor. Bu etkinlik beni meşgul ediyor ve bu rolün tadını çıkarıyor.

New York City'de yaşıyorum (en iyisi!) ve kültürünün, yemeğinin ve insanlarının (trafik değil) çeşitliliğinden gerçekten keyif alıyorum. Ömrüm boyunca dünyanın çoğunu görmeyi umduğum zaman seyahat etmeye bayılırım. Şu anda vahşi yaşam hakkında bilgi edinmek için Afrika'ya bir gezi araştırıyorum.

## <a name="guiding-principles"></a>Yol gösteren ilkeler

- **Basit genellikle daha iyidir**: Teknolojiyle (neredeyse) her şeyi yapabilirsiniz, ancak yapmanız gerektiği anlamına gelmez. Özellikle güvenlik alanında, birçok müşteri daha fazla yük devretme çözümü sunar. Google'ın Stripe konferansındaki [bu videodan](https://www.youtube.com/watch?v=SOQgABDSYZE) bu noktanın altını çiziyorum.
- **Kişiler, süreç, teknoloji**: İnsanların süreci geliştirmesi [için tasarım](https://en.wikipedia.org/wiki/Human-centered_design), önce teknoloji değil. "Mükemmel" çözümler yoktur. Çeşitli risk faktörlerini dengelememiz gerekiyor ve kararlar her işletme için farklı olacaktır. Çok fazla müşteri, kullanıcılarının daha sonra kaçındıkları bir yaklaşım tasarlar.
- **Önce 'neden' ve sonra 'nasıl' üzerine odaklanın**: Milyonlarca sorusu olan sinir bozucu 7-yr yaşlı çocuk olun. Sorulacak doğru soruları bilmiyorsak doğru yanıta ulaşamayız. Birçok müşteri, iş sorununu tanımlamak yerine işlerin nasıl çalışması gerektiği konusunda varsayımlarda bulunur. Her zaman alınabilecek birden çok yol vardır.
- **Geçmiş en iyi yöntemlerin uzun kuyruğu**: En iyi yöntemlerin ışık hızında değiştiğini fark edin. Üç aydan uzun bir süre önce Azure AD baktıysanız, muhtemelen eskimişsinizdir. Buradaki her şey yayından sonra değişebilir. "En iyi" seçenek bugünden itibaren altı ay sonra aynı olmayabilir.

## <a name="baseline-concepts"></a>Temel kavramlar

Bu bölümü atlamayın. Bulut hizmetlerini yıllardır kullanan müşteriler için bile bu makalelere geri adım atmam gerektiğini sık sık fark ediyorum.
Ne yazık ki, dil kesin bir araç değildir. Genellikle aynı sözcüğü farklı kavramlar veya aynı kavram anlamına gelen farklı sözcükler için kullanırız. Temel terminoloji ve "hiyerarşi modeli" oluşturmak için genellikle aşağıdaki diyagramı kullanıyorum.
<br><br>

![Kiracı, abonelik, hizmet ve verilerin çizimi.](../media/solutions-architecture-center/Identity-and-beyond-tenant-level.png)

<br>

Yüzmeyi öğrendiğinizde, okyanusun ortasında değil havuzdan başlamak daha iyidir. Bu diyagramda teknik olarak doğru olmaya çalışmıyorum. Bazı temel kavramların tartışıldığı bir modeldir.

Diyagramda:

- Kiracı = Azure AD örneği. Hiyerarşinin "en üstünde" veya diyagramda Düzey 1'de yer alır. Bu düzeyi, diğer her şeyin gerçekleştiği "[sınır](/azure/active-directory/users-groups-roles/licensing-directory-independence)" olarak düşünebiliriz ([Azure AD B2B](/azure/active-directory/b2b/what-is-b2b) bir yana). Tüm Microsoft kurumsal bulut hizmetleri bu kiracılardan birinin parçasıdır. Tüketici hizmetleri ayrıdır. "Kiracı", belgelerde Office 365 kiracı, Azure kiracısı, WVD kiracısı vb. olarak görünür. Bu çeşitlemelerin müşteriler için karışıklığa neden olduğunu sık sık buluyorum.
- Diyagramdaki Düzey 2 olan hizmetler/abonelikler tek bir kiracıya aittir. SaaS hizmetlerinin çoğu 1:1'dir ve geçiş olmadan taşınamaz. Azure farklıdır; faturalamayı ve/veya [aboneliği](/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) başka bir kiracıya [taşıyabilirsiniz](/azure/cost-management-billing/manage/billing-subscription-transfer). Azure aboneliklerini taşıması gereken birçok müşteri vardır. Bu senaryo çeşitli etkilere sahiptir. Aboneliğin dışında bulunan nesneler taşınmaz. Örneğin rol tabanlı erişim denetimi (Azure RBAC), Azure AD nesneleri (gruplar, uygulamalar, ilkeler vb.) ve bazı hizmetler (Azure Key Vault, Veri Tuğlaları vb.). İyi bir iş gereksinimi olmadan hizmetleri geçirmeyin. Geçiş için yararlı olabilecek bazı betikler [GitHub'da paylaşılır](https://github.com/lwajswaj/azure-tenant-migration).
- Belirli bir hizmetin genellikle bir tür "alt düzey" sınırı veya Düzey 3 (L3) vardır. Bu sınır, güvenlik, ilkeler, idare vb. ayrımını anlamak için kullanışlıdır. Ne yazık ki bildiğim tek tip bir isim yok. L3 için bazı örnek adlar şunlardır: Azure Aboneliği = [kaynak](/azure/azure-resource-manager/management/manage-resources-portal); Dynamics 365 CE = [örnek](/dynamics365/admin/new-instance-management); Power BI = [çalışma alanı](/power-bi/service-create-the-new-workspaces); Power Apps = [ortam](/power-platform/admin/environments-overview); ve benzeri.
- Düzey 4, gerçek verilerin bulunduğu yerdir. Bu 'veri düzlemi' karmaşık bir makaledir. Bazı hizmetler RBAC için Azure AD kullanıyor, diğerleri kullanmıyor. Temsilci makalelerine gelince bunu biraz tartışacağım.

Birçok müşteriyi (ve Microsoft çalışanlarını) bulduğum bazı ek kavramlar aşağıdaki sorunları içerir:

- Herkes [hiçbir ücret ödemeden](https://azure.microsoft.com/pricing/details/active-directory/) birçok kiracı [oluşturabilir](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant). Hizmetin içinde sağlanmış bir hizmete ihtiyacınız yoktur. Bende onlarca var. Her Kiracı adı, Microsoft'un dünya çapındaki bulut hizmetinde benzersizdir (başka bir deyişle, iki kiracı aynı ada sahip olamaz). Hepsi TenantName.onmicrosoft.com biçimindedir. Kiracıları otomatik olarak ([yönetilmeyen kiracılar](/azure/active-directory/users-groups-roles/directory-self-service-signup)) oluşturan işlemler de vardır. Örneğin, kullanıcı başka bir kiracıda mevcut olmayan bir e-posta etki alanıyla kurumsal hizmete kaydolduğunda bu durum oluşabilir.
- Yönetilen bir kiracıda, birçok [DNS etki alanı](/azure/active-directory/fundamentals/add-custom-domain) bu kiracıya kaydedilebilir. Bu, özgün kiracı adını değiştirmez. Şu anda kiracıyı yeniden adlandırmanın kolay bir yolu yoktur (geçiş dışında). Kiracı adı teknik olarak bu günlerde kritik olmasa da, bazıları bunun sınırlayıcı olduğunu düşünebilir.
- Henüz herhangi bir hizmet dağıtmayı planlamasanız bile kuruluşunuz için bir kiracı adı ayırmanız gerekir. Aksi takdirde, birisi bunu sizden alabilir ve geri almak için basit bir işlem yoktur (DNS adları ile aynı sorun). Müşterilerden bu şekilde çok sık duyuyorum. Kiracı adınızın ne olması gerektiği de bir tartışma makalesi.
- DNS ad alanlarınız varsa, bunların tümünü kiracılarınıza eklemeniz gerekir. Aksi takdirde, bu adla [yönetilmeyen bir kiracı](/azure/active-directory/users-groups-roles/directory-self-service-signup) oluşturulabilir ve bu da [yönetilmelerini sağlamak](/azure/active-directory/users-groups-roles/domains-admin-takeover) için kesintiye neden olur.
- DNS ad alanı (contoso.com gibi) tek bir kiracıya ait olabilir. Bunun çeşitli senaryolar üzerinde etkileri vardır (örneğin, birleştirme veya alma sırasında e-posta etki alanını paylaşma vb.). Dns alt öğesini (div.contoso.com gibi) farklı bir kiracıya kaydetmenin bir yolu vardır, ancak bundan kaçınılmalıdır. Üst düzey etki alanı adı kaydedildiğinde, tüm alt etki alanları aynı kiracıya ait olduğu varsayılır. Çok kiracılı senaryolarda (aşağıya bakın) normalde başka bir üst düzey etki alanı adı (contoso.ch veya ch-contoso.com gibi) kullanmanızı öneririm.
- Kim kiracıya "sahip olmalıdır"? Kiracılarının sahibini bilmeyen müşterileri sık sık görüyorum. Bu bilgi eksikliği büyük bir kırmızı bayraktır. Microsoft desteğini en kısa sürede arayın. Aynı sorun, bir hizmet sahibinin (genellikle Exchange yöneticisi) kiracıyı yönetmek üzere atandığında olduğu gibi. Kiracı, gelecekte isteyebileceğiniz tüm hizmetleri içerir. Kiracı sahibi, bir kuruluştaki tüm bulut hizmetlerinin etkinleştirilmesi için karar verebilen bir grup olmalıdır. Bir diğer sorun da kiracı sahibi grubunun tüm hizmetleri yönetmesi istendiğinde oluşur. Bu, büyük kuruluşlar için ölçeklendirilmiyor.
- Alt/süper kiracı kavramı yoktur. Nedense, bu efsane kendini tekrar ediyor. Bu[, Azure AD B2C](/azure/active-directory-b2c/) kiracıları için de geçerlidir. "B2C ortamım XYZ Kiracımda" veya "Azure kiracımı Office 365 kiracıma taşımak Nasıl yaparım??"
- Bu belge çoğunlukla ticari dünya çapındaki buluta odaklanır, çünkü çoğu müşteri bunu kullanıyor. Bazen [bağımsız bulutlar](/azure/active-directory/develop/authentication-national-cloud) hakkında bilgi edinmek yararlı olabilir. Bağımsız bulutların, bu tartışmanın kapsamı dışında olan ek etkileri vardır.

## <a name="baseline-identity-articles"></a>Temel kimlik makaleleri

Microsoft'un kimlik platformu (Azure Active Directory (Azure AD) hakkında çok fazla belge vardır. Yeni başlayanlar için genellikle bunaltıcı geliyor. Bu konuda bilgi edindikten sonra bile sürekli yeniliğe ve değişikliğe ayak uydurmak zor olabilir. Müşteri etkileşimlerimde genellikle iş hedefleri ile bunları ele almak için "İyi, Daha İyi, En İyi" yaklaşımlar (ve bu makaleler için insan "uçurum notları" gibi) arasında "çevirmen" olarak görev yapıyorum. Nadiren mükemmel bir yanıt vardır ve "doğru" karar çeşitli risk faktörlerinin bir dengesidir. Müşterilerle tartışma eğiliminde olduğum yaygın soru ve karışıklık alanlarından bazıları aşağıdadır.

### <a name="provisioning"></a>Sağlama

Azure AD, kimlik dünyanızdaki idare eksikliğini çözmez! [Kimlik idaresi](/azure/active-directory/governance/identity-governance-overview) , bulut kararlarından bağımsız olarak kritik bir öğe olmalıdır. İdare gereksinimleri zaman içinde değişir, bu nedenle bir araç değil, bir programdır.

[Connect](/azure/active-directory/hybrid/whatis-azure-ad-connect) ile [Microsoft Identity Manager](/microsoft-identity-manager/microsoft-identity-manager-2016) (MIM) ve başka bir şey (üçüncü taraf veya özel) karşılaştırması Azure AD? Şimdi ve gelecekte kendinize çok fazla baş ağrısı kaydedin ve Azure AD Connect ile devam edin. Bu araçta, kendine özgü müşteri yapılandırmalarını ve sürekli yenilikleri ele almak için her türlü akıllı vardır.

Daha karmaşık bir mimariye yönlendirebilecek bazı uç durumlar:

- Bunlar arasında ağ bağlantısı olmayan birden çok AD ormanım var. [Bulut Sağlama](/azure/active-directory/cloud-provisioning/what-is-cloud-provisioning) adlı yeni bir seçenek vardır.
- Active Directory'm yok ve yüklemek de istemiyorum. Azure AD Connect[, LDAP'den eşitlenecek](/azure/active-directory/hybrid/plan-hybrid-identity-design-considerations-tools-comparison) şekilde yapılandırılabilir (iş ortağı gerekebilir).
- Aynı nesneleri birden çok kiracıya sağlamam gerekiyor. Bu senaryo teknik olarak desteklenmemektedir ancak "aynı" tanımına bağlıdır.

Varsayılan eşitleme kurallarını ([nesneleri filtreleme](/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering), [öznitelikleri değiştirme](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized), [alternatif oturum açma kimliği](/azure/active-directory/hybrid/plan-connect-userprincipalname) vb.) özelleştirmeli miyim? Bundan kaçının! Kimlik platformu yalnızca onu kullanan hizmetler kadar değerlidir. Her türlü çatlak yapılandırmayı yapabileceksiniz ancak bu soruyu yanıtlamak için uygulamalar üzerindeki etkisine bakmanız gerekir. Posta özellikli nesneleri filtrelerseniz, çevrimiçi hizmetler için GAL eksik olur; uygulama belirli özniteliklere dayanırsa, bunları filtrelemenin öngörülemeyen bir etkisi olur ve bu şekilde devam eder. Bu bir kimlik ekibi kararı değil.

XYZ SaaS Tam Zamanında (JIT) sağlamayı destekliyor, neden eşitlememi istiyorsunuz? Yukarıya bakınız. Birçok uygulamanın işlevsellik için "profil" bilgilerine ihtiyacı vardır. Posta özellikli tüm nesneler kullanılamıyorsa GAL'niz olamaz. Aynı durum, Azure AD ile tümleştirilmiş uygulamalarda [kullanıcı sağlama](/azure/active-directory/app-provisioning/user-provisioning) için de geçerlidir.

### <a name="authentication"></a>Kimlik Doğrulama

[Parola karması eşitleme](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) (PHS) ile [geçişli kimlik doğrulaması](/azure/active-directory/hybrid/how-to-connect-pta-how-it-works) (PTA) ve [federasyon](/azure/active-directory/hybrid/how-to-connect-fed-compatibility) karşılaştırması.

Genellikle federasyonla ilgili tutkulu bir [tartışma](/azure/active-directory/hybrid/choose-ad-authn) olur. Daha basit genellikle daha iyidir ve bu nedenle iyi bir nedeniniz yoksa PHS kullanın. Aynı kiracıdaki farklı DNS etki alanları için farklı kimlik doğrulama yöntemleri de yapılandırılabilir.

Bazı müşteriler genellikle şunlar için federasyon + PHS'yi etkinleştirir:

- Federasyon hizmeti kullanılamıyorsa (olağanüstü durum kurtarma için) öğesine [geri dönme](/azure/active-directory/hybrid/plan-migrate-adfs-password-hash-sync) seçeneği.
- Ek özellikler (ör. [Azure AD DS](/azure/active-directory-domain-services/tutorial-configure-password-hash-sync)) ve güvenlik hizmetleri (ör. [sızdırılan kimlik bilgileri](/azure/active-directory/reports-monitoring/concept-risk-events#leaked-credentials))
- Azure'da federasyon kimlik doğrulamasını anlamayan hizmetler için destek (örneğin, [Azure Dosyalar](/azure/storage/files/storage-files-active-directory-overview)).

Bazı yanlış algıları netleştirmek için müşterilere genellikle istemci kimlik doğrulama akışında yol gösteririm. Sonuç, aşağıdaki resme benzer ve bu, etkileşimli oraya varma işlemi kadar iyi değildir.

![Örnek beyaz tahta konuşması.](../media/solutions-architecture-center/identity-beyond-whiteboard-example.png)

Bu beyaz tahta çizimi, güvenlik ilkelerinin bir kimlik doğrulama isteğinin akışı içinde nereye uygulandığını gösterir. Bu örnekte, Active Directory Federasyon Hizmeti (AD FS) aracılığıyla uygulanan ilkeler ilk hizmet isteğine uygulanır, ancak sonraki hizmet isteklerine uygulanmaz. Bu davranış, güvenlik denetimlerini mümkün olduğunca buluta taşımak için en az bir nedendir.

Hatırlayabildiğim kadar uzun süredir [çoklu oturum açma](/azure/active-directory/manage-apps/what-is-single-sign-on) (SSO) hayalinin peşindeyiz. Bazı müşteriler "doğru" federasyon (STS) sağlayıcısını seçerek bunu başarabileceklerine inanıyor. Azure AD [SSO özelliklerini etkinleştirmeye](/azure/active-directory/manage-apps/plan-sso-deployment) önemli ölçüde yardımcı olabilir, ancak hiçbir STS sihirli değildir. Kritik uygulamalar için hala kullanılan çok fazla "eski" kimlik doğrulama yöntemi vardır. Azure AD [iş ortağı çözümleriyle](/azure/active-directory/saas-apps/tutorial-list) genişletmek bu senaryoların çoğunu ele alabilir. SSO bir strateji ve bir yolculuk. [Uygulamalar için standartlara](/azure/active-directory/develop/v2-app-types) geçmeden oraya ulaşamazsınız. Bu makaleyle ilgili olarak, sihirli bir yanıtı olmayan [parolasız](/azure/active-directory/authentication/concept-authentication-passwordless) kimlik doğrulamasına yönelik bir yolculuk vardır.

[Çok faktörlü kimlik doğrulaması](/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) bugün çok önemlidir (daha fazlası için [burada](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984) ). Buna [kullanıcı davranışı analizi](/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) eklerseniz en yaygın siber saldırıları önleyen bir çözümünüz vardır. Tüketici hizmetleri bile MFA gerektirmek üzere hareket ediyor. Yine de [modern kimlik doğrulama](../enterprise/hybrid-modern-auth-overview.md) yaklaşımlarına geçmek istemeyen birçok müşteriyle görüşüyorum. Duyduğum en büyük bağımsız değişken, kullanıcıları ve eski uygulamaları etkileyecektir. Bazen iyi bir tekme, müşterilerin [duyurulan değişiklikler](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-auth-and-exchange-online-february-2020-update/ba-p/1191282) Exchange Online ilerlemelerine yardımcı olabilir. Müşterilerin bu geçişte yardımcı olması için birçok Azure AD [raporu](/azure/active-directory/fundamentals/concept-fundamentals-block-legacy-authentication) kullanıma sunulmuştur.

### <a name="authorization"></a>Yetkilendirme

[Wikipedia](https://en.wikipedia.org/wiki/Authorization) başına , "yetkilendirmek" bir erişim ilkesi tanımlamaktır. Birçok kişi buna bir nesneye (dosya, hizmet vb.) erişim denetimleri tanımlama özelliği olarak bakar. Mevcut siber tehdit dünyasında bu kavram, çeşitli tehdit vektörlerine tepki verebilen ve bunlara yanıt olarak erişim denetimlerini hızlı bir şekilde ayarlayabilen dinamik bir politikaya hızla gelişmektedir. Örneğin, banka hesabıma olağan dışı bir konumdan erişirsem ek onay adımları alıyorum. Buna yaklaşmak için yalnızca ilkenin kendisini değil, tehdit algılama ve sinyal bağıntı yöntemleri ekosistemini de göz önünde bulundurmamız gerekir.

Azure AD ilke altyapısı [Koşullu Erişim ilkeleri](/azure/active-directory/conditional-access/overview) kullanılarak uygulanır. Bu sistem, dinamik kararlar almak için diğer çeşitli tehdit algılama sistemlerinden alınan bilgilere bağlıdır. Basit bir görünüm aşağıdaki çizime benzer olacaktır:

![Azure AD'da ilke altyapısı.](../media/solutions-architecture-center/identity-and-beyond-illustration-3.png)

Tüm bu sinyallerin birleştirilmesi aşağıdaki gibi dinamik ilkelere olanak tanır:

- Cihazınızda bir tehdit algılanırsa, verilere erişiminiz indirme özelliği olmadan yalnızca web'e indirilir.
- Alışılmadık derecede yüksek miktarda veri indiriyorsanız, indirdiğiniz her şey şifrelenir ve kısıtlanır.
- Yönetilmeyen bir cihazdan bir hizmete erişirsen, yüksek oranda hassas verilere erişimin engellenir, ancak başka bir konuma kopyalama özelliği olmadan kısıtlanmamış verilere erişmesine izin verilir.

Bu genişletilmiş yetkilendirme tanımına katılıyorsanız ek çözümler uygulamanız gerekir. Hangi çözümleri uygulayacağınız, ilkenin ne kadar dinamik olmasını istediğinize ve öncelik vermek istediğiniz tehditlere bağlıdır. Bu tür sistemlere bazı örnekler şunlardır:

- [Azure AD Kimlik Koruması](/azure/active-directory/identity-protection/)
- [Kimlik için Microsoft Defender](/azure-advanced-threat-protection/)
- [Uç Nokta için Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Office 365 için Microsoft Defender](../security/office-365-security/defender-for-office-365.md)
- [Microsoft Defender for Cloud Apps](/cloud-app-security/) (Cloud Apps için Defender)
- [Microsoft 365 Defender](../security/defender/microsoft-365-defender.md)
- [Microsoft Intune](/mem/intune/)
- [Microsoft Purview Bilgi Koruması](../compliance/information-protection.md)
- [Microsoft Sentinel](/azure/sentinel/)

Tabii ki, Azure AD ek olarak, çeşitli hizmet ve uygulamaların kendi özel yetkilendirme modelleri vardır. Bunlardan bazıları daha sonra temsilci seçme bölümünde ele alınmıştır.

### <a name="audit"></a>Denetim

Azure AD ayrıntılı [denetim ve raporlama](/azure/active-directory/reports-monitoring/) özelliklerine sahiptir. Ancak bu raporlar genellikle güvenlik kararları almak için gereken tek bilgi kaynağı değildir. Temsilci seçme bölümünde bu konu hakkında daha fazla tartışmaya bakın.

## <a name="theres-no-exchange"></a>Exchange yok

Panik yapmayın! Bu, Exchange'in kullanım dışı bırakıldığı anlamına gelmez (veya SharePoint vb.). Hala temel bir hizmet. Demek istediğim, bir süredir teknoloji sağlayıcılarının kullanıcı deneyimlerini (UX) birden çok hizmetin bileşenlerini kapsayacak şekilde geçirmesi. Microsoft 365'te, e-posta [eklerinin](https://support.office.com/article/Attach-files-or-insert-pictures-in-Outlook-email-messages-BDFAFEF5-792A-42B1-9A7B-84512D7DE7FC) SharePoint Online'da veya OneDrive İş depolandığı "modern ekler" basit bir örnektir.

![E-postaya dosya ekleme.](../media/solutions-architecture-center/modern-attachments.png)

Outlook istemcisine baktığınızda, yalnızca Exchange'i değil, bu deneyimin bir parçası olarak "bağlı" olan birçok hizmeti görebilirsiniz. Buna Azure AD, Microsoft Search, Uygulamalar, Profil, uyumluluk ve Office 365 grupları dahildir.

![Açıklama balonları içeren Outlook arabirimi.](../media/solutions-architecture-center/identity-and-beyond-conceptual-screenshot.png)

Yaklaşan özelliklerin önizlemesi için [Microsoft Akıcı Çerçeve](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-ignite-blog-microsoft-fluid-framework-preview/ba-p/978268) hakkında bilgi edinin. Artık önizlemede Teams konuşmalarını doğrudan Outlook'ta okuyabilir ve yanıtlayabilirim. Aslında [Teams istemcisi](https://products.office.com/microsoft-teams/download-app) bu stratejinin en önemli örneklerinden biridir.

Genel olarak, Office 365 ile Microsoft bulutlarındaki diğer hizmetler arasında net bir çizgi çizmek zorlaşıyor. Tek bir bileşen kullansalar bile yaptığımız her şeyde toplam yenilikten yararlanabilecekleri için bunu müşterilere büyük bir avantaj olarak alıyorum. Oldukça havalı ve birçok müşteri için çok fazla etki var.

Bugün birçok müşteri BT grubunun "ürünler" etrafında yapılandırıldığını düşünüyorum. Her ürün için bir uzmana ihtiyacınız olduğundan, şirket içi bir dünya için mantıklıdır. Ancak, bu hizmetler buluta taşındığından bir daha bir Active Directory veya Exchange veritabanında hata ayıklamak zorunda olmadığım için çok mutluyum. Otomasyon (bulut türü) yinelenen bazı el ile işleri kaldırır (fabrikalara ne olduğuna bakın). Ancak, bu görevler hizmetler arası etkileşimi, etkiyi, iş gereksinimlerini vb. anlamak için daha karmaşık gereksinimlerle değiştirilir. [Öğrenmeye](/training/) istekliyseniz, bulut dönüşümü tarafından etkinleştirilen harika fırsatlar vardır. Teknolojiye atlamadan önce, BT becerilerinde ve ekip yapılarındaki değişikliği yönetme hakkında müşterilerle sık sık konuşuyorum.

Tüm SharePoint hayranları ve geliştiricileri için lütfen "SharePoint online'da XYZ'yi nasıl yapabilirim?" sorusunu durdurun. İş akışı için [Power Automate](/power-automate/) 'i (veya Flow'ı) kullanın, çok daha güçlü bir platform. 500 K öğe listenize daha iyi bir UX oluşturmak için [Azure Bot Framework'i](/azure/bot-service/) kullanın. CSOM yerine [Microsoft Graph](https://developer.microsoft.com/graph/) kullanmaya başlayın. [Microsoft Teams](/MicrosoftTeams/Teams-overview) , SharePoint'i ve daha fazlasını içerir. Listeleyebileceğiniz başka birçok örnek daha var. Dışarıda muazzam ve harika bir evren var. Kapıyı açın ve [keşfetmeye başlayın]().

Diğer yaygın etki uyumluluk alanındadır. Bu hizmetler arası yaklaşım birçok uyumluluk ilkesini tamamen karıştırıyor gibi görünüyor. "Tüm e-posta iletişimlerini bir eBulma sistemine günlüğe kaydetmeliyim" diyen kuruluşlar görüyorum. E-posta artık yalnızca e-posta değil diğer hizmetlere açılan bir pencere olduğunda bu gerçekten ne anlama gelir? Office 365 [uyumluluk](../compliance/index.yml) için kapsamlı bir yaklaşıma sahiptir, ancak insanların ve süreçlerin değiştirilmesi genellikle teknolojiden çok daha zordur.

Başka birçok kişi ve sürecin etkileri vardır. Bence bu faktör kritik ve tartışılmamış bir alan. Belki de başka bir makalede daha fazlası.

## <a name="tenant-structure-options"></a>Kiracı yapısı seçenekleri

### <a name="single-tenant-vs-multi-tenant"></a>Tek kiracı ve çok kiracılı

Genel olarak, çoğu müşterinin yalnızca bir üretim kiracısı olmalıdır. Birden çok kiracının zor olmasının birçok nedeni vardır ( [Bing araması](https://www.bing.com/search?q=office%20365%20multiple%20tenants) verin) veya bu [teknik incelemeyi](https://aka.ms/multi-tenant-user) okuyun. Aynı zamanda, birlikte çalıştığım birçok kurumsal müşterinin BT öğrenmesi, testi ve denemesi için başka bir (küçük) kiracısı var. Azure Lighthouse ile kiracılar arası Azure erişimi daha kolay hale [getiriliyor](https://azure.microsoft.com/services/azure-lighthouse/). Office 365 ve diğer birçok SaaS hizmeti, kiracılar arası senaryolar için sınırlara sahiptir. [Azure AD B2B](/azure/active-directory/b2b/what-is-b2b) senaryolarında dikkate alınması gereken çok şey vardır.

Birçok müşteri bir birleşme ve alımdan (M&A) sonra birden çok üretim kiracısına sahip olur ve birleştirmek ister. Bugün bu basit değildir ve Microsoft Danışmanlık Hizmetleri (MCS) veya bir iş ortağı artı üçüncü taraf yazılım gerektirir. Gelecekte çok kiracılı müşterilerle çeşitli senaryoları ele almak için devam eden mühendislik çalışmaları vardır.

Bazı müşteriler birden fazla kiracıyla gitmeyi tercih edebilir. Bu çok dikkatli bir karar olmalı ve neredeyse her zaman iş nedeni odaklı olmalıdır! Bazı örnekler aşağıdaki nedenleri içerir:

- Farklı varlıklar arasında kolay işbirliği gerektiren ve güçlü yönetim ve diğer yalıtım gereksinimlerinin bulunduğu bir holding türü şirket yapısı.
- Bir alımdan sonra, iki varlığı ayrı tutmak için bir iş kararı velanır.
- Müşterinin üretim ortamını değiştirmeyen müşterinin ortamının simülasyonu.
- Müşteriler için yazılım geliştirme.

Bu çok kiracılı senaryolarda müşteriler genellikle bazı yapılandırmaları kiracılar arasında aynı tutmak veya yapılandırma değişiklikleri ve kaymalarını bildirmek ister. Bu genellikle el ile yapılan değişikliklerden kod olarak yapılandırmaya geçiş anlamına gelir. Microsoft Premiere desteği, şu genel IP'yi temel alan bu tür gereksinimler için bir atölye sunar: <https://Microsoft365dsc.com>.

### <a name="multi-geo"></a>Multi-Geo

[Multi-Geo'ya](../enterprise/microsoft-365-multi-geo.md) veya Multi-Geo'ya değil, asıl soru bu. Office 365 Multi-Geo ile bekleyen verileri, veri [yerleşimi](../enterprise/o365-data-locations.md) gereksinimlerini karşılamak için seçtiğiniz coğrafi konumlarda sağlayabilir ve depolayabilirsiniz. Bu özellik hakkında birçok yanlış algı vardır. Aşağıdakileri unutmayın:

- Performans avantajları sağlamaz. [Ağ tasarımı](https://aka.ms/office365networking) doğru değilse performansı daha kötü hale getirebilir. Cihazları verilerinize değil Microsoft ağına "yakın" alın.
- [GDPR uyumluluğu](https://www.microsoft.com/trust-center/privacy/gdpr-overview) için bir çözüm değildir. GDPR, veri hakimiyetine veya depolama konumlarına odaklanmaz. Bunun için başka uyumluluk çerçeveleri de vardır.
- Yönetim temsilcisi seçme (aşağıya bakın) veya [bilgi engellerini](../compliance/information-barriers.md) çözmez.
- Çok kiracılı ile aynı değildir ve ek [kullanıcı sağlama](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) iş akışları gerektirir.
- Kiracınızı (Azure AD) başka bir coğrafyaya [taşımaz](../enterprise/moving-data-to-new-datacenter-geos.md).

## <a name="delegation-of-administration"></a>Yönetim temsilcisi

Çoğu büyük kuruluşta görev ayrımı ve rol tabanlı erişim denetimi (RBAC) gerekli bir gerçekliktir. Önceden özür dileyeceğim. Bu etkinlik bazı müşterilerin istediği kadar basit değildir. Müşteri, yasal, uyumluluk ve diğer gereksinimler farklıdır ve bazen dünya çapında çakışıyor. Basitlik ve esneklik genellikle birbirinin karşı tarafındadır. Beni yanlış anlamadım, bu işte daha iyi bir iş yapabiliriz. Zaman içinde önemli geliştirmeler yapıldı (ve olacak). 379230 belgelerini okumadan iş gereksinimlerinize uygun modeli bulmak için yerel [Microsoft Teknoloji Merkezinizi](https://www.microsoft.com/mtc) ziyaret edin! Burada, neden böyle olduğunu değil, düşünmeniz gereken şeylere odaklanacağım. Aşağıda plan yapmak için beş farklı alan ve karşılaştığım bazı yaygın sorular yer almaktadır.

### <a name="azure-ad-and-microsoft-365-admin-centers"></a>Azure AD ve Microsoft 365 yönetim merkezleri

[Yerleşik rollerin](/azure/active-directory/roles/permissions-reference) uzun ve büyüyen bir listesi vardır. Her rol, belirli eylemlerin gerçekleştirilebilmesine izin vermek için birlikte gruplandırılmış rol izinlerinin bir listesinden oluşur. Bu izinleri her rolün içindeki "Açıklama" sekmesinde görebilirsiniz. Alternatif olarak, Microsoft 365 Yönetici Merkezi'nde bu izinlerin daha insan tarafından okunabilir bir sürümünü görebilirsiniz. Yerleşik rollerin tanımları değiştirilemez. Genel olarak bu rolleri üç kategoride gruplandırıyorum:

- **Genel yönetici**: Bu "tüm güçlü" rol, diğer sistemlerde olduğu gibi [yüksek oranda korunmalıdır](../enterprise/protect-your-global-administrator-accounts.md). Tipik öneriler şunlardır: kalıcı atama yok ve Azure AD Privileged Identity Management (PIM) kullanma; güçlü kimlik doğrulaması ve benzeri. İlginçtir ki, bu rol varsayılan olarak her şeye erişmenize izin vermez. Genellikle, uyumluluk erişimi ve Azure erişimi hakkında daha sonra tartışılan karışıklıklar görüyorum. Ancak, bu rol her zaman kiracıdaki diğer hizmetlere erişim atayabilir.
- **Belirli hizmet yöneticileri**: Bazı hizmetler (Exchange, SharePoint, Power BI vb.) Azure AD üst düzey yönetim rollerini kullanır. Bu davranış tüm hizmetler arasında tutarlı değildir ve daha sonra ele alınan hizmete özgü daha fazla rol vardır.
- **İşlevsel**: Belirli işlemlere (konuk davet eden vb.) odaklanan rollerin uzun (ve büyüyen) bir listesi vardır. Düzenli aralıklarla, bu rollerin daha fazlası müşteri ihtiyaçlarına göre eklenir.

Her şeye temsilci seçmek mümkün değildir (boşluk azalsa da), bu da Genel yönetici rolünün bazen kullanılması gerektiği anlamına gelir. Bu rolün kişi üyeliği yerine kod olarak yapılandırma ve otomasyon dikkate alınmalıdır.

**Not**: Microsoft 365 yönetim merkezi daha kullanıcı dostu bir arabirime sahiptir ancak Azure AD yönetici deneyimine kıyasla özelliklerin bir alt kümesine sahiptir. Her iki portal da aynı Azure AD rollerini kullandığından, değişiklikler aynı yerde gerçekleşir. İpucu: Tüm Azure dağınıklığı olmadan kimlik yönetimi odaklı bir yönetici kullanıcı arabirimi istiyorsanız kullanın <https://aad.portal.azure.com>.

Adında ne var? Rolün adından varsayımlarda bulunmayın. Dil çok hassas bir araç değildir. Amaç, hangi rollerin gerekli olduğuna bakmadan önce temsilci olarak atanması gereken işlemleri tanımlamak olmalıdır. Birini "Güvenlik Okuyucusu" rolüne eklemek, her şeyin güvenlik ayarlarını görmesine neden olmaz.

[Özel roller](/azure/active-directory/users-groups-roles/roles-custom-overview) oluşturma özelliği yaygın bir sorudur. Bu özellik bugün Azure AD sınırlıdır (aşağıya bakın) ancak zamanla özellikler artacaktır. Bu özel rollerin Azure AD işlevler için geçerli olduğunu düşünüyorum ve hiyerarşi modelini "aşağı" yayamayabilirim (yukarıda anlatılmaktadır). "Özel" ile ne zaman ilgilensem, "basit daha iyidir" müdürüme geri dönme eğilimindeyim.

Sık sorulan bir diğer soru da rollerin bir dizinin alt kümesine göre kapsam oluşturabilmesidir. Bir örnek, "Yalnızca AB'deki kullanıcılar için Yardım Masası Yöneticisi" gibi bir örnektir. [Yönetim Birimleri](/azure/active-directory/users-groups-roles/directory-administrative-units) (AU) bunu ele almak için tasarlanmıştır. Yukarıdaki gibi, bu kapsamları Azure AD işlevleri için geçerli olduğunu düşünüyorum ve "aşağı" yayılmayabilir. Elbette, belirli rollerin kapsamını (genel yöneticiler, hizmet yöneticileri vb.) kapsaması mantıklı değildir.

Bugün, tüm bu roller doğrudan üyelik (veya [Azure AD PIM](/azure/active-directory/privileged-identity-management/) kullanıyorsanız dinamik atama) gerektirir. Bu, müşterilerin bunları doğrudan Azure AD yönetmesi gerektiği ve bu rollerin bir güvenlik grubu üyeliğine dayanamayacağı anlamına gelir. Yükseltilmiş haklarla çalışması gerekeceğinden bu rolleri yönetmek için betikler oluşturmayı pek sevmem. Genellikle ServiceNow gibi işlem sistemleriyle veya Saviynt gibi iş ortağı idare araçlarını kullanarak API tümleştirmesi öneriyorum. Zaman içinde bu sorunu çözmek için mühendislik çalışmaları devam edecek.

[PIM Azure AD birkaç kez bahsetmiştim](/azure/active-directory/privileged-identity-management/). Şirket içi denetimler için karşılık gelen bir Microsoft Identity Manager (MIM) [Privileged Access Management](/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services) (PAM) çözümü vardır. [Ayrıca Privileged Access Workstations](/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAW) ve [Azure AD Identity Governance'a da bakmak isteyebilirsiniz](/azure/active-directory/governance/identity-governance-overview). Tam zamanında, yeterli ve dinamik rol yükseltmeyi etkinleştirebilen çeşitli üçüncü taraf araçları da vardır. Bu özellik genellikle ortamın güvenliğini sağlamaya yönelik daha büyük bir tartışmanın parçasıdır.

Bazen senaryolar bir role dış kullanıcı eklemeyi çağırır (yukarıdaki çok kiracılı bölüme bakın). Bu gayet iyi çalışıyor. [Azure AD B2B](/azure/active-directory/b2b/), belki de başka bir makalede müşterilere yol gösteren başka bir büyük ve eğlenceli makaledir.

### <a name="microsoft-365-defender-and-microsoft-365-purview-compliance-portals"></a>Microsoft 365 Defender ve Microsoft 365 Purview uyumluluk portalları

Email & [Microsoft 365 Defender portalında](../security/office-365-security/permissions-microsoft-365-security-center.md) **İşbirliği rolleri** ve Microsoft [365 Purview uyumluluk portalındaki *Microsoft Purview](../compliance/microsoft-365-compliance-center-permissions.md) *_çözümleri için rol grupları_*, Azure AD rollerden ayrı ve ayrı olan bir "rol grupları" koleksiyonu. Bu rol gruplarından bazıları Azure AD rolleriyle (örneğin, Güvenlik Okuyucusu) aynı ada sahip olduğundan, ancak farklı üyelikleri olabileceğinden bu durum kafa karıştırıcı olabilir. Azure AD rollerini kullanmayı tercih ederim. Her rol grubu bir veya daha fazla "rolden" oluşur (aynı sözcüğü yeniden kullanma hakkında ne demek istediğimi görün?) ve e-posta özellikli nesneler olan Azure AD üyeleri vardır. Ayrıca, rolle aynı ada sahip bir rol grubu oluşturabilirsiniz; bu rol bu rolü içerebilir veya içermeyebilir (bu karışıklığı önleyin).

Bir anlamda, bu izinler Exchange rol grupları modelinin bir evrimidir. Ancak Exchange Online kendi [rol grubu yönetim](/exchange/permissions-exo) arabirimine sahiptir. Exchange Online'daki bazı rol grupları kilitlenir ve Azure AD veya Microsoft 365 Defender ve Microsoft 365 Purview uyumluluk portallarından yönetilir, ancak diğerleri aynı veya benzer adlara sahip olabilir ve Exchange Online (karışıklığa ek olarak) yönetilir. Exchange yönetimi için kapsamlara ihtiyacınız yoksa Exchange Online kullanıcı arabirimini kullanmaktan kaçınmanızı öneririz.

Özel roller oluşturamazsınız. Roller, Microsoft tarafından oluşturulan hizmetler tarafından tanımlanır ve yeni hizmetler kullanıma sunulduğunda büyür. Bu davranış, kavram olarak [Azure AD'deki uygulamalar tarafından tanımlanan rollere](/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) benzer. Yeni hizmetler etkinleştirildiğinde, bunlara erişim izni vermek veya bunlara temsilci atamak için genellikle yeni rol gruplarının oluşturulması gerekir (örneğin, [insider risk yönetimi](../compliance/insider-risk-management-configure.md)).

Bu rol grupları doğrudan üyelik gerektirir ve Azure AD grupları içeremez. Ne yazık ki bugün bu rol grupları Azure AD PIM tarafından desteklenmemektedir. Azure AD roller gibi, bu rol gruplarının API'ler veya Saviynt gibi bir iş ortağı idare ürünü veya diğerleri aracılığıyla yönetilmesini önerme eğilimindeyim.

Microsoft 365 Defender portalı ve Microsoft 365 Purview uyumluluk portalı rolleri Microsoft 365'e yayılmıştır ve bu rol gruplarının kapsamını ortamın bir alt kümesine (Azure AD yönetim birimleriyle yapabileceğiniz gibi) ekleyemezsiniz. Birçok müşteri nasıl altdelem yapabileceklerini soruyor. Örneğin, "yalnızca AB kullanıcıları için bir DLP ilkesi oluşturun." Bugün, Microsoft 365 Defender ve Microsoft 365 Purview uyumluluk portallarında belirli bir işlev üzerinde haklarınız varsa, kiracıda bu işlevin kapsadığı her şey üzerinde haklarınız vardır. Ancak, birçok ilke ortamın bir alt kümesini hedeflemeye yönelik özelliklere sahiptir (örneğin, "bu [etiketleri](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) yalnızca bu kullanıcılar için kullanılabilir hale getirme"). Doğru idare ve iletişim, çakışmaları önlemek için önemli bir bileşendir. Bazı müşteriler, Microsoft 365 Defender ve Microsoft 365 Purview uyumluluk portallarında alt teslimi ele almak için "kod olarak yapılandırma" yaklaşımını uygulamayı tercih eder. Bazı belirli hizmetler alt birleştirmeyi destekler (aşağıya bakın).

### <a name="service-specific"></a>Hizmete Özgü

Daha önce belirtildiği gibi, birçok müşteri daha ayrıntılı bir temsil modeli elde etmek için aramaktadır. Yaygın bir örnek: "XYZ hizmetini yalnızca Bölüm X kullanıcıları ve konumları için yönetme" (veya başka bir boyut). Bunu yapabilme özelliği her hizmete bağlıdır ve hizmetler ve yetenekler arasında tutarlı değildir. Ayrıca, her hizmetin ayrı ve benzersiz bir RBAC modeli olabilir. Bu modellerin tümünü tartışmak yerine (sonsuza kadar sürecek) her hizmet için ilgili bağlantılar ekliyorum. Bu liste tamamlanmaz, ancak başlamanıza neden olur.

- **Exchange Online** - (/exchange/permissions-exo/permissions-exo)
- **SharePoint Online** - (/sharepoint/manage-site-collection-administrators)
- **Microsoft Teams** - (/microsoftteams/itadmin-readiness)
- **eBulma** - (.. /compliance/index.yml)
  - **İzin Filtreleme -** (.. /compliance/index.yml)
  - **Uyumluluk Sınırları** - (.. /compliance/set-up-compliance-boundaries.md)
  - **eBulma (Premium)** - (.. /compliance/overview-ediscovery-20.md)
- **Yammer** - (/yammer/manage-yammer-users/manage-yammer-admins)
- **Multi-geo** - (.. /enterprise/add-a-sharepoint-geo-admin.md)
- **Dynamics 365** – (/dynamics365/)

  Not: Bu bağlantı belgelerin kökünedir. Yönetici/temsilci modelinde varyasyonları olan birden çok hizmet türü vardır.

- **Power Platform** - (/power-platform/admin/admin-documentation)
  - **Power Apps** - (/power-platform/admin/wp-security)

    Not: Yönetici/temsilci modellerinde varyasyonları olan birden çok tür vardır.

  - **Power Automate** - (/power-automate/environments-overview-admin)
  - **Power BI** - (/power-bi/service-admin-governance)

    Not: Veri platformu güvenliği ve temsilcisi (Power BI bir bileşendir) karmaşık bir alandır.

- **MEM/Intune** - (/mem/intune/fundamentals/role-based-access-control)
- **Uç Nokta için Microsoft Defender** - (/windows/security/threat-protection/microsoft-defender-atp/user-roles)
- **Microsoft 365 Defender** - (.. /security/defender/m365d-permissions.md)
- **Microsoft Defender for Cloud Apps** - (/cloud-app-security/manage-admins)
- **Stream** - (/stream/assign-administrator-user-role)
- **Bilgi engelleri** - (.. /compliance/information-barriers.md)

### <a name="activity-logs"></a>Etkinlik Günlükleri

Office 365 [birleşik bir denetim günlüğüne](../compliance/search-the-audit-log-in-security-and-compliance.md) sahiptir. Bu çok [ayrıntılı bir günlük](/office/office-365-management-api/office-365-management-activity-api-schema), ancak adı çok fazla okumayın. Güvenlik ve uyumluluk gereksinimleriniz için istediğiniz veya ihtiyacınız olan her şeyi içermeyebilir. Ayrıca, bazı müşteriler [Denetim (Premium)](../compliance/advanced-audit.md) ile gerçekten ilgileniyor.

Diğer API'ler aracılığıyla erişilen Microsoft 365 günlüklerine örnek olarak aşağıdaki özellikler verilebilir:

- [Azure AD](/azure/azure-monitor/platform/diagnostic-settings) (Office 365 ile ilgili olmayan etkinlikler)
- [Exchange İleti İzleme](/powershell/module/exchange/get-messagetrace)
- Yukarıda açıklanan Tehdit/UEBA Sistemleri (örneğin, kimlik koruması, Microsoft Defender for Cloud Apps, Uç Nokta için Microsoft Defender vb. Azure AD)
- [Microsoft Purview Bilgi Koruması](../compliance/data-classification-activity-explorer.md)
- [Uç Nokta için Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/api-power-bi)
- [Microsoft Graph](https://graph.microsoft.com)

Öncelikle bir güvenlik ve uyumluluk programı için gereken tüm günlük kaynaklarını belirlemek önemlidir. Ayrıca, farklı günlüklerin farklı satır içi saklama sınırlarına sahip olduğunu unutmayın.

Yönetici temsilcisi perspektifinden bakıldığında, çoğu Microsoft 365 etkinlik günlüğünün yerleşik bir RBAC modeli yoktur. Bir günlüğü görme izniniz varsa, içindeki her şeyi görebilirsiniz. Müşteri gereksiniminin yaygın bir örneği şunlardır: "Etkinliği yalnızca AB kullanıcıları için sorgulamak istiyorum" (veya başka bir boyut). Bu gereksinimi sağlamak için günlükleri başka bir hizmete aktarmamız gerekir. Microsoft bulutunda bunu [Microsoft Sentinel'e](/azure/sentinel/overview) veya [Log Analytics'e](/azure/azure-monitor/learn/quick-create-workspace) aktarmanızı öneririz.

Üst düzey diyagram:

![güvenlik ve uyumluluk programı için günlük kaynaklarının diyagramı.](../media/solutions-architecture-center/identity-beyond-illustration-4.png)

Yukarıdaki diyagram, Günlükleri Olay Hub'ına ve/veya Azure Depolama'ya ve/veya Azure Log Analytics'e göndermeye yönelik yerleşik özellikleri temsil eder. Henüz tüm sistemlerde bu kullanıma uygun sistem yok. Ancak bu günlükleri aynı depoya göndermeye yönelik başka yaklaşımlar da vardır. Örneğin, bkz. [Microsoft Sentinel ile Teams'inizi koruma](https://techcommunity.microsoft.com/t5/azure-sentinel/protecting-your-teams-with-azure-sentinel/ba-p/1265761).

Tüm günlüklerin tek bir depolama konumunda birleştirilmesi, çapraz bağıntılar, özel saklama süreleri, RBAC modelini desteklemek için gereken verilerle artırma gibi ek avantaj içerir. Veriler bu depolama sistemine eklendikten sonra, uygun bir RBAC modeline sahip bir Power BI panosu (veya başka bir görselleştirme türü) oluşturabilirsiniz.

Günlüklerin yalnızca bir yere yönlendirilmesi gerekmez. Power [BI'da](../admin/usage-analytics/usage-analytics.md) [Office 365 Günlüklerini Microsoft Defender for Cloud Apps](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) veya özel bir RBAC modeliyle tümleştirmek de yararlı olabilir. Farklı depoların farklı avantajları ve hedef kitleleri vardır.

Microsoft 365 Defender adlı bir hizmette güvenlik, tehditler, güvenlik açıkları vb. için çok zengin bir yerleşik analiz sistemi olduğunu belirtmek [gerekir](../security/defender/microsoft-365-defender.md).

Birçok büyük müşteri bu günlük verilerini üçüncü taraf bir sisteme (örneğin, SIEM) aktarmak ister. Bunun için farklı yaklaşımlar vardır, ancak genel olarak [Azure Olay Hub'ı](/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) ve [Graph](/graph/security-integration) iyi başlangıç noktalarıdır.

### <a name="azure"></a>Azure

Genellikle Azure AD, Azure ve SaaS arasında yüksek ayrıcalıklı rolleri ayırmanın bir yolu olup olmadığı sorulur (örneğin: Office 365 için Genel Yönetici ancak Azure değil). Pek değil. Tam yönetim ayrımı gerekiyorsa çok kiracılı mimari gereklidir, ancak bu önemli [bir karmaşıklık](https://aka.ms/multi-tenant-user) ekler (yukarıya bakın). Tüm bu hizmetler aynı güvenlik/kimlik sınırının bir parçasıdır (yukarıdaki hiyerarşi modeline bakın).

Aynı kiracıdaki çeşitli hizmetler arasındaki ilişkileri anlamak önemlidir. Azure, Office 365 ve Power Platform'a (ve genellikle şirket içi ve üçüncü taraf bulut hizmetlerine) yayılan iş çözümleri oluşturan birçok müşteriyle çalışıyorum. Yaygın örneklerden biri:

1. Bir dizi belge/görüntü/vb üzerinde işbirliği yapmak istiyorum (Office 365)
2. Her birini bir onay işlemi aracılığıyla gönderme (Power Platform)
3. Tüm bileşenler onaylandıktan sonra, bu öğeleri birleşik bir teslim edilebilir (Azure) (Azure) olarak bir araya getirerek [Microsoft Graph API](/azure/active-directory/develop/microsoft-graph-intro) burada en iyi arkadaşınızdır. İmkânsız değildir, ancak [birden çok kiracıyı](/azure/active-directory/develop/single-and-multi-tenant-apps) kapsayan bir çözüm tasarlamak çok daha karmaşıktır.

Azure Role-Based Access Control (RBAC), Azure için ayrıntılı erişim yönetimi sağlar. RBAC kullanarak, kullanıcılara işlerini gerçekleştirmek için gereken en az izni vererek kaynaklara erişimi yönetebilirsiniz. Ayrıntılar bu belgenin kapsamı dışındadır, ancak RBAC hakkında daha fazla bilgi için bkz. [Azure'da rol tabanlı erişim denetimi (RBAC) nedir?](/azure/role-based-access-control/overview) RBAC, Azure için idare konusunda dikkat edilmesi gerekenlerin yalnızca bir parçasıdır. [Bulut Benimseme Çerçevesi](/azure/cloud-adoption-framework/govern/) daha fazla bilgi edinmek için harika bir başlangıç noktasıdır. Arkadaşım [Andres Ravinet'in](https://www.linkedin.com/in/andres-ravinet/) müşterilere adım adım adım eşlik etme şeklini seviyorum ancak yaklaşıma karar vermek için çeşitli bileşenler var. Çeşitli öğeler için üst düzey görünüm (gerçek müşteri modeline ulaşmak kadar iyi değil) şöyledir:

![Temsilcili yönetim için Azure bileşenlerinin üst düzey görünümü.](../media/solutions-architecture-center/identity-beyond-illustration-5.png)

Yukarıdaki resimde görebileceğiniz gibi, diğer birçok hizmet tasarımın bir parçası olarak düşünülmelidir (örneğin: [Azure İlkeleri](/azure/governance/policy/overview), [Azure Blueprints](/azure/governance/blueprints/overview), [Yönetim Grupları](/azure/governance/management-groups/) vb.).

## <a name="conclusion"></a>Sonuç

Kısa bir özet olarak başladım, beklediğimden daha uzun bir süre sona erdi. Umarım artık kuruluşunuz için temsilci modeli oluşturma konusunda ayrıntılı bir bakışa başlamaya hazırsınızdır. Bu konuşma müşterilerle çok yaygındır. Herkes için çalışan bir model yoktur. Müşteriler genelinde gördüğümüz yaygın desenleri belgelemeden önce Microsoft mühendisliğinden birkaç planlı geliştirme bekleniyor. Bu arada, microsoft hesabı ekibinizle birlikte çalışarak en yakın [Microsoft Teknoloji Merkezi'ne](https://www.microsoft.com/mtc) bir ziyaret ayarlayabilirsiniz. Orada görüşürüz!
