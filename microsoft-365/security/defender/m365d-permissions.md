---
title: Microsoft 365 Defender portalında Microsoft 365 Defender verilere erişimi yönetme
description: Microsoft 365 Defender'da verilere yönelik izinleri yönetmeyi öğrenin
keywords: erişim, izinler, Microsoft 365 Defender, M365, güvenlik, Cloud Apps için Defender, Uç Nokta için Microsoft Defender, kapsam, kapsam, kapsam, RBAC
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 41cfe8d191f553ce2a6498d9badfd46e19f4c61e
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67495137"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a>Azure Active Directory genel rolleri ile Microsoft 365 Defender erişimini yönetme

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Microsoft 365 Defender erişimini yönetmenin iki yolu vardır:
- **Genel Azure Active Directory (AD) rolleri**
- **Özel rol erişimi**

Aşağıdaki **Genel Azure Active Directory (AD) rollerine** atanan hesaplar Microsoft 365 Defender işlevlere ve verilere erişebilir:
- Genel yönetici
- Güvenlik yöneticisi
- Güvenlik İşleci
- Genel Okuyucu
- Güvenlik Okuyucusu

Bu rollere sahip hesapları gözden geçirmek için [Microsoft 365 Defender portalında İzinler'i görüntüleyin](https://security.microsoft.com/permissions).

**Özel rol** erişimi, Microsoft 365 Defender yeni bir özelliktir ve Microsoft 365 Defender'daki belirli verilere, görevlere ve özelliklere erişimi yönetmenize olanak tanır. Özel roller, genel Azure AD rollerinden daha fazla denetim sunar ve kullanıcılara yalnızca ihtiyaç duydukları erişimi en az izin veren rollerle sağlar.  Genel Azure AD rollerine ek olarak özel roller de oluşturulabilir. [Özel roller hakkında daha fazla bilgi edinin](custom-roles.md).

> [!NOTE]
> Bu makale yalnızca genel Azure Active Directory rollerini yönetmek için geçerlidir. Özel rol tabanlı erişim denetimini kullanma hakkında daha fazla bilgi için bkz. [Rol tabanlı erişim denetimi için özel roller](custom-roles.md)

## <a name="access-to-functionality"></a>İşlevselliğe erişim
Belirli işlevlere erişim[, Azure AD rolünüz](/azure/active-directory/roles/permissions-reference) tarafından belirlenir. Size veya kullanıcı grubunuza yeni bir rol atanmasını gerektiren belirli işlevlere erişmeniz gerekiyorsa genel yöneticiye başvurun.

### <a name="approve-pending-automated-tasks"></a>Bekleyen otomatik görevleri onaylama
[Otomatik araştırma ve düzeltme](m365d-autoir-actions.md) e-postalar, iletme kuralları, dosyalar, kalıcılık mekanizmaları ve araştırma sırasında bulunan diğer yapıtlar üzerinde işlem yapabilir. Açık onay gerektiren bekleyen eylemleri onaylamak veya reddetmek için Microsoft 365'te belirli rollerin atanmış olması gerekir. Daha fazla bilgi için bkz [. İşlem merkezi izinleri](m365d-action-center.md#required-permissions-for-action-center-tasks).

## <a name="access-to-data"></a>Verilere erişim
Microsoft 365 Defender verilere erişim, Uç Nokta için Microsoft Defender rol tabanlı erişim denetiminde (RBAC) kullanıcı gruplarına atanan kapsam kullanılarak denetlenebilir. Erişiminizin kapsamı Uç Nokta için Defender'daki belirli bir cihaz kümesiyle belirlenmediyse, Microsoft 365 Defender'daki verilere tam erişiminiz olur. Ancak hesabınızın kapsamı tamamlandıktan sonra yalnızca kapsamınızdaki cihazlarla ilgili verileri görürsünüz.

Örneğin, Uç Nokta için Microsoft Defender rolüne sahip tek bir kullanıcı grubuna aitseniz ve bu kullanıcı grubuna yalnızca satış cihazlarına erişim verildiyse, Microsoft 365 Defender yalnızca satış cihazlarıyla ilgili verileri görürsünüz. [Uç Nokta için Microsoft Defender'da RBAC ayarları hakkında daha fazla bilgi edinin](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-defender-for-cloud-apps-access-controls"></a>erişim denetimlerini Microsoft Defender for Cloud Apps
Önizleme sırasında Microsoft 365 Defender, Cloud Apps için Defender ayarlarına göre erişim denetimlerini zorunlu kılmaz. Microsoft 365 Defender verilere erişim bu ayarlardan etkilenmez.

## <a name="related-topics"></a>İlgili konular
- [Microsoft 365 Defender için rol tabanlı erişim denetiminde özel roller](custom-roles.md)
- [Yerleşik rolleri Azure AD](/azure/active-directory/roles/permissions-reference)
- [RBAC Uç Nokta için Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Cloud Apps için Defender rolleri](/cloud-app-security/manage-admins)
