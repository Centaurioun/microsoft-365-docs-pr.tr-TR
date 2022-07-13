---
title: İş için Microsoft Defender'de cihazları yönetme
description: küçük ve orta ölçekli işletmeler için uç nokta koruması olan İş için Defender'da cihaz eklemeyi, kaldırmayı ve yönetmeyi öğrenin.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 735f9e04a9176ce1b6626a050429c0b7323a7c0b
ms.sourcegitcommit: fa90763559239c4c46c5e848939126763879d8e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2022
ms.locfileid: "66772937"
---
# <a name="manage-devices-in-microsoft-defender-for-business"></a>İş için Microsoft Defender'de cihazları yönetme

İş için Defender'da cihazları aşağıdaki gibi yönetebilirsiniz:

- Risk düzeylerini, maruz kalma düzeylerini ve sistem durumunu görmek için [eklenen cihazların listesini görüntüleme](#view-the-list-of-onboarded-devices)
- Tehdit algılamaları olan [bir cihazda işlem gerçekleştirme](#take-action-on-a-device-that-has-threat-detections)
- [İş için Defender'a cihaz ekleme](#onboard-a-device)  
- [İş için Defender'dan cihaz çıkarma](#offboard-a-device)


## <a name="view-the-list-of-onboarded-devices"></a>Eklenen cihazların listesini görüntüleme

:::image type="content" source="../../media/defender-business/mdb-deviceinventory.png" alt-text="Cihaz envanterinin ekran görüntüsü":::

1. Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com)) gidin ve oturum açın.

2. Gezinti bölmesinde **Cihaz envanteri'ni** seçin.

3. Durumu hakkında daha fazla bilgi edinebileceğiniz ve eylem gerçekleştirebileceğiniz açılır panelini açmak için bir cihaz seçin. 

   Henüz listelenen herhangi bir cihazınız yoksa, [Cihazları İş için Defender'a ekleme](mdb-onboard-devices.md)

## <a name="take-action-on-a-device-that-has-threat-detections"></a>Tehdit algılamaları olan bir cihazda işlem gerçekleştirme

:::image type="content" source="../../media/defender-business/mdb-selected-device.png" alt-text="Ayrıntıları ve eylemleri içeren seçili bir cihazın ekran görüntüsü":::

1. Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com) ) gezinti bölmesinde **Cihaz envanteri'ni** seçin. 

2. Açılır panelini açmak için bir cihaz seçin ve görüntülenen bilgileri gözden geçirin.

3. Eylemler menüsünü açmak için üç noktayı (**...**) seçin. 

4. **Virüsten koruma taraması çalıştır** veya **Otomatik Araştırma Başlat** gibi bir eylem seçin. 

## <a name="onboard-a-device"></a>Cihaz ekleme

Bkz [. Cihazları İş için Defender'a ekleme](mdb-onboard-devices.md).

## <a name="offboard-a-device"></a>Cihazı çıkarma

Bkz. [Cihazı çıkarma](mdb-offboard-devices.md).

## <a name="next-steps"></a>Sonraki adımlar

- [İş için Defender'da olayları görüntüleme ve yönetme](mdb-view-manage-incidents.md)
- [İş için Defender'da tehditlere yanıt verme ve tehditleri azaltma](mdb-respond-mitigate-threats.md)
- [İşlem merkezindeki düzeltme eylemlerini gözden geçirme](mdb-review-remediation-actions.md)
- [Cihaz gruplarını oluşturma veya düzenleme](mdb-create-edit-device-groups.md)