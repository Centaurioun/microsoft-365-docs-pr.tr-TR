---
title: Paylaşılan kanalda dış katılımcılarla işbirliği yapma
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.collection:
- highpri
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom: ''
localization_priority: Priority
f1.keywords: NOCSH
recommendations: false
description: Kuruluşunuzun dışındaki kişilerle işbirliği yapmak için Microsoft Teams'de paylaşılan kanalları etkinleştirmeyi öğrenin.
ms.openlocfilehash: 6f188f82e6f1c17cfc963449872e1c88a1c205ac
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67730693"
---
# <a name="collaborate-with-external-participants-in-a-shared-channel"></a>Paylaşılan kanalda dış katılımcılarla işbirliği yapma

Kullanıcılarınızın [paylaşılan kanallarda](/MicrosoftTeams/shared-channels) diğer Microsoft 365 kuruluşlarındaki kişilerle işbirliği yapmasını sağlamak istiyorsanız, işbirliği yapmak istediğiniz her kuruluş için B2B doğrudan bağlanmayı yapılandırmanız gerekir. (Alternatif olarak, [Paylaşılan kanalları tüm dış kuruluşlarla etkinleştirebilirsiniz](/microsoft-365/solutions/allow-direct-connect-with-all-organizations).)

Teams'de paylaşılan kanalları başka bir kuruluşla etkinleştirdiğinizde:

- Kuruluşunuzdaki ekip sahipleri, diğer kuruluşlardan kişileri paylaşılan kanallara katılmaya davet edebilecek.
- Kuruluşunuzun özel (iş kolu) uygulamaları paylaşılan kanallarda kullanılabilir ve dış katılımcılar bunlara erişebilir.
- Kuruluşunuzun uygulama listesi paylaşılan kanallarda kullanılabilir ve dış katılımcılar bunlara erişebilir.

> [!NOTE]
> Dış katılımcılarla paylaşılan kanalları kullanmak [için Microsoft 365 Grupları konuk ayarlarının](/microsoft-365/admin/create-groups/manage-guest-access-in-groups) etkinleştirilmesi gerekir.

## <a name="video-demonstration"></a>Video tanıtımı

Bu videoda, bu belgede açıklanan yapılandırma adımları gösterilmektedir.
<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4WRMx?autoplay=false]

## <a name="enable-shared-channels-in-teams"></a>Teams'de paylaşılan kanalları etkinleştirme

Paylaşılan kanallar Teams'de varsayılan olarak etkindir. Ayarları onaylamak için bu yordamı izleyin.

Paylaşılan kanalları yapılandırmak için
1. [Teams yönetim merkezinde Teams'i](https://admin.teams.microsoft.com/) **genişletin** ve teams **ilkeleri'ni** seçin.
1. Paylaşılan kanalları etkinleştirmek istediğiniz ilkeyi seçin ve ardından **Düzenle'yi** seçin.
1. Etkinleştirmek istediğiniz seçenekleri belirtin:
    - Ekip sahiplerinin paylaşılan kanallar oluşturmasına izin vermek için **Paylaşılan kanallar oluştur'u** açın.
    - Ekip sahiplerinin paylaşılan kanalları kuruluş dışındaki kişilerle paylaşmasına izin vermek **için Dış kullanıcıları paylaşılan kanallara davet et'i** açın.
    - Kullanıcıların diğer kuruluşlardaki paylaşılan kanallara davet edilmesine izin vermek için **Dış paylaşılan kanallara katıl'ı** açın.
1. **Uygula'yı** seçin.

Dış kanal katılımcılarının toplantılara katılması için dış erişimin etkinleştirilmesi gerekir. Bu, dış katılımcıların kanaldaki iletişim durumunu görebilmek için de gereklidir.

Dış erişimi etkinleştirmek için
1. [Teams yönetim merkezinde](https://admin.teams.microsoft.com/) **Kullanıcılar'ı** genişletin ve ardından **Dış erişim'i** seçin.
1. **Teams ve dış kuruluşlardaki kullanıcıları Skype Kurumsal** altında, işbirliği yapmak istediğiniz kuruluşların engellenmediğinden emin olun.

## <a name="configure-cross-tenant-access-settings-in-azure-ad"></a>Azure AD'de kiracılar arası erişim ayarlarını yapılandırma

Azure AD B2B doğrudan bağlantı varsayılan olarak devre dışıdır. Diğer kuruluşlardaki kişilerle paylaşılan kanallarda işbirliğini etkinleştirmek için şunları yapabilmeniz gerekir:

1. [Kuruluş ekleme](#add-an-organization).
1. Kuruluştaki kullanıcıların paylaşılan kanallarınıza davet edilmesine izin vermek için kuruluşa [yönelik gelen ayarları yapılandırın](#configure-inbound-settings).
1. Kullanıcılarınızın diğer kuruluşun paylaşılan kanallarına davet edilmesine izin vermek için kuruluş için [giden ayarlarını yapılandırın](#configure-outbound-settings).

Bu yapılandırmanın bir parçası olarak, Teams ve SharePoint gibi Teams ile tümleşik hizmetleri içeren **Office 365** uygulamasını etkinleştiririz.

> [!NOTE]
> Kiracılar arası erişim ayarlarında yapılan değişikliklerin etkili olması altı saat kadar sürebilir.

> [!NOTE]
> Ticari ve GCC bulutları arasında paylaşılan kanallar desteklenmez.

### <a name="add-an-organization"></a>Kuruluş ekleme

Paylaşılan kanallara katılmak istediğiniz her kuruluşu ekleyin.

Kuruluş eklemek için
1. Genel yönetici veya Güvenlik yöneticisi hesabı kullanarak [Azure Active Directory'de](https://aad.portal.azure.com) oturum açın.
1. **Dış Kimlikler'i** ve ardından **Kiracılar arası erişim ayarları'nı** seçin.
1. **Kuruluş ayarları'nı** seçin.
1. **Kuruluş ekle'yi** seçin.
1. **Kuruluş ekle** bölmesinde, kuruluşun tam etki alanı adını (veya kiracı kimliğini) yazın ve Enter tuşuna basın.
1. **Ekle**'yi seçin.
1. Kuruluş, kuruluşlar listesinde görünür. Bu noktada, bu kuruluşun tüm erişim ayarları varsayılan ayarlarınızdan devralınır.

### <a name="configure-inbound-settings"></a>Gelen ayarları yapılandırma

Dış katılımcıları davet etmek istediğiniz her kuruluş için bu yordamı izleyin.

Bir kuruluşun gelen ayarlarını yapılandırmak için
1. [Azure Active Directory'de](https://aad.portal.azure.com) **Dış Kimlikler'i** ve ardından **Kiracılar arası erişim ayarları'nı** seçin.
1. Değiştirmek istediğiniz kuruluşun gelen erişim bağlantısını seçin.
1. **B2B doğrudan bağlantı** sekmesinde **Ayarları özelleştir'i** seçin.
1. **Dış kullanıcılar ve gruplar** sekmesinde **Erişime izin ver'i** ve **Tüm dış kullanıcılar ve gruplar'ı** seçin. (Gizlilik sözleşmesi imzalayanlar gibi belirli **kullanıcılar ve gruplara** erişimi sınırlamak istiyorsanız Dış kullanıcıları ve grupları seç'i seçebilirsiniz.)
1. **Uygulamalar** sekmesinde **Erişime izin ver** ve **Uygulamaları seç'i** seçin.
1. **Microsoft uygulamaları ekle'yi** seçin.
1. **Office 365** uygulamasını ve ardından **Seç'i** seçin.
1. **Kaydet'i** seçin ve **Gelen erişim ayarları** dikey penceresini kapatın.

### <a name="configure-outbound-settings"></a>Giden ayarlarını yapılandırma

Kullanıcılarınızın dış paylaşılan kanallara katılmasını istediğiniz her kuruluş için bu yordamı izleyin.

Bir kuruluş için giden ayarları yapılandırmak için
1. [Azure Active Directory'de](https://aad.portal.azure.com) **Dış Kimlikler'i** ve ardından **Kiracılar arası erişim ayarları'nı** seçin.
1. Değiştirmek istediğiniz kuruluşun giden erişim bağlantısını seçin.
1. **B2B doğrudan bağlantı** sekmesinde **Ayarları özelleştir'i** seçin.
1. **Dış kullanıcılar ve gruplar** sekmesinde **Erişime izin ver'i** seçin ve Tüm kullanıcılar **için bir Geçerlidir'i** ayarlayın.
1. **Dış uygulamalar** sekmesinde **Erişime izin ver'i** ve **Dış uygulamaları seçin'i** seçin.
1. **Microsoft uygulamaları ekle'yi** seçin.
1. **Office 365** uygulamasını ve ardından **Seç'i** seçin.
1. **Kaydet'i** seçin, onaylamak için **Evet'i** seçin ve **Giden erişim ayarları** dikey penceresini kapatın.

## <a name="see-also"></a>Ayrıca bkz.

[B2B doğrudan bağlanmaya genel bakış](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[B2B doğrudan bağlantı için kiracılar arası erişim ayarlarını yapılandırma](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[Kuruluş tarafından kimlerin davet edilebileceğini sınırlayın](limit-invitations-from-specific-organization.md)

[Paylaşılan kanallar sınırları](/MicrosoftTeams/shared-channels#shared-channel-limits)
