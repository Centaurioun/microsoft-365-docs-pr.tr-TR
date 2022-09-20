---
title: Bir vakaya üye ekleme veya kaldırma
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: eBulma (Premium) servis talebini yönetirken servis talebine erişebilen üyeleri eklemeyi veya kaldırmayı öğrenin.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3d21d7953b69f2e449a2318caee7e75bdd64fc33
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67825180"
---
# <a name="add-or-remove-members-from-a-case"></a>Bir vakaya üye ekleme veya kaldırma

Olaya kimlerin erişebileceğini yönetmek için üye ekleyebilir veya kaldırabilirsiniz. Ancak, bir üyenin bir eBulma (Premium) olayına erişebilmesi (ve bu durumda görevleri gerçekleştirmesi) için kullanıcıyı Microsoft Purview uyumluluk portalı **İzinler** sayfasındaki eBulma Yöneticisi rol grubuna eklemeniz gerekir. Daha fazla bilgi için bkz. [eBulma izinleri atama](./assign-ediscovery-permissions.md).

1. **eBulma (Premium)** sayfasında, üye eklemek istediğiniz servis talebine gidin.

2. **Ayarlar** sekmesine tıklayın ve erişim **& izinleri** kutucuğunda **Seç'e** tıklayın.

3. **Üyeleri yönet'in** altında, olaya üye eklemek için **Ekle'ye** tıklayın. Ayrıca, Rol gruplarını yönet altında  **Ekle'ye** tıklayarak olaya **bir rol grubu** eklemeyi de seçebilirsiniz.

4. Servis talebi üyesi olarak eklenebilen kişi veya rol grupları listesinde, eklemek istediğiniz kişilerin veya rol gruplarının adlarının yanındaki onay kutusunu seçin.

   > [!NOTE]
   > Bir servis talebine rol grubu eklerken, yalnızca üyesi olduğunuz rol gruplarını ekleyebilirsiniz.

5. Servis talebine üye olarak eklenecek kişileri veya rol gruplarını seçtikten sonra **Ekle'ye** tıklayın.

6. **Yeni servis talebi** üyeleri listesini kaydetmek için Bu olayı yönet açılır sayfasında **Kaydet'e** tıklayın.

> [!IMPORTANT]
> Bir rolün, servis talebine üye olarak eklediğiniz bir rol grubuna eklenmesi veya kaldırılması durumunda rol grubu, servis talebinin bir üyesi olarak (veya rol grubunun üyesi olduğu herhangi bir durumda) otomatik olarak kaldırılır. Bunun nedeni, kuruluşunuzun bir olayın üyelerine yanlışlıkla ek izinler sağlamasını korumaktır. Benzer şekilde, bir rol grubu silinirse, üyesi olduğu tüm durumlardan kaldırılır. Daha fazla bilgi için bkz. [eBulma izinleri atama](assign-ediscovery-permissions.md#adding-role-groups-as-members-of-ediscovery-cases).

## <a name="removing-members-from-a-case"></a>Bir servis talebine üye kaldırma

Bir servis talebinin üyelerini yalnızca [eBulma Yöneticisi](assign-ediscovery-permissions.md) kaldırabilir. eBulma Yöneticisi rol grubuna atanmış olsanız veya başlangıçta olayı oluşturmuş olsanız bile, eBulma Yöneticisi olmadığınız sürece kendinizi veya diğer üyeleri bir servis talebinden kaldıramazsınız. Kendinizi veya diğer üyeleri bir servis talebinden kaldırmak için kuruluşunuzdaki bir eBulma Yöneticisine başvurun.
