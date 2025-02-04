---
title: Microsoft 365 kullanıcı hesabı parolalarını yönetme
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: overview
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- scotvorg
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Microsoft 365 kullanıcı hesabı parolalarını yönetme hakkında bilgi edinin.
ms.openlocfilehash: 3c6683fb916ac066d9fff3b168299c50391cbe63
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68163151"
---
# <a name="manage-microsoft-365-user-account-passwords"></a>Microsoft 365 kullanıcı hesabı parolalarını yönetme

*Bu makale hem Microsoft 365 Kurumsal hem de Office 365 Kurumsal için geçerlidir.*

Microsoft 365 kullanıcı hesabı parolalarını, kimlik yapılandırmanıza bağlı olarak çeşitli yollarla yönetebilirsiniz. Kullanıcı hesaplarını [Microsoft 365 yönetim merkezi, Active Directory Domain Services](/admin) (AD DS) veya Azure Active Directory (Azure AD) yönetim merkezinde yönetebilirsiniz.

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a>Kullanıcı hesabı parolalarınızı nerede ve nasıl yönetebileceğinizi planlama

Kullanıcı hesaplarınızı nerede ve nasıl yönetebileceğiniz, Microsoft 365'iniz için kullanmak istediğiniz kimlik modeline bağlıdır. İki model yalnızca bulut ve karmadır.
  
### <a name="cloud-only"></a>Yalnızca bulut

Kullanıcı hesabı parolalarını şu şekilde yönetirsiniz:

- [Microsoft 365 yönetim merkezi](/admin)
- Azure AD yönetim merkezi
    
### <a name="hybrid"></a>Karma

Karma kimlik ile parolalar AD DS'de depolanır, bu nedenle kullanıcı hesabı parolalarını yönetmek için şirket içi AD DS araçlarını kullanmanız gerekir. Azure AD AD DS'de karma sürümün karma sürümünü depoladığı Parola Karması Eşitlemesi (PHS) kullanırken bile, sizin ve kullanıcıların parolalarını AD DS'de yönetmeniz gerekir.

[Parola geri yazma](#pw_writeback) ile kullanıcılarınız Azure AD aracılığıyla AD DS parolalarını değiştirebilir.

## <a name="prevent-bad-passwords"></a>Hatalı parolaları önleme

Tüm kullanıcılarınız, kullanıcı hesabı [parolalarını oluşturmak için Microsoft'un parola kılavuzlarını](https://www.microsoft.com/research/publication/password-guidance) kullanmalıdır.

Kullanıcıların kolayca belirlenen bir parola oluşturmasını önlemek için, hem genel olarak yasaklanmış parola listesini hem de belirttiğiniz isteğe bağlı özel yasaklanmış parola listesini kullanan Azure AD parola korumasını kullanın. Örneğin, kuruluşunuza özgü terimler belirtebilirsiniz, örneğin:

- Marka adları
- Ürün adları
- Konumlar (örneğin, şirket merkezi)
- Şirkete özgü iç koşullar
- Belirli bir şirket anlamı olan kısaltmalar

Kötü parolaları [bulutta](/azure/active-directory/authentication/concept-password-ban-bad) ve [şirket içi AD DS'niz](/azure/active-directory/authentication/concept-password-ban-bad-on-premises) için yasaklayabilirsiniz.

## <a name="simplify-user-sign-in"></a>Kullanıcı oturum açma işlemini basitleştirme

Azure AD Sorunsuz Tek Sign-On (Azure AD Sorunsuz SSO), kullanıcılarınızın parolalarını yazmak zorunda kalmadan Azure AD kullanıcı hesaplarını kullanan hizmetlerde ve çoğu durumda kullanıcı adlarını kullanarak oturum açmasına olanak sağlamak için PHS ve Pass-Through Kimlik Doğrulaması (PTA) ile çalışır. Bu, kullanıcılarınıza kimlik federasyon sunucuları gibi ek şirket içi bileşenlere gerek kalmadan Office 365 gibi bulut tabanlı uygulamalara daha kolay erişim sağlar.

Azure AD Connect aracıyla sorunsuz Azure AD SSO yapılandırabilirsiniz. [Sorunsuz SSO Azure AD yapılandırma yönergelerine](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) bakın.

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a>AD DS'de parola güncelleştirmelerini basitleştirme

Parola geri yazma özelliği sayesinde kullanıcıların parolalarını Azure AD sıfırlayabilir ve bu da AD DS'ye çoğaltılır. Kullanıcıların parolalarını güncelleştirmek için şirket içi AD DS'lerine erişmeleri gerekmez. Bu, şirket içi ağa uzaktan erişim bağlantısı olmayan dolaşım veya uzak kullanıcılar için değerlidir.

Parola geri yazma, yüksek bir hesap güvenliğinin tehlikeye girme riski algılandığında kullanıcıların şirket içi parolalarını değiştirmelerini gerektirme gibi Azure AD Kimlik Koruması özelliklerini tam olarak kullanmak için gereklidir.

Ek bilgi ve yapılandırma yönergeleri için bkz. [Parola geri yazma ile SSPR Azure AD](/azure/active-directory/active-directory-passwords-writeback).

>[!Note]
>Yayınlandığında mümkün olan en iyi deneyimi ve yeni özellikleri sağlamak için Azure AD Connect'in en son sürümüne yükseltin. Daha fazla bilgi için bkz. [Azure AD Connect'in özel yüklemesi](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).
>

## <a name="simplify-password-resets"></a>Parola sıfırlamalarını basitleştirme

Self servis parola sıfırlama (SSPR), kullanıcıların parolalarını veya hesaplarını sıfırlamasına veya kilidini açmasına olanak tanır. Sizi kötüye kullanım veya kötüye kullanım konusunda uyarmak için, kullanıcıların sisteme ne zaman eriştiğine ilişkin ayrıntılı raporlamayı ve bildirimleri kullanabilirsiniz. Parola sıfırlamalarını dağıtabilmeniz için önce [parola geri yazmayı](#pw_writeback) etkinleştirmeniz gerekir.

[Parola sıfırlamayı kullanıma sunma yönergelerine](/azure/active-directory/authentication/howto-sspr-deployment) bakın.