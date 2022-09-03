---
title: Konuk paylaşımını belirli kuruluşlarla sınırlayın
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: Konuk paylaşımını belirli Azure AD veya Microsoft 365 kuruluşlarıyla sınırlamayı öğrenin.
ms.openlocfilehash: d6ee18f91955b1975baa85086a7f54942bfb1541
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67585740"
---
# <a name="limit-guest-sharing-to-specific-organizations"></a>Konuk paylaşımını belirli kuruluşlarla sınırlayın

Varsayılan olarak, kullanıcılar kuruluş dışındaki kişileri konuk olarak davet edebilir. Bu, onları Microsoft Team, SharePoint sitelerindeki ekiplere davet etmeyi ve tek tek dosya ve klasörleri onlarla paylaşmayı içerir.

Kullanıcılarınızın yalnızca belirli kuruluşlardan konuk davet etmesini istiyorsanız, [B2B işbirliği](/azure/active-directory/external-identities/what-is-b2b) için Azure Active Directory kiracılar arası erişim ayarlarında bu kuruluşları belirtebilirsiniz.

## <a name="configure-cross-tenant-access-settings"></a>Kiracılar arası erişim ayarlarını yapılandırma

Konuk paylaşımını sınırlamanın ilk adımı, konuk davetini varsayılan olarak engellemek için Azure AD kiracılar arası erişim ayarlarındaki varsayılan ayarları değiştirmektir. Ardından belirli kuruluşlar için konuk davetlerine izin vekleyebilirsiniz.

> [!NOTE]
> Kiracılar arası erişim ayarlarında yapılan değişikliklerin etkili olması iki saat sürebilir.

### <a name="set-the-default-b2b-collaboration-settings-to-block-inviting-guests"></a>Davet eden konukları engellemek için varsayılan B2B işbirliği ayarlarını belirleme

Konuk davet etme özelliği varsayılan olarak etkinleştirildiğinden, konuk davetlerini belirli kuruluşlarla sınırlamak için varsayılan olarak gelen B2B işbirliğinin engellenmesi gerekir.

Gelen B2B işbirliğini varsayılan olarak engellemek için
1. Genel yönetici veya Güvenlik yöneticisi hesabı kullanarak [Azure Active Directory'de](https://aad.portal.azure.com) oturum açın.
1. **Dış Kimlikler'i** ve ardından **Kiracılar arası erişim ayarları (önizleme)** seçeneğini belirleyin.
1. **Varsayılan ayarlar** sekmesini seçin.
1. **Gelen erişim ayarları'nın** altında **Gelen varsayılanları düzenle'yi** seçin.
1. **B2B işbirliği** sekmesini ve **Kullanıcılar ve gruplar** sekmesini seçin.
1. **Erişim durumu** altında **Erişimi engelle'yi** seçin.
1. **Dış erişim** sekmesini seçin.
1. **Erişim durumu** altında **Erişimi engelle'yi** seçin.
1. **Kaydet**'i seçin.
1. **Varsayılan ayarlar** dikey penceresini kapatın.

### <a name="add-the-organization-where-you-want-to-allow-guest-invitations"></a>Konuk davetlerine izin vermek istediğiniz kuruluşu ekleyin

Ardından, kullanıcılarınızın Azure AD kiracılar arası erişim listesine konuk davet etmelerine izin vermek istediğiniz kuruluşları ekleyin.

Kuruluş eklemek için
1. [Azure Active Directory'de](https://aad.portal.azure.com) **Dış Kimlikler'i** ve ardından **Kiracılar arası erişim ayarları (önizleme)** seçeneğini belirleyin.
1. **Kuruluş ayarları'nı** seçin.
1. **Kuruluş ekle'yi** seçin.
1. **Kuruluş ekle** bölmesinde, kuruluşun tam etki alanı adını (veya kiracı kimliğini) yazın.
1. Arama sonuçlarında kuruluşu seçin ve ardından **Ekle'yi** seçin.
1. Kuruluş, **Kuruluş ayarları** listesinde görünür.

Bu noktada, bu kuruluşun tüm erişim ayarları varsayılan ayarlarınızdan devralınır.

### <a name="configure-inbound-settings-for-the-organization-to-allow-all-users"></a>Kuruluş için gelen ayarları tüm kullanıcılara izin verecek şekilde yapılandırma

Kuruluşu ekledikten sonra, B2B işbirliği kullanıcılarının konuk olarak davet edilmesine izin vermek için kuruluşun gelen ayarlarını güncelleştirmeniz gerekir. Bunu, kullanıcılarınızın konuk davet edebilmesine izin vermek istediğiniz her kuruluş için yapın.

1. [Azure Active Directory'de](https://aad.portal.azure.com) **Dış Kimlikler'i** ve ardından **Kiracılar arası erişim ayarları (önizleme)** seçeneğini belirleyin.
1. Değiştirmek istediğiniz kuruluşun gelen erişim bağlantısını seçin.
1. **B2B işbirliği** sekmesinde **Ayarları özelleştir'i** seçin.
1. **Erişim durumu** altında **Erişime izin ver'i** seçin.
1. **Hedef'in** altında tüm kullanıcılara izin vermeyi seçin.
1. **Kaydet'i** seçin ve **Giden erişim ayarları** dikey penceresini kapatın.

## <a name="turn-off-one-time-passcode-authentication"></a>Tek seferlik geçiş kodu kimlik doğrulamasını kapatma

B2B işbirliğini belirli kuruluşlarla sınırlandırdıktan sonra bile, kişiler diğer kuruluşlardaki kişilerle dosya ve klasör paylaşmaya devam edebilir; bu kişilere dizininizde bir konuk hesabı verilmez.

Tamamen diğer kuruluşlarla paylaşımı önlemek istiyorsanız, Azure AD tek seferlik geçiş kodu özelliğini devre dışı bırakmanız gerekir. Bu, kuruluşunuzun dışındaki kişilerin paylaşılan dosyalara veya klasörlere kimlik doğrulaması için tek seferlik geçiş kodu gönderilmesini engeller.

E-posta tek seferlik geçiş kodu özelliğini devre dışı bırakmak için
1. Azure AD genel yöneticisi olarak [Azure portal](https://portal.azure.com/) oturum açın.
1. Gezinti bölmesinde **Azure Active Directory'yi** seçin.
1. **Dış Kimlikler** > **Tüm kimlik sağlayıcıları'ı** seçin.
1. **Tek seferlik Email geçiş kodunu** seçin ve konuklar **için tek seferlik geçiş kodu Email** altında **Konuklar için tek seferlik e-posta geçiş kodunu devre dışı bırak** 'ı seçin (veya Özellik önceden etkinleştirildiyse, devre dışı bırakıldıysa veya önizleme sırasında kabul edildiyse **Hayır'ı** seçin.
1. **Kaydet**'i seçin.

## <a name="related-topics"></a>İlgili konular

[B2B doğrudan bağlanmaya genel bakış](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[B2B doğrudan bağlantı için kiracılar arası erişim ayarlarını yapılandırma](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[Kuruluş tarafından kimlerin davet edilebileceğini sınırlayın](limit-invitations-from-specific-organization.md)

[Kullanıcıların konuk hesaplarına sahip olabileceği kuruluşları sınırlama](limit-organizations-where-users-have-guest-accounts.md)