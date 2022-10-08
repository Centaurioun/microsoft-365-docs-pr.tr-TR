---
title: Microsoft 365 grupları, Teams ve SharePoint'te erişimi yönetme
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Microsoft 365 grupları, Teams ve SharePoint'te erişimi yönetme hakkında bilgi edinin.
ms.openlocfilehash: 7d0f49f394bb6c5408c7de98d9fe63f306b334b2
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67985750"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Microsoft 365 grupları, Teams ve SharePoint'te erişimi yönetme

Kişilerin gruplar, ekipler ve SharePoint'teki kaynaklara nasıl erişeceklerini yönetmenizi sağlayan birçok denetim vardır. Bu seçenekleri gözden geçirin ve bunların iş gereksinimlerinizle nasıl eşlendiğini, verilerinizin duyarlılığını ve kullanıcılarınızın işbirliği yapması gereken kişilerin kapsamını göz önünde bulundurun.

Aşağıdaki tabloda, Microsoft 365'te kullanılabilen erişim denetimleri için hızlı başvuru sağlanmaktadır. Aşağıdaki bölümlerde daha fazla bilgi verilmiştir.

|Kategori|Açıklama|Başvuru|
|:-------|:----------|:--------|
|Üyelik|||
||Özel ekipleri bulma|[Microsoft Teams'de özel ekiplerin keşfini yönetme](/microsoftteams/manage-discovery-of-private-teams)|
||Kurallara göre dinamik grup üyeliği|[Azure Active Directory'de dinamik grup oluşturma veya güncelleştirme](/azure/active-directory/users-groups-roles/groups-create-rule)|
||Dosyaları, klasörleri ve siteleri kimlerin paylaşabileceğini denetleyin.|[Erişim isteklerini ayarlama ve yönetme](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|Koşullu erişim|||
||Çok Faktörlü Kimlik Doğrulaması|[çok faktörlü kimlik doğrulamasını Azure AD](/azure/active-directory/authentication/concept-mfa-howitworks)|
||Grup, ekip veya site duyarlılığına göre cihaz erişimini denetleme.|[Microsoft Teams, Microsoft 365 grupları ve SharePoint sitelerindeki içeriği korumak için duyarlılık etiketlerini kullanma](../compliance/sensitivity-labels-teams-groups-sites.md)|
||Yönetilmeyen cihazlar için site erişimini sınırlayın.|[Yönetilmeyen cihazlardan SharePoint erişimini denetleme](/sharepoint/control-access-from-unmanaged-devices)|
||Konuma göre site erişimini denetleme|[Ağ konumuna göre SharePoint ve OneDrive verilerine erişimi denetleme](/sharepoint/control-access-based-on-network-location)|
|Konuk erişimi|||
||Belirtilen etki alanlarından SharePoint paylaşımına izin verin veya bunları engelleyin.|[SharePoint ve OneDrive içeriğinin etki alanına göre paylaşımını kısıtlama](/sharepoint/restricted-domains-sharing)|
||Belirtilen etki alanlarından ekip veya grup üyeliğine izin verin veya bunları engelleyin.|[Belirli kuruluşların B2B kullanıcılarına yönelik davetlere izin verme veya davetleri engelleme](/azure/active-directory/b2b/allow-deny-list)|
||Anonim paylaşımı önleyin.|[Herkes bağlantılarını kapatma](./share-limit-accidental-exposure.md#turn-off-anyone-links)|
||Anonim erişim bağlantılarının izinlerini denetleyin.|[Herkes bağlantıları için bağlantı izinlerini ayarlama](./best-practices-anonymous-sharing.md#set-link-permissions)|
||Anonim paylaşım bağlantılarının süre sonunu denetleme.|[Herkes bağlantıları için son kullanma tarihi ayarlama](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)|
||Varsayılan olarak kullanıcılara gösterilen paylaşım bağlantısının türünü kontrol edin.|[Bir site için varsayılan bağlantı türünü değiştirme](/sharepoint/change-default-sharing-link)|
||Dış paylaşımı belirli kişilerle sınırlayın.|[Dış paylaşımı belirtilen güvenlik gruplarıyla sınırlama](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||Bilgi duyarlılığına göre grup, ekip veya siteye konuk erişimini denetleme.|[Microsoft Teams, Microsoft 365 grupları ve SharePoint sitelerindeki içeriği korumak için duyarlılık etiketlerini kullanma](../compliance/sensitivity-labels-teams-groups-sites.md)|
||Paylaşım seçeneklerini kapatın.|[Microsoft 365'te paylaşımı sınırlama](./microsoft-365-limit-sharing.md)|
|Kullanıcı yönetimi|||
||Ekip ve grup üyeliğini düzenli olarak gözden geçirin.|[erişim gözden geçirmeleri Azure AD nedir?](/azure/active-directory/governance/access-reviews-overview)|
||Gruplara ve ekiplere erişim yönetimini otomatikleştirme.|[Azure AD yetkilendirme yönetimi nedir?](/azure/active-directory/governance/entitlement-management-overview)|

## <a name="membership"></a>Üyelik

Ekipler ve grupların üyeliği sahipler tarafından denetlenmektedir. Üyeler başkalarını davet edebilir, ancak davetler onay için sahiplere gönderilir. Genel ekipler ve gruplar kuruluştaki herkes tarafından bulunabilir olsa da, özel ekiplerin ve grupların bulunabilir olup olmadığını denetleyebilirsiniz:

- [Microsoft Teams'de özel ekiplerin keşfini yönetme](/microsoftteams/manage-discovery-of-private-teams)

Bir grubun veya ekibin üyeliğini departman gibi bazı ölçütlere göre dinamik olarak yönetebilirsiniz. Bu durumda, üyeler ve sahipler kişileri ekise davet edemez. Dinamik gruplar, grubun kimlerin üyesi olduğunu denetlemek için Azure Active Directory'de tanımladığınız meta verileri kullanır. Yanlış meta veriler kullanıcıların grup dışında bırakılmasına veya yanlış kullanıcıların eklenmesine neden olabileceğinden, kullandığınız meta verilerin eksiksiz ve güncel olduğundan emin olun.

- [Azure Active Directory'de dinamik grup oluşturma veya güncelleştirme](/azure/active-directory/users-groups-roles/groups-create-rule)

SharePoint siteleri, grup veya ekip üyeliği dışında sahipler, üyeler ve ziyaretçiler ekleme olanağı sağlar. Gereksinimlerinize bağlı olarak, siteye kişileri davet edebilecek kişileri kısıtlamak isteyebilirsiniz. Ayrıca, belirli bir sitedeki bilgilerin duyarlılığına bağlı olarak, dosya ve klasör paylaşabilecek kişileri kısıtlamak isteyebilirsiniz. Bu kısıtlamalar ekip, grup veya site sahibi tarafından yapılandırılır:

- [Erişim isteklerini ayarlama ve yönetme](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>Koşullu erişim

Microsoft 365 ile hem kuruluşunuzun içindeki hem de dışındaki kişiler için çok faktörlü kimlik doğrulaması gerektirebilirsiniz. kişilere ikinci bir kimlik doğrulaması faktörü istendiğinde, bu koşullar için birçok seçenek vardır. Kuruluşunuz için çok faktörlü kimlik doğrulamasını dağıtmanızı kesinlikle öneririz:

- [Çok faktörlü kimlik doğrulamasını Azure AD](/azure/active-directory/authentication/concept-mfa-howitworks)

Bazı gruplarınızda ve ekiplerinizde hassas bilgiler varsa, bir grubun veya ekibin duyarlılık etiketine göre cihaz yönetimi ilkelerini zorunlu kılabilirsiniz. Yönetilmeyen cihazlardan erişimi tamamen engelleyebilir veya yalnızca sınırlı web erişimine izin vekleyebilirsiniz:

- [Microsoft Teams, Microsoft 365 grupları ve SharePoint sitelerindeki içeriği korumak için duyarlılık etiketlerini kullanma](../compliance/sensitivity-labels-teams-groups-sites.md)

SharePoint'te, belirtilen ağ konumlarından sitelere erişimi kısıtlayabilirsiniz.

- [Ağ konumuna göre SharePoint ve OneDrive verilerine erişimi denetleme](/sharepoint/control-access-based-on-network-location)


Ek kaynaklar:

- [Koşullu Erişim dağıtımı planlama](/azure/active-directory/conditional-access/plan-conditional-access)

- [Microsoft Intune genel bakış](/mem/intune/fundamentals/what-is-intune)

- [Yönetilmeyen cihazlardan SharePoint erişimini denetleme](/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>Konuk erişimi

Konukları e-posta adreslerinin etki alanına göre kısıtlayabilirsiniz. SharePoint kuruluş genelinde ve siteye özgü etki alanı kısıtlama ayarları sunar. Gruplar ve Teams, Azure AD'da etki alanı izin verilenler listesini veya blok listelerini kullanır. İstenmeyen paylaşımlardan kaçınmak ve tutarlı bir kullanıcı deneyimi sağlamak için her iki ayarı da yapılandırdığından emin olun:

- [SharePoint ve OneDrive içeriğinin etki alanına göre paylaşımını kısıtlama](/sharepoint/restricted-domains-sharing)

- [Belirli kuruluşların B2B kullanıcılarına yönelik davetlere izin verme veya davetleri engelleme](/azure/active-directory/b2b/allow-deny-list)

Microsoft 365, *Herkes* paylaşım bağlantılarını kullanarak dosya ve klasörlerin anonim olarak paylaşılmasına izin verir. *Herkes* bağlantı iletilebilir ve bağlantıya sahip olan herkes paylaşılan öğeye erişebilir. Verilerinizin duyarlılığına bağlı olarak *, Herkes* bağlantılarının nasıl kullanıldığını (bunların tamamını kapatma, bağlantı izinlerini salt okunur olarak kısıtlama veya bunlar için bir süre sonu süresi ayarlama dahil) yönetmeyi göz önünde bulundurun:

- [Herkes bağlantılarını kapatma](./share-limit-accidental-exposure.md#turn-off-anyone-links)

- [Herkes bağlantıları için bağlantı izinlerini ayarlama](./best-practices-anonymous-sharing.md#set-link-permissions)

- [Herkes bağlantıları için son kullanma tarihi ayarlama](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)

Dosya veya klasör paylaşırken, kullanıcıların aralarından seçim yapabileceğiniz çeşitli bağlantı türleri vardır. Yanlışlıkla uygunsuz paylaşım riskini azaltmak için, kullanıcılar paylaştığında kullanıcılara sunulan varsayılan bağlantı türünü değiştirebilirsiniz. Örneğin, varsayılanı anonim erişime izin veren *Herkes* bağlantılarından *kuruluşunuzdaki Kişiler* olarak değiştirmek, hassas bilgilerin istenmeyen dış paylaşımı riskini azaltabilir:

- [Bir site için varsayılan bağlantı türünü değiştirme](/sharepoint/change-default-sharing-link)

Kuruluşunuzda konuklarla paylaşmanız gereken hassas veriler varsa ancak uygunsuz paylaşım konusunda endişeleriniz varsa, dosya ve klasörlerin dış paylaşımını belirtilen güvenlik gruplarının üyeleriyle sınırlayabilirsiniz. Bu şekilde, dış paylaşımı belirli bir grup kişiyle kısıtlayabilir veya kullanıcılarınızın güvenlik grubuna eklemeden önce uygun dış paylaşım hakkında eğitim almasını zorunlu kılabilirsiniz:

- [Dış paylaşımı belirtilen güvenlik gruplarıyla sınırlama](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

Gruplar ve Teams, konuk erişimine izin veren veya erişimi reddeden kuruluş düzeyinde ayarlara sahiptir. [Microsoft PowerShell kullanarak belirli ekiplere veya gruplara konuk erişimini kısıtlayabilirsiniz](per-group-guest-access.md) ancak bunu duyarlılık etiketi aracılığıyla yapmanız önerilir. Duyarlılık etiketleriyle, uygulanan etikete göre konuk erişimine otomatik olarak izin verebilir veya erişimi reddedebilirsiniz:

- [Microsoft Teams, Microsoft 365 grupları ve SharePoint sitelerindeki içeriği korumak için duyarlılık etiketlerini kullanma](../compliance/sensitivity-labels-teams-groups-sites.md)

Konukları sık sık gruplara ve ekiplere davet ettiğiniz bir ortamda, düzenli olarak zamanlanmış konuk erişimi gözden geçirmeleri ayarlamayı göz önünde bulundurun. Sahiplerin gruplarında ve ekiplerinde konukları gözden geçirmeleri ve erişimi onaylamaları veya reddetmeleri istenebilir.

- [Konuk erişimi gözden geçirmelerini ayarlama](/microsoft-365/solutions/create-secure-guest-sharing-environment#set-up-guest-access-reviews)

Microsoft 365, bilgi paylaşmanın birçok farklı yöntemini sunar. Hassas bilgileriniz varsa ve paylaşılma biçimini kısıtlamak istiyorsanız paylaşımı sınırlama seçeneklerini gözden geçirin:

- [Microsoft 365'te paylaşımı sınırlama](./microsoft-365-limit-sharing.md)

Ek kaynaklar:

- [Microsoft 365 ile güvenli işbirliği kurun](./setup-secure-collaboration-with-teams.md)

- [Kimliği doğrulanmamış kullanıcılarla dosya ve klasör paylaşmaya yönelik en iyi yöntemler](./best-practices-anonymous-sharing.md)

- [Kuruluşunuzun dışındaki kişilerle paylaşım yaparken dosyaların yanlışlıkla açığa çıkmalarını sınırlayın](./share-limit-accidental-exposure.md)

- [Güvenli bir konuk paylaşım ortamı oluşturma](./create-secure-guest-sharing-environment.md)

- [B2B dış işbirliğini etkinleştirme ve konukları kimlerin davet edebileceğini yönetme](/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>Kullanıcı yönetimi

Kuruluşunuzda gruplar ve ekipler geliştikçe, ekip ve grup üyeliğini düzenli olarak gözden geçirmek iyi bir uygulamadır. Bu özellikle üyeliği değişen ekipler ve gruplar, hassas bilgiler içerenler veya konuk içeren gruplar için yararlı olabilir. Bu ekipler ve gruplar için erişim gözden geçirmeleri ayarlamayı göz önünde bulundurun:

- [erişim gözden geçirmeleri Azure AD nedir?](/azure/active-directory/governance/access-reviews-overview)

Birçok kuruluşun, işbirliği yaptıkları diğer kuruluşlar veya önemli satıcılarla iş ortaklıkları vardır. Bu senaryolarda kullanıcı yönetimi ve kaynaklara erişimi yönetmek zor olabilir. Bazı kullanıcı yönetimi görevlerini otomatikleştirmeyi ve hatta bazılarını iş ortağı kuruluşunuza geçirmeyi göz önünde bulundurun:

- [Azure AD yetkilendirme yönetimi nedir?](/azure/active-directory/governance/entitlement-management-overview)

Teams'deki özel kanallar, ekip üyelerinin bir alt kümesi arasında kapsamlı konuşmalara ve dosya paylaşımına olanak tanır. Belirli iş gereksinimlerinize bağlı olarak, bu özelliğe izin vermek veya bu özelliği engellemek isteyebilirsiniz.

- [Microsoft Teams'de özel kanallar](/MicrosoftTeams/private-channels)

Paylaşılan kanallar, ekip dışından veya kuruluş dışından kişileri davet etmenizi sağlar. Belirli iş gereksinimlerinize ve dış paylaşım ilkelerinize bağlı olarak, bu özelliğe izin vermek veya bu özelliği engellemek isteyebilirsiniz.

- [Paylaşılan kanallar](/MicrosoftTeams/shared-channels)

Ek kaynaklar:

- [Azure Active Directory Kimlik İdaresi](/azure/active-directory/governance)

## <a name="related-topics"></a>İlgili konular

[İşbirliği idaresi planlama önerileri](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[İşbirliği idare planınızı oluşturma](collaboration-governance-first.md)

[Microsoft Teams'de güvenlik ve uyumluluk](/microsoftteams/security-compliance-overview)

[SharePoint'te paylaşım ayarlarını yönetme](/sharepoint/turn-external-sharing-on-or-off)

[Yammer'da dış ağ oluşturma ve yönetme](/yammer/work-with-external-users/create-and-manage-an-external-network)

[Teams'i üç koruma katmanıyla yapılandırma](./configure-teams-three-tiers-protection.md)