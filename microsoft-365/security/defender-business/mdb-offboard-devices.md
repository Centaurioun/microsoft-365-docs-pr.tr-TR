---
title: cihazı İş için Microsoft Defender'dan çıkarma
description: Bir cihazı İş için Microsoft Defender kaldırma veya çıkarma hakkında bilgi edinin.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: bd6ea78daa1a19d84efc23c34bdb58704484c0d1
ms.sourcegitcommit: fa90763559239c4c46c5e848939126763879d8e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2022
ms.locfileid: "66772421"
---
# <a name="offboard-a-device-from-microsoft-defender-for-business"></a>cihazı İş için Microsoft Defender'dan çıkarma

Bir cihazı boşaltmak istiyorsanız aşağıdaki yordamlardan birini kullanın:

- [Windows cihazını çıkarma](#offboard-a-windows-device)
- [Mac'i çıkarma](#offboard-a-mac)

## <a name="offboard-a-windows-device"></a>Windows cihazını çıkarma

1. Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com)) gidin ve oturum açın.

2. Gezinti bölmesinde **Ayarlar'ı** ve ardından **Uç Noktalar'ı** seçin.

3. **Cihaz yönetimi'nin** altında **Çıkarma'yı** seçin.

4. **Windows 10 ve 11** gibi bir işletim sistemi seçin ve ardından **Cihazı kullanıma alma** altında Dağıtım **yöntemi** bölümünde **Yerel betik'i** seçin. 

5. Onay ekranında bilgileri gözden geçirin ve ardından devam etmek için **İndir'i** seçin.

6. **Çıkarma paketini indir'i** seçin. Çıkarma paketini çıkarılabilir bir sürücüye kaydetmenizi öneririz.

7. Betiği, gemiden çıkarmak istediğiniz her cihazda çalıştırın.

## <a name="offboard-a-mac"></a>Mac'i çıkarma

1. **Bulucu** > **Uygulamaları'na** gidin. 

2. **İş için Microsoft Defender** sağ tıklayın ve ardından **Çöp Kutusuna Taşı'yı** seçin. <br/>--- veya --- <br/> Şu komutu kullanın: `sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'`.

> [!IMPORTANT]
> Cihazı kullanıma almak, cihazların İş için Defender'a veri göndermeyi durdurmasına neden olur. Ancak, çıkarmadan önce alınan veriler altı (6) aya kadar saklanır.

## <a name="next-steps"></a>Sonraki adımlar

- [İş için Microsoft Defender'da Tehdit & Güvenlik Açığı Yönetimi panonuzu kullanma](mdb-view-tvm-dashboard.md)
- [İş için Microsoft Defender'de ilkeleri görüntüleme veya düzenleme](mdb-view-edit-create-policies.md)
- [İş için Microsoft Defender'de cihazları yönetme](mdb-manage-devices.md)