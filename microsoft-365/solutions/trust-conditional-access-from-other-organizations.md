---
title: Kuruluşunuzun dışındaki kişiler için koşullu erişim gerektirme
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
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: Kuruluşunuz dışındaki kişilerin MFA ve uyumlu cihazlar gibi koşullu erişim denetimlerini geçirmesini nasıl zorunlu kacağınızı öğrenin.
ms.openlocfilehash: 9e424ef6dde16137a334f391efa71b6b61860dfb
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67731452"
---
# <a name="require-conditional-access-for-people-outside-your-organization"></a>Kuruluşunuzun dışındaki kişiler için koşullu erişim gerektirme

Kuruluşunuzun dışındaki kişiler için aşağıdaki koşullu erişim seçeneklerinden herhangi birini gerektirebilirsiniz:

- Çok faktörlü kimlik doğrulaması
- Uyumlu cihazlar
- Karma Azure AD katılmış cihazlar

Teams'de paylaşılan kanallar gibi Azure AD B2B doğrudan bağlantı kullanırken, bu seçenekler için diğer kuruluşların koşullu erişim ayarlarına güvenmeyi seçebilirsiniz. Koşullu erişim ilkelerinin yalnızca paylaşılan kanaldaki Dosyalar sekmesine ve ilişkili SharePoint sitesine erişim için kullanıldığını unutmayın.

## <a name="planning-considerations-for-conditional-access"></a>Koşullu erişim için planlama konuları

Çok faktörlü kimlik doğrulaması herhangi bir dış hesapla kullanılabilir. Kuruluşunuz diğer Azure AD kuruluşlarının çok faktörlü kimlik doğrulamasına güvenmiyorsa, kuruluşunuzdaki kaynaklara erişirken bu kuruluşların kullanıcılarının çok faktörlü kimlik doğrulaması gerçekleştirmesi gerekir. Üçüncü taraf e-posta adresleriyle (Microsoft tarafından barındırılmayan) Kişiler her zaman çok faktörlü kimlik doğrulaması istenir.

**Cihazın uyumlu olarak işaretlenmesini gerektir** ve **Karma Azure AD katılmış cihaz gerektir** seçenekleri, Azure AD'de yönetilen cihazlar gerektirir. Bu seçenekleri etkinleştirmeyi seçerseniz, kuruluşunuzun dışındaki kişilerin kuruluşunuz veya güvendiğiniz bir kuruluş tarafından yönetilen cihazları kullanıyor olması gerekir. Yönetilen cihazlar olmadan Kişiler engellenir, örneğin:

- Üçüncü taraf veya tüketici e-posta adresleriyle Kişiler
- Cihazları yönetmeyen Microsoft 365 veya Azure AD kuruluşlarından Kişiler
- Kuruluşunuzun koşullu erişim ayarlarına güvenmediği yönetilen cihazlar gerektiren Microsoft 365 veya Azure AD kuruluşlarından Kişiler.

Uyumlu veya karma Azure AD birleştirilmiş cihazlar gerektiğinde dikkatli olmanız önerilir çünkü bu durum birçok dış işbirliği senaryolarını engeller. Tüm iş ortağı kuruluşlarınızın cihazlarını yönettiğinden ve kuruluşunuzun ayarlarına güvendiğinden emin olun.

## <a name="set-up-conditional-access-requirements-for-people-outside-your-organization"></a>Kuruluşunuzun dışındaki kişiler için koşullu erişim gereksinimlerini ayarlama

Kuruluşunuzun dışındaki kişiler için koşullu erişim istemek için aşağıdakileri yapın:

1. [Diğer kuruluşlardan güvenebileceğiniz koşullu erişim ayarlarını seçin](#choose-conditional-access-settings-to-trust-from-other-organizations).
1. [Kuruluşunuzun dışındaki kişiler için koşullu erişim ayarlayın](#set-up-conditional-access-for-people-outside-your-organization).

## <a name="choose-conditional-access-settings-to-trust-from-other-organizations"></a>Diğer kuruluşlardan güvenebileceğiniz koşullu erişim ayarlarını seçme

Diğer tüm Microsoft 365 ve Azure AD kuruluşlarından veya yalnızca sizin belirttiğiniz kuruluşlardan koşullu erişim ayarlarına güvenmeyi seçebilirsiniz.

> [!NOTE]
> Kiracılar arası erişim ayarlarında yapılan değişikliklerin etkili olması iki saat sürebilir.

### <a name="trust-conditional-access-settings-from-all-azure-active-directory-organizations"></a>Tüm Azure Active Directory kuruluşlarının koşullu erişim ayarlarına güvenme

Tüm kuruluşların koşullu erişim ayarlarına güvenmek istiyorsanız bu yordamı izleyin.

Tüm Azure Active Directory kuruluşlarının koşullu erişim ayarlarına güvenmek için
1. Genel yönetici veya Güvenlik yöneticisi hesabı kullanarak [Azure Active Directory'de](https://aad.portal.azure.com) oturum açın.
1. **Dış Kimlikler'i** ve ardından **Kiracılar arası erişim ayarları (önizleme)** seçeneğini belirleyin.
1. **Varsayılan ayarlar** sekmesini seçin.
1. **Gelen erişim ayarları'nın** altında **Gelen varsayılanları düzenle'yi** seçin.
1. **Güven ayarları** sekmesini seçin.
1. Koşullu erişim ilkelerinizin diğer kuruluşlardan kabul etmelerini istediğiniz ayarları seçin.
1. **Kaydet'i** seçin ve **Varsayılan ayarlar** dikey penceresini kapatın.

### <a name="trust-conditional-access-settings-from-a-specific-organization"></a>Belirli bir kuruluştan koşullu erişim ayarlarına güvenme

Belirli bir kuruluşun koşullu erişim ayarlarına güvenmek istiyorsanız bu yordamı izleyin.

Belirli bir kuruluşun koşullu erişim ayarlarına güvenmek için
1. Genel yönetici veya Güvenlik yöneticisi hesabı kullanarak [Azure Active Directory'de](https://aad.portal.azure.com) oturum açın.
1. **Dış Kimlikler'i** ve ardından **Kiracılar arası erişim ayarları (önizleme)** seçeneğini belirleyin.
1. Koşullu erişim ayarlarına güvenmek istediğiniz kuruluş için **Gelen** erişim ayarlarını seçin.
1. **Güven ayarları** sekmesini seçin.
1. **Ayarları özelleştir** seçeneğini belirleyin.
1. Koşullu erişim ilkelerinizin diğer kuruluşlardan kabul etmelerini istediğiniz ayarları seçin.
1. **Kaydet'i** seçin ve **Varsayılan ayarlar** dikey penceresini kapatın.

## <a name="set-up-conditional-access-for-people-outside-your-organization"></a>Kuruluşunuzun dışındaki kişiler için koşullu erişim ayarlama

Kuruluşunuzun dışındaki kişiler için koşullu erişim ilkesi ayarlamak aşağıdakileri etkiler:

- Konuk hesaplarını (B2B işbirliği kullanıcıları Azure AD) kullanarak Kişiler
- Teams paylaşılan kanallarındaki dış katılımcılar (B2B doğrudan bağlantı kullanıcıları Azure AD)

> [!IMPORTANT]
> Yalnızca kuruluşunuzun dışındaki herkes kuruluşunuz veya güvenilir bir Microsoft 365 veya Azure AD kuruluşu tarafından yönetilen bir cihaz kullanıyorsa **Cihazın uyumlu olarak işaretlenmesini gerektir** veya **Karma Azure AD katılmış cihaz gerektir'i** seçin.

Kuruluşunuzun dışındaki kişiler için koşullu erişim ayarlamak için
1. [Azure koşullu erişim ilkeleri'ne](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade) gidin.
1. **Koşullu Erişim | İlkeler** dikey penceresinde **Yeni ilke'ye** tıklayın.
1. **Ad** alanına bir ad yazın.
1. **Atamalar'ın** altında **Kullanıcılar ve gruplar'a** tıklayın.
1. **Kullanıcılar ve gruplar** dikey penceresinde **Kullanıcıları ve grupları seç'i** seçin, **Tüm konuklar ve dış kullanıcılar** onay kutusunu seçin.
1. **Atamalar'ın** altında **Bulut uygulamaları veya eylemleri'ne** tıklayın.
1. **Bulut uygulamaları veya eylemler** dikey penceresinde **Ekle** sekmesinde **Tüm bulut uygulamaları'nı** seçin.
1. **Erişim denetimleri'nin** altında **Ver'e** tıklayın.
1. **Ver** dikey penceresinde, kuruluşunuzun dışındaki kişiler için gerekli olmasını istediğiniz seçenekleri belirleyin ve **seç'e** tıklayın.
1. **Yeni** dikey penceresindeki **İlkeyi etkinleştir'in** altında **Açık'a** ve ardından **Oluştur'a** tıklayın.

## <a name="related-topics"></a>İlgili konular

[Öğretici: B2B konukları için çok faktörlü kimlik doğrulamasını zorunlu kılma](/azure/active-directory/external-identities/b2b-tutorial-require-mfa)
