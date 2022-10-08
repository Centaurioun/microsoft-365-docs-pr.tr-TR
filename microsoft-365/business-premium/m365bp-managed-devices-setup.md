---
title: Yönetilen cihazları ayarlama
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
ms.date: 07/19/2022
ms.collection:
- M365-Campaigns
- m365solution-smb
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
description: Yönetilen cihazları ayarlama
ms.openlocfilehash: 55f814a5e0d49526b0eae2dcd22e15504b9f3d25
ms.sourcegitcommit: db89873e22a12705ed313964c1bc2fa19d4fe719
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67878002"
---
# <a name="set-up-managed-devices"></a>Yönetilen cihazları ayarlama

"Yönetilen" cihaz, denetim altında olan ve kuruluş tarafından izlenen ve bu nedenle düzenli olarak güncelleştirilen ve güvenli olan cihazdır. Cihazların yönetilen denetim altında olması kritik bir hedeftir. Bu cihazları denetim altına almak için, her ikisi de Microsoft Business Premium'a dahil olan Microsoft Intune ve Azure Active Directory ile bir cihaz yöneticisine kaydedin.

1. [Kurulum sihirbazında](../business/set-up.md) cihaz ve veri koruma ilkelerini ayarlayın.

2. Bilgisayarı Microsoft 365 kullanıcı adı ve parolasıyla [Azure Active Directory'ye](../business/set-up-windows-devices.md) bağladı. 

## <a name="enroll-devices-in-intune"></a>Cihazları Intune'a kaydetme

1. Microsoft Endpoint Manager yönetim merkezine ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) gidin ve oturum açın.

2. **Cihazlar Cihazları** > **kaydet'i** seçin. 

   :::image type="content" source="media/m365bp-endpoint-manager-enroll-devices.png" alt-text="Cihazları kaydetmek için Microsoft Endpoint Manager kullanın."::: 

3. Aşağıdaki belirli cihaz kaydı kılavuzlarını izleyin.

### <a name="for-windows-enrollment"></a>Windows kaydı için:

1. **Windows kaydı'ı** >  seçin. 

2. Listelenen kayıt yöntemlerinden **Otomatik kayıt'ı** seçin.

### <a name="for-ios-enrollment"></a>iOS kaydı için:

1. **iOS iOS** > **kaydı'ı** seçin.

2. İlke listesinden ayrıntılarını görmek için bir ilke seçin.

3. İlkeyi yönetmek için **Özellikler'i** seçin.

4. **Ayarlar** > **Sistem Güvenliği'ne** tıklayın ve Intune'da güvenlik ayrıntılarını yapılandırın.

5. Yapılandırma profillerine bakın. 

6. Bir profil oluşturun ve gerektiğinde bunu kuruluşunuzdaki cihazlara gönderebilirsiniz.

### <a name="for-android-enrollment"></a>Android kaydı için:

1. **Android Android** > **kaydı'ı** seçin.

2. **Yönetilen Google Play'i** seçin ve Microsoft'a Google'a bilgi gönderme izni verin.

## <a name="next-objective"></a>Sonraki hedef

[Cihazları İş için Defender özelliklerine eklemek için](m365bp-onboard-devices-mdb.md) aşağıdaki kılavuzu kullanın.

