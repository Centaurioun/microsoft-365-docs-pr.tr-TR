---
title: Mac'te Uç Nokta için Microsoft Defender yükleme sorunlarını giderme
description: Mac'te Uç Nokta için Microsoft Defender yükleme sorunlarını giderme.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, mac, install
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
ms.openlocfilehash: 9de2083062e720016facebef118a9c279cd15697
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67519544"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-macos"></a>macOS'ta Uç Nokta için Microsoft Defender yükleme sorunlarını giderme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**

- [macOS üzerinde Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="installation-failed"></a>Yükleme başarısız oldu

El ile yükleme için, yükleme sihirbazının Özet sayfasında "Yükleme sırasında bir hata oluştu. Yükleyici, yüklemenin başarısız olmasına neden olan bir hatayla karşılaştı. Yardım için yazılım yayımcısı ile iletişime geçin." MDM dağıtımları için genel bir yükleme hatası olarak da görüntülenir.

Son kullanıcıya tam bir hata görüntülemesek de, içinde yükleme ilerlemesi `/Library/Logs/Microsoft/mdatp/install.log`olan bir günlük dosyası saklarız. Her yükleme oturumu bu günlük dosyasına eklenir. Yalnızca son yükleme oturumunun çıkışını almak için kullanabilirsiniz `sed` :

```bash
sed -n 'H; /^preinstall com.microsoft.wdav begin/h; ${g;p;}' /Library/Logs/Microsoft/mdatp/install.log
```
```Output
preinstall com.microsoft.wdav begin [2020-03-11 13:08:49 -0700] 804
INSTALLER_SECURE_TEMP=/Library/InstallerSandboxes/.PKInstallSandboxManager/CB509765-70FC-4679-866D-8A14AD3F13CC.activeSandbox/89FA879B-971B-42BF-B4EA-7F5BB7CB5695
correlation id=CB509765-70FC-4679-866D-8A14AD3F13CC
[ERROR] Downgrade from 100.88.54 to 100.87.80 is not permitted
preinstall com.microsoft.wdav end [2020-03-11 13:08:49 -0700] 804 => 1
```

Bu örnekte, gerçek nedeni ön ek olarak `[ERROR]`verilmiştir.
Bu sürümler arasında bir düşürme desteklenmediğinden yükleme başarısız oldu.

## <a name="mdatp-install-log-missing-or-not-updated"></a>MDATP yükleme günlüğü eksik veya güncelleştirilmedi

Nadir durumlarda, yükleme MDATP'nin /Library/Logs/Microsoft/mdatp/install.log dosyasında hiçbir iz bırakmaz.
İlk olarak bir yüklemenin gerçekleştiğini doğrulayın. Ardından macOS günlüklerini sorgulayarak olası hataları analiz edin. İstemci kullanıcı arabirimi olmadığında MDM dağıtımlarında bunu yapmak yararlı olur. Çok fazla bilgi olacağı için sorguyu çalıştırmak ve günlük işlemi adına göre filtrelemek için dar bir zaman penceresi kullanmanızı öneririz.

```bash
grep '^2020-03-11 13:08' /var/log/install.log
```
```Output
log show --start '2020-03-11 13:00:00' --end '2020-03-11 13:08:50' --info --debug --source --predicate 'processImagePath CONTAINS[C] "install"' --style syslog
```
