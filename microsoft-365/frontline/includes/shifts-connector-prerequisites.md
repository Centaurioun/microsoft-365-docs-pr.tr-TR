---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: microsoft-365-frontline
ms.openlocfilehash: 89752e9d13f8647b1c99f6ad99c2baa096b74e02
ms.sourcegitcommit: 99b174a8d431092b3cf7d650593248671297fd91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68300082"
---
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- Blue Yonder WFM sürüm 2020.3, 2021.1 veya 2021.2.

    > [!NOTE]
    > Blue Yonder WFM 2020.3 veya 2021.1'iniz varsa, 2020.3.0.4 veya 2021.1.0.3 düzeltme ekini uygulayın. Bu düzeltme eki, kullanıcıların Vardiyalar'da kalıcı bir hata iletisi alması sorununu düzeltir. Ayrıca, kullanıcıların Vardiyalar'da kullanılabilirliklerini güncelleştirmelerini engelleyen bir sorunu da düzeltir.

- Mavi Yonder WFM hizmet hesabı adınız ve parolanız ile hizmet URL'leriniz:

    - Federasyon kimlik doğrulaması URL'si
    - Tanımlama bilgisi kimlik doğrulaması URL'si
    - Çalışan self servis URL'si
    - Perakende web API'si URL'si
    - Site yöneticisi API'si URL'si
    - Yönetim API'si URL'si

    Bu bilgilere sahip değilseniz Blue Yonder desteğine başvurun. Hesap, bir Blue Yonder kuruluş yöneticisi tarafından kök kuruluş düzeyinde oluşturulur. API Erişimi, İstemci Yönetici ve Store Manager erişimi olmalıdır. Bağlantı oluşturmak için hesap ve parola gereklidir.
- Federasyon SSO kimlik doğrulaması, Blue Yonder WFM ortamınızda etkinleştirilir. Federasyon SSO'nun etkinleştirildiğinden emin olmak için Mavi Yonder desteğine başvurun. Aşağıdaki bilgilere ihtiyaçları olacaktır:

    - federatedSSOValidationService: `https://wfmconnector.teams.microsoft.com/api/v1/fedauth/{tenantId}/6A51B888-FF44-4FEA-82E1-839401E9CD74/authorize` burada {tenantId} sizin tenantId'nizdir
     - proxyHeader: X-MS-AuthToken

- Teams'te en az bir ekip ayarlanır.
- Eşlemek istediğiniz tüm takımlara ekip sahibi olarak bir Microsoft 365 sistem hesabı eklediniz.</br> [Bu hesabı Microsoft 365'te oluşturun](/microsoft-365/admin/add-users/add-users) ve bir Microsoft 365 lisansı atayın. Ardından hesabı eşlemek istediğiniz tüm ekiplere ekip sahibi olarak ekleyin. Shifts bağlayıcısı, Blue Yonder WFM vardiya değişikliklerini eşitlerken bu hesabı kullanır.

    Bu amaçla özel olarak bir hesap oluşturmanızı ve kullanıcı hesabınızı kullanmamanızı öneririz.