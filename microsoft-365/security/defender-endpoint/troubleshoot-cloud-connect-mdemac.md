---
title: macOS'ta Uç Nokta için Microsoft Defender için bulut bağlantısı sorunlarını giderme
description: Bu konuda, macOS'ta Uç Nokta için Microsoft Defender için bulut bağlantısı sorunlarını giderme adımları açıklanmaktadır
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 55c3e0376094ace126c775afa9f47f349e0eff90
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68227712"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-macos"></a>macOS'ta Uç Nokta için Microsoft Defender için bulut bağlantısı sorunlarını giderme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Platform** macOS

Bu konuda, macOS'ta Uç Nokta için Microsoft Defender için bulut bağlantısı sorunlarını giderme adımları açıklanmaktadır.

## <a name="run-the-connectivity-test"></a>Bağlantı testini çalıştırma
Mac'te Uç Nokta için Defender'ın geçerli ağ ayarlarıyla bulutla iletişim kurarak iletişim kuramadığını test etmek için komut satırından bir bağlantı testi çalıştırın:

```Bash
mdatp connectivity test
```

beklenen çıkış:
```Bash
Testing connection with https://cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://eu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://wu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://x.cp.wd.microsoft.com/api/report ... [OK]
Testing connection with https://winatp-gw-cus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-eus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-weu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-neu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-ukw.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-uks.microsoft.com/test ... [OK]
Testing connection with https://eu-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://us-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://uk-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://v20.events.data.microsoft.com/ping ... [OK]
```

Bağlantı testi başarısız olursa cihazın İnternet erişimi olup olmadığını ve [ürünün gerektirdiği uç noktalardan herhangi birinin](microsoft-defender-endpoint-mac.md#network-connections) ara sunucu veya güvenlik duvarı tarafından engellenip engellenmediğini denetleyin.

Curl hatası 35 veya 60 olan hatalar sertifika sabitleme reddini gösterir ve bu da SSL veya HTTPS incelemesiyle ilgili olası bir sorunu gösterir. SSL inceleme yapılandırmasıyla ilgili aşağıdaki yönergelere bakın.

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-proxy-autoconfig-pac-or-with-web-proxy-autodiscovery-protocol-wpad"></a>Ara sunucu içermeyen veya Ara Sunucu otomatik yapılandırması (PAC) veya Web Proxy Otomatik Bulma Protokolü (WPAD) olan ortamlar için sorun giderme adımları
Ara sunucu olmayan bir ortamda, Ara Sunucu otomatik yapılandırması (PAC) veya Web Proxy Otomatik Bulma Protokolü (WPAD) ile bağlantının engellenmediğini test etmek için aşağıdaki yordamı kullanın.

Bir ara sunucu veya güvenlik duvarı anonim trafiği engelliyorsa, önceden listelenen URL'lerde anonim trafiğe izin verildiğinden emin olun.

> [!WARNING]
> Kimliği doğrulanmış proxy'ler desteklenmez. Yalnızca PAC, WPAD veya statik ara sunucu kullanıldığından emin olun. GÜVENLIK nedeniyle SSL denetimi ve ara sunucuları da desteklenmez. SSL denetimi ve ara sunucunuzun macOS'ta Uç Nokta için Microsoft Defender verileri kesmeden ilgili URL'lere doğrudan geçirmesi için bir özel durum yapılandırın. Kesme sertifikanızı genel depoya eklemek kesmeye izin vermez.
Bir bağlantının engellenmediğini test etmek için: Mac için Microsoft Edge veya Safari gibi bir tarayıcıda ve https://cdn.x.cp.wd.microsoft.com/ping'yi açınhttps://x.cp.wd.microsoft.com/api/report.

İsteğe bağlı olarak Terminal'de aşağıdaki komutu çalıştırın:

```Bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping' 
```

Bu komutun çıkışı şuna benzer olmalıdır:
```bash
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```
