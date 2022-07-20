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
ms.date: 07/19/2022
ms.collection: ''
ms.custom:
- MiniMaven
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 İş Ekstra'de Autopilot kullanarak cihazları karşıya yüklemeyi öğrenin. Bir cihaza veya bir cihaz grubuna profil atayabilirsiniz.
ms.openlocfilehash: 9e02b985e5742331426210d6d3824dfa120a21d3
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2022
ms.locfileid: "66894997"
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
