---
title: Kullanıcıların konuk hesaplarına sahip olabileceği kuruluşları sınırlama
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
description: Kullanıcılarınızın hangi kuruluşlarda konuk hesabı olabileceğini belirtmeyi öğrenin.
ms.openlocfilehash: 8fa2134c59f42924224fc2161c16e26f92532aa1
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67580105"
---
# <a name="limit-organizations-where-users-can-have-guest-accounts"></a>Kullanıcıların konuk hesaplarına sahip olabileceği kuruluşları sınırlama

Varsayılan olarak, diğer Microsoft 365 ve Azure Active Directory kuruluşları kullanıcılarınızı kendi kuruluşlarına konuk olarak katılmaya davet edebilir. Bu, onları Microsoft Team, SharePoint sitelerindeki ekiplere davet etmeyi ve tek tek dosya ve klasörleri onlarla paylaşmayı içerir.

Kullanıcılarınızın yalnızca belirli kuruluşlara konuk olarak katılmasını istiyorsanız bu kuruluşları [B2B işbirliği](/azure/active-directory/external-identities/what-is-b2b) için Azure Active Directory kiracılar arası erişim ayarlarında belirtebilirsiniz.

> [!NOTE]
> Kiracılar arası erişim ayarlarında yapılan değişikliklerin etkili olması iki saat sürebilir.

## <a name="set-the-default-b2b-collaboration-settings-to-block-users-from-being-guests"></a>Kullanıcıların konuk olmasını engellemek için varsayılan B2B işbirliği ayarlarını belirleme

Konuk olarak katılma varsayılan olarak etkinleştirildiğinden, konuk katılımını belirli kuruluşlarla sınırlamak için varsayılan olarak giden B2B işbirliğinin engellenmesi gerekir.

Varsayılan olarak giden B2B işbirliğini engellemek için
1. Genel yönetici veya Güvenlik yöneticisi hesabı kullanarak [Azure Active Directory'de](https://aad.portal.azure.com) oturum açın.
1. **Dış Kimlikler'i** ve ardından **Kiracılar arası erişim ayarları (önizleme)** seçeneğini belirleyin.
1. **Varsayılan ayarlar** sekmesini seçin.
1. **Giden erişim ayarları'nın** altında **Giden varsayılanlarını düzenle'yi** seçin.
1. **B2B işbirliği** sekmesini ve **Kullanıcılar ve gruplar** sekmesini seçin.
1. **Erişim durumu** altında **Erişimi engelle'yi** seçin.
1. **Dış erişim** sekmesini seçin.
1. **Erişim durumu** altında **Erişimi engelle'yi** seçin.
1. **Kaydet**'i seçin.
1. **Varsayılan ayarlar** dikey penceresini kapatın.

## <a name="add-an-organization"></a>Kuruluş ekleme

Ardından, kullanıcılarınızın konuk olarak işbirliği yapmasına izin vermek istediğiniz kuruluşları Azure AD kiracılar arası erişim listesine ekleyin.

Kuruluş eklemek için
1. [Azure Active Directory'de](https://aad.portal.azure.com) **Dış Kimlikler'i** ve ardından **Kiracılar arası erişim ayarları (önizleme)** seçeneğini belirleyin.
1. **Kuruluş ayarları'nı** seçin.
1. **Kuruluş ekle'yi** seçin.
1. **Kuruluş ekle** bölmesinde, kuruluşun tam etki alanı adını (veya kiracı kimliğini) yazın.
1. Arama sonuçlarında kuruluşu seçin ve ardından **Ekle'yi** seçin.
1. Kuruluş, **Kuruluş ayarları** listesinde görünür.

Bu noktada, bu kuruluşun tüm erişim ayarları varsayılan ayarlarınızdan devralınır.

## <a name="configure-the-organizations-outbound-setting-to-allow-all-users"></a>Kuruluşun giden ayarını tüm kullanıcılara izin verecek şekilde yapılandırma

Kuruluşu ekledikten sonra, B2B işbirliği kullanıcılarının konuk olarak eklenmesine izin vermek için kuruluşun giden ayarlarını güncelleştirmeniz gerekir. Bunu, kullanıcılarınızın konuk olarak eklenmesine izin vermek istediğiniz her kuruluş için yapın.

Kullanıcıların bir kuruluştaki B2B işbirliği konuklarına izin vermek için
1. [Azure Active Directory'de](https://aad.portal.azure.com) **Dış Kimlikler'i** ve ardından **Kiracılar arası erişim ayarları (önizleme)** seçeneğini belirleyin.
1. Değiştirmek istediğiniz kuruluşun giden erişim bağlantısını seçin.
1. **B2B işbirliği** sekmesinde **Ayarları özelleştir'i** seçin.
1. **Erişim durumu** altında **Erişime izin ver'i** seçin.
1. **Hedef'in** altında tüm kullanıcılara izin vermeyi seçin.
1. **Kaydet'i** seçin ve **Giden erişim ayarları** dikey penceresini kapatın.

## <a name="related-topics"></a>İlgili konular

[B2B doğrudan bağlanmaya genel bakış](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[B2B doğrudan bağlantı için kiracılar arası erişim ayarlarını yapılandırma](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[Kuruluş tarafından kimlerin davet edilebileceğini sınırlayın](limit-invitations-from-specific-organization.md)

[Konuk paylaşımını belirli kuruluşlarla sınırlayın](limit-guest-sharing-to-specific-organization.md)