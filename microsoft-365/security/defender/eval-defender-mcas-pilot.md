---
title: Microsoft 365 Defender ile pilot Microsoft Defender for Cloud Apps
description: Cihazları, kimliği, verileri ve uygulamaları korumak için tasarlanmış güvenlik çözümünü test etmek ve deneyimlemek için Microsoft 365 Defender deneme laboratuvarınızı veya pilot ortamınızı ayarlayın.
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
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
ms.topic: conceptual
ms.openlocfilehash: 68b623bb1e04340e7f112e7e2d0a58210cca0e3b
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480920"
---
# <a name="pilot-microsoft-defender-for-cloud-apps-with-microsoft-365-defender"></a>Microsoft 365 Defender ile pilot Microsoft Defender for Cloud Apps


**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Bu makale, Microsoft Defender for Cloud Apps için değerlendirme ortamını ayarlama [sürecindeki Adım 3/3'tür](eval-defender-mcas-overview.md). Bu işlem hakkında daha fazla bilgi için [genel bakış makalesine](eval-defender-mcas-overview.md) bakın.

Microsoft Defender for Cloud Apps için pilotu ayarlamak ve yapılandırmak için aşağıdaki adımları kullanın.


:::image type="content" source="../../media/defender/m365-defender-mcas-pilot-steps.png" alt-text="Microsoft Defender for Cloud Apps pilot uygulama adımları" lightbox="../../media/defender/m365-defender-mcas-pilot-steps.png":::
- [1. Adım. Pilot grubu oluşturma—Pilot dağıtımınızın kapsamını belirli kullanıcı gruplarına göre belirleyin](#step-1-create-the-pilot-groupscope-your-pilot-deployment-to-certain-user-groups)
- [2. Adım. Korumayı yapılandırma—Koşullu Erişim Uygulama Denetimi](#step-2-configure-protectionconditional-access-app-control)
- [3. Adım. Özellikleri deneyin— Ortamınızı korumaya yönelik öğreticilerde adım adım ilerleyin](#step-3-try-out-capabilitieswalk-through-tutorials-for-protecting-your-environment) 

## <a name="step-1-create-the-pilot-groupscope-your-pilot-deployment-to-certain-user-groups"></a>Adım 1. Pilot grubu oluşturma—Pilot dağıtımınızın kapsamını belirli kullanıcı gruplarına göre belirleyin

Microsoft Defender for Cloud Apps, dağıtımınızın kapsamını oluşturmanıza olanak tanır. Kapsam belirleme, uygulamalar için izlenecek veya izlemenin dışında tutulacak belirli kullanıcı gruplarını seçmenize olanak tanır. Kullanıcı gruplarını dahil edebilir veya dışlayabilirsiniz. Pilot dağıtımınızın kapsamını bulmak için bkz [. Kapsamlı Dağıtım](/cloud-app-security/scoped-deployment).


## <a name="step-2-configure-protectionconditional-access-app-control"></a>Adım 2. Korumayı yapılandırma—Koşullu Erişim Uygulama Denetimi

Yapılandırabileceğiniz en güçlü korumalardan biri Koşullu Erişim Uygulama Denetimi'dir. Bu koruma, Azure Active Directory (Azure AD) ile tümleştirme gerektirir. Tasdiklediğiniz bulut uygulamalarına ilgili ilkeler (sağlıklı cihazlar gerektirme gibi) dahil olmak üzere Koşullu Erişim ilkeleri uygulamanıza olanak tanır. 

SaaS uygulamalarını yönetmek için Microsoft Defender for Cloud Apps kullanmanın ilk adımı, bu uygulamaları bulmak ve sonra bunları Azure AD kiracınıza eklemektir. Bulma konusunda yardıma ihtiyacınız varsa bkz. [Ağınızdaki SaaS uygulamalarını bulma ve yönetme](/cloud-app-security/tutorial-shadow-it). Uygulamaları keşfettikten sonra [bu uygulamaları Azure AD kiracınıza ekleyin](/azure/active-directory/manage-apps/add-application-portal).

Aşağıdaki görevleri yürüterek bu uygulamaları yönetmeye başlayabilirsiniz:

- İlk olarak, Azure AD yeni bir koşullu erişim ilkesi oluşturun ve bunu "Koşullu Erişim Uygulama Denetimi Kullan" olarak yapılandırın. Bu yapılandırma, isteğin Cloud Apps için Defender'a yeniden yönlendirilmesini sağlar. Bir ilke oluşturabilir ve tüm SaaS uygulamalarını bu ilkeye ekleyebilirsiniz.
- Ardından, Cloud Apps için Defender'da oturum ilkeleri oluşturun. Uygulamak istediğiniz her denetim için bir ilke oluşturun.

Desteklenen uygulamalar ve istemciler de dahil olmak üzere daha fazla bilgi için bkz. [Microsoft Defender for Cloud Apps Koşullu Erişim Uygulama Denetimi ile uygulamaları koruma](/cloud-app-security/proxy-intro-aad). 

Örneğin ilkeler için bkz. [SaaS uygulamaları için önerilen Microsoft Defender for Cloud Apps ilkeleri](../office-365-security/mcas-saas-access-policies.md). Bu ilkeler, tüm müşteriler için başlangıç noktası olarak önerilen bir dizi [ortak kimlik ve cihaz erişim ilkesi](../office-365-security/microsoft-365-policies-configurations.md) üzerinde oluşturulur. 

## <a name="step-3-try-out-capabilitieswalk-through-tutorials-for-protecting-your-environment"></a>Adım 3. Özellikleri deneyin— Ortamınızı korumaya yönelik öğreticilerde adım adım ilerleyin 

Microsoft Defender for Cloud Apps belgeleri, riski keşfetmenize ve ortamınızı korumanıza yardımcı olacak bir dizi öğretici içerir. 

Cloud Apps için Defender öğreticilerini deneyin:

- [Şüpheli kullanıcı etkinliğini algılama](/cloud-app-security/tutorial-suspicious-activity)
- [Riskli kullanıcıları araştırma](/cloud-app-security/tutorial-ueba)
- [Riskli OAuth uygulamalarını araştırma](/cloud-app-security/investigate-risky-oauth)
- [Hassas bilgileri bulma ve koruma](/cloud-app-security/tutorial-dlp)
- [Kuruluşunuzdaki tüm uygulamaları gerçek zamanlı olarak koruma](/cloud-app-security/tutorial-proxy)
- [Hassas bilgilerin indirilmelerini engelleme](/cloud-app-security/use-case-proxy-block-session-aad)
- [Dosyalarınızı yönetici karantinası ile koruma](/cloud-app-security/use-case-admin-quarantine)
- [Riskli eylemde adım adım kimlik doğrulaması gerektir](/cloud-app-security/tutorial-step-up-authentication)

Microsoft Defender for Cloud Apps verilerde gelişmiş avlanma hakkında daha fazla bilgi için [videoya](https://www.microsoft.com/en-us/videoplayer/embed/RWFISa) bakın.

## <a name="next-steps"></a>Sonraki adımlar

[Pilot ortamda Microsoft 365 Defender kullanarak araştırma ve yanıtlama](eval-defender-investigate-respond.md)

[Değerlendirme Microsoft Defender for Cloud Apps](eval-defender-mcas-overview.md) için genel bakışa dönün

[Değerlendirme ve pilot Microsoft 365 Defender](eval-overview.md) genel bakışa dönün
