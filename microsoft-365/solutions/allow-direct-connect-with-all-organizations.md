---
title: Tüm dış kuruluşlarla paylaşılan kanalları etkinleştirme
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
description: Diğer tüm Microsoft 365 ve Azure Active Directory kuruluşlarıyla paylaşılan kanalları etkinleştirmeyi öğrenin.
ms.openlocfilehash: 601bfaa825afdaf9ec5addb4b7c7e21804b07cb7
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2022
ms.locfileid: "66861387"
---
# <a name="enable-shared-channels-with-all-external-organizations"></a>Tüm dış kuruluşlarla paylaşılan kanalları etkinleştirme

Teams'te paylaşılan kanalların dış olarak paylaşılması varsayılan olarak etkin olsa da [, B2B doğrudan bağlantı](/azure/active-directory/external-identities/b2b-direct-connect-overview) için Azure Active Directory kiracılar arası erişim ayarları da bir kanalı dışarıdan paylaşacak şekilde yapılandırılmalıdır. Varsayılan olarak, bu ayarlar tüm kuruluşları engelleyecek şekilde ayarlanır.

Tüm kuruluşlara izin vermek için B2B doğrudan bağlantı varsayılan ayarlarını değiştirebilirsiniz. Bu, kuruluşunuzun işbirliği yapmak istediğiniz her kuruluş için ayrı bir yapılandırma oluşturmak zorunda kalmadan kullanıcıların paylaşılan kanallarda işbirliği yapmasına olanak tanır. (İşbirliği yaptığınız kuruluşların B2B doğrudan bağlantı ayarlarını da yapılandırmaları gerekeceğini unutmayın.)

Kuruluşunuzun diğer kuruluşlarla işbirliğini kısıtlama gereksinimi yoksa, tüm kuruluşların varsayılan olarak etkinleştirilmesi, her kuruluşu ayrı ayrı yönetme konusunda size zaman ve karmaşıklık kazandırabilir.

> [!NOTE]
> Kiracılar arası erişim ayarlarında yapılan değişikliklerin etkili olması iki saat sürebilir.

## <a name="allow-users-to-invite-people-in-other-organizations-to-participate-in-shared-channels"></a>Kullanıcıların diğer kuruluşlardaki kişileri paylaşılan kanallara katılmaya davet etmelerine izin verme

Kullanıcılarınızın varsayılan olarak diğer kuruluşlardaki kişileri Teams'deki paylaşılan kanallar gibi paylaşılan kaynakları kullanmaya davet etmelerine izin vekleyebilirsiniz.

Kullanıcıların varsayılan olarak B2B doğrudan bağlantı katılımcılarını davet etmelerine izin vermek için
1. Genel yönetici veya Güvenlik yöneticisi hesabı kullanarak [Azure Active Directory'de](https://aad.portal.azure.com) oturum açın.
1. **Dış Kimlikler'i** ve ardından **Kiracılar arası erişim ayarları (önizleme)** seçeneğini belirleyin.
1. **Varsayılan ayarlar** sekmesindeki **Gelen erişim ayarları'nın** altında **Gelen varsayılanları düzenle'yi** seçin.
1. **B2B doğrudan bağlantı** sekmesini seçin.
1. **Kullanıcılar ve gruplar** sekmesinde, **Erişim durumu altında Erişime** **izin ver'i** seçin.
1. **Dış uygulamalar** sekmesinde, **Erişim durumu altında Erişime** **izin ver'i** seçin.
1. **Kaydet**'i seçin.
1. **Güven ayarları** sekmesini seçin.
1. Diğer kuruluşların çok faktörlü kimlik doğrulamasına, uyumlu cihazlara veya karma Azure AD katılmış cihazlara güvenmek isteyip istemediğinizi seçin.
1. **Kaydet**'i seçin.
1. **Varsayılan ayarlar** dikey penceresini kapatın.

## <a name="allow-users-to-participate-in-shared-channels-in-other-organizations"></a>Kullanıcıların diğer kuruluşlardaki paylaşılan kanallara katılmasına izin verme

Kullanıcılarınızın varsayılan olarak Teams'deki paylaşılan kanallar gibi bir dış kuruluş tarafından barındırılan kaynaklara erişmesine izin vekleyebilirsiniz.

Kullanıcıların varsayılan olarak diğer kuruluşlardan gelen kaynağa erişmesine izin vermek için
1. [Azure Active Directory'de](https://aad.portal.azure.com) **Dış Kimlikler'i** ve ardından **Kiracılar arası erişim ayarları (önizleme)** seçeneğini belirleyin.
1. **Varsayılan ayarlar** sekmesinde, **Giden erişim ayarları'nın** altında **Giden varsayılanları düzenle'yi** seçin.
1. **B2B doğrudan bağlantı** sekmesini seçin.
1. **Kullanıcılar ve gruplar** sekmesinde, **Erişim durumu altında Erişime** **izin ver'i** seçin.
1. **Dış uygulamalar** sekmesinde, **Erişim durumu altında Erişime** **izin ver'i** seçin.
1. **Kaydet**'i seçin.
1. **Varsayılan ayarlar** dikey penceresini kapatın.

## <a name="related-topics"></a>İlgili konular

[B2B doğrudan bağlanmaya genel bakış](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[B2B doğrudan bağlantı için kiracılar arası erişim ayarlarını yapılandırma](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

