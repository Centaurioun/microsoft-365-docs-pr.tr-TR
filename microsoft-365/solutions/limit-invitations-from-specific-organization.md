---
title: Kuruluş tarafından kimlerin davet edilebileceğini sınırlayın
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: Kullanıcılarınızdan hangilerinin belirli bir kuruluşa konuk veya paylaşılan kanal katılımcısı olarak davet edilebileceğini sınırlamayı öğrenin.
ms.openlocfilehash: 9298d0f6cb251d9734a8cfb4036e305bb603b680
ms.sourcegitcommit: e4882e3c66166ea7b834ad2e8fafeab42293e07d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2022
ms.locfileid: "67099799"
---
# <a name="limit-who-can-be-invited-by-an-organization"></a>Kuruluş tarafından kimlerin davet edilebileceğini sınırlayın

Başka bir kuruluşla işbirliği yaparsanız ve Teams'de konuk veya paylaşılan kanal üyesi olarak kimlerin davet edilebileceğini sınırlamak istiyorsanız, Azure Active Directory'deki kiracılar arası erişim ayarlarında kimlerin davet edilebileceğini belirtebilirsiniz.

> [!NOTE]
> Kiracılar arası erişim ayarlarında yapılan değişikliklerin etkili olması altı saat sürebilir.

## <a name="create-a-security-group"></a>Güvenlik grubu oluşturma

Başka bir kuruluşa kimlerin davet edilebileceğini belirtmenin en kolay yolu bir güvenlik grubu kullanmaktır. Tanımlı üyelik veya dinamik güvenlik grubuyla bir güvenlik grubu kullanabilirsiniz. Var olan bir güvenlik grubunu kullanabilir veya bu amaçla yeni bir güvenlik grubu oluşturabilirsiniz.

Güvenlik grubu oluşturmak için
1. Genel yönetici veya Güvenlik yöneticisi hesabı kullanarak [Azure Active Directory'de](https://aad.portal.azure.com) oturum açın.
1. **Active Directory** sayfasında **Gruplar'ı** ve ardından **Yeni grup'ı** seçin.
1. **Grup türü** için **Güvenlik'i** seçin.
1. **Bir Grup adı yazın.** 
1. İsteğe bağlı olarak, grup için bir açıklama ekleyin.
1. **Gruba Azure AD rol atanabilmesi için** **Hayır'ı** seçin.
1. Önceden tanımlanmış bir **Üyelik türü (gerekli)** seçin.
1. Dinamik kullanıcı üyeliği kullanıyorsanız grup sahipleri ve üyeleri veya [dinamik sorgu](/azure/active-directory/enterprise-users/groups-dynamic-membership) ekleyin.
1. **Oluştur**’u seçin. Grubunuz oluşturulur ve üye eklemeniz için hazır.

## <a name="add-an-organization"></a>Kuruluş ekleme

Başka bir kuruluşla işbirliği kuralları tanımlamak için bu kuruluşu Azure AD kiracılar arası erişim ayarlarına eklemeniz gerekir. Kuruluşu henüz eklemediyseniz, eklemek için bu yordamı izleyin.

Kuruluş eklemek için
1. [Azure Active Directory'de](https://aad.portal.azure.com) **Dış Kimlikler'i** ve ardından **Kiracılar arası erişim ayarları (önizleme)**.1'i seçin. **Kuruluş ayarları'nı** seçin.
1. **Kuruluş ekle'yi** seçin.
1. **Kuruluş ekle** bölmesinde, kuruluşun tam etki alanı adını (veya kiracı kimliğini) yazın.
1. Arama sonuçlarında kuruluşu seçin ve ardından **Ekle'yi** seçin.
1. Kuruluş, **Kuruluş ayarları** listesinde görünür. Bu noktada, bu kuruluşun tüm erişim ayarları varsayılan ayarlarınızdan devralınır.

## <a name="choose-who-can-be-invited-by-an-organization"></a>Kuruluş tarafından kimlerin davet edilebileceğini seçme

Bir kuruluşa kimlerin davet edilebileceğini sınırlamak için iki seçenek vardır:

- Konuk olarak davet edilebilecekleri sınırlayın. Bu, kullanıcıların diğer kuruluşun Azure AD konuk olarak eklenmesini önler. Dosyaların, klasörlerin, sitelerin, ekiplerin ve Microsoft 365 gruplarının güvenlik grubunda yer almayan kişilerle paylaşılmasını engeller.
- Dış paylaşılan kanala kimlerin eklenebileceğini sınırlayın. Bu, güvenlik grubunda yer almayan kişilerin diğer kuruluştaki paylaşılan kanallara eklenmesini önler.

[Azure Active Directory'de](https://aad.portal.azure.com) **Dış Kimlikler'i** ve ardından **Kiracılar arası erişim ayarları (önizleme)** seçeneğini belirleyin.

Konuk olarak davet edilebilecekleri sınırlamak için
1. Değiştirmek istediğiniz kuruluşun giden erişim bağlantısını seçin.
1. **B2B işbirliği** sekmesinde **Ayarları özelleştir'i** seçin.
1. **Erişim durumu** altında **Erişime izin ver'i** seçin.
1. **Hedef'in** altında **Dış kullanıcıları ve grupları seçin'i** seçin.
1. Kullanıcı ve grup eklemek için bağlantıyı seçin.
1. Kullanmak istediğiniz güvenlik grubunu arayın ve seçin.
1. **Seç'i seçin**.
1. **Kaydet'i** seçin ve **Giden erişim ayarları** dikey penceresini kapatın.


Paylaşılan kanal katılımcısı olarak davet edilebilecekleri sınırlamak için
1. Değiştirmek istediğiniz kuruluşun giden erişim bağlantısını seçin.
1. **B2B doğrudan bağlantı** sekmesinde **Ayarları özelleştir'i** seçin.
1. **Erişim durumu** altında **Erişime izin ver'i** seçin.
1. **Hedef'in** altında **Dış kullanıcıları ve grupları seçin'i** seçin.
1. Kullanıcı ve grup eklemek için bağlantıyı seçin.
1. Kullanmak istediğiniz güvenlik grubunu arayın ve seçin.
1. **Seç'i seçin**.
1. **Kaydet'i** seçin ve **Giden erişim ayarları** dikey penceresini kapatın.

## <a name="related-topics"></a>İlgili konular

[B2B doğrudan bağlanmaya genel bakış](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[B2B doğrudan bağlantı için kiracılar arası erişim ayarlarını yapılandırma](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[Kullanıcıların konuk hesaplarına sahip olabileceği kuruluşları sınırlama](limit-organizations-where-users-have-guest-accounts.md)

[Konuk paylaşımını belirli kuruluşlarla sınırlayın](limit-guest-sharing-to-specific-organization.md)
