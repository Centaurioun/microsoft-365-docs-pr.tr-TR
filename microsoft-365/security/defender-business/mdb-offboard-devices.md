---
title: cihazı İş için Microsoft Defender'dan çıkarma
description: Bir cihazı İş için Microsoft Defender kaldırma veya çıkarma hakkında bilgi edinin.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.date: 08/11/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-security
- m365-initiative-defender-business
- tier1
ms.openlocfilehash: 06e3e116886ef719f6c57c9711ef770704a53bfb
ms.sourcegitcommit: 0283c436f3ba61a708b52b57a1955f5ea74376a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2022
ms.locfileid: "68096445"
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

2. **İş için Microsoft Defender** sağ tıklayın ve ardından **Çöp Kutusuna Taşı'yı** seçin. <br/>---Veya--- <br/> Şu komutu kullanın: `sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'`.

> [!IMPORTANT]
> Cihazı kullanıma almak, cihazların İş için Defender'a veri göndermeyi durdurmasına neden olur. Ancak, çıkarmadan önce alınan veriler altı (6) aya kadar saklanır.

## <a name="next-steps"></a>Sonraki adımlar

- [İş için Microsoft Defender'da Microsoft Defender Güvenlik Açığı Yönetimi panonuzu kullanma](mdb-view-tvm-dashboard.md)
- [İş için Microsoft Defender'de ilkeleri görüntüleme veya düzenleme](mdb-view-edit-create-policies.md)
- [İş için Microsoft Defender'de cihazları yönetme](mdb-manage-devices.md)