---
title: Kimlerin konuk davet edebileceğini sınırlayın
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
description: Kuruluşunuza konuk davet eden kişileri sınırlamayı öğrenin.
ms.openlocfilehash: ac8417f2fb564c1dcd85b375318f3b3943555974
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67582724"
---
# <a name="limit-who-can-invite-guests"></a>Kimlerin konuk davet edebileceğini sınırlayın

Kuruluşunuzda kimlerin konuk davet edebileceğini sınırlayabilirsiniz. Konuk hesapları ekipleri, SharePoint sitelerini, dosyalarını ve klasörlerini kuruluşunuzun dışındaki kişilerle paylaşmak için kullanılabilir.

İş süreçleriniz, konuklarla paylaşabilecek kişileri sınırlamanızı gerektiriyorsa veya kullanıcıların konuklarla paylaşabilmeleri için eğitimi tamamlamalarını istiyorsanız, Azure Active Directory'de Konuk davet eden rolünü kullanarak kimlerin paylaşabileceğini sınırlayabilirsiniz.

## <a name="create-a-security-group-for-people-allowed-to-invite-guests"></a>Konuk davet etmesine izin verilen kişiler için bir güvenlik grubu oluşturma

İlk adım, konukları davet etmelerine izin verilecek kullanıcılar için bir güvenlik grubu oluşturmaktır. Bu grubu bir Azure AD rolüne izin verecek şekilde yapılandırdığınızdan emin olun ve ardından konuk davet eden rolü atayın.

Konuk davetliler için bir güvenlik grubu oluşturmak için
1. Genel yönetici veya Güvenlik yöneticisi hesabı kullanarak [Azure Active Directory'de](https://aad.portal.azure.com) oturum açın.
1. **Active Directory** sayfasında **Gruplar'ı** ve ardından **Yeni grup'ı** seçin.
1. **Grup türü** için **Güvenlik'i** seçin.
1. **Bir Grup adı yazın.** 
1. İsteğe bağlı olarak, grup için bir açıklama ekleyin.
1. **Gruba Azure AD rol atanabilmesi için** **Evet'i** seçin.
1. Grup sahiplerini ve üyelerini ekleyin.
1. **Roller'in** altında **Seçili rol yok'a** tıklayın.
1. **Konuk davet eden** rolünü arayıp seçin ve ardından **Seç'i** seçin.
1. **Oluştur'u** seçin ve rollerin atanabileceği bir grup istediğinizi onaylayın. Grubunuz oluşturulur ve üye eklemeniz için hazır.

## <a name="configure-external-collaboration-settings"></a>Dış işbirliği ayarlarını yapılandırma

Güvenlik grubunu oluşturduktan ve konuk davet etmek istediğiniz kullanıcıları ekledikten sonraki adım, Azure AD dış işbirliği ayarlarını yalnızca Konuk davet eden rolüne sahip kullanıcıların konuk davet etmelerine izin verecek şekilde yapılandırmaktır.

Genel yöneticilerin bu ayardan bağımsız olarak her zaman konukları davet edebildiğini unutmayın.

> [!NOTE]
> Kiracılar arası erişim ayarlarında yapılan değişikliklerin etkili olması iki saat sürebilir.

konuk davetlerini Konuk davet eden rolüyle sınırlamak için Azure AD yapılandırmak için
1. [Azure Active Directory'de](https://aad.portal.azure.com/) **Dış kimlikler'i** seçin.
1. **Dış işbirliği ayarları'nı** seçin.
1. **Konuk daveti ayarları'nın** altında **Yalnızca belirli yönetici rollerine atanan kullanıcılar konuk davet edebilir'i** seçin.
1. **Kaydet**'i seçin.

## <a name="related-topics"></a>İlgili konular

[Yalnızca belirli güvenlik gruplarındaki kullanıcıların SharePoint ve OneDrive'da harici olarak paylaşmasına izin ver](/sharepoint/manage-security-groups)

[B2B dış işbirliğini etkinleştirme ve konukları kimlerin davet edebileceğini yönetme](/azure/active-directory/external-identities/delegate-invitations)