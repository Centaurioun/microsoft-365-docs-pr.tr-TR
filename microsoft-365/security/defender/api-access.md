---
title: Microsoft 365 Defender API'lerine erişme
description: Microsoft 365 Defender API'lerine erişmeyi öğrenin
keywords: access, API'ler, uygulama bağlamı, kullanıcı bağlamı, aad uygulaması, erişim belirteci
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.custom: api
ms.openlocfilehash: 0562ff901aa8021973fb1ed36e8caf464f22d672
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67481580"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Microsoft 365 Defender API'lerine erişme

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

Microsoft 365 Defender, bir dizi programlı API aracılığıyla verilerinin ve eylemlerinin büyük bir kısmını kullanıma sunar. Bu API'ler iş akışlarını otomatikleştirmenize ve Microsoft 365 Defender özelliklerinden tam olarak yararlanmanıza yardımcı olur.

Genel olarak, API'leri kullanmak için aşağıdaki adımları uygulamanız gerekir:

- Azure Active Directory uygulaması oluşturma
- Bu uygulamayı kullanarak erişim belirteci alma
- Microsoft 365 Defender API'sine erişmek için belirteci kullanma

> [!NOTE]
> API erişimi için OAuth2.0 kimlik doğrulaması gerekir. Daha fazla bilgi için bkz [. OAuth 2.0 Yetkilendirme Kodu Akışı](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Bu adımları tamamladıktan sonra, belirli bir bağlamı kullanarak Microsoft 365 Defender API'sine erişmeye hazırsınız demektir.

## <a name="application-context-recommended"></a>Uygulama bağlamı (Önerilen)

Arka plan hizmetleri veya daemon'lar gibi oturum açmış bir kullanıcı olmadan çalışan uygulamalar için bu bağlamı kullanın.

1. Azure Active Directory web uygulaması oluşturun.
2. İstenen izinleri uygulamaya atayın.
3. Uygulama için bir anahtar oluşturun.
4. Uygulamayı ve anahtarını kullanarak bir güvenlik belirteci alın.
5. Microsoft 365 Defender API'sine erişmek için belirteci kullanın.

Daha fazla bilgi için bkz. **[Kullanıcı olmadan Microsoft 365 Defender erişmek için uygulama oluşturma](api-create-app-web.md)**.

## <a name="user-context"></a>Kullanıcı bağlamı

Tek bir kullanıcı adına eylemler gerçekleştirmek için bu bağlamı kullanın.

1. Azure Active Directory yerel uygulaması oluşturun.
2. İstenen izni uygulamaya atayın.
3. Uygulamanın kullanıcı kimlik bilgilerini kullanarak bir güvenlik belirteci alın.
4. Microsoft 365 Defender API'sine erişmek için belirteci kullanın.

Daha fazla bilgi için bkz. **[Kullanıcı adına Microsoft 365 Defender API'lere erişmek için uygulama oluşturma](api-create-app-user-context.md)**.

## <a name="partner-context"></a>İş ortağı bağlamı

[Birden çok kiracıda](/azure/active-directory/develop/single-and-multi-tenant-apps) birçok kullanıcıya uygulama sağlamanız gerektiğinde bu bağlamı kullanın.

1. Azure Active Directory çok kiracılı bir uygulama oluşturun.
2. İstenen izni uygulamaya atayın.
3. Her kiracıdan uygulama için [yönetici onayı](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) alın.
4. Müşterinin kiracı kimliğine göre kullanıcı kimlik bilgilerini kullanarak bir güvenlik belirteci alın.
5. Microsoft 365 Defender API'sine erişmek için belirteci kullanın.

Daha fazla bilgi için bkz. **[Microsoft 365 Defender API'lere iş ortağı erişimi olan bir uygulama oluşturma](api-partner-access.md)**.

## <a name="related-articles"></a>İlgili makaleler

- [Microsoft 365 Defender API'lere genel bakış](api-overview.md)
- [Kullanıcı oturum açma ve API erişimi için OAuth 2.0 yetkilendirmesi](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Azure Key Vault ile sunucu uygulamalarınızdaki gizli dizileri yönetme](/learn/modules/manage-secrets-with-azure-key-vault/)
- [Microsoft 365 API'lerine erişen bir 'Merhaba dünya' uygulaması oluşturma](api-hello-world.md)
