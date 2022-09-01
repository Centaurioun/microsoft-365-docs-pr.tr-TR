---
title: Ön cephe çalışanları için Microsoft 365'i ayarlama
author: samanro
ms.author: samanro
ms.reviewer: samanro
manager: pamgreen
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Ön cephe çalışanlarınız için ihtiyacınız olan hizmetler ve özelliklerle Microsoft 365'i ayarlamayı öğrenin.
ms.localizationpriority: high
ms.collection:
- m365-frontline
- m365solution-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: ad81e7f7f04247be406d77cc54f8d31bd44c187f
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67497637"
---
# <a name="set-up-microsoft-365-for-frontline-workers"></a>Ön cephe çalışanları için Microsoft 365'i ayarlama

Ön cephe çalışanları için Microsoft 365'i ayarlamak için şu genel süreci izleyin:

1. **[Senaryolarınızı belirleme](#step-1-identify-your-scenarios)**: Ön cephe çalışanlarınız için hangi senaryoları uygulamak istiyorsunuz? Hangi senaryoları istediğinizi belirledikten sonra, uygulamak istediğiniz her senaryo için gerekli uygulamaları ve hizmetleri belirlemek için aşağıdaki tabloyu kullanın.
1. **[Ortamınızı ve temel Microsoft 365'i ayarlama: Microsoft 365'i](#step-2-set-up-your-environment-and-core-microsoft-365)** ayarlamak için Microsoft 365 yönetim merkezi Kurulum Kılavuzlarını izleyin. Bu kılavuzlara nasıl erişeceğinizi öğrenmek için okumaya devam edin.
1. **[Microsoft Teams'i ayarlama](#step-3-set-up-microsoft-teams)**: Hizmeti yapılandırmak ve ekiplerinizi oluşturmak için ekleme sihirbazını veya Ekipleri büyük ölçekte dağıtma işlemini kullanın.
1. **[Senaryonuz için gereken diğer hizmetleri ayarlayın](#step-4-set-up-other-services)**: Bu hizmetleri ayarlamak için aşağıdaki bölümlerde yer alan yönergeleri izleyin.
1. **[Uygulamaları yapılandırma](#step-5-configure-apps-for-your-scenario)**: Yönetim merkezinde her şey ayarlandıktan ve yapılandırıldıktan sonra, senaryolarınızın kılavuzunu izleyerek her senaryo için ihtiyacınız olan uygulamaları daha fazla yapılandırabilirsiniz.
1. **[Cihazlar](#step-6-set-up-devices)**: Paylaşılan ve kişisel cihazları Microsoft 365 ve Microsoft Teams ile çalışacak ve ön cephe çalışanlarınızın kuruluşunuz içinde daha güvenli iletişim kurabilmesini sağlayacak şekilde ayarlayın.

:::image type="content" source="media/m365-frontline-setup-steps.png" alt-text="Ön cephe çalışanları için Microsoft 365'i ayarlama adımları." lightbox="media/m365-frontline-setup-steps.png":::

## <a name="step-1-identify-your-scenarios"></a>1. Adım: Senaryolarınızı tanımlama

Aşağıdaki tabloda ön cephe çalışanlarınızın senaryoları listelemektedir. [Senaryolarınızı seçerken](flw-choose-scenarios.md) her senaryonun özetini okuyabilir ve her senaryoya ve gerekli olan her uygulama veya hizmete yönelik bağlantıları izleyerek tam olarak ne yapılandırmanız gerektiğini öğrenebilirsiniz.

| Senaryo | Gerekli hizmetler |
|  ------- | -------  |
| [Ekip iletişimi ve işbirliği](flw-team-collaboration.md) | [Microsoft Teams](#step-3-set-up-microsoft-teams) <br>[Exchange Online ile Email](#set-up-email-with-exchange-online) |
| [Kurumsal İletişimler](flw-corp-comms.md) | [Microsoft Teams](#step-3-set-up-microsoft-teams) <br>[SharePoint](#set-up-sites-with-sharepoint-in-microsoft-365) <br>[Viva Bağlantılar](#set-up-viva-connections) <br>[Yammer](#set-up-your-organizations-social-network-with-yammer) |
| [Sanal randevular](virtual-appointments.md) | [Microsoft Teams](#step-3-set-up-microsoft-teams) |
| [Çalışanlarınızla etkileşim kurun ve çalışanların refahı üzerine odaklanın](flw-wellbeing-engagement.md)| [Microsoft Teams](#step-3-set-up-microsoft-teams) <br>[SharePoint](#set-up-sites-with-sharepoint-in-microsoft-365) <br>[Viva Bağlantılar](#set-up-viva-connections) <br>[Yammer](#set-up-your-organizations-social-network-with-yammer) |
| [Vardiyalar ile ekibinizi zamanlama](shifts-for-teams-landing-page.md) | [Microsoft Teams](#step-3-set-up-microsoft-teams) |
| [Yeni çalışanları ekleme](/sharepoint/onboard-employees)| [Microsoft Teams](#step-3-set-up-microsoft-teams) <br>[SharePoint](#set-up-sites-with-sharepoint-in-microsoft-365) <br>[Viva Bağlantılar](#set-up-viva-connections) <br>[Viva Öğrenme](#set-up-viva-learning)|
| [Devam eden eğitim](flw-onboarding-training.md) | [Microsoft Teams](#step-3-set-up-microsoft-teams) <br>[Viva Öğrenme](#set-up-viva-learning) |
| [İş süreçlerini basitleştirme](simplify-business-processes.md) | [Microsoft Teams](#step-3-set-up-microsoft-teams) <br>[Power Apps, Power Automate ve Power BI](#set-up-power-apps-power-automate-and-power-bi) |

Bazı hizmetler yalnızca e-posta ve Power Platform gibi F3 lisanslarına dahil edilir. Kullanıcılarınız için ihtiyacınız olan lisans türünü belirlemek için [Ön çalışan kullanıcı türlerini ve lisanslamayı anlama](flw-licensing-options.md) bölümüne göz atın.

## <a name="step-2-set-up-your-environment-and-core-microsoft-365"></a>2. Adım: Ortamınızı ve temel Microsoft 365'i ayarlama

Microsoft 365 yönetim merkezi, Microsoft 365'te ürünleri, güvenlik özelliklerini ve işbirliği araçlarını ayarlama adımlarında size yol gösteren bir [dizi Kurulum kılavuzu](/microsoft-365/enterprise/setup-guides-for-microsoft-365) içerir. Kurulum kılavuzları, Microsoft 365 yönetim merkezi [Kurulum kılavuzu sayfasından](https://aka.ms/setupguidance) erişilebilir.

1. Kuruluşunuzun ortamını Microsoft 365 ve Office 365 hizmetlerine hazırlamak için [Ortamınızı hazırlama](https://aka.ms/prepareyourenvironment) kılavuzunu kullanın.
1. Üretkenlik araçlarını, güvenlik ilkelerini ve cihaz yönetimi özelliklerini ayarlamak için [Microsoft 365 kurulum](https://aka.ms/microsoft365setupguide) kılavuzunu kullanın. Kuruluşunuzun cihazlarını ayarlamak ve yapılandırmak için de bu danışmanı kullanabilirsiniz.

## <a name="step-3-set-up-microsoft-teams"></a>3. Adım: Microsoft Teams'i ayarlama

Pilot projede ön cephe çalışanlarınız için yapılandırılmış tek bir ekip ayarlamak için Ön Cephe çalışanı ekleme sihirbazını kullanabilirsiniz. Adım adım yönergeler için bkz [. Ön cephe çalışanlarınızı çalışır duruma getirmek için Ön Cephe Çalışanı ekleme sihirbazını kullanma](flw-onboarding-wizard.md).

Tam dağıtımlar [için, ön cephe çalışanları için Teams'i uygun ölçekte dağıtma](deploy-teams-at-scale.md) yönergelerini izleyin.

## <a name="step-4-set-up-other-services"></a>4. Adım: Diğer hizmetleri ayarlama

### <a name="set-up-email-with-exchange-online"></a>Exchange Online ile e-postayı ayarlama

Ön cephe yöneticilerinizin ve çalışanlarınızın e-postaya erişmesini istiyorsanız, Microsoft 365'te e-postayı ayarlamanız gerekir. Kullanıcıların e-postaya erişmek için F3 lisansına sahip olması gerekir. Ayarlamak için [Email kurulum kılavuzunu](https://aka.ms/office365setup) izleyin.

Kullanıcılarınızın e-postaları için kullanmak üzere Outlook uygulamasını da yükleyebileceğini unutmayın. Bu nedenle, Outlook uygulamasının indirileceği yeri onlarla paylaştığınızdan emin olmak istersiniz.

### <a name="set-up-sites-with-sharepoint-in-microsoft-365"></a>Microsoft 365'te SharePoint ile siteleri ayarlama

[SharePoint](/sharepoint/sharepoint-online) , belgeleri paylaşmanıza ve site oluşturmanıza olanak tanır. Ayarlamak için Microsoft 365 yönetim merkezi [SharePoint kurulum kılavuzunu](https://aka.ms/spoguidance) kullanın.

### <a name="set-up-employee-experiences-with-viva-modules"></a>Viva modülleriyle çalışan deneyimlerini ayarlama

[Microsoft Viva](/viva/microsoft-viva-overview) , iletişimleri, bilgileri, öğrenmeyi, kaynakları ve içgörüleri iş akışında bir araya getiren tümleşik bir çalışan deneyimiyle çalışanları birbirine bağlamaya yardımcı olur. Microsoft Viva,çalışan deneyimleri oluşturmak için Microsoft Teams ile birlikte kullanılabilecek çeşitli modüllere sahiptir.

#### <a name="set-up-viva-connections"></a>Viva Bağlantılar’ı Ayarlayın

Ön cephe çalışanlarınızla iletişime geçmenize ve bunları bilgilendirmenize yardımcı olan bir pano oluşturmak için [Viva Bağlantılar](/viva/connections/viva-connections-overview) kullanın. Viva Bağlantılar, Microsoft Teams'de herkese ilgili haberleri, konuşmaları ve başarılı olmaları için ihtiyaç duydukları araçları keşfetmek için kişiselleştirilmiş bir hedef sağlayan özelleştirilebilir bir uygulamadır. 

Ayarlamak için [Çalışan deneyimini oluşturma kurulum kılavuzunu](https://aka.ms/EmployeeExperienceDashboard) izleyin. [Viva Bağlantılar ayarlama](/viva/connections/guide-to-setting-up-viva-connections) hakkında daha fazla bilgi edinin.

#### <a name="set-up-viva-learning"></a>Viva Öğrenme ayarlama

[Viva Öğrenme](/viva/learning/), Microsoft Teams'de çalışanlara, zaten kullandıkları araçlar ve platformlar içinde öğrenmeyi iş akışına getirerek öğrenmeyi günün doğal bir parçası yapma gücü veren bir uygulamadır. [Viva Öğrenme ayarlamayı öğrenmek için Bkz. Teams yönetim merkezinde](/viva/learning/set-up-viva-learning) Microsoft Viva Öğrenme ayarlama.

### <a name="set-up-your-organizations-social-network-with-yammer"></a>Yammer ile kuruluşunuzun sosyal ağını ayarlama

[Yammer](/yammer) , iş gücünüzle şirketiniz arasında bağlantı kurmanıza yardımcı olur. [Yammer dağıtım danışmanını](https://aka.ms/yammerdeploymentguide) kullanarak ayarlayın.

### <a name="set-up-power-apps-power-automate-and-power-bi"></a>Power Apps, Power Automate ve Power BI'ı ayarlama

Bu uygulamaların tümünü Microsoft Teams'de kullanabilirsiniz. Bunların nasıl ayarlanacağı hakkında daha fazla bilgi için bkz:

- [Power Apps ve Microsoft Teams tümleştirmesi](/powerapps/teams/overview)
- [Power Automate - Microsoft Teams'de akışları kullanma](/power-automate/teams/overview)
- [Power BI ile Microsoft Teams'de işbirliği yapma](/power-bi/collaborate-share/service-collaborate-microsoft-teams)
- [Microsoft Teams'de Power Virtual Agents uygulaması](/power-virtual-agents/teams/fundamentals-what-is-power-virtual-agents-teams)
- [Power Apps](/microsoftteams/manage-power-platform-apps)

## <a name="step-5-configure-apps-for-your-scenario"></a>5. Adım: Senaryonuz için uygulamaları yapılandırma

Yönetim merkezinde her şey ayarlandıktan ve yapılandırıldıktan sonra, senaryolarınızın kılavuzunu izleyerek her senaryo için ihtiyacınız olan uygulamaları daha fazla yapılandırabilirsiniz.

Senaryolar ve uygulamalar

| Senaryo | Onaylar | Rezervasyon | Liste | Övgü | Vardiya | Görevler | Güncelleştirmeler |
| :---- | :----: | :----: | :----: | :----: | :----: | :----: | :----: |
| [Ekip iletişimi ve işbirliği](flw-team-collaboration.md) | &#x2705; | &nbsp; | &#x2705; | &#x2705; | &nbsp; | &#x2705; | &#x2705; |
| [Kurumsal İletişimler](flw-corp-comms.md) |  &nbsp; |  &nbsp; |  &nbsp; |  &nbsp; |  &nbsp; |  &nbsp; |  &nbsp; |
| [Microsoft Teams ve Bookings uygulaması ile sanal randevular](bookings-virtual-visits.md) |  &nbsp; | &#x2705; |  &nbsp; |  &nbsp; | &#x2705; |  &nbsp;|  &nbsp; |
| Dengeli yaşam ve katılım |  &nbsp; |  &nbsp; |  &nbsp; | &#x2705; |  &nbsp; |  &nbsp; | &#x2705; |
| [Vardiyalar ile ekibinizi zamanlama](shifts-for-teams-landing-page.md) |  &nbsp; | &nbsp; | &#x2705; |  &nbsp; | &#x2705; | &#x2705; | &#x2705; |
| [Eğitim: Yeni çalışanları ekleme](/sharepoint/onboard-employees) |  &nbsp; |  &nbsp; | &#x2705; |  &nbsp; |  &nbsp; | &#x2705; | &#x2705; |
| Devam eden eğitim |  &nbsp; |  &nbsp; | &#x2705; |  &nbsp; |  &nbsp; | &#x2705; | &#x2705; |
| [İş süreçlerini basitleştirme](simplify-business-processes.md) | &#x2705; |  &nbsp; | &#x2705; |  &nbsp; |  &nbsp; | &#x2705; | &#x2705; |
| Siteleri, depoları ve projeleri yönetme | &#x2705; |  &nbsp; | &#x2705; |  &nbsp; | &nbsp; | &#x2705; | &#x2705; |

## <a name="step-6-set-up-devices"></a>6. Adım: Cihazları ayarlama

Paylaşılan ve kişisel cihazları Microsoft 365 ve Microsoft Teams ile çalışacak şekilde ayarlamak ve ön cephe çalışanlarınızın kuruluşunuz içinde daha güvenli iletişim kurmasına olanak sağlamak için bkz. [Ön cephe çalışanları için mobil cihazları yönetme](flw-devices.md).
