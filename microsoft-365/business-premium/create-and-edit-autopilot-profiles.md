---
title: Autopilot profili oluşturma ve düzenleme
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-business
ms.subservice: business-premium
ms.localizationpriority: high
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: Bir Autopilot profili oluşturmayı ve bunu bir cihaza uygulamayı, bir profili düzenlemeyi veya silmeyi ya da bir cihazdan profil kaldırmayı öğrenin.
ms.openlocfilehash: 2a74bf007f0dcac400033248813afe9558f0b2f8
ms.sourcegitcommit: db89873e22a12705ed313964c1bc2fa19d4fe719
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67877869"
---
# <a name="create-and-edit-autopilot-profiles"></a>Autopilot profili oluşturma ve düzenleme

Bir [cihaz grubundaki](m365bp-device-groups-mdb.md) cihazlara [Windows Autopilot dağıtım profili](/mem/autopilot/profiles) uygulayabilirsiniz. Dağıtım profilleri, kullanıcıların sahip olacağı Windows dağıtım ve kayıt deneyimini belirler. 

## <a name="create-a-profile"></a>Profil oluşturma

Profiller bir cihaza veya cihaz grubuna uygulanır,
  
1. Microsoft 365 yönetim merkezi **Cihazlar** \> **Otomatik Pilotu'nu** seçin.
  
2. **Autopilot** sayfasında **Profiller** sekmesini \> **Profil oluştur'u** seçin.

3. **Profil oluştur** sayfasında, profili tanımlamanıza yardımcı olacak bir ad girin, örneğin Pazarlama. İstediğiniz ayarı açın ve **kaydet'i** seçin. Autopilot profil ayarları hakkında daha fazla bilgi için bkz. [Autopilot Profili ayarları hakkında](m365bp-Autopilot-profile-settings.md).

    ![Enter name and turn on settings in the Create profile panel.](./../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>Cihaza profil uygulama

Profil oluşturduktan sonra bir cihaza veya bir cihaz grubuna uygulayabilirsiniz. [Adım adım kılavuzda](m365bp-add-Autopilot-devices-and-profile.md) var olan bir profili seçebilir ve yeni cihazlara uygulayabilir ya da bir cihaz veya cihaz grubu için mevcut profili değiştirebilirsiniz.
  
1. **Windows'u Hazırla** sayfasında **Cihazlar** sekmesini seçin.

2. Cihaz adının yanındaki onay kutusunu seçin ve **Cihaz** panelinde **Atanan profil** açılan listesinden \> **bir profil seçin Kaydet**.

    ![In the Device panel, select an Assigned profile to apply it.](./../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>Profili düzenleme, silme veya kaldırma

Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.
  
### <a name="edit-a-profile"></a>Profili düzenleme

1. **Windows'u Hazırla** sayfasında **Profiller** sekmesini seçin.

2. Cihaz adının yanındaki onay kutusunu seçin ve **Profil** panelinde, kullanılabilir ayarlardan \> herhangi birini **Güncelleştir Kaydet'i seçin**.

    Bir kullanıcı cihazı İnternet'e bağlamadan önce bu görevi yaparsanız, profil kurulum işlemine uygulanır.

### <a name="delete-a-profile"></a>Profili silme

1. **Windows'u Hazırla** sayfasında **Profiller** sekmesini seçin.

2. Cihaz adının yanındaki onay kutusunu seçin ve **Profil** panelinde **Profili** \> sil **Kaydet'i** seçin.

    Silinen profiller, atanmış oldukları cihazdan veya cihaz grubundan kaldırılır.

### <a name="remove-a-profile"></a>Profili kaldırma

1. **Windows'u Hazırla** sayfasında **Cihazlar** sekmesini seçin.

2. Cihaz adının yanındaki onay kutusunu seçin ve **Cihaz** panelinde **Atanan profil** açılan **listesinden**\> Kaydet'i **seçin.**

## <a name="see-also"></a>Ayrıca bkz.

[İş için Microsoft 365 planlarının güvenliğini sağlamaya yönelik en iyi yöntemler](../admin/security-and-compliance/secure-your-business-data.md)
