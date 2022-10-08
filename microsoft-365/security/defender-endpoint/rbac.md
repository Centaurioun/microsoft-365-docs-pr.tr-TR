---
title: Microsoft 365 Defender portalına ayrıntılı erişim vermek için rol tabanlı erişim denetimini kullanma
description: Portala erişim vermek için güvenlik işlemlerinizde roller ve gruplar oluşturun.
keywords: rbac, rol, tabanlı, erişim, denetim, gruplar, denetim, katman, aad
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
- tier2
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: f55ca70c94fa73c26cefd067f2006f174ce4b15c
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68232682"
---
# <a name="manage-portal-access-using-role-based-access-control"></a>Rol tabanlı erişim denetimini kullanarak portal erişimini yönetme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Azure Active Directory
- Office 365

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-rbac-abovefoldlink)

Rol tabanlı erişim denetimini (RBAC) kullanarak, portala uygun erişim vermek için güvenlik operasyonları ekibinizde roller ve gruplar oluşturabilirsiniz. Oluşturduğunuz rollere ve gruplara bağlı olarak, portala erişimi olan kullanıcıların görebilecekleri ve yapabilecekleri üzerinde ayrıntılı denetime sahip olursunuz. 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bJ2a]

Büyük coğrafi olarak dağıtılmış güvenlik operasyonları ekipleri genellikle güvenlik portallarına erişim atamak ve erişim yetkisi vermek için katman tabanlı bir model benimser. Tipik katmanlar aşağıdaki üç düzeyi içerir:

|Katmanı |Açıklama  |
|---------|---------|
|Katman 1    | **Yerel güvenlik operasyonları ekibi / BT ekibi** <br> Bu ekip genellikle coğrafi konum içinde yer alan uyarıları önceliklendirmek ve araştırmakta ve etkin bir düzeltmenin gerekli olduğu durumlarda Katman 2'ye yükseltmektedir.        |
|Katman 2    | **Bölgesel güvenlik operasyonları ekibi** <br> Bu ekip, bölgelerinin tüm cihazlarını görebilir ve düzeltme eylemleri gerçekleştirebilir.        |
|Katman 3     |**Küresel güvenlik operasyonları ekibi** <br> Bu ekip güvenlik uzmanlarından oluşur ve portaldan tüm eylemleri görme ve gerçekleştirme yetkisine sahip.         |

> [!NOTE]
> Katman 0 varlıkları için güvenlik yöneticilerinin Uç Nokta için Microsoft Defender ve [Microsoft 365 Defender](/azure/active-directory/privileged-identity-management/pim-configure) daha ayrıntılı denetimi sağlamak için Privileged Identity Management bakın.  

Uç Nokta için Defender RBAC, tercih ettiğiniz katman veya rol tabanlı modeli destekleyecek şekilde tasarlanmıştır ve size hangi rollerin görebileceği, erişebileceği cihazlar ve gerçekleştirebilecekleri eylemler üzerinde ayrıntılı denetim sağlar. RBAC çerçevesi aşağıdaki denetimlerin etrafında ortalanır:

- **Belirli eylemleri kimin gerçekleştirebileceğini denetleme**
  - Özel roller oluşturun ve ayrıntı düzeyiyle erişebilecekleri Uç Nokta için Defender özelliklerini denetleyin.
- **Belirli cihaz grubu veya gruplarıyla ilgili bilgileri kimlerin görebileceğini denetleme**
  - Adlar, etiketler, etki alanları ve diğerleri gibi belirli ölçütlere göre [cihaz grupları oluşturun](machine-groups.md), ardından belirli bir Azure Active Directory (Azure AD) kullanıcı grubunu kullanarak bunlara rol erişimi verin.
    > [!NOTE]
    > Cihaz grubu oluşturma, Uç Nokta Için Defender Plan 1 ve Plan 2'de desteklenir.  

Rol tabanlı erişim uygulamak için yönetici rollerini tanımlamanız, ilgili izinleri atamanız ve rollere atanmış Azure AD kullanıcı grubu atamanız gerekir.

### <a name="before-you-begin"></a>Başlamadan önce

RBAC'yi kullanmadan önce, izin verebilen rolleri ve RBAC'yi açmanın sonuçlarını anlamanız önemlidir.

> [!WARNING]
> Özelliği etkinleştirmeden önce, Azure AD'da Genel Yönetici rolüne veya Güvenlik Yöneticisi rolüne sahip olmanız ve Azure AD gruplarınızın portaldan kilitlenme riskini azaltmaya hazır olması önemlidir. 

Microsoft 365 Defender portalında ilk kez oturum açtığınızda size tam erişim veya salt okunur erişim verilir. Azure AD'da Güvenlik Yöneticisi veya Genel Yönetici rollerine sahip kullanıcılara tam erişim hakları verilir. Azure AD'de Güvenlik Okuyucusu rolüne sahip kullanıcılara salt okunur erişim verilir. 

Uç Nokta için Defender Genel yönetici rolüne sahip biri, cihaz grubu ilişkilendirmesi ve Azure AD kullanıcı grupları atamalarından bağımsız olarak tüm cihazlara sınırsız erişime sahiptir.

> [!WARNING]
> Başlangıçta, Microsoft 365 Defender portalında yalnızca Azure AD Genel Yönetici veya Güvenlik Yöneticisi haklarına sahip olanlar rol oluşturabilir ve atayabilir, bu nedenle Azure AD'de doğru grupların hazır olması önemlidir.
>
> **Rol tabanlı erişim denetiminin etkinleştirilmesi, salt okunur izinlere sahip kullanıcıların (örneğin, Azure AD Güvenlik okuyucusu rolüne atanan kullanıcılar) bir role atanana kadar erişimi kaybetmesine neden olur.** 
>
>Yönetici izinlerine sahip kullanıcılara otomatik olarak tam izinlere sahip varsayılan Yerleşik Uç Nokta için Defender genel yönetici rolü atanır. RBAC kullanmayı kabul ettikten sonra, Genel veya Güvenlik Yöneticileri Azure AD olmayan ek kullanıcıları Uç Nokta için Defender genel yönetici rolüne atayabilirsiniz. 
>
> RBAC'yi kullanmayı kabul ettikten sonra, portalda ilk oturum açtığınızda olduğu gibi ilk rollere geri dönemezsiniz.

## <a name="related-topic"></a>İlgili konu

- [RBAC rolleri](../office-365-security/migrate-to-defender-for-office-365-onboard.md#rbac-roles)
- [Uç Nokta için Microsoft Defender'de cihaz grupları oluşturma ve yönetme](machine-groups.md)
