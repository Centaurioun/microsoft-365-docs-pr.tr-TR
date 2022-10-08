---
title: Microsoft 365 Defender MSSP müşteri portalına erişme
description: Microsoft 365 Defender MSSP müşteri portalına erişme
keywords: yönetilen güvenlik hizmeti sağlayıcısı, mssp, yapılandırma, tümleştirme
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 204e2e9b966de5eec246cfdaea6515b26fb8235a
ms.sourcegitcommit: b9282493c371d59c2e583b9803825096499b5e2c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68142465"
---
# <a name="access-the-microsoft-365-defender-mssp-customer-portal"></a>Microsoft 365 Defender MSSP müşteri portalına erişme

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)

> [!NOTE]
> Bu adım kümesi MSSP'ye yönlendirilir.

Varsayılan olarak, MSSP müşterileri Microsoft 365 Defender kiracılarına şu URL aracılığıyla erişmektedir: `https://security.microsoft.com/`.

Ancak MSSP'lerin kiracıya özgü bir URL'yi şu biçimde kullanması gerekir:  `https://security.microsoft.com?tid=customer_tenant_id` MSSP müşteri portalına erişmek için.

Genel olarak, MSSP müşterisinin yönetmeyi amaçladıkları Azure AD her birine MSSP'lerin eklenmesi gerekir.

MSSP müşteri kiracı kimliğini almak için aşağıdaki adımları kullanın ve kiracıya özgü URL'ye erişmek için kimliği kullanın:

1. MSSP olarak kimlik bilgilerinizle Azure AD oturum açın.

2. Dizini MSSP müşterisinin kiracısına geçirin.

3. **Azure Active Directory > Özellikleri'ni** seçin. Kiracı kimliğini Dizin Kimliği alanında bulabilirsiniz.

4. Aşağıdaki URL'deki değeri değiştirerek MSSP müşteri portalına `customer_tenant_id` erişin: `https://security.microsoft.com/?tid=customer_tenant_id`.

## <a name="related-topics"></a>İlgili konular

- [Portala MSSP erişimi ver](grant-mssp-access.md)
- [Uyarı bildirimlerini yapılandırın](configure-mssp-notifications.md)
- [Müşteri kiracı uyarılarını getir](fetch-alerts-mssp.md)
