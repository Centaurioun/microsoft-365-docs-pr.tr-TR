---
title: Linux statik proxy bulmada Uç Nokta için Microsoft Defender
ms.reviewer: ''
description: Statik ara sunucu bulma için Linux'ta Uç Nokta için Microsoft Defender nasıl yapılandırıldığı açıklanır.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, linux, yükleme, ara sunucu
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
ms.openlocfilehash: 37fa8cf1acf8c557401a698710495d39882bf318
ms.sourcegitcommit: 2dedd0f594b817779e034afa6c4418def2382a22
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2022
ms.locfileid: "67796866"
---
# <a name="configure-microsoft-defender-for-endpoint-on-linux-for-static-proxy-discovery"></a>Linux'ta statik ara sunucu bulma için Uç Nokta için Microsoft Defender yapılandırma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Uç Nokta için Microsoft Defender ortam değişkenini `HTTPS_PROXY` kullanarak bir proxy sunucusu bulabilir. Bu ayar hem yükleme zamanında **hem de** ürün yüklendikten sonra yapılandırılmalıdır.

## <a name="installation-time-configuration"></a>Yükleme zamanı yapılandırması

Yükleme sırasında ortam `HTTPS_PROXY` değişkeni paket yöneticisine geçirilmelidir. Paket yöneticisi bu değişkeni aşağıdaki yollardan herhangi biriyle okuyabilir:

- `HTTPS_PROXY` değişkeni içinde aşağıdaki satırla tanımlanır`/etc/environment`:

  ```bash
  HTTPS_PROXY="http://proxy.server:port/"
  ```

- `HTTPS_PROXY` değişkeni paket yöneticisi genel yapılandırmasında tanımlanır. Örneğin, Ubuntu 18.04'te aşağıdaki satırı öğesine `/etc/apt/apt.conf.d/proxy.conf`ekleyebilirsiniz:

  ```bash
  Acquire::https::Proxy "http://proxy.server:port/";
  ```

  > [!CAUTION]
  > Yukarıdaki iki yöntemin sisteminizdeki diğer uygulamalar için kullanılacak ara sunucuyu tanımlayabileceğini unutmayın. Bu yöntemi dikkatli kullanın veya yalnızca bunun genel bir yapılandırma olması gerekiyorsa kullanın.

- `HTTPS_PROXY` değişkeni yükleme veya kaldırma komutlarına eklenir. Örneğin, APT paket yöneticisiyle, Uç Nokta için Microsoft Defender yüklerken değişkeni aşağıdaki gibi ekleyin:

  ```bash
  HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
  ```

  > [!NOTE]
  > Ortam değişkeni tanımı ile apt arasında sudo eklemeyin, aksi takdirde değişken yayılmaz.

Ortam `HTTPS_PROXY` değişkeni, kaldırma sırasında benzer şekilde tanımlanabilir.

Bir ara sunucu gerekliyse ancak yapılandırılmamışsa yükleme ve kaldırma işleminin mutlaka başarısız olacağını unutmayın. Ancak telemetri gönderilmez ve ağ zaman aşımları nedeniyle işlem çok daha uzun sürebilir.

## <a name="post-installation-configuration"></a>Yükleme sonrası yapılandırma

Yüklemeden sonra ortam değişkeniNin `HTTPS_PROXY` Uç Nokta için Defender hizmet dosyasında tanımlanması gerekir. Bunu yapmak için komutunu çalıştırın `sudo systemctl edit --full mdatp.service`.
Ardından değişkeni hizmete iki yoldan biriyle yayabilirsiniz:

- Satırın `#Environment="HTTPS_PROXY=http://address:port"` açıklamasını kaldırın ve statik proxy adresinizi belirtin.

- Bir satır `EnvironmentFile=/path/to/env/file`ekleyin. Bu yol, aşağıdaki satırı eklemesi gereken özel bir dosyaya veya özel bir dosyaya işaret `/etc/environment` edebilir:

  ```bash
  HTTPS_PROXY="http://proxy.server:port/"
  ```

öğesini değiştirdikten `mdatp.service`sonra dosyayı kaydedin ve aşağıdaki komutlar kullanılarak değişikliklerin uygulanabilmesi için hizmeti yeniden başlatın:

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```
> [!NOTE]
> 'yi kaldırmadan `mdatp`önce yapmış olabileceğiniz tüm eklemeleri kaldırmak için, içinden özel dosyayı `/etc/systemd/system`silin.
