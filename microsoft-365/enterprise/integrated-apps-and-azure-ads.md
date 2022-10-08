---
title: Microsoft 365 yöneticileri için tümleşik uygulamalar ve Azure AD
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: landing-page
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- scotvorg
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: cb2250e3-451e-416f-bf4e-363549652c2a
description: Azure AD'da Office 365 tümleşik Uygulamaları kaydetmeyi ve yönetmeyi, **Azure AD DC yöneticisi** veya **Genel yönetici** düzeyinde uygulama yetkilendirmelerine izin verme hakkında bilgi edinin.
ms.openlocfilehash: fac21bb980623c0456727593840628aa2753027e
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68208908"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>Microsoft 365 yöneticileri için tümleşik uygulamalar ve Azure AD

Tümleşik uygulamaları yönetmek için yalnızca [uygulamalara kullanıcı onayı yönetmekten](../admin/misc/user-consent.md) daha fazlası vardır. Microsoft 365 REST API'lerinin ortaya çıkmasıyla, kullanıcılar uygulamalara posta, takvimler, kişiler, kullanıcılar, gruplar, dosyalar ve klasörler gibi Microsoft 365 verilerine erişim izni verebilir. Varsayılan olarak, kullanıcıların her uygulamaya ayrı ayrı izin vermesi gerekir. 

Ancak bir uygulamayı **Azure AD DC yöneticisi** veya **Genel yönetici** düzeyinde bir kez yetkilendirmek ve uygulama başlatıcı aracılığıyla tüm kuruluşunuza dağıtmak istiyorsanız bu durum iyi ölçeklendirilemez. Bunu yapmak için uygulamayı Azure Active Directory'ye (Azure AD) kaydetmeniz gerekir. Bir uygulamayı Azure AD kaydetmeden önce uygulamanız gereken bazı adımlar ve Microsoft 365 kuruluşunuzdaki uygulamaları yönetmenize yardımcı olabilecek bilmeniz gereken bazı arka plan bilgileri vardır.
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Microsoft 365 yöneticileri için Azure AD kaynakları

Microsoft 365 uygulamalarınızı Azure AD'da yönetebilmek için önce bu iki görevi yerine getirmek gerekir.
  
|Önkoşullar|Açıklamalar|
|:-----|:-----|
|[Ücretsiz Azure AD aboneliğinizi kullanma](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) <br/> |Microsoft 365'e yapılan her ücretli abonelik, Azure AD için ücretsiz bir abonelikle birlikte gelir. uygulamalarınızı yönetmek, kullanıcı ve grup hesapları oluşturup yönetmek için Azure AD kullanabilirsiniz. Azure AD kullanmak için adresinde Azure portal [https://portal.azure.com](https://portal.azure.com) gidin ve Microsoft 365 hesabınızı kullanarak oturum açın.  <br/> |
|[Uygulamalara kullanıcı onaylarını yönetme](../admin/misc/user-consent.md) <br/> |Üçüncü taraf uygulamaların kullanıcı Microsoft 365 bilgilerine erişmesine izin vermek ve uygulamaları Azure AD kaydetmeniz için uygulamalara kullanıcı onayınızı yönetmeniz gerekir. Örneğin, bir kullanıcı üçüncü taraf bir uygulama kullandığında, uygulama, kullanıcının takvimlerine erişme ve bir OneDrive klasöründeki dosyaları düzenleme izni isteyebilir.  <br/> |
   
Microsoft 365 uygulamalarını yönetmek için Azure AD'daki uygulamalar hakkında bilgi sahibi olmanız gerekir. İhtiyacınız olan arka planı sağlamak için bu makaleleri kullanın.
  
|Makale|Açıklamalar|
|:-----|:-----|
|[Microsoft 365 uygulama başlatıcısı ile tanışın](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |Uygulama başlatıcıyı yeni kullanmaya başlamadıysanız bunun ne olduğunu ve nasıl kullanılacağını merak ediyor olabilirsiniz. Uygulama başlatıcı, Uygulamalarınıza Microsoft 365'in her yerinden ulaşabileceğiniz şekilde tasarlanmıştır.  <br/> |
|[Office 365 yönetim API'lerine genel bakış](/office/office-365-management-api/office-365-management-apis-overview) <br/> |Microsoft 365 yönetim API'leri, microsoft 365 verilerinize, en çok önem verdikleri şeyler (postaları, takvimleri, kişileri, kullanıcıları ve grupları, dosyaları ve klasörleri) erişmenizi sağlar. <br/> |
|[Uygulamaları Azure AD tümleştirme](/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Azure AD ile tümleştirilmiş uygulamalar ve uygulamanızı kaydetme, kayıtlı bir uygulamanın arkasındaki kavramları anlama ve çok kiracılı uygulamalar için markalama yönergeleri hakkında bilgi edinin.  <br/> |
|[Uygulama başlatıcıya özel kutucuklar ekleme](/office365/admin/manage/customize-the-app-launcher)  <br/> |Microsoft 365'teki uygulama başlatıcı, kullanıcıların uygulamalarını bulmasını ve uygulamalarına erişmesini kolaylaştırır. Bu makalede, geliştirici olarak uygulamalarınızın kullanıcıların uygulama başlatıcılarında görünmesini sağlamanın ve ayrıca Microsoft 365 kimlik bilgilerini kullanarak onlara çoklu oturum açma (SSO) deneyimi sunmanın yolları açıklanmaktadır.  <br/> |
|[Azure AD tümleştirme öğreticileri](/azure/active-directory/saas-apps/tutorial-list) <br/> |Bu öğreticilerin amacı, üçüncü taraf SaaS uygulamaları için Azure AD SSO'nun nasıl yapılandırabileceğinizi göstermektir.  <br/> |
|[Azure AD için kimlik doğrulama senaryoları](/azure/active-directory/develop/authentication-vs-authorization) <br/> |Azure AD, OAuth 2.0 ve OpenID Connect gibi endüstri standardı protokollerin yanı sıra kodlamaya hızlı bir şekilde başlamanıza yardımcı olmak için farklı platformlar için açık kaynak kitaplıkları ile hizmet olarak kimlik sağlayarak geliştiriciler için kimlik doğrulamasını basitleştirir. Bu belge, Azure AD desteklediği çeşitli senaryoları anlamanıza yardımcı olur ve nasıl başlayacağınızı gösterir.  <br/> |
|[Uygulama erişimi](/azure/active-directory/manage-apps/what-is-access-management) <br/> |Azure AD, günümüzün popüler hizmet olarak yazılım (SaaS) uygulamalarının çoğuna kolay tümleştirme sağlar. Kimlik ve erişim yönetimi sağlar ve kullanıcılara hangi uygulama erişimine sahip olduklarını ve uygulamalarına erişmek için SSO'nun nerede kullanabileceklerini keşfedebilecekleri bir Erişim Paneli sunar. Bu makalede, Azure AD için uygulama erişim geliştirmeleri ve bunlara nasıl katkıda bulunabileceğiniz hakkında daha fazla bilgi edinmenizi sağlayan ilgili kaynaklara bağlantılar sağlanır.  <br/> |
|[Office 365 deneyiminizi kişiselleştirme](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |Microsoft 365 uygulama başlatıcısına uygulama ekleyerek veya kaldırarak her gün kullandığınız uygulamalara hızlı erişim elde edebilirsiniz.  <br/> |
