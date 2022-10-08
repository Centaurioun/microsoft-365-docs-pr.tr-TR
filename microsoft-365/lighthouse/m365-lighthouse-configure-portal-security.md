---
title: Microsoft 365 Lighthouse portal güvenliğini yapılandırma
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: vivkuma
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouse kullanan Yönetilen Hizmet Sağlayıcıları (MSP) için portal güvenliğini yapılandırmayı öğrenin.
ms.openlocfilehash: dbadd9742e8b477bf4fa97e2556c37b0a3e3fe3b
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68193223"
---
# <a name="configure-microsoft-365-lighthouse-portal-security"></a>Microsoft 365 Lighthouse portal güvenliğini yapılandırma

Yönetilen Hizmet Sağlayıcısı (MSP) kiracılarına temsilci erişim izinleri verdiğinde müşteri verilerine erişimi korumak bir siber güvenlik önceliğidir. Microsoft 365 Lighthouse, Lighthouse portal güvenliğini yapılandırmanıza yardımcı olmak için hem gerekli hem de isteğe bağlı özelliklerle birlikte gelir. Lighthouse'a erişebilmek için önce çok faktörlü kimlik doğrulaması (MFA) etkinleştirilmiş belirli rolleri ayarlamanız gerekir. İsteğe bağlı olarak Azure AD Privileged Identity Management (PIM) ve Koşullu Erişim ayarlayabilirsiniz.

## <a name="set-up-multifactor-authentication-mfa"></a>Çok faktörlü kimlik doğrulamasını (MFA) ayarlama

Blog gönderisinde belirtildiği gibi [Pa$$word önemli değildir](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984):

> "Parolanız önemli değil, ama MFA önemli. Yaptığımız çalışmalara dayanarak, MFA kullanıyorsanız hesabınızın gizliliğinin %99,9'dan daha az tehlikeye girmiş olma olasılığı daha düşüktür."

Kullanıcılar Lighthouse'a ilk kez eriştiğinde, Microsoft 365 hesaplarında henüz yapılandırılmamışsa MFA'yı ayarlamaları istenir. Gerekli MFA kurulum adımı tamamlanana kadar kullanıcılar Lighthouse'a erişemez. Kimlik doğrulama yöntemleri hakkında daha fazla bilgi edinmek için bkz. [Çok faktörlü kimlik doğrulaması için Microsoft 365 oturum açma bilgilerinizi ayarlama](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14).

## <a name="set-up-role-based-access-control"></a>Rol tabanlı erişim denetimini ayarlama

Rol tabanlı erişim denetimi (RBAC), kullanıcı rollerine göre kaynaklara veya bilgilere erişim verir. Lighthouse'daki müşteri kiracı verilerine ve ayarlarına erişim, Bulut Çözümü Sağlayıcısı (CSP) programındaki belirli rollerle sınırlıdır. Lighthouse'da RBAC rollerini ayarlamak için, kullanıcılar için ayrıntılı atamalar uygulamak üzere Ayrıntılı Temsilci Yönetici Ayrıcalıkları (GDAP) kullanmanızı öneririz. Kiracının başarıyla eklenebilmesi için temsilci Yönetici Ayrıcalıkları (DAP) hala gereklidir, ancak yalnızca GDAP müşterileri yakında DAP bağımlılığı olmadan ekleme yapabilir. MÜŞTERI için DAP ve GDAP bir arada olduğunda GDAP izinleri önceliklidir.

GDAP ilişkisi ayarlamak için bkz. [Müşterinin hizmetini yönetmek için ayrıntılı yönetici izinleri alma](/partner-center/gdap-obtain-admin-permissions-to-manage-customer). Lighthouse'un hangi rolleri kullanmasını önerdiğimiz hakkında daha fazla bilgi için bkz. [Microsoft 365 Lighthouse'de izinlere genel bakış](m365-lighthouse-overview-of-permissions.md).

MSP teknisyenleri ayrıca Temsilci Yönetici Ayrıcalıkları (DAP) aracılığıyla Yönetici Aracısı veya Yardım Masası Aracısı rollerini kullanarak Lighthouse'a erişebilir.

Lighthouse'da müşteri kiracısı ile ilgili olmayan eylemler için (örneğin, ekleme, müşteri devre dışı bırakma/yeniden etkinleştirme, etiketleri yönetme, günlükleri gözden geçirme), MSP teknisyenlerinin iş ortağı kiracısında atanmış bir rolü olmalıdır. İş ortağı kiracı rolleri hakkında daha fazla bilgi için bkz. Microsoft 365 Lighthouse izinlere [genel bakış](m365-lighthouse-overview-of-permissions.md).

## <a name="set-up-azure-ad-privileged-identity-management-pim"></a>Azure AD Privileged Identity Management ayarlama (PIM)

MSP'ler, PIM kullanarak bilgileri veya kaynakları güvenli hale getirmek için yüksek ayrıcalıklı rol erişimine sahip kişi sayısını en aza indirebilirsiniz. PIM, kötü amaçlı bir kişinin kaynaklara veya yetkili kullanıcılara yanlışlıkla hassas bir kaynağı etkileme olasılığını azaltır. MSP'ler ayrıca kullanıcılara kaynaklara erişmek, geniş değişiklikler yapmak ve belirlenen kullanıcıların ayrıcalıklı erişimleriyle ne yaptığını izlemek için tam zamanında yüksek ayrıcalıklı roller verebilir.

> [!NOTE]
> Azure AD PIM kullanmak için iş ortağı kiracısında Azure AD Premium P2 lisansı gerekir.

Aşağıdaki adımlar, PIM kullanarak iş ortağı kiracı kullanıcılarını zaman kapsamlı daha yüksek ayrıcalık rollerine yükseltin:

1. [Azure Active Directory'de rol atamak için grup oluşturma](/azure/active-directory/roles/groups-create-eligible) makalesinde açıklandığı gibi rol atanabilir bir grup oluşturun.

2. [Azure AD – Tüm Gruplar'a](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) gidin ve yeni grubu yüksek ayrıcalıklı roller için bir güvenlik grubunun üyesi olarak ekleyin (örneğin, DAP için aracılar güvenlik grubu veya GDAP rolleri için benzer bir güvenlik grubu Yönetici).

3. Ayrıcalıklı erişim [grupları için uygun sahipler ve üyeler atama](/azure/active-directory/privileged-identity-management/groups-assign-member-owner) makalesinde açıklandığı gibi yeni gruba ayrıcalıklı erişim ayarlayın.

PIM hakkında daha fazla bilgi edinmek için bkz. [Privileged Identity Management nedir?](/azure/active-directory/privileged-identity-management/pim-configure)

## <a name="set-up-risk-based-azure-ad-conditional-access"></a>Risk tabanlı Azure AD Koşullu Erişimi ayarlama

MSP'ler, personel üyelerinin kimliklerini MFA kullanarak ve riskli bir kullanıcı olarak algılandığında parolalarını değiştirerek (sızan kimlik bilgileriyle veya Azure AD tehdit bilgilerine göre) kimliklerini kanıtlamalarını sağlamak için risk tabanlı Koşullu Erişim kullanabilir. Kullanıcıların riskli bir oturum açma olarak algılandığında tanıdık bir konumdan veya kayıtlı cihazdan da oturum açması gerekir. Diğer riskli davranışlar arasında kötü amaçlı veya anonim bir IP adresinden ya da atipik veya imkansız bir seyahat konumundan oturum açma, anormal belirteç kullanma, parola spreyinden parola kullanma veya başka olağan dışı oturum açma davranışı sergileme sayılabilir. Bir kullanıcının risk düzeyine bağlı olarak, MSP'ler oturum açma sırasında erişimi engellemeyi de seçebilir. Riskler hakkında daha fazla bilgi edinmek için bkz. [Risk nedir?](/azure/active-directory/identity-protection/concept-identity-protection-risks)

> [!NOTE]
> Koşullu Erişim, iş ortağı kiracısında Azure AD Premium P2 lisansı gerektirir. Koşullu Erişim'i ayarlamak için bkz. [Azure Active Directory Koşullu Erişimi Yapılandırma](/appcenter/general/configuring-aad-conditional-access).

## <a name="related-content"></a>İlgili içerik

[Parola sıfırlama izinleri](/azure/active-directory/roles/permissions-reference#password-reset-permissions) (makale)\
[Microsoft 365 Lighthouse izinlerine genel bakış](m365-lighthouse-overview-of-permissions.md) (makale)\
[Azure Active Directory rollerinizi Microsoft 365 Lighthouse 'de görüntüleme](m365-lighthouse-view-your-roles.md) (makale)\
[Microsoft 365 Lighthouse gereksinimleri](m365-lighthouse-requirements.md) (makale)\
[Microsoft 365 Lighthouse genel bakış](m365-lighthouse-overview.md) (makale)\
[Microsoft 365 Lighthouse için kaydolun](m365-lighthouse-sign-up.md) (makale)\
[Microsoft 365 Lighthouse SSS](m365-lighthouse-faq.yml) (makale)