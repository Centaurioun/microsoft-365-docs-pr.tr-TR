---
title: Linux'ta Uç Nokta için Microsoft Defender için bulut bağlantısı sorunlarını giderme
ms.reviewer: ''
description: Linux'ta Uç Nokta için Microsoft Defender için bulut bağlantısı sorunlarını gidermeyi öğrenin
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, linux, bulut, bağlantı, iletişim
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
ms.openlocfilehash: 67de082c32affeab90584a71efad1a657f95969e
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67690083"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Linux'ta Uç Nokta için Microsoft Defender için bulut bağlantısı sorunlarını giderme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a>Bağlantı testini çalıştırma

Linux'ta Uç Nokta için Defender'ın geçerli ağ ayarlarıyla bulutla iletişim kurarak iletişim kuramadığını test etmek için komut satırından bir bağlantı testi çalıştırın:

```bash
mdatp connectivity test
```

beklenen çıkış:

```output
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

Bağlantı testi başarısız olursa cihazın İnternet erişimi olup olmadığını ve [ürünün gerektirdiği uç noktalardan herhangi birinin](microsoft-defender-endpoint-linux.md#network-connections) ara sunucu veya güvenlik duvarı tarafından engellenip engellenmediğini denetleyin.

Curl hatası 35 veya 60 olan hatalar, sertifika sabitleme reddini gösterir. Lütfen bağlantının SSL veya HTTPS denetimi altında olup olmadığını denetleyin. Öyleyse, izin ver listesine Uç Nokta için Microsoft Defender ekleyin.

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a>Ara sunucu olmayan veya saydam ara sunucu içeren ortamlar için sorun giderme adımları

Ara sunucu olmayan veya saydam ara sunucu içeren bir ortamda bağlantının engellenmediğini test etmek için terminalde aşağıdaki komutu çalıştırın:

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

Bu komutun çıkışı şuna benzer olmalıdır:

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a>Statik ara sunucusu olan ortamlar için sorun giderme adımları

> [!WARNING]
> PAC, WPAD ve kimliği doğrulanmış proxy'ler desteklenmez. Yalnızca statik bir ara sunucu veya saydam proxy kullanıldığından emin olun.
>
> GÜVENLIK nedeniyle SSL denetimi ve ara sunucuları da desteklenmez. SSL incelemesi için bir özel durum yapılandırın ve ara sunucunuzu, Linux'ta Uç Nokta için Defender'dan kesme olmadan ilgili URL'lere doğrudan veri geçirmek için yapılandırın. Kesme sertifikanızı genel depoya eklemek kesmeye izin vermez.

Statik ara sunucu gerekiyorsa, yukarıdaki komuta `proxy_address:port` ara sunucu adresine ve bağlantı noktasına karşılık gelen bir proxy parametresi ekleyin:

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

Dosyada yapılandırılan proxy adresini ve bağlantı noktasını kullandığınızdan `/lib/system/system/mdatp.service` emin olun. Yukarıdaki komutlardan hatalar olup olmadığını proxy yapılandırmanızı denetleyin.

mdatp proxy'sini ayarlamak için aşağıdaki komutu kullanın:

```bash
mdatp config proxy set --value http://address:port 
```


Başarılı olduğunda, komut satırından başka bir bağlantı testi deneyin:

```bash
mdatp connectivity test
```

Sorun devam ederse müşteri desteğine başvurun.

## <a name="resources"></a>Kaynaklar

- Ürünü statik ara sunucu kullanacak şekilde yapılandırma hakkında daha fazla bilgi için bkz[. Statik ara sunucu bulma için Uç Nokta için Microsoft Defender yapılandırma](linux-static-proxy-configuration.md).
