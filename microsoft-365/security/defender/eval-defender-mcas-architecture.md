---
title: Microsoft Defender for Cloud Apps için mimari gereksinimlerini ve yapısını gözden geçirin
description: Microsoft Defender for Cloud Apps teknik diyagramlar, pilot bir ortam oluşturmanıza yardımcı olacak Microsoft 365 Defender mimarisini açıklar.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
- tier1
ms.topic: conceptual
ms.openlocfilehash: 30e7d46cfc07035b073b39f878a6dc8c11040817
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68048956"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Apps için mimari gereksinimlerini ve temel kavramları gözden geçirin


**Şunlar için geçerlidir:**

- Microsoft 365 Defender

Bu makale, Microsoft 365 Defender yanı sıra Microsoft Defender for Cloud Apps için değerlendirme ortamını ayarlama işleminde [3.Adım 1'dir](eval-defender-mcas-overview.md). Bu işlem hakkında daha fazla bilgi için [genel bakış makalesine](eval-defender-identity-overview.md) bakın.

Microsoft Defender for Cloud Apps etkinleştirmeden önce mimariyi anladığınızdan ve gereksinimleri karşılayabildiğinize emin olun. 

## <a name="understand-the-architecture"></a>Mimariyi anlama

Microsoft Defender for Cloud Apps bir bulut erişim güvenlik aracısıdır (CASB). CASB'ler, kullanıcılarınızın bulunduğu her yerde ve kullandıkları cihazdan bağımsız olarak, kurumsal kullanıcılarınız ve kullandıkları bulut kaynakları arasında gerçek zamanlı olarak erişime aracılık yapmak için bir ağ geçidi denetleyicisi görevi alır. Microsoft Defender for Cloud Apps, Microsoft 365 Defender dahil olmak üzere Microsoft güvenlik özellikleriyle yerel olarak tümleşir.

Cloud Apps için Defender olmadan, kuruluşunuz tarafından kullanılan bulut uygulamaları, gösterildiği gibi yönetilmeyen ve korumasızdır.

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-a.png" alt-text="Microsoft Defender for Cloud Apps mimarisi" lightbox="../../media/defender/m365-defender-mcas-architecture-a.png":::

Çizimde:
- Bulut uygulamalarının bir kuruluş tarafından kullanımı izlenmez ve korumasızdır. 
- Bu kullanım, yönetilen bir kuruluşta elde edilen korumaların dışında kalır. 

#### <a name="discovering-cloud-apps"></a>Bulut uygulamalarını keşfetme

Bulut uygulamalarının kullanımını yönetmenin ilk adımı, kuruluşunuz tarafından hangi bulut uygulamalarının kullanıldığını keşfetmektir. Bu sonraki diyagramda bulut bulmanın Cloud Apps için Defender ile nasıl çalıştığı gösterilmektedir.

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-b.png" alt-text="Bulut bulmada Microsoft Defender for Cloud Apps mimarisi" lightbox="../../media/defender/m365-defender-mcas-architecture-b.png":::


Bu çizimde, ağ trafiğini izlemek ve kuruluşunuz tarafından kullanılan bulut uygulamalarını keşfetmek için kullanılabilecek iki yöntem vardır.
- C. Cloud App Discovery, Uç Nokta için Microsoft Defender ile yerel olarak tümleşir. Uç Nokta için Defender, BT tarafından yönetilen Windows 10 ve Windows 11 cihazlardan erişilen bulut uygulamalarını ve hizmetlerini raporlar. 
- B. Ağa bağlı tüm cihazlarda kapsama için, uç noktalardan veri toplamak üzere güvenlik duvarlarına ve diğer ara sunuculara Cloud Apps için Defender günlük toplayıcısı yüklenir. Bu veriler analiz için Bulut Uygulamaları için Defender'a gönderilir.

#### <a name="managing-cloud-apps"></a>Bulut uygulamalarını yönetme

Bulut uygulamalarını keşfettikten ve bu uygulamaların kuruluşunuz tarafından nasıl kullanıldığını analiz ettikten sonra, seçtiğiniz bulut uygulamalarını yönetmeye başlayabilirsiniz. 

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-c.png" alt-text="Bulut uygulamalarını yönetirken Microsoft Defender for Cloud Apps mimarisi" lightbox="../../media/defender/m365-defender-mcas-architecture-c.png":::

Bu çizimde:
- Bazı uygulamalar kullanım için tasdik edilir. Bu tasdik, uygulamaları yönetmeye başlamanın basit bir yoludur.
- Uygulamaları uygulama bağlayıcılarına bağlayarak daha fazla görünürlük ve denetim sağlayabilirsiniz. Uygulama bağlayıcıları, uygulama sağlayıcılarının API'lerini kullanır.


#### <a name="applying-session-controls-to-cloud-apps"></a>Bulut uygulamalarına oturum denetimleri uygulama

Microsoft Defender for Cloud Apps, tasdikli bulut uygulamalarına ara sunucu erişimi sağlayan bir ters proxy görevi görür. Bu sağlama, Cloud Apps için Defender'ın yapılandırdığınız oturum denetimlerini uygulamasına olanak tanır. 

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-d.png" alt-text="Microsoft Defender for Cloud Apps - Ara sunucu erişim oturumu denetimi mimarisi" lightbox="../../media/defender/m365-defender-mcas-architecture-d.png":::

Bu çizimde:
- Kuruluşunuzdaki kullanıcılardan ve cihazlardan tasdikli bulut uygulamalarına erişim, Bulut Uygulamaları için Defender aracılığıyla yönlendirilir.
- Bu ara sunucu erişimi, oturum denetimlerinin uygulanmasına izin verir.
- Tasdik edilmemiş veya açıkça tasdik edilmemiş bulut uygulamaları etkilenmez.

Oturum denetimleri, bulut uygulamalarının kuruluşunuz tarafından nasıl kullanıldığına parametreler uygulamanıza olanak sağlar. Örneğin, kuruluşunuz Salesforce kullanıyorsa yalnızca yönetilen cihazların Salesforce'ta kuruluşunuzun verilerine erişmesine izin veren bir oturum ilkesi yapılandırabilirsiniz. Daha basit bir örnek, daha katı ilkeler uygulamadan önce bu trafiğin riskini analiz edebilmeniz için yönetilmeyen cihazlardan gelen trafiği izlemek için bir ilke yapılandırmak olabilir.

#### <a name="integrating-with-azure-ad-with-conditional-access-app-control"></a>Koşullu Erişim Uygulama Denetimi ile Azure AD tümleştirme

Çok faktörlü kimlik doğrulamasını ve diğer koşullu erişim ilkelerini zorunlu kılmak için Azure AD kiracınıza zaten SaaS uygulamaları eklenmiş olabilir. Microsoft Defender for Cloud Apps Azure AD ile yerel olarak tümleşir. Tek yapmanız gereken, Cloud Apps için Defender'da Koşullu Erişim Uygulama Denetimi'ni kullanmak üzere Azure AD'da bir ilke yapılandırmaktır. Bu, bu yönetilen SaaS uygulamaları için ağ trafiğini, Bulut Uygulamaları için Defender'ın bu trafiği izlemesine ve oturum denetimlerini uygulamasına olanak tanıyan bir proxy olarak Cloud Apps için Defender aracılığıyla yönlendirir. 

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-e.png" alt-text="Microsoft Defender for Cloud Apps için mimari - SaaS uygulamaları" lightbox="../../media/defender/m365-defender-mcas-architecture-e.png":::

Bu çizimde:
- SaaS uygulamaları Azure AD kiracısıyla tümleşiktir. Bu tümleştirme, Azure AD çok faktörlü kimlik doğrulaması da dahil olmak üzere koşullu erişim ilkelerini zorlamasına olanak tanır.
- SaaS uygulamalarının trafiğini Cloud Apps için Defender'a yönlendirmek için Azure Active Directory'ye bir ilke eklenir. İlke, bu ilkenin uygulanacağı SaaS uygulamalarını belirtir. Bu nedenle, Azure AD bu SaaS uygulamaları için geçerli olan tüm koşullu erişim ilkelerini zorunlu kıldıktan sonra Azure AD ardından oturum trafiğini Cloud Apps için Defender aracılığıyla yönlendirir (proxy'ler).
- Cloud Apps için Defender bu trafiği izler ve yöneticiler tarafından yapılandırılan tüm oturum denetimi ilkelerini uygular. 

Bulut uygulamaları için Defender'ı kullanarak Azure AD eklenmemiş bulut uygulamalarını keşfetmiş ve tasdik etmiş olabilirsiniz. Bu bulut uygulamalarını Azure AD kiracınıza ve koşullu erişim kurallarınızın kapsamına ekleyerek Koşullu Erişim Uygulama Denetimi'nin avantajlarından yararlanabilirsiniz.

#### <a name="protecting-your-organization-from-hackers"></a>Kuruluşunuzu korsanlardan koruma

Cloud Apps için Defender kendi başına güçlü koruma sağlar. Ancak, Microsoft 365 Defender diğer özellikleriyle birleştirildiğinde, Cloud Apps için Defender paylaşılan sinyallere (birlikte) saldırıların durdurulmasını sağlayan veriler sağlar.

Genel bakıştan bu Microsoft 365 Defender değerlendirme ve pilot kılavuza kadar bu çizimi tekrar etmeye değer. 

:::image type="content" source="../../media/defender/m365-defender-eval-threat-chain.png" alt-text="Microsoft 365 Defender tehdit zincirini nasıl durdurur?" lightbox="../../media/defender/m365-defender-eval-threat-chain.png":::

Bu çizimin sağ tarafına odaklanarak Microsoft Defender for Cloud Apps imkansız seyahat, kimlik bilgisi erişimi ve olağan dışı indirme, dosya paylaşımı veya posta iletme etkinliği gibi anormal davranışlar fark eder ve bu davranışları güvenlik ekibine bildirir. Bu nedenle, Bulut Uygulamaları için Defender, korsanların yanal hareketini önlemeye ve hassas verilerin sızmasını önlemeye yardımcı olur. Bulut için Microsoft 356 Defender, tüm bileşenlerden gelen sinyalleri ilişkilendirerek tam saldırı hikayesi sağlar.

## <a name="understand-key-concepts"></a>Temel kavramları anlama

Aşağıdaki tabloda, Microsoft Defender for Cloud Apps değerlendirilirken, yapılandırılırken ve dağıtılırken anlaşılması gereken önemli kavramlar tanımlanmıştır.


|Kavram  |Açıklama |Daha fazla bilgi  |
|---------|---------|---------|
| Cloud Apps için Defender Panosu | Kuruluşunuzla ilgili en önemli bilgilere genel bir bakış sunar ve daha derin araştırmalara bağlantılar sunar.        | [Panoyla çalışma ](/cloud-app-security/daily-activities-to-protect-your-cloud-environment)       |
| Koşullu Erişim Uygulama Denetimi    | Azure AD koşullu erişim ilkeleri sağlamak ve oturum denetimlerini seçmeli olarak zorunlu kılmak için Kimlik Sağlayıcınızla (IdP) tümleşen ters ara sunucu mimarisi.        |  [Microsoft Defender for Cloud Apps Koşullu Erişim Uygulama Denetimi ile uygulamaları koruma](/cloud-app-security/proxy-intro-aad)       |
|  Cloud App Kataloğu   | Bulut Uygulaması Kataloğu, 80'den fazla risk faktörüne göre derecelendirilen ve puanlanan 16.000'den fazla bulut uygulamasından oluşan Microsoft kataloğunda tam bir resim sunar.    |  [Uygulama risk puanları ile çalışma](/cloud-app-security/risk-score)       |
| Cloud Discovery Panosu    | Cloud Discovery, trafik günlüklerinizi analiz eder ve bulut uygulamalarının kuruluşunuzda nasıl kullanıldığı hakkında daha fazla içgörü sağlamanın yanı sıra uyarılar ve risk düzeyleri sağlamak için tasarlanmıştır.     |  [Bulunan uygulamalarla çalışma   ](/cloud-app-security/discovered-apps)    |
|Bağlı Uygulamalar |Cloud Apps için Defender, Koşullu Uygulama Erişim Denetimlerimizi kullanarak Buluttan Buluta tümleştirme, API bağlayıcıları ve gerçek zamanlı erişim ve oturum denetimlerini kullanarak bağlı uygulamalar için uçtan uca koruma sağlar. |[Bağlı uygulamaları koruma](/cloud-app-security/protect-connected-apps) |
| | | |

## <a name="review-architecture-requirements"></a>Mimari gereksinimleri gözden geçirin

### <a name="discovering-cloud-apps"></a>Bulut uygulamalarını keşfetme

Ortamınızda kullanılan bulut uygulamalarını bulmak için aşağıdaki yöntemlerden birini veya ikisini birden uygulayabilirsiniz:

- Uç Nokta için Microsoft Defender ile tümleştirerek Cloud Discovery ile hızla çalışmaya başlayın. Bu yerel tümleştirme, ağınızdaki ve ağınızdaki Windows 11 ve Windows 10 cihazlarınızda bulut trafiğiyle ilgili verileri hemen toplamaya başlamanızı sağlar.
- Ağınıza bağlı tüm cihazlar tarafından erişilen tüm bulut uygulamalarını bulmak için, güvenlik duvarlarınıza ve diğer proxy'lerinize Cloud Apps için Defender günlük toplayıcısını dağıtın. Bu dağıtım uç noktalarınızdan veri toplamaya yardımcı olur ve analiz için Bulut Uygulamaları için Defender'a gönderir. Cloud Apps için Defender, daha da fazla özellik için bazı üçüncü taraf proxy'lerle yerel olarak tümleşir.

Bu seçenekler [2. Adım'da yer alır. Değerlendirme ortamını etkinleştirin](eval-defender-mcas-enable-eval.md). 

### <a name="applying-azure-ad-conditional-access-policies-to-cloud-apps"></a>Bulut uygulamalarına Azure AD Koşullu Erişim ilkeleri uygulama

Koşullu Erişim Uygulama Denetimi (bulut uygulamalarına Koşullu Erişim ilkeleri uygulama özelliği), Azure AD ile tümleştirme gerektirir. Bu tümleştirme, Cloud Apps için Defender'ı kullanmaya başlamak için gerekli değildir. Bu, pilot aşamasında denemenizi tavsiye ettiğimiz bir adımdır: [3. Adım. Pilot Microsoft Defender for Cloud Apps](eval-defender-mcas-pilot.md).

## <a name="siem-integration"></a>SIEM tümleştirmesi

Bağlı uygulamalardan gelen uyarıların ve etkinliklerin merkezi olarak izlenmesini sağlamak için Microsoft Defender for Cloud Apps genel SIEM sunucunuzla veya Microsoft Sentinel ile tümleştirebilirsiniz. 

Ayrıca Microsoft Sentinel, Microsoft Sentinel ile daha ayrıntılı tümleştirme sağlamak için bir Microsoft Defender for Cloud Apps bağlayıcısı içerir. Bu düzenleme yalnızca bulut uygulamalarınıza görünürlük sağlamakla kalmaz, aynı zamanda siber tehditleri belirleyip bunlarla mücadele etmek ve verilerinizin nasıl ilerlediğini denetlemek için gelişmiş analizler elde etmenizi sağlar.

- [Genel SIEM tümleştirmesi](/cloud-app-security/siem)
- [Cloud Apps için Defender'dan Microsoft Sentinel'e uyarıları ve Cloud Discovery günlüklerini akışla aktarma](/azure/sentinel/connect-cloud-app-security)

### <a name="next-steps"></a>Sonraki adımlar

Adım 2 / 3: [Microsoft Defender for Cloud Apps için değerlendirme ortamını etkinleştirme](eval-defender-mcas-enable-eval.md)

[Değerlendirme Microsoft Defender for Cloud Apps](eval-defender-mcas-overview.md) için genel bakışa dönün

[Değerlendirme ve pilot Microsoft 365 Defender](eval-overview.md) genel bakışa dönün
