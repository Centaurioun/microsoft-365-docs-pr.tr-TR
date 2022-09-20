---
title: macOS'ta Uç Nokta için Microsoft Defender çekirdek uzantısı sorunlarını giderme
description: macOS'ta Uç Nokta için Microsoft Defender çekirdek uzantısıyla ilgili sorunları giderin.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, mac, çekirdek, uzantı
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 29f84a51f8156f3a238130ebd2b33f84c7ea5ef0
ms.sourcegitcommit: 95ac076310ab9006ed92c69938f7ae771cd10826
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67851776"
---
# <a name="troubleshoot-kernel-extension-issues-in-microsoft-defender-for-endpoint-on-macos"></a>macOS'ta Uç Nokta için Microsoft Defender çekirdek uzantısı sorunlarını giderme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**

- [macOS üzerinde Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Bu makalede, macOS'ta Uç Nokta için Microsoft Defender bir parçası olarak yüklenen çekirdek uzantısıyla ilgili sorunları giderme hakkında bilgi sağlanır.

macOS High Sierra 'dan (10.13) başlayarak macOS, cihazda çalıştırılmasına izin verilmeden önce tüm çekirdek uzantılarının açıkça onaylanmasını gerektirir.

macOS'ta Uç Nokta için Microsoft Defender dağıtımı/yüklemesi sırasında çekirdek uzantısını onaylamadıysanız, uygulama bunu etkinleştirmenizi isteyen bir başlık görüntüler:

:::image type="content" source="images/mdatp-32-main-app-fix.png" alt-text="RTP devre dışı" lightbox="images/mdatp-32-main-app-fix.png":::

komutunu da çalıştırabilirsiniz ```mdatp health```. Gerçek zamanlı korumanın etkinleştirilip etkinleştirilmediğini ancak kullanılamadığını bildirir. Bu, çekirdek uzantısının cihazınızda çalıştırılmasının onaylanmamış olduğunu gösterir.

```bash
mdatp health
```
```Output
...
real_time_protection_enabled                : true
real_time_protection_available              : false
...
```

Aşağıdaki bölümlerde, macOS'ta Uç Nokta için Microsoft Defender dağıtmak için kullandığınız yönteme bağlı olarak bu sorunun nasıl giderılacağına ilişkin yönergeler sağlanır.

## <a name="managed-deployment"></a>Yönetilen dağıtım

Ürünü dağıtmak için kullandığınız yönetim aracına karşılık gelen yönergelere bakın:

- [JAMF tabanlı dağıtım](mac-install-with-jamf.md)
- [Microsoft Intune tabanlı dağıtım](mac-install-with-intune.md#create-system-configuration-profiles)

## <a name="manual-deployment"></a>El ile dağıtım

Ürün yüklendikten sonra 30 dakikadan az bir süre geçtiyse, "Microsoft Corporation" geliştiricilerinin sistem yazılımına **izin ver** seçeneğini kullanmanız gereken **Sistem Tercihleri** \> **Güvenliği & Gizlilik'e** gidin.

Bu istemi görmüyorsanız, bu 30 veya daha fazla dakika geçtiği ve çekirdek uzantısının cihazınızda çalıştırılmasının hala onaylanmadığı anlamına gelir:

:::image type="content" source="images/mdatp-33-securityprivacysettings-noprompt.png" alt-text="İstem süresi dolduktan sonra güvenlik ve gizlilik penceresi" lightbox="images/mdatp-33-securityprivacysettings-noprompt.png":::

Bu durumda, onay akışını yeniden tetiklemeniz için aşağıdaki adımları gerçekleştirmeniz gerekir.

1. Terminal'de sürücüyü yüklemeyi deneme. Çekirdek uzantısının cihazda çalıştırılması onaylanmamış olduğundan aşağıdaki işlem başarısız olur. Ancak onay akışını yeniden tetikler.

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```

    ```Output
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Diagnostics for /Library/Extensions/wdavkext.kext:
    ```

2. **Menüden Sistem Tercihleri** \> **Güvenliği & Gizlilik'i** açın. (Açıksa önce kapatın.)

3. "Microsoft Corporation" geliştiricilerinin sistem yazılımına **izin ver**

4. Terminal'de sürücüyü yeniden yükleyin. Bu kez işlem başarılı olur:

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```

    Başlığın Defender uygulamasından kaybolması ve ```mdatp health``` artık gerçek zamanlı korumanın hem etkin hem de kullanılabilir olduğunu bildirmesi gerekir:

    ```bash
    mdatp health
    ```

    ```Output
    ...
    real_time_protection_enabled                : true
    real_time_protection_available              : true
    ...
    ```
