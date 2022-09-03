---
title: Adım 1. MFA ile karma çalışanlar için oturum açma güvenliğini artırma
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Karma çalışanlarınızın çok faktörlü kimlik doğrulaması (MFA) ile oturum açmasını zorunlu kılar.
ms.openlocfilehash: 73387246a8300c42cb7c2f9eefe5301d752ebb15
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67586566"
---
# <a name="step-1-increase-sign-in-security-for-hybrid-workers-with-mfa"></a>Adım 1. MFA ile karma çalışanlar için oturum açma güvenliğini artırma

Karma çalışanlarınızın oturum açma güvenliğini artırmak için çok faktörlü kimlik doğrulamasını (MFA) kullanın. MFA, kullanıcı oturum açma işlemleri için kullanıcı hesabı parolasının ötesinde ek bir doğrulamaya tabi olmasını gerektirir. Kötü amaçlı bir kullanıcı bir kullanıcı hesabı parolası belirlese bile, erişim verilmeden önce akıllı telefona gönderilen kısa mesaj gibi ek bir doğrulamaya yanıt verebilmelidir.

![Doğru parolanın yanı sıra ek doğrulama başarılı bir oturum açma işlemiyle sonuçlanmıştır.](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

Microsoft, karma çalışanlar ve özellikle yöneticiler dahil olmak üzere tüm kullanıcılar için MFA'yı kesinlikle önerir.

Kullanıcılarınızın Microsoft 365 planınıza göre MFA kullanmasını gerektirmenin üç yolu vardır.

|Plan  |Öneri  |
|---------|---------|
|Tüm Microsoft 365 planları (Azure AD Premium P1 veya P2 lisansları olmadan)     |[Azure AD'de Güvenlik varsayılanlarını etkinleştirin](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Azure AD'deki güvenlik varsayılanları, kullanıcılar ve yöneticiler için MFA içerir.   |
|Microsoft 365 E3 (Azure AD Premium P1 lisansları içerir)     | Aşağıdaki ilkeleri yapılandırmak için [Ortak Koşullu Erişim ilkelerini](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) kullanın: <br>- [Yöneticiler için MFA gerektir](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [Tüm kullanıcılar için MFA gerektir](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Eski kimlik doğrulamasını engelle](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (Azure AD Premium P2 lisansları içerir)     | Azure AD Kimlik Koruması'nın avantajlarından yararlanarak, şu ilkeleri oluşturarak Microsoft'un [önerilen Koşullu Erişim ve ilgili ilkeler kümesini](../security/office-365-security/identity-access-policies.md) uygulamaya başlayın:<br> - [Oturum açma riski orta veya yüksek olduğunda MFA gerektirme](../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Modern kimlik doğrulamayı desteklemeyen istemcileri engelleme](../security/office-365-security/identity-access-policies.md#block-clients-that-dont-support-multi-factor)<br>- [Yüksek riskli kullanıcıların parola değiştirmesi gerekir](../security/office-365-security/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

## <a name="security-defaults"></a>Güvenlik varsayılanları

Güvenlik varsayılanları, Microsoft 365 ve 21 Ekim 2019 Office 365 dan sonra oluşturulan ücretli veya deneme abonelikleri için yeni bir özelliktir. Bu aboneliklerde güvenlik varsayılanları açıktır ve ***bu da tüm kullanıcılarınızın Microsoft Authenticator uygulamasıyla MFA kullanmasını gerektirir***.
 
Kullanıcıların akıllı telefonlarından Microsoft Authenticator uygulamasına MFA'ya kaydolmaları için 14 günü vardır. Bu, güvenlik varsayılanları etkinleştirildikten sonra ilk kez oturum açtıktan sonra başlar. 14 gün geçtikten sonra, MFA kaydı tamamlanana kadar kullanıcı oturum açamaz.

Güvenlik varsayılanları, tüm kuruluşların kullanıcı oturum açma için varsayılan olarak etkin olan temel bir güvenlik düzeyine sahip olmasını sağlar. Koşullu Erişim ilkeleriyle veya tek tek hesaplar için MFA'nın lehine güvenlik varsayılanlarını devre dışı bırakabilirsiniz.

Daha fazla bilgi için güvenlik [varsayılanlarına genel bakış konusuna](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) bakın.

## <a name="conditional-access-policies"></a>Koşullu Erişim ilkeleri

Koşullu Erişim ilkeleri, oturum açmaların değerlendirildiği ve izin verilen koşulları belirten bir dizi kuraldır. Örneğin, şunları belirten bir Koşullu Erişim ilkesi oluşturabilirsiniz:

- Kullanıcı hesabı adı Exchange, kullanıcı, parola, güvenlik, SharePoint veya genel yönetici rollerine atanmış kullanıcılar için bir grubun üyesiyse, erişime izin vermeden önce MFA'yı gerektirir.

Bu ilke, bu yönetici rollerinden atandığında veya atanmadığında MFA için tek tek kullanıcı hesaplarını yapılandırmaya çalışmak yerine grup üyeliğine göre MFA'yı zorunlu kılmasını sağlar.

Oturum açma işleminin Windows 11 veya 10 çalıştıran dizüstü bilgisayarınız gibi uyumlu bir cihazdan yapılmasını gerektirme gibi daha gelişmiş özellikler için Koşullu Erişim ilkelerini de kullanabilirsiniz.

Koşullu Erişim, Microsoft 365 E3 ve E5 ile birlikte gelen Azure AD Premium P1 lisansları gerektirir.

Daha fazla bilgi için bkz. [Koşullu Erişim'e genel bakış](/azure/active-directory/conditional-access/overview).

## <a name="azure-ad-identity-protection-support"></a>Azure AD Kimlik Koruması desteği

Azure AD Kimlik Koruması ile şunları belirten ek bir Koşullu Erişim ilkesi oluşturabilirsiniz:

- Oturum açma riskinin orta veya yüksek olduğu belirlendiyse MFA'yı gerekli kılmalıdır.

Azure AD Kimlik Koruması, Microsoft 365 E5 dahil Azure AD Premium P2 lisansları gerektirir.

Daha fazla bilgi için bkz. [Risk Tabanlı Koşullu Erişim](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk#require-mfa-medium-or-high-sign-in-risk-users).

Azure AD Kimlik Koruması ile, kullanıcılarınızın MFA'ya kaydolmasını gerektirecek bir ilke de oluşturabilirsiniz. Daha fazla bilgi için bkz[. Azure AD Multi-Factor Authentication kayıt ilkesini yapılandırma](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)


## <a name="using-these-methods-together"></a>Bu yöntemleri birlikte kullanma

Aşağıdakileri unutmayın:

- Koşullu Erişim ilkeleri etkinse güvenlik varsayılanlarını etkinleştiremezsiniz.
- Güvenlik varsayılanları etkinse koşullu erişim ilkelerini etkinleştiremezsiniz.

Güvenlik varsayılanları etkinse, tüm yeni kullanıcılardan MFA kaydı ve Microsoft Authenticator uygulamasının kullanımı istenir. 

Bu tabloda, MFA'nın güvenlik varsayılanları ve Koşullu Erişim ilkeleriyle etkinleştirilmesinin sonuçları gösterilir.

| Yöntem | Etkin | Devre dışı | Ek kimlik doğrulama yöntemi |
|:-------|:-----|:-------|:-------|
| **Güvenlik varsayılanları**  | Koşullu Erişim ilkeleri kullanılamaz | Koşullu Erişim ilkelerini kullanabilir | Microsoft Authenticator uygulaması |
| **Koşullu Erişim ilkeleri** | Etkinse, güvenlik varsayılanlarını etkinleştiremezsiniz | Tümü devre dışı bırakılırsa, güvenlik varsayılanlarını etkinleştirebilirsiniz  | Kullanıcı MFA kaydı sırasında belirtir  |
||||

## <a name="let-your-users-reset-their-own-passwords"></a>Kullanıcılarınızın kendi parolalarını sıfırlamasına izin verin

Self-Service Parola Sıfırlama (SSPR), kullanıcıların BT personelini etkilemeden kendi parolalarını sıfırlamasına olanak tanır. Kullanıcılar istedikleri zaman ve istedikleri yerden parolalarını hızlı bir şekilde sıfırlayabilir. Daha fazla bilgi için bkz. [Azure AD self servis parola sıfırlama dağıtımı planlama](/azure/active-directory/authentication/howto-sspr-deployment).

## <a name="sign-in-to-saas-apps-with-azure-ad"></a>Azure AD ile SaaS uygulamalarında oturum açma

Kullanıcılara bulut kimlik doğrulaması sağlamanın yanı sıra Azure AD şirket içinde, Microsoft bulutunda veya başka bir bulutta yer alan tüm uygulamalarınızın güvenliğini sağlamanın merkezi yolu da olabilir. [Uygulamalarınızı Azure AD tümleştirerek](/azure/active-directory/manage-apps/plan-an-application-integration) hibrit çalışanların ihtiyaç duydukları uygulamaları keşfetmesini ve güvenli bir şekilde oturum açmasını kolaylaştırabilirsiniz.

## <a name="admin-technical-resources-for-mfa-and-identity"></a>MFA ve kimlik için teknik kaynakları Yönetici

- [Azure AD uzaktan çalışmayı etkinleştirmenize yardımcı olabilecek en iyi 5 yol](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [Microsoft 365 için kimlik altyapısı](../enterprise/deploy-identity-solution-overview.md)
- [Azure Academy Azure AD eğitim videoları](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)

## <a name="results-of-step-1"></a>1. Adımın Sonuçları

MFA dağıtımından sonra kullanıcılarınız:

- Oturum açma işlemleri için MFA'nın kullanılması gerekir.
- MFA kayıt işlemini tamamladınız ve tüm oturum açma işlemleri için MFA kullanıyorlar.
- Kendi parolalarını sıfırlamak için SSPR kullanabilir.

## <a name="next-step"></a>Sonraki adım

[![2. Adım: Şirket içi uygulama ve hizmetlere uzaktan erişim sağlayın.](../media/empower-people-to-work-remotely/remote-workers-step-grid-2.png)](empower-people-to-work-remotely-remote-access.md)

Şirket içi uygulama ve hizmetlere uzaktan erişim sağlamak için [2. Adımla](empower-people-to-work-remotely-remote-access.md) devam edin.