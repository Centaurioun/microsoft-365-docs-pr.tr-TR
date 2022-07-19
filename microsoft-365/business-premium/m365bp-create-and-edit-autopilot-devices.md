---
title: Autopilot cihazları oluşturma ve düzenleme
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Microsoft 365 İş Ekstra'de Autopilot kullanarak cihazları karşıya yüklemeyi öğrenin. Bir cihaza veya bir cihaz grubuna profil atayabilirsiniz.
ms.openlocfilehash: 994eab29d4b04e2de21d3e42a4abc174270f67f7
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66861976"
---
# <a name="create-and-edit-autopilot-devices"></a>Autopilot cihazları oluşturma ve düzenleme

## <a name="upload-a-list-of-devices"></a>Cihaz listesini karşıya yükleme

Cihazları karşıya yüklemek için [Adım adım kılavuzu](m365bp-add-Autopilot-devices-and-profile.md) kullanabilirsiniz, ancak **cihazları Cihazlar** sekmesinden de karşıya yükleyebilirsiniz. 
  
Cihazların şu gereksinimleri karşılaması gerekir:
  
- Windows 10, sürüm 1703 veya üzeri
    
- Windows ilk çalıştırma deneyiminden geçmemiş yeni cihazlar

1. Microsoft 365 yönetim merkezi **Cihazlar** \> **Otomatik Pilotu'nu** seçin.
  
2. **Autopilot** sayfasında **Cihazlar** sekmesini \> **Cihaz ekle'yi** seçin.
    
    ![In the Devices tab, choose Add devices.](./../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. **Cihaz ekle** panelinde, **Kapat'ı** **Kaydet'i** \> hazırladığınız \> [bir Cihaz listesi CSV dosyasına](../admin/misc/device-list.md) gidin.
    
    Bu bilgileri donanım satıcınızdan alabilir veya [Get-WindowsAutopilotInfo PowerShell betiğini](https://www.powershellgallery.com/packages/Get-WindowsAutopilotInfo) kullanarak CSV dosyası oluşturabilirsiniz. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Cihaza veya cihaz grubuna profil atama

1. **Windows'u Hazırla** sayfasında **Cihazlar** sekmesini seçin ve bir veya daha fazla cihazın yanındaki onay kutusunu seçin. 
    
2. **Cihaz** panelinde, **Atanan profil** açılan listesinden bir profil seçin. 
    
    Henüz hiç profiliniz yoksa yönergeler için [bkz. Autopilot profilleri oluşturma ve düzenleme](../admin/devices/create-and-edit-Autopilot-profiles.md) . 

## <a name="see-also"></a>Ayrıca bkz.

[İş için Microsoft 365 planlarının güvenliğini sağlamaya yönelik en iyi yöntemler](../admin/security-and-compliance/secure-your-business-data.md)
