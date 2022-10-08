---
author: LanaChin
ms.author: v-lanachin
ms.date: ''
ms.topic: include
audience: admin
ms.service: microsoft-365-frontline
ms.openlocfilehash: f3a764a66f3be2fc553581b45dead569ffda1fb6
ms.sourcegitcommit: 99b174a8d431092b3cf7d650593248671297fd91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68301852"
---
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- UKG Dimensions hizmet hesabınızın adı, parolası ve hizmet URL'leri:

  - Uygulama programı arabirimi URL'si
  - Uygulama anahtarı
  - İstemci Kimliği
  - İstemci gizli dizisi
  - Çoklu Oturum Açma URL'si

  Bu bilgilere sahip değilseniz UKG Dimensions desteğine başvurun.
- Federasyon çoklu oturum açma (SSO) kimlik doğrulaması UKG Dimensions ortamınızda etkinleştirilir. </br>Azure Active Directory (Azure AD), SSO için desteklenen kimlik sağlayıcısıdır. SSO'nun etkinleştirilmesi için Azure AD ve UKG Boyutları arasında tümleştirme ayarlayın. Adım adım öğretici için bkz[. Öğretici: Kronos Workforce Dimensions ile SSO tümleştirmesi Azure AD](/azure/active-directory/saas-apps/kronos-workforce-dimensions-tutorial). SSO'nun kurulumu hakkında yardıma veya daha fazla bilgiye ihtiyacınız varsa UKG Dimensions desteğine başvurun.

    Tümleştirme ayarlandıktan sonra, UKG Dimensions'taki profil sayfasında kullanıcıları federasyon hesapları olarak yapılandırın.
- Teams'te en az bir ekip ayarlanır.
- Eşlemek istediğiniz tüm takımlara ekip sahibi olarak bir Microsoft 365 sistem hesabı eklediniz.</br> [Bu hesabı Microsoft 365'te oluşturun](/microsoft-365/admin/add-users/add-users) ve bir Microsoft 365 lisansı atayın. Ardından hesabı eşlemek istediğiniz tüm ekiplere ekip sahibi olarak ekleyin. Shifts bağlayıcısı, UKG Boyutlarından vardiya değişikliklerini eşitlerken bu hesabı kullanır.

    Bu amaçla özel olarak bir hesap oluşturmanızı ve kullanıcı hesabınızı kullanmamanızı öneririz.
