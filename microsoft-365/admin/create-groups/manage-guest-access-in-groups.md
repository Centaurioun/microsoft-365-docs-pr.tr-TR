---
title: Microsoft 365 gruplarında konuk erişimini yönetme
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Bir Microsoft 365 grubuna konuk eklemeyi, konukları görüntülemeyi ve konuk erişimini denetlemek için PowerShell'i kullanmayı öğrenin.
ms.openlocfilehash: c2545c4b6e0d87f3f143139887ff50126bf41d06
ms.sourcegitcommit: cd9df1a681265905eef99c039f7036b2fa6e8b6d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67274758"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Microsoft 365 gruplarında konuk erişimini yönetme

Varsayılan olarak, kuruluşunuzda Microsoft 365 grupları için konuk erişimi açıktır. Yöneticiler, tüm kuruluşlarında veya tek tek gruplar için gruplara konuk erişimine izin verilip verilmeyeceğini denetleyebilir.

Etkinleştirildiğinde, grup üyeleri Web üzerinde Outlook aracılığıyla bir Microsoft 365 grubuna konuk davet edebilir. Davetler onay için grup sahibine gönderilir.

Onaylandıktan sonra konuk dizine ve gruba eklenir.

> [!Note]
> Yerel Modda veya [AB Coğrafi](/yammer/manage-security-and-compliance/manage-data-compliance) Olarak bulunan Yammer Kurumsal ağları ağ konuklarını desteklemez.
> Microsoft 365 Bağlı Yammer grupları şu anda konuk erişimini desteklemez, ancak Yammer ağınızda bağlı olmayan dış gruplar oluşturabilirsiniz. Yönergeler için bkz. [Yammer'da dış gruplar oluşturma ve yönetme](/yammer/work-with-external-users/create-and-manage-external-groups) .

Gruplardaki konuk erişimi genellikle SharePoint veya Teams içeren daha geniş bir senaryonun parçası olarak kullanılır. Bu hizmetlerin kendi konuk paylaşım ayarları vardır. Gruplar, SharePoint ve Teams arasında konuk paylaşımını ayarlamaya yönelik eksiksiz yönergeler için bkz:

- [Sitedeki konuklarla işbirliği yapma](../../solutions/collaborate-in-site.md)
- [Ekipteki konuklarla işbirliği yapma](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Grupların konuk erişimini yönetme

Gruplarda konuk erişimini etkinleştirmek veya devre dışı bırakmak istiyorsanız, bunu <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**Gruplar'da**</a> yapabilirsiniz.

1. Yönetim merkezinde Tüm \> **Ayarlar** \> **Kuruluş ayarlarını** **göster'e** gidin ve <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">**Hizmetler** sekmesinde</a> **Microsoft 365 Grupları'yi** seçin.
  
2. **Microsoft 365 Grupları** sayfasında, kuruluşunuzun dışındaki kişilerin grup kaynaklarına erişmesine izin vermek mi yoksa grup sahiplerinin kuruluşunuz dışındaki kişileri gruplara eklemesine izin vermek mi istediğinizi seçin.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Yönetim merkezinden bir Microsoft 365 grubuna konuk ekleme

Konuk dizininizde zaten varsa, <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">bunları Microsoft 365 yönetim merkezi</a> gruplarınıza ekleyebilirsiniz. (Dinamik üyeliği olan gruplar [Azure Active Directory'de yönetilmelidir](/azure/active-directory/enterprise-users/groups-create-rule).)
  
1. Yönetim merkezinde **Gruplar Grupları'na** >  gidin.<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a>
  
2. Konuğu eklemek istediğiniz grubu seçin ve **Üyeler** sekmesinde **Tümünü görüntüle ve üyeleri yönet'i** seçin. 
  
3. **Üye ekle'yi** seçin ve eklemek istediğiniz konuğun adını seçin.

4. **Kaydet**'i seçin.

Doğrudan dizine konuk eklemek istiyorsanız, [Azure portal Azure Active Directory B2B işbirliği kullanıcıları ekleyebilirsiniz](/azure/active-directory/b2b/add-users-administrator).

Bir konuğun bilgilerini düzenlemek istiyorsanız [, Azure Active Directory'yi kullanarak kullanıcının profil bilgilerini ekleyebilir veya güncelleştirebilirsiniz](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

## <a name="remove-a-guest"></a>Konuk kaldırma

Konuk kullanıcıyla işbirliği yaptıktan sonra, bu kullanıcıları kaldırabilirsiniz ve artık kuruluşunuza erişimi olmaz.

1. Microsoft 365 yönetim merkezi **Kullanıcılar'ı** genişletin ve <a href="https://go.microsoft.com/fwlink/p/?linkid=2074830" target="_blank">**konuk kullanıcılar'ı**</a> seçin.
1. **Konuk kullanıcılar** sayfasında, kaldırmak istediğiniz kullanıcıyı seçin ve ardından **Kullanıcıyı sil'i** seçin.

Azure AD portalında kullanıcıları kaldırmak için bkz. [Konuk kullanıcıyı ve kaynakları kaldırma](/azure/active-directory/b2b/b2b-quickstart-add-guest-users-portal#clean-up-resources).


## <a name="related-content"></a>İlgili içerik

[Belirli bir gruptan gelen konukları engelleme](../../solutions/per-group-guest-access.md) (makale)\
[Microsoft 365 yönetim merkezi grup üyeliğini yönetme](add-or-remove-members-from-groups.md) (makale)\
[Azure Active Directory erişim gözden geçirmeleri](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (makale)\
[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (makale)
