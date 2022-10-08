---
title: Azure Active Directory kurulum kılavuzları
ms.author: Kwekua
author: Kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
description: Azure Active Directory kurulum kılavuzları hakkında bilgi edinin.
ms.openlocfilehash: 1e1d78b79411a31f4d39ba9fe0268b5f821a5933
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68187107"
---
# <a name="azure-active-directory-setup-guides"></a>Azure Active Directory kurulum kılavuzları

Azure Active Directory (Azure AD) özellikleri, kuruluşunuzu yönetmenize ve güvenliğini sağlamanıza yardımcı olur. Bu kurulum kılavuzları, bu özellikleri basit bir şekilde tümleştirmenize yardımcı olur. Aşağıdaki bölümlerde kurulum kılavuzlarını kısaca açıklayacağız ve kılavuzların bağlantılarını paylaşacağız.

## <a name="who-are-these-setup-guides-for"></a>Bu kurulum kılavuzları kimler içindir?

Bu kurulum kılavuzları, genellikle adanmış bir kimlik ekibine sahip olmayan küçük ve orta ölçekli kuruluşlar için tasarlanmıştır. Bunları kullanmak için kimlik uzmanı olmanız gerekmez.

## <a name="what-to-expect-and-what-youll-need"></a>Ne bekleyebileceğiniz ve neye ihtiyacınız olacak?

Kurulum kılavuzları, Azure AD temel işlevselliğini yapılandırmanıza yardımcı olur. Daha gelişmiş bir yapılandırma ayarlamanız gerekirse kurulum kılavuzu sizi Azure AD portalında uygun konuma yönlendirir.

### <a name="required-permissions"></a>Gerekli izinler

Aşağıdaki yönetim rollerinin üyesi olmanız gerekir:

- Genel yönetici: Microsoft 365 kuruluşunuzda değişiklik yapmak için kurulum kılavuzlarındaki tümleşik araçları kullanmanıza olanak tanır.

- Genel okuyucu: Kurulum kılavuzlarını görüntülemenize izin verir, ancak kiracınızda değişiklik yapmanıza izin vermez.

## <a name="identity-security-for-teams"></a>Teams için kimlik güvenliği

Azure Active Directory (Azure AD), çalışanlarınızın oturum açmasına ve uygulama ve hizmetlere erişmesine yardımcı olan bulut tabanlı kimlik ve erişim yönetimi hizmetimizdir.
Bu katalog, kullanıcılarınızın güvende olmasını ve Teams'i kullanarak en verimli şekilde zaman geçirmesini sağlamak için kullanabileceğiniz bazı temel güvenlik özelliklerini içerir.

### <a name="licensing"></a>Lisanslama

Bu katalogdaki güvenlik özelliklerini kullanmak için bir Azure Active Directory P2 lisansı gereklidir.

[Teams için Kimlik güvenliği kataloğunu açma](https://portal.office.com/AdminPortal/home?Q=azuredocs#/teamsidentity)

## <a name="identity-governance"></a>Kimlik İdaresi

Bu sihirbaz kataloğu, müşterilerin Erişim Gözden Geçirmeleri (AR), Privileged Identity Management (PIM) ve Yetkilendirme Yönetimi (ELM) gibi Azure Active Directory P2 işlevlerine yardımcı olmak için tasarlanmıştır. PIM ve ELM için, seçilen bir belge listesi ve yöneticinin bu işlevselliği yapılandırabileceği Azure Active Directory yönetim merkezine yönelik bir işaretçi sunuyoruz. AR için, yöneticilerin iki şablon arasından seçim yapmasına olanak tanıyan tam otomatik bir deneyim sunuyoruz. Bu şablonlar, grup sahiplerinin tüm Microsoft 365 gruplarında konuk kullanımını onaylamasına olanak tanıyan bir şablon içerir. Bu, müşterilerin bugün kullandığı en önemli ilkedir.  

Ardından, yöneticinin seçtikleri belirli bir grup için konukların gözden geçireni olduğu bir test şablonu sunuyoruz. Kiracının tüm Microsoft 365 grupları konuk kullanıcılarını kapsayan bir gözden geçirmesi zaten varsa, yönetici mevcut gözden geçirmeyi yönetmek için Azure Active Directory yönetim merkezine yönlendirilir ve otomatikleştirilmiş bir deneyim olmaz.

[Kimlik İdaresi kurulum kılavuzunu açma](https://admin.microsoft.com/adminportal/home?Q=azuredocs#/modernonboarding/identitygovernance)

> [!NOTE]
> Bu katalogdaki güvenlik özelliklerini kullanmak için Azure Active Directory P2 lisansı gereklidir.

## <a name="azure-active-directory-deployment"></a>Azure Active Directory dağıtımı  

Azure Active Directory kurulum kılavuzu, en yaygın Azure AD özelliklerini önerilen sırayla ayarlamanıza yardımcı olur. Kurulum kılavuzu üç bölüme ayrılmıştır: **İlk**, **Çekirdek** ve **Gelişmiş**. Her bölümde açmanız gereken bir özellik kümesi önerilir.

Kurulum kılavuzları, tamamlamanız gereken görevlerin denetim listesini içerir ve kılavuzlarda ilerlerken ilerleme durumunuzu izleyebilirsiniz. Kılavuzlar gerektiğinde diğer kurulum kılavuzlarına da bağlanır.

[Azure Active Directory kurulum kılavuzunu açın](https://admin.microsoft.com/adminportal/home?Q=azuredocs#/modernonboarding/azureadsetup).

## <a name="add-or-sync-users-to-your-microsoft-account"></a>Microsoft hesabınıza kullanıcı ekleme veya eşitleme  

Bu kılavuz, Azure ve Microsoft 365'te kullanıcı hesapları kurulumunu ayarlamanıza yardımcı olur. Ortamınıza ve gereksinimlerinize göre kullanıcıları tek tek eklemeyi, şirket içi dizininizi Azure AD bulut eşitlemesi veya Azure AD Connect ile geçirmeyi veya mevcut eşitleme sorunlarını gidermeyi seçebilirsiniz.

### <a name="licensing"></a>Lisanslama

Azure Active Directory eşitleme araçlarını kullanmak ücretsizdir ve tüm Microsoft 365 aboneliklerine dahildir.

[Kullanıcı ekleme veya eşitleme kurulum kılavuzunu açın](https://admin.microsoft.com/adminportal/home?Q=azuredocs#/modernonboarding/identitywizard).

## <a name="secure-your-cloud-apps-with-single-sign-on-sso"></a>Çoklu Oturum Açma (SSO) ile bulut uygulamalarınızın güvenliğini sağlama

Bu kılavuz, Microsoft 365'e bulut uygulamaları eklemenize yardımcı olmak için tasarlanmıştır. Kılavuzumuzda kiracınıza bir uygulama ekleyebilir, uygulamaya kullanıcı ekleyebilir, roller atayabilir ve daha fazlasını yapabilirsiniz.  Uygulama Tek Sign-On (SSO) destekliyorsa, bu yapılandırmada size de yol gösteririz.

### <a name="licensing"></a>Lisanslama

Microsoft 365'e yapılan her ücretli abonelik, Azure AD için ücretsiz bir abonelikle birlikte gelir. uygulamalarınızı yönetmek, kullanıcı ve grup hesapları oluşturup yönetmek için Azure AD kullanabilirsiniz.

[Microsoft 365'e bulut uygulaması ekleme kurulum kılavuzunu açın](https://portal.office.com/AdminPortal/home?Q=azuredocs#/azureadappintegration)

## <a name="azure-self-service-password-reset-sspr-guide"></a>Azure Self-Service parola sıfırlama (SSPR) kılavuzu

Bu kurulum kılavuzu self servis parola sıfırlamayı etkinleştirmenize ve yapılandırmanıza yardımcı olmak için tasarlanmıştır. Kurulum kılavuzu, parola geri yazma ve yönetici bildirimleri de dahil olmak üzere önerilen seçeneklerde size yol gösterir.

### <a name="licensing"></a>Lisanslama

SSPR aşağıdaki lisanslardan birini gerektirir:

- Azure Active Directory P1 veya P2

- Microsoft 365 Business Premium

- E3 veya E5 Microsoft 365 Kurumsal  

- Enterprise Mobility and Security E3 veya E5

[Self servis parola sıfırlama kurulum kılavuzunu açın](https://admin.microsoft.com/adminportal/home?Q=azuredocs#/modernonboarding/ssprsetup).

## <a name="multi-factor-authentication-mfa"></a>Çok faktörlü kimlik doğrulaması (MFA)

Bu kılavuz geçerli MFA durumunu sağlar ve BT yöneticilerinin kuruluş gereksinimlerini karşılayan en iyi MFA seçeneğini belirlemesine yardımcı olur. Ardından kuruluş için seçilen MFA yöntemini yapılandırma ve zorunlu tutma konusunda yardımcı olacağız.

### <a name="licensing"></a>Lisanslama

Koşullu Erişim bir Azure Active Directory P1 veya P2 lisansı gerektirir, güvenlik varsayılanları ve kullanıcı başına MFA ücretsizdir ve tüm Microsoft 365 aboneliklerine dahildir.

[Çok faktörlü kimlik doğrulama (MFA) kılavuzunu açma](https://admin.microsoft.com/adminportal/home?Q=azuredocs#/modernonboarding/mfasetupguide)

## <a name="the-passwordless-setup-guide"></a>Parolasız kurulum kılavuzu

Parolasız kurulum kılavuzu, ortamınız için en iyi parolasız yöntemi belirlemenize yardımcı olacak şekilde tasarlanmıştır. Yöntemler güvenlik anahtarları, İş İçin Windows Hello ve Microsoft Authenticator uygulamasını içerir. Öneri İş İçin Windows Hello ise, farklı seçeneklerde size yol gösteren bir bölüm vardır. Kılavuz, adım adım plan oluşturmanıza yardımcı olacak sorular sorar.

### <a name="licensing"></a>Lisanslama

Microsoft 365'e yapılan her ücretli abonelik, Azure AD için ücretsiz bir abonelikle birlikte gelir. uygulamalarınızı yönetmek, kullanıcı ve grup hesapları oluşturup yönetmek için Azure AD kullanabilirsiniz.

[Parolasız kurulum kılavuzunu açın](https://admin.microsoft.com/adminportal/home?Q=azuredocs#/modernonboarding/passwordlesssetup).
