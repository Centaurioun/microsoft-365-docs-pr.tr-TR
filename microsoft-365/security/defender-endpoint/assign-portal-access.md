---
title: Microsoft Defender Güvenlik Merkezi'ne kullanıcı erişimi atama
description: Uç Nokta için Microsoft Defender portalına okuma ve yazma veya salt okuma erişimi atayın.
keywords: kullanıcı rolleri atama, okuma ve yazma erişimi atama, salt okunur erişim atama, kullanıcı, kullanıcı rolleri, roller
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.service: microsoft-365-security
ms.subservice: mde
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 1a02bcd596043ee27fc250f60ab68e627246bf62
ms.sourcegitcommit: 078149c9645ce220911ccd6ce54f984a4c92ce53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67811646"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a>Microsoft Defender Güvenlik Merkezi'ne kullanıcı erişimi atama

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Azure Active Directory
- Office 365
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Uç Nokta için Defender izinleri yönetmek için iki yolu destekler:

- **Temel izin yönetimi**: İzinleri tam erişim veya salt okunur olarak ayarlayın.
- **Rol tabanlı erişim denetimi (RBAC)**: Rolleri tanımlayarak, rollere Azure AD kullanıcı grupları atayarak ve kullanıcı gruplarına cihaz gruplarına erişim vererek ayrıntılı izinleri ayarlayın. RBAC hakkında daha fazla bilgi için bkz. [Rol tabanlı erişim denetimini kullanarak portal erişimini yönetme](rbac.md).

> [!NOTE]
> Temel izinleri zaten atadıysanız, istediğiniz zaman RBAC'ye geçebilirsiniz. Geçiş yapmadan önce aşağıdakileri göz önünde bulundurun:
>
> - Tam erişimi olan kullanıcılara (Azure AD'da Genel Yönetici veya Güvenlik Yöneticisi dizin rolü atanmış olan kullanıcılara) otomatik olarak varsayılan Uç Nokta için Defender yönetici rolü atanır ve bu rol de tam erişime sahiptir. RBAC'ye geçtikten sonra Uç Nokta için Defender yönetici rolüne ek Azure AD kullanıcı grupları atanabilir. RBAC kullanarak izinleri yalnızca Uç Nokta için Defender yönetici rolüne atanan kullanıcılar yönetebilir. 
> - Salt okunur erişimi olan kullanıcılar (Güvenlik Okuyucuları) kendilerine rol atanana kadar portala erişimi kaybeder. RBAC altında yalnızca Azure AD kullanıcı grubuna rol atanabileceğini unutmayın.
> - RBAC'ye geçtikten sonra temel izin yönetimini kullanmaya geri dönemezsiniz.

## <a name="related-topics"></a>İlgili konular

- [Portala erişmek için temel izinleri kullanın](basic-permissions.md)
- [RBAC kullanarak portal erişimini yönetin](rbac.md)
