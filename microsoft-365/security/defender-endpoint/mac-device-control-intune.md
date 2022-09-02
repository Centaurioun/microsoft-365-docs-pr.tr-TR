---
title: Intune için cihaz denetimi ilkeleri örnekleri
description: Intune ile kullanılabilecek örnekleri kullanarak cihaz denetim ilkelerini kullanmayı öğrenin.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, mac, device, control, usb, çıkarılabilir, medya, intune
ms.service: microsoft-365-security
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
ms.subservice: mde
ms.openlocfilehash: c601707dc34b4564319ec5f48455a5ab1cf54c64
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67522575"
---
# <a name="examples-of-device-control-policies-for-intune"></a>Intune için cihaz denetimi ilkeleri örnekleri

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Bu belge, kendi kuruluşunuz için özelleştirebileceğiniz cihaz denetimi ilkelerinin örneklerini içerir. Kuruluşunuzdaki cihazları yönetmek için Intune kullanıyorsanız bu örnekler geçerlidir.

## <a name="restrict-access-to-all-removable-media"></a>Tüm çıkarılabilir medyaya erişimi kısıtlama

Aşağıdaki örnek, tüm çıkarılabilir medyaya erişimi kısıtlar. İlkenin `none` en üst düzeyinde uygulanan izni not edin; diğer bir deyişle tüm dosya işlemlerine izin verilmez.

```xml
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
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
        </array>
    </dict>
</plist>
```

## <a name="set-all-removable-media-to-be-read-only"></a>Tüm çıkarılabilir medyayı salt okunur olarak ayarlama

Aşağıdaki örnekte tüm çıkarılabilir medya salt okunur olacak şekilde yapılandırılır. İlkenin `read` en üst düzeyinde uygulanan izne dikkat edin; başka bir deyişle tüm yazma ve yürütme işlemlerine izin verilmez.

```xml
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
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
        </array>
    </dict>
</plist>
```

## <a name="disallow-program-execution-from-removable-media"></a>Çıkarılabilir medyadan program yürütülmesine izin verme

Aşağıdaki örnekte, çıkarılabilir medyadan program yürütmeye nasıl izin verilebileceği gösterilmektedir. İlkenin `read` en üst düzeyinde uygulanan ve `write` izinlerine dikkat edin.

```xml
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
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
        </array>
    </dict>
</plist>
```

## <a name="restrict-all-devices-from-specific-vendors"></a>Belirli satıcıların tüm cihazlarını kısıtlama

Aşağıdaki örnek belirli satıcıların tüm cihazlarını kısıtlar (bu örnekte ve `4525`tarafından `fff0` tanımlanır). İlkenin en üst düzeyinde tanımlanan izin tüm olası izinleri (okuma, yazma ve yürütme) listelediğinden diğer tüm cihazlar kısıtlanmayacaktır.

```xml
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
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
        </array>
    </dict>
</plist>
```

## <a name="restrict-specific-devices-identified-by-vendor-id-product-id-and-serial-number"></a>Satıcı kimliği, ürün kimliği ve seri numarası ile tanımlanan belirli cihazları kısıtlama

Aşağıdaki örnek satıcı kimliği , ürün kimliği `fff0``1000`ve seri numaraları `04ZSSMHI2O7WBVOA` ve `04ZSSMHI2O7WBVOB`ile tanımlanan iki belirli cihazı kısıtlar. İlkenin diğer tüm düzeylerinde izinler tüm olası değerleri (okuma, yazma ve yürütme) içerir, yani diğer tüm cihazlar kısıtlanmamış olur.

```xml
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
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
        </array>
    </dict>
</plist>
```

## <a name="related-topics"></a>İlgili konular

- [macOS için cihaz denetimine genel bakış](mac-device-control-overview.md)
