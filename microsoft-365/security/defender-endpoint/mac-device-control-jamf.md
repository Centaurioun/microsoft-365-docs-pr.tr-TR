---
title: JAMF için cihaz denetimi ilkeleri örnekleri
description: JAMF ile kullanılmaktadır örnekleri kullanarak cihaz denetim ilkelerini kullanmayı öğrenin.
keywords: microsoft, defender, uç nokta, Uç nokta için Microsoft Defender, mac, cihaz, denetim, usb, çıkarılabilir, medya, jamf
ms.prod: m365-security
ms.mktglfcycl: security
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
ms.technology: mde
ms.openlocfilehash: 74925625f6d004c1901756cde75310b345dd5747
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2022
ms.locfileid: "63011881"
---
# <a name="examples-of-device-control-policies-for-jamf"></a>JAMF için cihaz denetimi ilkeleri örnekleri

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aşağıdakiler için geçerlidir:**
- [Uç Nokta Planı 1 için Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta Planı 2 için Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı mı deneyimliysiniz? [Ücretsiz deneme için kaydol'](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Bu belgede, kendi organizasyonunız için özelleştirebileceğiniz cihaz denetimi ilkelerinin örnekleri yer aldı. Bu örnekler, kuruluşta cihazları yönetmek için JAMF kullanıyorsanız uygulanabilir.

## <a name="restrict-access-to-all-removable-media"></a>Tüm çıkarılabilir medyaya erişimi kısıtlama

Aşağıdaki örnek, tüm çıkarılabilir medyaya erişimi kısıtlar. İlkenin `none` en üst düzeyinde uygulanan izinlere dikkat olun; bu, tüm dosya işlemlerinin yasaklanmayacakları anlamına gelir.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>deviceControl</key>
    <dict>
        <key>removableMediaPolicy</key>
        <dict>
            <key>enforcementLevel</key>
            <string>block</string>
            <key>permission</key>
            <array>
                <string>none</string>
            </array>
        </dict>
    </dict>
</dict>
</plist>
```

## <a name="set-all-removable-media-to-be-read-only"></a>Tüm çıkarılabilir medyayı salt okunur olacak şekilde ayarlama

Aşağıdaki örnekte, tüm çıkarılabilir medya salt okunur olacak şekilde yapılandırılır. İlkenin `read` en üst düzeyinde uygulanan izinlere dikkatin; bu, tüm yazma ve yürütme işlemlerine izin verilmeyecek anlamına gelir.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>deviceControl</key>
    <dict>
        <key>removableMediaPolicy</key>
        <dict>
            <key>enforcementLevel</key>
            <string>block</string>
            <key>permission</key>
            <array>
                <string>read</string>
            </array>
        </dict>
    </dict>
</dict>
</plist>
```

## <a name="disallow-program-execution-from-removable-media"></a>Çıkarılabilir medyadan program yürütmeye izin yok

Aşağıdaki örnekte, çıkarılabilir medyadan program yürütmeye nasıl izin verilmiyor? İlkenin `read` `write` en üst düzeyinde uygulanan ve izinlere dikkat olun.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>deviceControl</key>
    <dict>
        <key>removableMediaPolicy</key>
        <dict>
            <key>enforcementLevel</key>
            <string>block</string>
            <key>permission</key>
            <array>
                <string>read</string>
                <string>write</string>
            </array>
        </dict>
    </dict>
</dict>
</plist>
```

## <a name="restrict-all-devices-from-specific-vendors"></a>Belirli satıcılardan tüm cihazları kısıtlama

Aşağıdaki örnekte, belirli satıcılardan tüm cihazlar kısıtlandı (bu örnekte ve ile tanımlanır `fff0` `4525`). İlkenin en üst düzeyinde tanımlanan izin tüm olası izinleri (okuma, yazma ve yürütme) listeleyene kadar diğer tüm cihazlar kısıtlanmamıştır.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>deviceControl</key>
    <dict>
        <key>removableMediaPolicy</key>
        <dict>
            <key>enforcementLevel</key>
            <string>block</string>
            <key>permission</key>
            <array>
                <string>read</string>
                <string>write</string>
                <string>execute</string>
            </array>
            <key>vendors</key>
            <dict>
                <key>fff0</key>
                <dict>
                    <key>permission</key>
                    <array>
                        <string>none</string>
                    </array>
                </dict>
                <key>4525</key>
                <dict>
                    <key>permission</key>
                    <array>
                        <string>none</string>
                    </array>
                </dict>
            </dict>
        </dict>
    </dict>
</dict>
</plist>
```

## <a name="restrict-specific-devices-identified-by-vendor-id-product-id-and-serial-number"></a>Satıcı kimliği, ürün kimliği ve seri numarasına göre tanımlanan belirli cihazları kısıtlama

Aşağıdaki örnek satıcı kimliği, ürün kimliği ve seri numaraları `fff0`ve ile tanımlanan iki `1000`cihazı kısıtlar `04ZSSMHI2O7WBVOA` `04ZSSMHI2O7WBVOB`. İlkenin diğer tüm düzeylerinde, izinler tüm olası değerleri (okuma, yazma ve yürütme) içerir; başka bir ifadeyle tüm diğer cihazlar kısıtlanır.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>deviceControl</key>
    <dict>
        <key>removableMediaPolicy</key>
        <dict>
            <key>enforcementLevel</key>
            <string>block</string>
            <key>permission</key>
            <array>
                <string>read</string>
                <string>write</string>
                <string>execute</string>
            </array>
            <key>vendors</key>
            <dict>
                <key>fff0</key>
                <dict>
                    <key>permission</key>
                    <array>
                        <string>read</string>
                        <string>write</string>
                        <string>execute</string>
                    </array>
                    <key>products</key>
                    <dict>
                        <key>1000</key>
                        <dict>
                            <key>permission</key>
                            <array>
                                <string>read</string>
                                <string>write</string>
                                <string>execute</string>
                            </array>
                            <key>serialNumbers</key>
                            <dict>
                                <key>04ZSSMHI2O7WBVOA</key>
                                <array>
                                  <string>none</string>
                                </array>
                                <key>04ZSSMHI2O7WBVOB</key>
                                <array>
                                  <string>none</string>
                                </array>
                            </dict>
                        </dict>
                    </dict>
                </dict>
            </dict>
        </dict>
    </dict>
</dict>
</plist>
```

## <a name="related-topics"></a>İlgili konular

- [macOS için cihaz denetimine genel bakış](mac-device-control-overview.md)