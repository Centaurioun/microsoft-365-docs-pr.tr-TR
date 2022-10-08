---
title: Linux'ta Uç Nokta için Microsoft Defender'da Anacron kullanarak virüsten koruma taraması zamanlama
description: Kuruluşunuzun varlıklarının daha iyi korunması için Linux'ta Uç Nokta için Microsoft Defender virüsten koruma taraması zamanlamayı öğrenin.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, linux, scans, virüsten koruma, linux üzerinde uç nokta için microsoft defender
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
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: ad13d3e403f3fad81bec275506017f2da4066737
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68223930"
---
# <a name="schedule-an-antivirus-scan-using-anacron-in-microsoft-defender-for-endpoint-on-linux"></a>Linux'ta Uç Nokta için Microsoft Defender'da Anacron kullanarak virüsten koruma taraması zamanlama

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)


Linux için Microsoft Defender Virüsten Koruma taramasını çalıştırmak için bkz. [Desteklenen Komutlar](/microsoft-365/security/defender-endpoint/linux-resources#supported-commands).

> [!NOTE]
> Bu makale, Red Hat Enterprise Linux dağıtımları (RHEL) için Linux'ta Uç Nokta için Microsoft Defender destekler.

## <a name="system-requirements"></a>Sistem gereksinimleri

Linux'ta Microsoft Defender Uç Noktası'nda Microsoft Defender Virüsten Koruma taraması zamanlamak için gereken aşağıdaki sistem gereksinimlerine bakın.

- Linux sunucu dağıtımları ve sürümleri: Red Hat Enterprise Linux 7.2 veya üzeri.
- Çekirdekteki **FANOTIFY** seçeneğinin etkinleştirilmesi gerekir.

## <a name="scheduling-microsoft-defender-antivirus-scan-in-red-hat-linux"></a>Red Hat Linux'ta Microsoft Defender Virüsten Koruma taraması zamanlama

Microsoft Defender Virüsten Koruma taramalarını bir zamanlamaya göre başlatmak için cron işleri zamanlayabilirsiniz. Daha fazla bilgi için bkz. [Linux'ta Uç Nokta için Microsoft Defender ile tarama zamanlama](linux-schedule-scan-mde.md). Cihaz her zaman çalışır durumdaysa bu işlem iyi çalışır. 

Ancak cron zamanlaması sırasında Linux cihazları kapatılırsa veya çevrimdışı olursa tarama çalışmaz. Bu gibi durumlarda, zaman damgasını okumak ve son yürütülen işi bulmak için **anacron** kullanabilirsiniz. Cihaz zamanlanan cron işi sırasında kapatıldıysa, bir sonraki zamanlanan saate kadar beklemesi gerekir. Sistem **, anacron** kullanarak taramanın en son ne zaman çalıştırıldığını algılar. Cihaz cron işini çalıştırmadıysa otomatik olarak başlatır. 

### <a name="schedule-microsoft-defender-antivirus-scans-in-red-hat-linux"></a>Red Hat Linux'ta Microsoft Defender Virüsten Koruma taramalarını zamanlama

Taramaları zamanlamak için aşağıdaki adımları kullanın:

1. Putty kullanarak RedHat sunucusuna bağlanın.
1. Anacron dosyasını düzenleyin: 

    ```vi /etc/anacron```

    :::image type="content" source="images/vi_etc_anacron.png" alt-text="anacron dosyası":::

    ```
    # /etc/anacrontab: configuration file for anacron
    # See anacron (8) and anacrontab (5) for details.
    SHELL=/bin/sh
    PATH=/sbin:/bin:/usr/sbin:/usr/bin
    RANDOM_DELAY=45
    # Anacron jobs will start between 8pm and 11pm.
    START_HOURS_RANGE=20-23
    # delay will be 5 minutes + RANDOM_DELAY for cron.daily
    ```

1. Dosyada aşağıdaki öğelere dikkat edin.
    1. **Kabuk:** Kabuk olarak değil olarak ```/bin/bash```adlandırılır```/bin/sh```. İşleri yazarken unutmayın.
    1. **RANDOM_DELAY:** İş için dakika cinsinden en uzun süreyi açıklar. Bu değer, aynı anda çalışan çok fazla iş olmaması için işleri dengelemek için kullanılır. Bu gecikmeyi kullanmak VDI çözümleri için idealdir.
    1. **START_HOURS_RANGE:** İşin çalıştırıldığı zaman aralığını açıklar.
    1. **cron.daily:** 1'i, iş yürütme sıklığı için gereken gün sayısı olarak tanımlar. 5, anacron'un cihaz yeniden başlatıldıktan sonra beklediği dakika cinsinden gecikmedir.

1. Anacron işlerini gözden geçirin:

    ```ls -lh /etc/cron*```

    :::image type="content" source="images/ls_lh_etc_cron.png" alt-text="anacron işleri":::

    ```
    [root@enaredhat7 /] # 1s -1h /etc/cron*
    - rw - - - - - - -. 1   root    root    0   Nov 30  2021    /etc/cron.deny
    - rw - r - - r - -. 1   root    root    451 Dec 27  2013    /etc/crontab

    /etc/cron.d:
    total 28k
    - rw - r - - r - -. 1   root    root    128 Nov 30  2021    0hourly
    - rw - r - - r - -. 1   root    root    121 Feb 25  18:11   omilogotate
    - rw - r - - r - -. 1   root    root    118 Feb 25  18:14   omsagent
    - rw - r - - r - -. 1   root    root    79  Feb 25  18:15   OMSConsistencyInvoker
    - rw - r - - r - -. 1   root    root    108 Nov 9   2021    raid-check
    - rw - r - - r - -. 1   root    root    135 Jun 1   22:35   scxagent
    - rw - - - - - - -. 1   root    root    235 Jan 20  2020    sysstat

    /etc/cron.daily:
    total 24k
    - rwxr - xr - x.    1   root    root    127 Jun 14  16:49   avscandaily
    - rwx - - - - - -.  1   root    root    219 Aug 7   2019    logrotate
    - rwxr - xr - x.    1   root    root    618 Jul 10  2018    man-db.cron
    - rwx - - - - - -.  1   root    root    208 Nov 9   2017    mlocate
    - rwx - - - - - -.  1   root    root    558 Apr 18  19:03   rhsmd
    - rwxr - xr - x.    1   root    root    114 Apr 8   2021    rhui-update-client

    /etc/cron.hourly:
    total 8.0k
    - rwxr - xr - x.    1   root    root    392 Nov 30  2021    0anacron
    - rwxr - xr - x.    1   root    root    131 Jun 14  17:05   update

    /etc/cron.monthly:
    total 0
    - rwxr - xr - x.    1   root    root    0   Jun 14  17:47   mdatpupdate
    
    /etc/cron.weekly:
    total 0
    ```

1. Dizinini ```/etc/cron.d``` yoksaydığınızda görürsünüz ```/etc/corn.daily, hourly, monthly, and weekly```. 

1. Haftalık virüsten koruma taraması zamanlamak için dizinin altında ```/etc/cron.weekly``` bir dosya (İş) oluşturabilirsiniz.

    ```cd /etc/cron.weekly```

   ``` vi mdavfullscan```

    ```Press Insert```
    
    :::image type="content" source="images/vi_mdavfullscan.png" alt-text="haftalık virüsten koruma taramaları":::

   ```
    #!/bin/sh
    set -e
    echo    $(date)     “Time Scan Begins”  >>/logs/mdav_avacron_full_scan.log
    /bin/mdatp scan full >> /logs/mdav_avacron_full_scan.log
    echo    $(date) “Time Scan Finished”        >>/logs/mdav_avacron_full_scan.log
    exit    0
    ~
    ```

    ```Press Esc```

    ```Type: wq!```

1. Dosyanın yürütülmesine izin vermek için dosya izinlerini değiştirin.

    ```Chmod 755 mdavfullscan```

    ```ls -la```

    :::image type="content" source="images/chmod-755-mdavfullscan.png" alt-text="7. Dosya izinlerini değiştirme":::

    ```
    [root@enaredhat7    cron.weekly]# 1s -1a
    total   16
    drwxr - xr – x. 2   root    root    26  Jun 14  19:19   .
    drwxr - xr – x. 85  root    root    8192    Jun 14  19:01   ..
    - rw - r - - r - -. 1   root    root    128 Jun 14  19:19   mdavfullscan
    [root@enaredhat7 cron.weekly] # chmod 755 mdavfullscan
    [root@enaredhat7 cron.weekly] # 1s  -1h
    total 4. 0k
    - rwxr - xr – x.    1   root    root    128 Jun 14  19:19   mdavfullscan
    [root@enaredhat7 cron.weekly] #
    ```

1. Haftalık anacron işini test etmek için komutunu kullanın.
    
    ```./mdavfullscan```

1. İşin başarıyla çalıştığını doğrulamak için komutunu kullanın.

    ```cat /logs/mdav_avacron_full_scan.log```

    :::image type="content" source="images/mdav_avacron_full_scan_log.png" alt-text="işin çalıştırdığını doğrulama":::

    ```
    [root@enaredhat7    cron.weekly] # cat  / logs / mdav_avacron_full_scan.log
    Tue Jun 14  20:20:44    UTC 2022 Time Scan Begins
    Scan has finished
        66547   file(s) scanned
    0   threat(s) detected
    Tue Jun 14  20:20:50    UTC 2022 Time Scan Finished
    [root@enaredhat7 cron.weekly] #
    ```
