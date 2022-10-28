---
title: macOS'ta Uç Nokta için Microsoft Defender ile tarama zamanlama
description: Kuruluşunuzun varlıklarını daha iyi korumak için macOS'ta Uç Nokta için Microsoft Defender için otomatik tarama süresi zamanlamayı öğrenin.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, mac, scans, virüsten koruma, catalina, big sur, monterey, ventura, mac için mde
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
ms.openlocfilehash: 791288321d6968d63ba551e0872491a773ce53d4
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2022
ms.locfileid: "68769391"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>macOS'ta Uç Nokta için Microsoft Defender ile tarama zamanlama

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Uç Nokta için Microsoft Defender ile istediğiniz zaman bir tehdit taraması başlatabilirsiniz ancak kuruluşunuz zamanlanmış veya zamanlanmış taramalardan yararlanabilir. Örneğin, her iş günü veya haftanın başında çalışacak bir tarama zamanlayabilirsiniz. 

## <a name="schedule-a-scan-with-launchd"></a>*Başlatılan* bir tarama zamanlama

Bir macOS cihazında *başlatılan* daemon'u kullanarak bir tarama zamanlaması oluşturabilirsiniz.

Burada kullanılan *.plist* dosya biçimi hakkında daha fazla bilgi için, resmi Apple geliştirici web sitesindeki [Bilgi Özellik Listesi Dosyaları Hakkında](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) bölümüne bakın.

### <a name="schedule-a-quick-scan"></a>Hızlı tarama zamanlama

Aşağıdaki kod, hızlı tarama zamanlamak için kullanmanız gereken şemayı gösterir. 

1. Bir metin düzenleyicisi açın ve bu örneği kendi zamanlanmış tarama dosyanız için kılavuz olarak kullanın.

    ```XML
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
      "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>Label</key>
        <string>com.microsoft.wdav.schedquickscan</string>
        <key>ProgramArguments</key>
        <array>
            <string>sh</string>
            <string>-c</string>
            <string>/usr/local/bin/mdatp scan quick</string>
        </array>
        <key>RunAtLoad</key>
        <true/>
        <key>StartCalendarInterval</key>
        <dict>
            <key>Day</key>
            <integer>3</integer>
            <key>Hour</key>
            <integer>2</integer>
            <key>Minute</key>
            <integer>0</integer>
            <key>Weekday</key>
            <integer>5</integer>
        </dict>
        <key>WorkingDirectory</key>
        <string>/usr/local/bin/</string>
    </dict>
    </plist>
     ```

2. Dosyayı *com.microsoft.wdav.schedquickscan.plist* olarak kaydedin.

### <a name="schedule-a-full-scan"></a>Tam tarama zamanlama

1. Bir metin düzenleyicisi açın ve tam tarama için bu örneği kullanın.

    ```XML
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
      "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>Label</key>
        <string>com.microsoft.wdav.schedfullscan</string>
        <key>ProgramArguments</key>
        <array>
            <string>sh</string>
            <string>-c</string>
            <string>/usr/local/bin/mdatp scan full</string>
        </array>
        <key>RunAtLoad</key>
        <true/>
        <key>StartCalendarInterval</key>
        <dict>
            <key>Day</key>
            <integer>3</integer>
            <key>Hour</key>
            <integer>2</integer>
            <key>Minute</key>
            <integer>50</integer>
            <key>Weekday</key>
            <integer>5</integer>
        </dict>
        <key>WorkingDirectory</key>
        <string>/usr/local/bin/</string>
    </dict>
    </plist>
     ```

2. Dosyayı *com.microsoft.wdav.schedfullscan.plist* olarak kaydedin.
 
### <a name="load-your-file"></a>Dosyanızı yükleme

1. **Terminal'i** açın.
2. Dosyanızı yüklemek için aşağıdaki komutları girin:

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

3. Zamanlanmış taramanız, p listenizde tanımladığınız tarih, saat ve sıklıkta çalışır. Önceki örneklerde tarama her Cuma 02:50'de çalıştırılır. 

    - değeri`StartCalendarInterval`, `Weekday` haftanın beşinci gününü veya Cuma gününü belirtmek için bir tamsayı kullanır. Aralık 0 ile 7 arasında, 7 ise Pazar'ı temsil ediyor.
    - değeri`StartCalendarInterval`, `Day` ayın üçüncü gününü belirtmek için bir tamsayı kullanır. Aralık 1 ile 31 arasındadır.
    - değeri`StartCalendarInterval`, `Hour` günün ikinci saatini belirtmek için bir tamsayı kullanır. Aralık 0 ile 24 arasındadır.
    değeri`StartCalendarInterval`, `Minute` saatin elli dakikasını belirtmek için bir tamsayı kullanır. Aralık 0 ile 59 arasındadır.
    
    
 > [!IMPORTANT]
 > *Başlatılan* aracılarla yürütülen aracılar, cihaz uykudayken zamanlanan zamanda çalışmaz. Bunun yerine cihaz uyku modundan devam ettikten sonra çalışır.
 >
 > Cihaz kapalıysa, tarama bir sonraki zamanlanmış tarama zamanında çalışır.

## <a name="schedule-a-scan-with-intune"></a>Intune ile tarama zamanlama

Taramaları Microsoft Intune ile de zamanlayabilirsiniz. [Uç Nokta için Microsoft Defender](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) [için Betikler'de bulunan runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) kabuk betiği, cihaz uyku modundan devam ettiğinde kalıcı olur. 

Kuruluşunuzda bu betiği kullanma hakkında daha ayrıntılı yönergeler için bkz. [Intune macOS cihazlarında kabuk betiklerini](/mem/intune/apps/macos-shell-scripts) kullanma.
