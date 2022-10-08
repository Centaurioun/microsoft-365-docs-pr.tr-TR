---
title: Microsoft 365 gruplarına üye ekleme veya gruptan üye kaldırma
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
ms.assetid: e186d224-a324-4afa-8300-0e4fc0c3000a
description: Microsoft 365 yönetim merkezi bir gruba üye eklemeyi, gruptan üyeyi kaldırmayı ve grup sahibi durumunu yönetmeyi öğrenin.
ms.openlocfilehash: 92f198ebfd354fddf54f67d8054bc8725dd30fca
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68190429"
---
# <a name="add-or-remove-members-from-microsoft-365-groups-using-the-admin-center"></a>Yönetim merkezini kullanarak Microsoft 365 gruplarına üye ekleme veya gruptan üye kaldırma

Microsoft 365'te grup üyeleri genellikle kendi gruplarını oluşturur, katılmak istedikleri gruplara kendilerini ekler veya grup sahipleri tarafından davet edilir. Grup sahipliği değişirse veya yönetici olarak bir üyenin eklenmesi veya kaldırılması gerektiğini belirlerseniz, bu değişikliği de yapabilirsiniz. Bu değişiklikleri yalnızca genel yönetici, Exchange yöneticisi, Gruplar yöneticisi veya kullanıcı yöneticisi yapabilir. [Microsoft 365 grubu nedir?](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

> [!TIP]
> Yönetici değilseniz [Outlook'u kullanarak üye ekleyebilir veya kaldırabilirsiniz](https://support.microsoft.com/office/3b650f4a-5c9b-4f94-a1bb-0cca4b1091de).
  
## <a name="add-a-member-to-a-group-in-the-admin-center"></a>Yönetim merkezindeki bir gruba üye ekleme

1. Yönetim merkezinde [**Etkin gruplar**](https://admin.microsoft.com/Adminportal/Home?#/groups) sayfasına gidin.  

2. Bir grup adına tıklayın.

3. Ayrıntılar bölmesindeki **Üyeler** sekmesinde **Tümünü görüntüle ve üyeleri yönet'i** ve ardından **Üye ekle'yi** seçin.

4. Eklemek istediğiniz üyenin adını arayın veya seçin.

5. **Kaydet**'i seçin.

## <a name="add-a-group-to-a-member-in-the-admin-center"></a>Yönetim merkezindeki üyeye grup ekleme

1. Yönetim merkezinde [**Etkin kullanıcılar**](https://admin.microsoft.com/Adminportal/Home?#/users) sayfasına gidin.  

2. Bir kullanıcıya tıklayın.

3. Ayrıntılar bölmesindeki **Hesap** sekmesinde **Grupları yönet'i** seçin.

4. Eklemek istediğiniz grubun adını arayın veya seçin.

5. **Kaydet**'i seçin.

## <a name="remove-a-member-from-a-group-in-the-admin-center"></a>Yönetim merkezindeki bir gruptan üye kaldırma

> [!NOTE]
> Bir üyeyi özel gruptan kaldırdığınızda, kişinin gruptan engellenmesi 5 dakika sürer.

1. Yönetim merkezinde [**Etkin gruplar**](https://admin.microsoft.com/Adminportal/Home?#/groups) sayfasına gidin.  

2. Bir grup adına tıklayın.

3. Ayrıntılar bölmesindeki **Üyeler** sekmesinde **Tümünü görüntüle ve üyeleri yönet'i** seçin.

4. Kaldırmak istediğiniz üyenin yanındaki X işaretini seçin.

5. Üyeyi kaldırmak için **Kaydet'i** seçin.

## <a name="manage-group-owner-status"></a>Grup sahibi durumunu yönetme

By default, the person who created the group is the group owner. Often a group will have multiple owners for backup support or other reasons. Members can be promoted to owner status and owners can be demoted to member status.
  
### <a name="promote-a-member-to-owner-status-in-the-admin-center"></a>Yönetim merkezinde üyeyi sahip durumuna yükseltme

1. Yönetim merkezinde [**Etkin gruplar**](https://admin.microsoft.com/Adminportal/Home?#/groups) sayfasına gidin.  

2. Bir grup adına tıklayın.

3. Ayrıntılar bölmesindeki **Üyeler** sekmesinde **Tümünü görüntüle ve sahiplerini yönet'i** seçin.

4. **Sahip ekle'yi** seçin.

5. Eklemek istediğiniz üyenin adının yanındaki onay kutusunu seçin.

6. **Kaydet'i** ve ardından **Kapat'ı** seçin.

### <a name="remove-owner-status-in-the-admin-center"></a>Yönetim merkezinde sahip durumunu kaldırma

1. Yönetim merkezinde [**Etkin gruplar**](https://admin.microsoft.com/Adminportal/Home?#/groups) sayfasına gidin.  

2. Bir grup adına tıklayın.

3. Ayrıntılar bölmesindeki **Üyeler** sekmesinde **Tümünü görüntüle ve sahiplerini yönet'i** seçin.

4. Sahibin adının yanındaki X işaretini seçin.

5. **Kaydet**'i seçin.

## <a name="next-steps"></a>Sonraki adımlar

- [Azure Active Directory'de grupları dinamik olarak yönetme](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal): "Bir grubun üyeliğini dinamik olarak nasıl yönetirim?" bölümüne bakın.

- Gruplara yüzlerce veya binlerce kullanıcı eklemek için [Add-UnifiedGroupLinks'i](/powershell/module/exchange/add-unifiedgrouplinks) kullanın.

- [Sahipsiz bir gruba yeni sahip atama](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

## <a name="related-content"></a>İlgili içerik

[Dağıtım listelerini Outlook'ta Microsoft 365 gruplarına yükseltme](../manage/upgrade-distribution-lists.md) (makale)\
[Dağıtım listelerinizi neden Outlook'ta gruplara yükseltmeniz gerekir](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188) (makale)\
[Microsoft 365 gruplarında konuk erişimini yönetme](manage-guest-access-in-groups.md) (makale)\
[PowerShell ile Microsoft 365 gruplarını yönetme](../../enterprise/manage-microsoft-365-groups-with-powershell.md): Bu makalede size önemli cmdlet'ler tanıtılır ve örnekler sağlanır (makale)\
[Microsoft 365 grupları adlandırma ilkesi](../../solutions/groups-naming-policy.md) (makale)