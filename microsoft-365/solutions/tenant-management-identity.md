---
title: Adım 3. Kurumsal kiracılar için Microsoft 365'inizin kimliği
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Microsoft 365 kiracılarınız için doğru kimlik modelini dağıtın ve güçlü kullanıcı oturum açma işlemleri uygulayın.
ms.openlocfilehash: b31bbc089d6c6824eacc9cce00f71a877052ec72
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67986432"
---
# <a name="step-3-identity-for-your-microsoft-365-for-enterprise-tenants"></a>Adım 3. Kurumsal kiracılar için Microsoft 365'inizin kimliği

Microsoft 365 kiracınız, oturum açma işlemleri için kimlikleri ve kimlik doğrulamasını yönetmek için bir Azure Active Directory (Azure AD) kiracısı içerir. Kimlik altyapınızın doğru yapılandırılmasını sağlamak, Kuruluşunuz için Microsoft 365 kullanıcı erişimini ve izinlerini yönetmek için çok önemlidir.

## <a name="cloud-only-vs-hybrid"></a>Yalnızca bulut ile hibrit karşılaştırması

İki tür kimlik modeli ve bunların en uygun ve avantajlarını aşağıda bulabilirsiniz.


| Modeli | Açıklama | Microsoft 365 kullanıcı kimlik bilgilerini nasıl doğrular? | Için en iyi | En büyük avantaj |
|:-------|:-----|:-----|:-----|:-----|
| Yalnızca bulut | Kullanıcı hesabı yalnızca Microsoft 365 kiracınızın Azure AD kiracısında bulunur. | Microsoft 365 kiracınızın Azure AD kiracısı, kimlik doğrulamasını bulut kimliği hesabıyla gerçekleştirir. | şirket içi Active Directory olmayan veya ihtiyacı olmayan kuruluşlar. | Kullanımı basit. Ek dizin araçları veya sunucuları gerekmez. |
| Karma |  Kullanıcı hesabı şirket içi Active Directory Etki Alanı Hizmetleri'nizde (AD DS) var ve bir kopyası da Microsoft 365 kiracınızın Azure AD kiracısında yer alır. Azure AD Connect, AD DS değişikliklerini Azure AD kiracınızla eşitlemek için şirket içi sunucuda çalışır. Azure AD'daki kullanıcı hesabı, zaten karma ad DS kullanıcı hesabı parolasının karma sürümünü de içerebilir. | Microsoft 365 kiracınızın Azure AD kiracısı, kimlik doğrulama işlemini işler veya kullanıcıyı başka bir kimlik sağlayıcısına yönlendirir. | AD DS veya başka bir kimlik sağlayıcısı kullanan kuruluşlar. | Kullanıcılar şirket içi veya bulut tabanlı kaynaklara erişirken aynı kimlik bilgilerini kullanabilir. |
||||||

Burada yalnızca bulut kimliğinin temel bileşenleri yer alır.

![Yalnızca bulut kimliğinin temel bileşenleri.](../media/about-microsoft-365-identity/cloud-only-identity.png)

Bu çizimde, şirket içi ve uzak kullanıcılar Microsoft 365 kiracılarının Azure AD kiracısında hesaplarla oturum açar.

Karma kimliğin temel bileşenleri aşağıdadır.

![Karma kimliğin temel bileşenleri.](../media/about-microsoft-365-identity/hybrid-identity.png)

Bu çizimde, şirket içi ve uzak kullanıcılar, şirket içi AD DS'lerinden kopyalanmış Azure AD kiracıdaki hesaplarla Microsoft 365 kiracılarında oturum açar.

## <a name="synchronizing-your-on-premises-ad-ds"></a>Şirket içi AD DS'nizi eşitleme

İş gereksinimlerinize ve teknik gereksinimlerinize bağlı olarak karma kimlik modeli ve dizin eşitlemesi, Microsoft 365'i benimseyen kurumsal müşteriler için en yaygın seçenektir. Dizin eşitleme, AD DS'nizdeki kimlikleri yönetmenize olanak tanır ve kullanıcı hesaplarına, gruplara ve kişilere yönelik tüm güncelleştirmeler Microsoft 365 kiracınızın Azure AD kiracısı ile eşitlenir.

> [!NOTE]
> AD DS kullanıcı hesapları ilk kez eşitlendiğinde, bunlara otomatik olarak bir Microsoft 365 lisansı atanamaz ve e-posta gibi Microsoft 365 hizmetlerine erişemez. Önce onlara bir kullanım konumu atamanız gerekir. Ardından, grup üyeliği aracılığıyla bu kullanıcı hesaplarına tek tek veya dinamik olarak bir lisans atayın.

Karma kimlik modeli kullanılırken iki kimlik doğrulaması türü aşağıdadır.

| Kimlik doğrulama türü | Açıklama |
|:-------|:-----|
| Yönetilen kimlik doğrulaması | Azure AD, parolanın yerel olarak depolanan karma sürümünü kullanarak kimlik doğrulama işlemini işler veya kimlik bilgilerini şirket içi AD DS tarafından kimlik doğrulaması için şirket içi yazılım aracısına gönderir. <br> <br>  İki tür yönetilen kimlik doğrulaması vardır: Parola karması eşitlemesi (PHS) ve Geçişli kimlik doğrulaması (PTA). PHS ile Azure AD kimlik doğrulamasının kendisini gerçekleştirir. PTA ile Azure AD kimlik doğrulamasını AD DS gerçekleştirir. |
| Şirket Dışı Kimlik Doğrulaması | Azure AD, kimlik doğrulaması isteyen istemci bilgisayarı başka bir kimlik sağlayıcısına yönlendirir. |
|  |  |

Daha fazla bilgi edinmek için [doğru kimlik doğrulama yöntemini seçme](/azure/active-directory/hybrid/choose-ad-authn) bölümüne bakın.

## <a name="enforcing-strong-sign-ins"></a>Güçlü oturum açma işlemleri uygulama

Kullanıcı oturum açma bilgilerinin güvenliğini artırmak için aşağıdaki tabloda yer alan özellikleri ve özellikleri kullanın.

| Yeteneği | Açıklama | Daha fazla bilgi | Lisans gereksinimleri |
|:-------|:-----|:-----|:-----|:-----|
| İş İçin Windows Hello | Windows cihazında oturum açarken parolaları güçlü iki faktörlü kimlik doğrulamasıyla değiştirir. İki faktör, bir cihaza ve biyometrik veya PIN'e bağlı yeni bir kullanıcı kimlik bilgisi türüdür. | [İş İçin Windows Hello Genel Bakış](/windows/security/identity-protection/hello-for-business/hello-overview) | Microsoft 365 E3 veya E5 |
| Parola Koruması'Azure AD | Bilinen zayıf parolaları ve bunların değişkenlerini algılar ve engeller ve ayrıca kuruluşunuza özgü ek zayıf terimleri engelleyebilir. | [parola korumasını Azure AD yapılandırma](/azure/active-directory/authentication/concept-password-ban-bad) | Microsoft 365 E3 veya E5 |
| Çok faktörlü kimlik doğrulamasını (MFA) kullanma | MFA, kullanıcı oturum açma bilgilerinin, akıllı telefon uygulamasıyla doğrulama veya akıllı telefona gönderilen kısa mesaj gibi kullanıcı hesabı parolasının ötesinde başka bir doğrulamaya tabi olmasını gerektirir. Kullanıcıların MFA'yı nasıl kurduğuna ilişkin yönergeler için [bu videoya](https://support.microsoft.com/office/set-up-multi-factor-authentication-in-microsoft-365-business-a32541df-079c-420d-9395-9d59354f7225) bakın. | [Kuruluş için Microsoft 365 MFA](../enterprise/microsoft-365-secure-sign-in.md#mfa) | Microsoft 365 E3 veya E5 |
| Kimlik ve cihaz erişimi yapılandırmaları | Belirli bir erişim isteğinin verilip verilmeyeceğini ve hangi koşullar altında verilmesi gerektiğini belirleyen Koşullu Erişim, Intune ve Azure AD Kimlik Koruması ilkeleriyle birlikte önerilen önkoşul özelliklerinden ve bunların ayarlarından oluşan ayarlar ve ilkeler.  | [Kimlik ve cihaz erişimi yapılandırmaları](../security/office-365-security/microsoft-365-policies-configurations.md) | Microsoft 365 E3 veya E5 |
| Azure AD Kimlik Koruması | Bir saldırganın bir kuruluşun bulut hizmetlerine ve verilerine erişim elde etmek için kullanıcının hesap adını ve parolasını belirlediği kimlik bilgileri güvenliğinin aşılmasına karşı koruma sağlayın. | [Azure AD Kimlik Koruması](/azure/active-directory/active-directory-identityprotection) | Kimlik & Tehdit Koruması eklentisiyle Microsoft 365 E5 veya Microsoft 365 E3 |
|  |  |  |



## <a name="results-of-step-3"></a>3. Adımın Sonuçları

Microsoft 365 kiracınızın kimliği için şunları belirlediniz:

- Kullanılacak kimlik modeli.
- Güçlü kullanıcı ve cihaz erişimini nasıl zorunlu kılacağınız.

Burada, yeni karma kimlik öğelerinin vurgulandığı bir kiracı örneği verilmiştir.

![Kiracı için karma kimlik örneği.](../media/tenant-management-overview/tenant-management-tenant-build-step3.png)

Bu çizimde kiracının şunları vardır:

- Dizin eşitleme sunucusu kullanılarak Azure AD kiracısıyla eşitlenen ve Connect'i Azure AD bir AD DS ormanı.
- AD DS kullanıcı hesaplarının ve AD DS ormanındaki diğer nesnelerin bir kopyası.
- Kullanıcı hesabına göre güvenli kullanıcı oturum açmalarını ve erişimi zorlamak için bir dizi Koşullu Erişim ilkesi.

## <a name="ongoing-maintenance-for-identity"></a>Kimlik için devam eden bakım

Sürekli olarak şunları yapmanız gerekebilir:

- Kullanıcı hesaplarını ve gruplarını ekleyin veya değiştirin. Yalnızca bulut kimliği için bulut tabanlı kullanıcılarınızın ve gruplarınızın bakımını Microsoft 365 yönetim merkezi veya PowerShell gibi Azure AD araçlarıyla gerçekleştirirsiniz. Karma kimlik için şirket içi kullanıcılarınızın ve gruplarınızın bakımını AD DS araçlarıyla gerçekleştirirsiniz.
- Oturum açma güvenlik gereksinimlerini zorunlu kılmak için kimlik ve cihaz erişim yapılandırmanızı ekleyin veya değiştirin.

## <a name="next-step"></a>Sonraki adım

[![4. Adım. Şirket içi Office sunucularınızı ve verilerinizi geçirin.](../media/tenant-management-overview/tenant-management-step-grid-migration.png)](tenant-management-migration.md)

Şirket içi Office sunucularınızı ve verilerini Microsoft 365'e geçirmek için [geçişe](tenant-management-migration.md) devam edin.