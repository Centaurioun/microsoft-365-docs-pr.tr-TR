---
title: Linux'ta Uç Nokta için Microsoft Defender yükleme sorunlarını giderme
ms.reviewer: ''
description: Linux'ta Uç Nokta için Microsoft Defender yükleme sorunlarını giderme
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, linux, yükleme
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
ms.openlocfilehash: 761cc1ea72bfccba98145daa2e8649f33268997e
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67521729"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Linux'ta Uç Nokta için Microsoft Defender yükleme sorunlarını giderme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-that-the-installation-succeeded"></a>Yüklemenin başarılı olduğunu doğrulayın

Yüklemedeki bir hata, paket yöneticisi tarafından anlamlı bir hata iletisiyle sonuçlanabilir veya oluşmayabilir. Yüklemenin başarılı olup olmadığını doğrulamak için aşağıdakileri kullanarak yükleme günlüklerini alın ve denetleyin:

```bash
 sudo journalctl --no-pager|grep 'microsoft-mdatp' > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
```

Önceki komutun doğru yükleme tarihi ve saatini içeren bir çıktı başarılı olduğunu gösterir.

Ayrıca ürünün durumunu doğrulamak ve EICAR metin dosyasını algılamak için [İstemci yapılandırmasını](linux-install-manually.md#client-configuration) denetleyin.

## <a name="make-sure-you-have-the-correct-package"></a>Doğru pakete sahip olduğunuzdan emin olun

Yüklediğiniz paketin konak dağıtımı ve sürümüyle eşleşip eşleşmediğini doğrulayın.

<br>

****

|Paket|Dağıtım|
|---|---|
|mdatp-rhel8. Linux.x86_64.rpm|Oracle, RHEL ve CentOS 8.x|
|mdatp-sles12. Linux.x86_64.rpm|SUSE Linux Enterprise Server 12.x|
|mdatp-sles15. Linux.x86_64.rpm|SUSE Linux Enterprise Server 15.x|
|mdatp. Linux.x86_64.rpm|Oracle, RHEL ve CentOS 7.x|
|mdatp. Linux.x86_64.deb|Debian ve Ubuntu 16.04, 18.04 ve 20.04|
|

[El ile dağıtım](linux-install-manually.md) için doğru dağıtım ve sürümün seçildiğinden emin olun.

## <a name="installation-failed"></a>Yükleme başarısız oldu

Uç Nokta için Defender hizmetinin çalıştırılıp çalıştırılamadığını denetleyin:

```bash
service mdatp status
```

```Output
 ● mdatp.service - Microsoft Defender for Endpoint
   Loaded: loaded (/lib/systemd/system/mdatp.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2020-03-26 10:37:30 IST; 23h ago
 Main PID: 1966 (wdavdaemon)
    Tasks: 105 (limit: 4915)
   CGroup: /system.slice/mdatp.service
           ├─1966 /opt/microsoft/mdatp/sbin/wdavdaemon
           ├─1967 /opt/microsoft/mdatp/sbin/wdavdaemon
           └─1968 /opt/microsoft/mdatp/sbin/wdavdaemon
 ```

## <a name="steps-to-troubleshoot-if-the-mdatp-service-isnt-running"></a>mdatp hizmeti çalışmıyorsa sorun giderme adımları

1. "mdatp" kullanıcısı olup olmadığını denetleyin:

    ```bash
    id "mdatp"
    ```

    Çıkış yoksa komutunu çalıştırın

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. Aşağıdakileri kullanarak hizmeti etkinleştirmeyi ve yeniden başlatmayı deneyin:

    ```bash
    sudo service mdatp start
    ```

    ```bash
    sudo service mdatp restart
    ```

3. Önceki komutu çalıştırdıktan sonra mdatp.service bulunamazsa şunu çalıştırın:

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path> 
    ```

    `/lib/systemd/system` burada `<systemd_path>` Ubuntu ve Debian dağıtımları ve Rhel, CentOS, Oracle ve SLES için /usr/lib/systemd/system' içindir. Ardından 2. adımı yeniden çalıştırın.

4. Yukarıdaki adımlar işe yaramazsa SELinux'in yüklü ve zorunlu modda olup olmadığını denetleyin. Öyleyse, izinli (tercihen) veya devre dışı moduna ayarlamayı deneyin. Parametresi dosyada `SELINUX` "izin" veya "devre dışı" `/etc/selinux/config` olarak ayarlanarak ve ardından yeniden başlatılarak yapılabilir. Daha fazla ayrıntı için selinux'un erkek sayfasına bakın.
Şimdi 2. adımı kullanarak mdatp hizmetini yeniden başlatmayı deneyin. Yapılandırmayı denedikten ve yeniden başlattıktan sonra güvenlik nedenleriyle yapılandırma değişikliğini hemen geri alın.

5. Dizin sembolik bir bağlantıysa `/opt` , için `/opt/microsoft`bir bağlama bağlaması oluşturun.

6. Daemon'un yürütülebilir izinlere sahip olduğundan emin olun.

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    Daemon'un yürütülebilir izinleri yoksa şunu kullanarak yürütülebilir hale getirin:

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ve 2. adımı çalıştırmayı yeniden deneyin.

7. wdavdaemon içeren dosya sisteminin "noexec" ile bağlanmadığından emin olun.

## <a name="if-the-defender-for-endpoint-service-is-running-but-the-eicar-text-file-detection-doesnt-work"></a>Uç Nokta için Defender hizmeti çalışıyorsa ancak EICAR metin dosyası algılama çalışmıyorsa

1. Şunu kullanarak dosya sistemi türünü denetleyin:

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    Şu anda erişim etkinliği için desteklenen dosya sistemleri [burada](microsoft-defender-endpoint-linux.md#system-requirements) listelenmiştir. Bu dosya sistemlerinin dışındaki dosyalar taranmayacak.

## <a name="command-line-tool-mdatp-isnt-working"></a>Komut satırı aracı "mdatp" çalışmıyor

1. Komut satırı aracını `mdatp` çalıştırmak hata `command not found`veriyorsa, aşağıdaki komutu çalıştırın:

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    ögelerini seçip yeniden deneyin.

    Yukarıdaki adımlardan hiçbiri yardımcı olmazsa tanılama günlüklerini toplayın:

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    Günlükleri içeren bir zip dosyasının yolu çıkış olarak görüntülenir. Bu günlüklerle müşteri desteğimize ulaşın.
