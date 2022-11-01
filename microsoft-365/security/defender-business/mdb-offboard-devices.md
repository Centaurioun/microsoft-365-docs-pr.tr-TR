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
ms.openlocfilehash: c87446bc9ce25287f2d615e72c11a56619742186
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68804849"
---
# <a name="offboard-a-device-from-microsoft-defender-for-business"></a>cihazı İş için Microsoft Defender'dan çıkarma

Cihazlar değiştirildiğinde veya kullanımdan kaldırıldığından veya iş gereksinimleriniz değiştikçe, Cihazları İş için Defender'dan çıkarabilirsiniz. Cihazı kullanıma almak, cihazın İş için Defender'a veri göndermeyi durdurmasına neden olur. Ancak, çıkarmadan önce alınan veriler altı (6) aya kadar saklanır.

> [!IMPORTANT]
> Bu makaledeki yordamlarda, bir cihazın İş için Defender tarafından izlenmesinden nasıl kaldırılacağı açıklanmaktadır. Cihazları yönetmek için Microsoft Intune kullanıyorsanız ve cihazı Intune'dan kaldırmayı tercih ediyorsanız, bkz. [Cihazı temizleme, devre dışı bırakma veya el ile kaydını kaldırma kullanarak cihazları kaldırma](/mem/intune/remote-actions/devices-wipe).

## <a name="what-to-do"></a>Yapılması gerekenler

1. Bir sekme seçin:

   - **Windows 10 veya 11**
   - **Mac**
   - **Sunucular** (Windows Server veya Linux Server)
   - **Mobil** (iOS/iPadOS veya Android cihazlar için)

2. Seçili sekmedeki yönergeleri izleyin.
3. Sonraki adımlarınıza geçin. 

## <a name="windows-10-or-11"></a>[**Windows 10 veya 11**](#tab/Windows1011)

## <a name="windows-10-or-11"></a>Windows 10 veya 11

1. Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com)) gidin ve oturum açın.

2. Gezinti bölmesinde **Ayarlar'ı** ve ardından **Uç Noktalar'ı** seçin.

3. **Cihaz yönetimi'nin** altında **Çıkarma'yı** seçin.

4. **Windows 10 ve 11** gibi bir işletim sistemi seçin ve ardından **Cihazı kullanıma alma** altında Dağıtım **yöntemi** bölümünde **Yerel betik'i** seçin. 

5. Onay ekranında bilgileri gözden geçirin ve ardından devam etmek için **İndir'i** seçin.

6. **Çıkarma paketini indir'i** seçin. Çıkarma paketini çıkarılabilir bir sürücüye kaydetmenizi öneririz.

7. Betiği, gemiden çıkarmak istediğiniz her cihazda çalıştırın.

## <a name="next-steps"></a>Sonraki adımlar

- [İş için Microsoft Defender'da Microsoft Defender Güvenlik Açığı Yönetimi panonuzu kullanma](mdb-view-tvm-dashboard.md)
- [İş için Microsoft Defender'de ilkeleri görüntüleme veya düzenleme](mdb-view-edit-create-policies.md)
- [İş için Microsoft Defender'de cihazları yönetme](mdb-manage-devices.md)

## <a name="mac"></a>[**Mac**](#tab/mac)

## <a name="offboard-a-mac"></a>Mac'i çıkarma

1. **Bulucu** > **Uygulamaları'na** gidin. 

2. **İş için Microsoft Defender** sağ tıklayın ve ardından **Çöp Kutusuna Taşı'yı** seçin. <br/>---Veya--- <br/> Şu komutu kullanın: `sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'`.

## <a name="next-steps"></a>Sonraki adımlar

- [İş için Microsoft Defender'da Microsoft Defender Güvenlik Açığı Yönetimi panonuzu kullanma](mdb-view-tvm-dashboard.md)
- [İş için Microsoft Defender'de ilkeleri görüntüleme veya düzenleme](mdb-view-edit-create-policies.md)
- [İş için Microsoft Defender'de cihazları yönetme](mdb-manage-devices.md)


## <a name="servers"></a>[**Sunucular**](#tab/Servers)

## <a name="servers"></a>Sunucular

Sunucunuz için işletim sistemini seçin:

- [Windows Server:](#windows-server)
- [Linux Server](#linux-server)

### <a name="windows-server"></a>Windows Server

1. Microsoft 365 Defender portalına ()[https://security.microsoft.com](https://security.microsoft.com) gidin ve oturum açın.

2. Gezinti bölmesinde **Ayarlar** > **Uç Noktaları'nı** seçin ve ardından **Cihaz yönetimi'nin** altında **Çıkarma'yı** seçin.

3. **Windows Server 1803, 2019 ve 2022** gibi bir işletim sistemi seçin ve ardından **Dağıtım yöntemi** bölümünde **Yerel betik'i** seçin. 

4. **Paketi indir'i** seçin. Çıkarma paketini çıkarılabilir bir sürücüye kaydetmenizi öneririz. Sıkıştırılmış klasör çağrılır `WindowsDefenderATPOffboardingPackage_valid_until_YYYY-MM-DD.zip` (burada `YYYY-MM-DD` paketin süre sonu tarihidir).

5. Windows Server cihazınızda sıkıştırılmış klasörün içeriğini Masaüstü klasörü gibi bir konuma ayıklayın.  

6. Bir komut istemini yönetici olarak açın.

7. Betik dosyasının konumunu yazın. Örneğin, dosyayı Desktop klasörüne kopyaladıysanız, (burada `YYYY-MM-DD` paketin süre sonu tarihidir) yazıp `%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_2022-11-11.cmd` Enter tuşuna (veya **Tamam'ı** seçin) basın.

### <a name="linux-server"></a>Linux Server

1. Microsoft 365 Defender portalına ()[https://security.microsoft.com](https://security.microsoft.com) gidin ve oturum açın.

2. Gezinti bölmesinde **Ayarlar** > **Uç Noktaları'nı** seçin ve ardından **Cihaz yönetimi'nin** altında **Çıkarma'yı** seçin.

3. İşletim sistemi için **Linux Server'ı** seçin ve ardından **Dağıtım yöntemi** bölümünde **Yerel betik'i** seçin. 

4. **Paketi indir'i** seçin. Çıkarma paketini çıkarılabilir bir sürücüye kaydetmenizi öneririz. Sıkıştırılmış klasör çağrılır `WindowsDefenderATPOffboardingPackage_valid_until_YYYY-MM-DD.zip` (burada `YYYY-MM-DD` paketin süre sonu tarihidir).

5. Linux Server cihazınızda sıkıştırılmış klasörün içeriğini Desktop klasörü gibi bir konuma ayıklayın.  

6. Bir terminal açın ve dosyanın bulunduğu dizine `MicrosoftDefenderATPOffboardingLinuxServer_valid_until_YYYY-MM-DD` gidin (dosyanın `YYYY-MM-DD` bitiş tarihidir).

7. Terminale yazın `python MicrosoftDefenderATPOffboardingLinuxServer_valid_until_YYYY-MM-DD.py` .

> [!TIP]
> Daha fazla bilgi için Bkz. Linux'ta Uç Nokta için Microsoft Defender yönergelerinde [Kaldırma](../defender-endpoint/linux-resources.md).

## <a name="next-steps"></a>Sonraki adımlar

- [İş için Microsoft Defender'da Microsoft Defender Güvenlik Açığı Yönetimi panonuzu kullanma](mdb-view-tvm-dashboard.md)
- [İş için Microsoft Defender'de ilkeleri görüntüleme veya düzenleme](mdb-view-edit-create-policies.md)
- [İş için Microsoft Defender'de cihazları yönetme](mdb-manage-devices.md)

## <a name="mobile-devices"></a>[**Mobil cihazlar**](#tab/mobiles)

## <a name="mobile-devices"></a>Mobil cihazlar

iOS, iPadOS ve Android cihazlar gibi mobil cihazları yönetmek için Microsoft Intune kullanabilirsiniz.

Bkz. [Microsoft Intune cihaz yönetimi](/mem/intune/remote-actions/device-management).

## <a name="next-steps"></a>Sonraki adımlar

- [İş için Microsoft Defender'da Microsoft Defender Güvenlik Açığı Yönetimi panonuzu kullanma](mdb-view-tvm-dashboard.md)
- [İş için Microsoft Defender'de ilkeleri görüntüleme veya düzenleme](mdb-view-edit-create-policies.md)
- [İş için Microsoft Defender'de cihazları yönetme](mdb-manage-devices.md)