---
title: Konuk ve dış kullanıcı B2B erişimine izin vermek için kimlik ve cihaz erişim ilkeleri - Kurumsal | için Microsoft 365 Microsoft Docs
description: Önerilen Koşullu Erişim'i ve konukların ve dış kullanıcıların erişimini korumaya yönelik ilgili ilkeleri açıklar.
ms.service: microsoft-365-security
ms.topic: article
ms.author: dansimp
author: dansimp
audience: Admin
manager: Laurawi
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- m365-security
- m365solution-identitydevice
- m365solution-scenario
- zerotrust-solution
- highpri
ms.subservice: mdo
search.appverid: met150
ms.openlocfilehash: 0d7a51a8afb51265a63954749370f4939557a11b
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68088673"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a>Konuk erişimine ve B2B dış kullanıcı erişimine izin verme ilkeleri

Bu makalede, Azure Active Directory (Azure AD) İşletmeler arası (B2B) hesabı olan konuklara ve dış kullanıcılara erişime izin vermek için önerilen Sıfır Güven kimlik ve cihaz erişim ilkelerinin ayarlanması ele alınmaktadır. Bu kılavuz [, ortak kimlik ve cihaz erişim ilkelerine](identity-access-policies.md) dayalıdır.

Bu öneriler, korumanın **başlangıç noktası** katmanına uygulanacak şekilde tasarlanmıştır. Ancak önerileri **kurumsal** ve **özel güvenlik** koruması gereksinimlerinize göre de ayarlayabilirsiniz.

B2B hesaplarının Azure AD kiracınızla kimlik doğrulaması için bir yol sağlanması, bu hesapların ortamınızın tamamına erişim izni vermez. B2B kullanıcıları ve hesapları, Koşullu Erişim ilkesi tarafından kendileriyle paylaşılan dosyalar gibi hizmetlere ve kaynaklara erişebilir.

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a>Konuk ve dış kullanıcı erişimine izin vermek ve bunları korumak için ortak ilkeleri güncelleştirme

Bu diyagramda, B2B konuk ve dış kullanıcı erişimi için ortak kimlik ve cihaz erişim ilkeleri arasında hangi ilkelerin ekleneceği veya güncelleştirildiği gösterilir.

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png" alt-text="Konuk erişimini korumaya yönelik ilke güncelleştirmelerinin özeti" lightbox="../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png":::

Aşağıdaki tabloda oluşturmanız ve güncelleştirmeniz gereken ilkeler listelenir. Ortak ilkeler, [Ortak kimlik ve cihaz erişim ilkeleri](identity-access-policies.md) makalesindeki ilişkili yapılandırma yönergelerine bağlanır.

|Koruma düzeyi|İlkeler|Daha fazla bilgi|
|---|---|---|
|**Başlangıç noktası**|[Konuklar ve dış kullanıcılar için her zaman MFA gerektir](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Bu yeni ilkeyi oluşturun ve yapılandırın: <ul><li>**Dahil > Kullanıcılar ve gruplar > Atamalar** için **Kullanıcıları ve grupları seç'i** ve ardından **Tüm konuk ve dış kullanıcılar'ı** seçin.</li><li>**Atamalar > Koşulları > Oturum Açma için**, her zaman çok faktörlü kimlik doğrulamasını (MFA) zorunlu kılmak için tüm seçenekleri işaretsiz bırakın.</li></ul>|
||[Oturum açma riski *orta* veya *yüksek* olduğunda MFA gerektirme](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Konukları ve dış kullanıcıları dışlamak için bu ilkeyi değiştirin.|

Koşullu Erişim ilkelerine konukları ve dış kullanıcıları dahil etmek veya dışlamak için, **Kullanıcılar ve Gruplar > Dahil Et** veya **Dışla** > Atamalar için **Tüm konuk ve dış kullanıcılar'ı** işaretleyin.

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png" alt-text="Konukları ve dış kullanıcıları dışlamak için denetimler" lightbox="../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png":::

## <a name="more-information"></a>Daha fazla bilgi

### <a name="guests-and-external-user-access-with-microsoft-teams"></a>Microsoft Teams ile konuklara ve dış kullanıcıya erişim

Microsoft Teams aşağıdaki kullanıcıları tanımlar:

- **Konuk erişimi**, bir ekibin üyesi olarak eklenebilen ve ekibin iletişimlerine ve kaynaklarına erişebilen bir Azure AD B2B hesabı kullanır.

- **Dış erişim** , B2B hesabı olmayan bir dış kullanıcıya yöneliktir. Dış kullanıcı erişimi davetleri, aramaları, sohbetleri ve toplantıları içerir, ancak ekip üyeliğini ve ekibin kaynaklarına erişimi içermez.

Daha fazla bilgi için bkz. [Ekipler için konuklar ve dış kullanıcı erişimi karşılaştırması](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).

Teams için kimlik ve cihaz erişim ilkelerinin güvenliğini sağlama hakkında daha fazla bilgi için bkz. [Teams sohbetlerinin, gruplarının ve dosyalarının güvenliğini sağlamaya yönelik ilke önerileri](teams-access-policies.md).

### <a name="require-mfa-always-for-guest-and-external-users"></a>Konuk ve dış kullanıcılar için her zaman MFA iste

Bu ilke, konuklarınızın ev kiracısında MFA'ya kayıtlı olup olmadıklarına bakılmaksızın kiracınızda MFA'ya kaydolmalarını ister. Kiracınızdaki kaynaklara erişirken, konukların ve dış kullanıcıların her istek için MFA kullanması gerekir.

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a>Risk tabanlı MFA'dan konukları ve dış kullanıcıları dışlama

Kuruluşlar Azure AD Kimlik Koruması kullanarak B2B kullanıcıları için risk tabanlı ilkeleri zorunlu kılabilirken, B2B işbirliği kullanıcıları için Azure AD Kimlik Koruması'nın bir kaynak dizininde uygulanmasında, giriş dizinlerinde var olan kimlikleri nedeniyle sınırlamalar vardır. Bu sınırlamalar nedeniyle Microsoft, konukları risk tabanlı MFA ilkelerinin dışında tutmanızı ve bu kullanıcıların her zaman MFA kullanmasını zorunlu tutmanızı önerir.

Daha fazla bilgi için bkz. [B2B işbirliği kullanıcıları için Kimlik Koruması sınırlamaları](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).

### <a name="excluding-guests-and-external-users-from-device-management"></a>Konukları ve dış kullanıcıları cihaz yönetiminden dışlama

Bir cihazı yalnızca bir kuruluş yönetebilir. Konukları ve dış kullanıcıları cihaz uyumluluğu gerektiren ilkelerden dışlamıyorsanız, bu ilkeler bu kullanıcıları engeller.

## <a name="next-step"></a>Sonraki adım

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png" alt-text="Microsoft 365 bulut uygulamaları ve Microsoft Defender for Cloud Apps için İlkeler" lightbox="../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png":::

Koşullu Erişim ilkelerini yapılandırma:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
- [Bulut Uygulamaları için Microsoft Defender](mcas-saas-access-policies.md)
 
