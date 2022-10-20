---
title: Tek bir cihazda kurcalama korumasını yönetme
ms.reviewer: mattcall, pahuijbr, hayhov, oogunrinde
manager: dansimp
description: Tek bir cihaz için kurcalama korumasını açın veya kapatın.
keywords: kötü amaçlı yazılım, defender, virüsten koruma, kurcalama koruması
ms.pagetype: security
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom:
- nextgen
- admindeeplinkDEFENDER
ms.subservice: mde
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: eebc7e9328f68754a16342b70e6ad1a7ea67960b
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68629423"
---
# <a name="manage-tamper-protection-on-an-individual-device"></a>Tek bir cihazda kurcalama korumasını yönetme

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

> [!NOTE]
> Kurcalama koruması, kayıt defteri aracılığıyla Microsoft Defender Virüsten Koruma ayarlarını değiştirme girişimlerini engeller.
> Kurcalama korumasının Microsoft dışı güvenlik ürünlerini veya bu ayarları değiştiren kurumsal yükleme betiklerini engellemediğinden emin olmak için **Windows Güvenliği** gidin ve **Güvenlik zekasını** 1.287.60.0 veya sonraki bir sürüme güncelleştirin. (Bkz [. Güvenlik bilgileri güncelleştirmeleri](https://www.microsoft.com/wdsi/definitions).) Bu güncelleştirmeyi yaptıktan sonra, kurcalama koruması kayıt defteri ayarlarınızı korumaya devam eder ve hataları döndürmeden bunları değiştirmeye çalışır.

Ev kullanıcısıysanız veya güvenlik ekibi tarafından yönetilen ayarlara tabi değilseniz, kurcalama korumasını yönetmek için Windows Güvenliği uygulamasını kullanabilirsiniz. Kurcalama koruması gibi güvenlik ayarlarını değiştirmek için cihazınızda uygun yönetici izinlerine sahip olmanız gerekir.

Windows Güvenliği uygulamasında şunları görürsünüz:

:::image type="content" source="images/tamperprotectionturnedon.png" alt-text="Windows 10 Home'de kurcalama korumasını açma" lightbox="images/tamperprotectionturnedon.png":::

1. **Başlat'ı** seçin ve *Güvenlik* yazmaya başlayın. Arama sonuçlarında **Windows Güvenliği'ı** seçin.

2. **Virüs & tehdit koruması** \> **Virüs & tehdit koruması ayarlarını** seçin.

3. **Kurcalama Koruması'na** **Açık** veya **Kapalı** olarak ayarlayın.

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)

