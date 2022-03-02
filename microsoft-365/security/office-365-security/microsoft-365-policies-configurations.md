---
title: Sıfır Güven kimliği ve cihaz erişimi yapılandırmaları - Microsoft 365 yapılandırmaları
description: Sıfır Güven için güvenli e-posta, belge ve uygulama ilkelerini ve yapılandırmalarını dağıtmak için Microsoft önerilerini ve temel kavramları açıklar.
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-overview
- m365solution-zero-trust
ms.technology: mdo
ms.openlocfilehash: 01fb2a01903eba98f9659d0fd6d85fff4507d72f
ms.sourcegitcommit: aac7e002ec6e10a41baa2d0bd38614b0ed471a70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/27/2022
ms.locfileid: "63009998"
---
# <a name="zero-trust-identity-and-device-access-configurations"></a>Sıfır Güven kimliği ve cihaz erişimi yapılandırmaları

Bir kuruluşun teknoloji kaynaklarını ve hizmetlerini yalıtmak ve erişimi kısıtlamak için ağ güvenlik duvarlarına ve sanal özel ağlara (VPN' ler) güvenen güvenlik mimarileri, artık geleneksel şirket ağı sınırlarının ötesinde uygulamalara ve kaynaklara erişmeyi gerektiren iş gücü için artık yeterli olmaz.

Bu yeni bilgi işlem dünyasına hitap etmek için, Microsoft şu yol gösteren ilkelere dayalı olan Sıfır Güven güvenlik modelini kesinlikle önermektedir:

- Açık bir şekilde doğrulama

  Her zaman kullanılabilir tüm veri noktalarına göre kimlik doğrulama ve yetkilendirme. Bu noktada, Sıfır Güven kimliği ve cihaz erişim ilkeleri oturum açma ve devam eden doğrulama için çok önemlidir.

- En az ayrıcalık erişimini kullanma

  Kullanıcı erişimini Just-In-Time ve Just-Enough-Access (JIT/JEA), risk tabanlı uyarlanabilir ilkeler ve veri koruması ile sınırlandırın.  

- İhlal olduğu varsay

  Yarıçap yarıçapını ve segment erişimini en aza indirgeyin. Ender şifrelemeyi doğrulayın ve görünürlük elde etmek, tehdit algılamayı geliştirmek ve savunmayı geliştirmek için çözümlemeleri kullanın.

Sıfır Güven'in genel mimarisi aşağıdaki gibidir.

:::image type="content" source="../../media/microsoft-365-policies-configurations/zero-trust-architecture.png" alt-text="Microsoft Sıfır Güven mimarisi" lightbox="../../media/microsoft-365-policies-configurations/zero-trust-architecture.png":::

Sıfır Güven kimliği ve cihaz erişim ilkeleri, Aşağıdakiler **için açıkça** temel ilkeyi doğrula::

- Kimlikler

  Kimlik bir kaynağa erişmeye geldiğinde, güçlü kimlik doğrulamasıyla kimliği doğrulayın ve istenen erişimin uyumlu ve normal olduğundan emin olur.

- Cihazlar (uç noktalar olarak da adlandırılan)

  Güvenli erişim için cihaz sistem durumu ve uyumluluk gereksinimlerini takip edin ve zorunlu kılın.

- Uygulamalar

  Gölge IT'sini keşfetmek, uygun uygulama için izinleri sağlamak, gerçek zamanlı çözümlemeye dayalı olarak kapı erişimi sağlamak, olağandışı davranışı izlemek, kullanıcı eylemlerini kontrol etmek ve güvenli yapılandırma seçeneklerini doğrulamak için denetimler ve teknolojiler uygulayabilirsiniz.

Bu makale dizisinde, Azure Active Directory'e Sıfır Güven erişimi için kimlik ve cihaz erişimi önkoşullu yapılandırmaları ve Azure Active Directory (Azure AD) Koşullu Erişim, Microsoft Intune ve diğer ilkeler açık Microsoft 365  Azure AD Uygulama Ara Sunucusu ile yayımlanan kurumsal bulut uygulamaları ve hizmetleri, diğer SaaS hizmetleri ve şirket içi uygulamalar için.

Sıfır Güven kimliği ve cihaz erişim ayarları ve ilkeleri üç katmanda önerilir: başlangıç noktası, kurumsal ve özel güvenlik ve yüksek düzeyde düzenlemeye tabi veya sınıflandırılmış veriler olan ortamlar için. Bu katmanlar ve bunlara karşılık gelen yapılandırmalar verileriniz, kimlikleriniz ve cihazlarınız arasında tutarlı Sıfır Güven koruma düzeyleri sağlar.

Bu özellikler ve onların önerileri:

- Microsoft 365 E3 ve Microsoft 365 E5.
- Azure AD'de [kimlik puanının yanı sıra Microsoft Güvenli](../defender/microsoft-secure-score.md) [Puanı'nın](/azure/active-directory/fundamentals/identity-secure-score) yanı sıra uyumlu hale gelir ve bu puanları organizasyonunız için artıracaktır.
- Kimlik altyapının güvenliğini sağlamak [için bu beş adımı uygulamanıza yardımcı olur](/azure/security/azure-ad-secure-steps).

Kuruluşta benzersiz ortam gereksinimleri veya karmaşıklıklar varsa, başlangıç noktası olarak bu önerileri kullanın. Bununla birlikte, çoğu kuruluş bu önerileri, öngörülen şekilde uygulayamaz.

Kurumsal kimlik ve cihaz erişimi yapılandırmalarına hızlı bir genel bakış için bu Microsoft 365 izleyin.

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxEDQ]

> [!NOTE]
> Microsoft ayrıca, Enterprise Mobility + Security abonelikleri için Enterprise Mobility + Security (EMS) Office 365 satar. EMS E3 ve EMS E5 özellikleri, e-posta ve Microsoft 365 E3 özelliklerle Microsoft 365 E5. Ayrıntılar [için EMS](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing) planlarına bakın.

## <a name="intended-audience"></a>Hedef kitle

Bu öneriler; Azure AD (kimlik), Microsoft Intune (cihaz yönetimi) ve Microsoft Bilgi Koruması (veri koruması) dahil olmak üzere Microsoft 365 bulut üretkenliği ve güvenlik hizmetlerini bilen kurumsal mimarlara ve BT uzmanlarına yöneliktir.

### <a name="customer-environment"></a>Müşteri ortamı

Önerilen ilkeler, hem tamamen Microsoft bulutu içinde çalışan kurumsal kuruluşlara hem de Azure AD kiracısı ile eşitlenen şirket içi Active Directory Etki Alanı Hizmetleri (AD DS) ormanı olan karma kimlik altyapısına sahip müşteriler için geçerlidir.

Sağlanan önerilerin çoğu, E5 Güvenlik eklenti, EMS E5 veya Microsoft 365 E5 Microsoft 365 E3 lisansları ile sağlanan hizmetlere Azure AD Premium P2 güvenmektedir.

Bu lisanslara sahip olan kuruluşlar için Microsoft en azından tüm proje planlarına dahil olan güvenlik varsayılanları [](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)uygulama Microsoft 365 öneririz.

### <a name="caveats"></a>Uyarılar

Bu önerilen yapılandırmalardan ayrı olarak ilkeleri uygulamanızı gerektirecek belirli öneriler de dahil olmak üzere, organizasyonuz yasal düzenlemelere veya diğer uyumluluk gereksinimlerine tabi olabilir. Bu yapılandırmalar, geçmişte hiç kullanılabilir olmadığınız kullanım denetimleri önerin. Güvenlik ve verimlilik arasındaki dengeyi temsil edeceklerine inandığımız için bu denetimleri öneririz.

Çok çeşitli kurumsal koruma gereksinimlerini karşılamak için elimizden gelenin en iyisini yaptık, ancak tüm olası gereksinimleri ya da kuruma özgü yönlerini hesaba hazır bir şekilde ala bire bir hesaplayam.

## <a name="three-tiers-of-protection"></a>Korumanın üç katmanı

Çoğu kuruluşun güvenlik ve veri korumasıyla ilgili belirli gereksinimleri vardır. Bu gereksinimler, sektör segmentinde ve kuruluşlar içindeki iş işlevlerine göre değişiklik gösterir. Örneğin, hukuk departmanınız ve yöneticileriniz e-posta yazışmaları çevresinde başka iş birimleri için gerekli değildir ve bu denetimler için ek güvenlik ve bilgi koruma denetimleri gerekebilir.

Her endüstrinin ayrıca özel yasal düzenlemelere sahip olduğunu da ifade edin. Tüm olası güvenlik seçeneklerinin listesini ya da endüstri segmenti veya iş işlevine göre öneri sağlamak yerine, ihtiyaçlarınızı ayrıntılı olarak temel alan üç farklı güvenlik ve koruma düzeyi için öneriler sağlanmıştır.

- **Başlangıç noktası**: Tüm müşterilerin, verilerinize erişen kimliklerin ve cihazların yanı sıra verileri korumak için en düşük standardı kurmalarını ve kullanmalarını öneririz. Tüm kuruluşlar için başlangıç noktası olarak güçlü varsayılan koruma sağlamak için bu önerileri takip edin.
- **Enterprise**: Bazı müşterilerin daha yüksek düzeylerde korunması gereken bir veri alt kümesi vardır veya tüm verilerin daha yüksek düzeyde korunmasını gerekli olabilir. Çalışma ortamınıza, tüm veya belirli veri kümelerini daha Microsoft 365 uygulayabilirsiniz. Hassas verilere erişen kimlikleri ve cihazları, karşılaştırılabilir güvenlik düzeyleriyle korumanız önerilir.
- **Özel güvenlik**: Gerektiğinde, çok az miktarda veriye sahip olan, üst düzeyde sınıflandırılmış, ticari sırlardan biri olan veya düzenlemeye tabi olan birkaç müşteri vardır. Microsoft, bu müşterilerin bu gereksinimleri karşılamalarına yardımcı olacak, kimlikler ve cihazlara ek koruma da dahil olmak üzere özellikler sunar.

![Güvenlik konisi - Tüm > Bazı müşteriler > birkaç müşteri olabilir](../../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png)

Bu kılavuz, bu koruma düzeylerinin her biri için kimlikler ve cihazlara Sıfır Güven Koruması'nın nasıl uygulandığını gösterir. Bu kılavuzu, organizasyonunız için en az olarak kullanın ve ilkeleri, kuruma özel gereksinimlerine uygun olarak ayarlayın.

Kimlikleriniz, cihazlarınız ve verileriniz arasında tutarlı bir koruma düzeyleri kullanmak önemlidir. Örneğin,&mdash; öncelik hesabına sahip kullanıcılar için koruma (yöneticiler,&mdash; liderler, yöneticiler ve diğerleri gibi) kimlikleri, cihazları ve erişimleri için aynı koruma düzeyini içermeli. 
<!--

The **Zero Trust identity and device protection for Microsoft 365** architecture model shows you which capabilities are comparable.

[![Thumb image for Zero Trust Identity and device protection for Microsoft 365 poster.](../../media/microsoft-365-policies-configurations/zero-trust-id-device-protection-model-thumbnail.png)](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) <br> [View as a PDF](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Download as a PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.pdf)  \| [Download as a Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.vsdx)

--> 

Ayrıca, Bu makalede [depolanan bilgileri korumak için veri gizliliği düzenlemelerine](../../solutions/information-protection-deploy.md) ilişkin çözüm için Bilgi korumasını dağıtma Microsoft 365.

## <a name="security-and-productivity-trade-offs"></a>Güvenlik ve üretkenlik ticari artışları

Herhangi bir güvenlik stratejisinin uygulanması, güvenlik ve verimlilik arasında ticarete açıklık gerektirir. Her kararın güvenlik, işlev ve kullanım kolaylığı bakiyesini nasıl etkileyeceğini değerlendirmek yararlı olur.

![Güvenlik üç durumlu dengeleme güvenlik, işlevsellik ve kullanım kolaylığı.](../../media/microsoft-365-policies-configurations/security-triad.png)

Sağlanan öneriler aşağıdaki ilkelere dayalıdır:

- Kullanıcılarınızı tanıyor ve güvenlik ve işlevsel gereksinimlerine göre esnek olun.
- Tam zamanında bir güvenlik ilkesi uygulayabilir ve anlamlı olduğundan emin olursunuz.

## <a name="services-and-concepts-for-zero-trust-identity-and-device-access-protection"></a>Sıfır Güven kimliği ve cihaz erişim koruması için hizmetler ve kavramlar

Microsoft 365 kurumsal çözümler, büyük kuruluşlar için herkesin yaratıcı olması ve güvenli bir şekilde birlikte çalışması için güç katıyor.

Bu bölümde, Sıfır Güven kimliği Microsoft 365 cihaz erişimi için önemli olan en yeni hizmet ve özelliklere genel bir bakış yer almaktadır.

### <a name="azure-ad"></a>Azure AD

Azure AD, tam bir kimlik yönetimi özellikleri paketi sağlar. Erişimin güvenliğini sağlamak için bu özellikleri kullanmalarını öneririz.

|Özellik veya özellik|Açıklama|Lisanslama|
|---|---|---|
|[Çok faktörlü kimlik doğrulaması (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)|MFA, kullanıcıların iki tür doğrulama (kullanıcı parolası, ayrıca Microsoft Authenticator uygulamasından gelen bildirim veya telefon görüşmesi gibi) sağlamasını gerektirir. MFA, çalınmış kimlik bilgilerinin ortamınıza erişmek için kullanılma riskini büyük ölçüde azaltır. Microsoft 365, MFA tabanlı oturum açmalarda Azure AD Multi-Factor Authentication hizmetini kullanır.|Microsoft 365 E3 E5|
|[Koşullu Erişim](/azure/active-directory/conditional-access/overview)|Azure AD, kullanıcının oturum açma koşullarını değerlendirir ve izin verilen erişimi belirlemek için Koşullu Erişim ilkelerini kullanır. Örneğin, bu kılavuzda size hassas verilere erişim için cihaz uyumluluğu gerektirmeye yönelik bir Koşullu Erişim ilkesi oluşturma hakkında bilgi sağlarız. Bu, bilgisayar korsanı ve çalınmış kimlik bilgileriyle hassas verilerinize erişme riskini önemli ölçüde azaltır. Ayrıca cihazlar hassas verileri de korur, çünkü cihazlar sistem durumu ve güvenlik için belirli gereksinimleri karşılamalıdır.|Microsoft 365 E3 E5|
|[Azure AD grupları](/azure/active-directory/fundamentals/active-directory-manage-groups)|Koşullu Erişim ilkeleri, Intune ile cihaz yönetimi, hatta kuruluşta dosyaların ve sitelerin izinleri bile atamayı kullanıcı hesaplarına veya Azure AD gruplarına dayandırıyor. Uygulamakta olduğu koruma düzeylerine karşılık gelen Azure AD grupları oluşturmanızı öneririz. Örneğin, üst düzey personeliniz korsanlar için büyük olasılıkla daha yüksek değerli hedeflere sahip. Bu nedenle, bu çalışanların kullanıcı hesaplarını bir Azure AD grubuna eklemek ve bu grubu, erişim için daha yüksek bir koruma düzeyi uygulayan Koşullu Erişim ilkelerine ve diğer ilkelere atamak anlamlıdır.|Microsoft 365 E3 E5|
|[Cihaz kaydı](/azure/active-directory/devices/overview)|Cihaz için bir kimlik oluşturmak için cihazı Azure AD'ye kaydettirebilirsiniz. Bu kimlik, kullanıcı oturum ayaları kullandığında cihazın kimliğini doğrulamak ve etki alanına katılmış veya uyumlu bilgisayarlar gerektiren Koşullu Erişim ilkeleri uygulamak için kullanılır. Bu kılavuzda, etki alanına katılmış cihazları otomatik olarak kaydetmek için cihaz Windows kullanıruz. Cihaz kaydı, Intune ile cihazları yönetmek için önkoşuldur.|Microsoft 365 E3 E5|
|[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)|Kuruluş kimliklerini etkileyen olası güvenlik açıklarını algılamanıza olanak sağlar ve otomatik düzeltme ilkesi düşük, orta ve yüksek oturum açma riski ile kullanıcı risklerini yapılandırabilir. Bu kılavuz, çok faktörlü kimlik doğrulamasına Koşullu Erişim ilkeleri uygulamak için bu risk değerlendirmesini temel almaktadır. Bu kılavuzda ayrıca, kullanıcıların hesapları için yüksek riskli etkinlik algılandığında parolalarını değiştirmelerini gerektiren bir Koşullu Erişim ilkesi de yerlanır.|Microsoft 365 E5, Microsoft 365 E3 E5 Güvenlik eklenti, EMS E5 veya diğer kullanıcı Azure AD Premium P2 seçin|
|[Kendi kendine parola sıfırlama (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)|Yöneticinin denetiminde olduğu birden çok kimlik doğrulama yönteminin doğrulamasını sağlayarak, kullanıcılarınızı parolalarını güvenli bir şekilde ve yardım masası müdahalesi olmadan sıfırlamasına izin verme.|Microsoft 365 E3 E5|
|[Azure AD parola koruması](/azure/active-directory/authentication/concept-password-ban-bad)|Bilinen zayıf parolaları, değişkenlerini ve zayıf olan organizasyona özgü ek zayıf terimlerini algıla ve engelle. Varsayılan genel yasaklanmış parola listeleri, Bir Azure AD kiracısı'nın tüm kullanıcılarına otomatik olarak uygulanır. Özel bir yasaklanan parola listesinde ek girişler tanımlayabilirsiniz. Kullanıcılar parolalarını değiştirse veya sıfırlasa, güçlü parolaların kullanımını zorunlu yapmak için bu yasaklanmış parola listeleri denetlenir.|Microsoft 365 E3 E5|
|

Burada, Intune ve Azure AD nesneleri, ayarlar ve alt hizmetler dahil olmak üzere Sıfır Güven kimliği ve cihaz erişiminin bileşenleri ve bunlar yer almaktadır.

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-device-access-components.png" alt-text="Sıfır Güven kimliği ve cihaz erişiminin bileşenleri." lightbox="../../media/microsoft-365-policies-configurations/identity-device-access-components.png":::

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](/intune/introduction-intune) , Microsoft'un bulut tabanlı mobil cihaz yönetim hizmetidir. Bu kılavuz, Intune içeren Windows ve cihaz uyumluluk ilkesi yapılandırmalarını önermektedir. Intune, cihazların uyumlu olup olmadığını belirler ve Koşullu Erişim ilkeleri uygularken kullanmak üzere bu verileri Azure AD'ye gönderir.

#### <a name="intune-app-protection"></a>Intune uygulama koruması

[Intune uygulama koruma](/intune/app-protection-policy) ilkeleri, mobil uygulamalarda, cihazları yönetime kaydetmeden veya kaydetmeden kuruluş verilerinizi korumak için kullanılabilir. Intune bilgileri korumaya, çalışanlarının üretken olabilir olduğundan emin olmak ve veri kaybını önlemeye yardımcı olur. Uygulama düzeyi ilkeler uygulayarak, şirket kaynaklarına erişimi kısıtlar ve verileri, it departmanınız tarafından kontrol altında tutabilirsiniz.

Bu kılavuzda, onaylı uygulamaların kullanımını zorunlu kılınan önerilen ilkelerin nasıl oluşturularak bu uygulamaların iş verilerinizle nasıl kullanılabileceklerini belirlemesi açıklanmıştır.

### <a name="microsoft-365"></a>Microsoft 365

Bu kılavuzda, Microsoft Teams, Exchange, SharePoint ve diğer bulut hizmetleri dahil olmak üzere Microsoft 365 bulut hizmetlerinin erişimini korumak için bir dizi ilkeyi OneDrive. Bu ilkeleri uygulamaya ek olarak, şu kaynakları kullanarak kiracınız için koruma düzeyini yükseltmenizi de öneririz:

- [Daha yüksek güvenlik için kiracınızı yapılandırma](tenant-wide-setup-for-increased-security.md)

  Öneriler, başlangıç noktası güvenliği için geçerli olan güvenlik.

- [Güvenlik yol haritası: İlk 30 gün, son 90 gün ve daha sonra için en önemli öncelikler](security-roadmap.md)

  Öneriler, veri yönetimi, yönetici erişimi ve tehdit koruması gibi bilgileri içerir.

### <a name="windows-11-or-windows-10-with-microsoft-365-apps-for-enterprise"></a>Windows 11'i veya Windows 10'i Kurumlar için Microsoft 365 Uygulamaları

Windows 11 veya Windows 10, Kurumlar için Microsoft 365 Uygulamaları bilgisayarlar için önerilen istemci ortamıdır. Azure hem Windows Hem Windows 10 Azure AD için mümkün olan en rahat deneyimi sağlamak üzere tasar olduğundan, Azure'a 11 veya daha uzun bir süre için izin Windows 10 öneririz. Windows 11 veya Windows 10, Intune aracılığıyla yönetiliş gelişmiş güvenlik özellikleri de içerir. Kurumlar için Microsoft 365 Uygulamaları, Office uygulamalarının en son sürümlerini içerir. Bunlar daha güvenli olan ve Koşullu Erişim için bir gereksinim olan modern kimlik doğrulamayı kullanır. Bu uygulamalar ayrıca gelişmiş uyumluluk ve güvenlik araçlarını da içerir.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Bu özellikleri korumanın üç katmanı boyunca uygulama

Aşağıdaki tabloda, korumanın üç katmanında bu özellikleri kullanma önerilerimiz özetlenmiştir.

|Koruma mekanizması|Başlangıç noktası|Enterprise|Özel güvenlik|
|---|---|---|---|
|**MFA'nın zorunlu kılınma**|Orta veya üzeri oturum açma riskine karşı|Oturum açma risk altında veya üzerinde|Tüm yeni oturumlarda|
|**Parola değişikliğini zorunlu kılın**|Yüksek riskli kullanıcılar için|Yüksek riskli kullanıcılar için|Yüksek riskli kullanıcılar için|
|**Intune uygulama korumasını zorunlu kılın**|Evet|Evet|Evet|
|**Kuruluşa ait cihaz için Intune kaydı zorunlu kılın**|Uyumlu veya etki alanına katılmış bir bilgisayar gerektirir, ancak kendi cihazlarınızı (BYOD) telefon ve tabletlerinizi getirmenize izin verme|Uyumlu veya etki alanına katılmış bir cihaz gerektirme|Uyumlu veya etki alanına katılmış bir cihaz gerektirme|
|

## <a name="device-ownership"></a>Cihaz sahipliği

Yukarıdaki tablo, birçok kuruluşun iş gücü genelinde mobil üretkenlik sağlamak için kişisel veya BYOD'ların yanı sıra, kuruluşa ait cihazlar karma olarak destekleme eğilimini yansıtıyor. Intune uygulama koruma ilkeleri, e-postanın hem kuruluşa ait cihazlarda hem de BYOD'larda Outlook mobil uygulamasından ve diğer Office mobil uygulamalardan dışarı çıkmalarına karşı korunmasını sağlar.

Ek koruma ve denetim uygulamak için kuruluşa ait cihazların Intune veya etki alanına bağlı olarak yönetillerini öneririz. Veri duyarlılığına bağlı olarak, kuruluş belirli kullanıcı popülasyonları veya belirli uygulamalar için BYODs'a izin vermenizi tercih ediyor olabilir.

## <a name="deployment-and-your-apps"></a>Dağıtım ve uygulamalarınız

Azure AD ile tümleşik uygulamalarınız için Sıfır Güven kimliği ve cihaz erişim yapılandırmasını yapılandırmadan ve bu yapılandırmayı yapılandırmadan önce:

- Organizasyonda hangi uygulamaları korumak istediğinize karar verin.
- Uygun koruma düzeylerini sağlayan ilke kümelerini belirlemek için bu uygulama listesini çözümle.

  Her uygulama için ayrı ilke kümeleri oluşturmamelisiniz çünkü bunların yönetimi zahmetli olabilir. Microsoft, aynı kullanıcılar için aynı koruma gereksinimlerine sahip olan uygulamalarınızı gruplamanızı öneririz.

  Örneğin, başlangıç noktası koruması için tüm kullanıcılarınızı Microsoft 365 uygulamalarını ve insan kaynakları veya finans departmanları tarafından kullanılanlar gibi tüm hassas uygulamalar için ikinci bir ilke kümesi içeren bir ilke kümeniz olabilir ve bunları bu gruplara uygulayabilirsiniz.

Güvenliğini sağlamak istediğiniz uygulamalar için ilke kümesi belirlediktan sonra, bu ilkeleri adım adım kullanıcılarınıza aşamalı olarak ve yol boyunca sorunları çözüm olarak verin.

Örneğin, yalnızca iş veya öğretmen uygulamalarınız için Microsoft 365 için kullanılacak ilkeleri, Exchange değişikliklerle birlikte Exchange. Bu ilkeleri kullanıcılarınıza salım ve tüm sorunları birlikte çalışalım. Ardından, Teams değişikliklerle birlikte yeni bir e-posta ekleyin ve bunu kullanıcılarınıza sn. Ardından, SharePoint değişikliklerle birlikte ekle'yi seçin. Bu başlangıç noktası ilkelerini tüm uygulamalarınızı içerecek şekilde güvenli bir şekilde yapılandırıncaya kadar, uygulamalarınızı diğer Microsoft 365 devam edin.

Benzer şekilde, hassas uygulamalarınız için ilkeler kümesi oluşturun, bir defada tek bir uygulama ekleyin ve hepsi hassas uygulama ilkesi kümesine ekleyene kadar tüm sorunları çözümlenin.

Microsoft, tüm uygulamalara uygulanacak ilke kümeleri oluşturmamanızı öneririz, çünkü bu yapılandırmalar bazı önerilmez yapılandırmalara neden olabilir. Örneğin, tüm uygulamaları engellemeye yönelik ilkeler yöneticilerinizi Azure portaldan dışarı kilitler ve dışlamalar Microsoft güvenlik uygulamaları gibi önemli uç noktalar için Graph.

## <a name="steps-to-configure-zero-trust-identity-and-device-access"></a>Sıfır Güven kimliği ve cihaz erişimini yapılandırma adımları

![Sıfır Güven kimliği ve cihaz erişimini yapılandırma adımları.](../../media/microsoft-365-policies-configurations/identity-device-access-steps.png)

1. Önkoşul kimlik özelliklerini ve ayarlarını yapılandırma.
2. Ortak kimliği yapılandırarak Koşullu Erişim ilkelerine erişin.
3. Konuk ve dış kullanıcılar için Koşullu Erişim ilkelerini yapılandırma.
4. Bulut uygulamaları için Koşullu Microsoft 365 ilkelerini&mdash; Microsoft Teams, Exchange ve SharePoint&mdash; için Microsoft Defender ilkeleri gibi uygulamaları yapılandırabilirsiniz.

Sıfır Güven kimliği ve cihaz erişimini yapılandırdikten sonra, göz önünde tutulacak ek özelliklerin aşamalı denetim listesi ve erişimi korumak, izlemek ve izlemek için [Azure AD](/azure/active-directory/governance/) Kimlik Yönetimi'ni görmek için Azure [AD](/azure/active-directory/fundamentals/active-directory-deployment-checklist-p2) özellik dağıtım kılavuzuna bakın.

## <a name="next-step"></a>Sonraki adım

[Sıfır Güven kimliği ve cihaz erişim ilkelerinin uygulanması için önkoşul çalışma](identity-access-prerequisites.md)