---
title: Windows'da gelişmiş sorun giderme için veri toplama
description: Karmaşık sorun giderme senaryoları için veri toplamak için istemci çözümleyicisini kullanmayı öğrenin
keywords: analzyer, veri toplama, mdeclientanalyzer sorunlarını giderme, gelişmiş sorun giderme
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: conceptual
ms.subservice: m365d
ms.openlocfilehash: d85b44777098c4b013746e138fe1b057f7b0edb2
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479918"
---
# <a name="data-collection-for-advanced-troubleshooting-on-windows"></a>Windows'da gelişmiş sorun giderme için veri toplama

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft destek uzmanlarıyla işbirliği yaparken, daha karmaşık senaryolarda sorun giderme amacıyla veri toplamak için istemci çözümleyicisini kullanmanız istenebilir. Çözümleyici betiği bu amaç için diğer parametreleri destekler ve araştırılması gereken gözlemlenen belirtilere göre belirli bir günlük kümesini toplayabilir.

'**MDEClientAnalyzer.cmd /?**' komutunu çalıştırın kullanılabilir parametrelerin listesini ve açıklamalarını görmek için:

:::image type="content" source="images/d89a1c04cf8441e4df72005879871bd0.png" alt-text="MDEClientAnalyzer.cmd parametreleri" lightbox="images/d89a1c04cf8441e4df72005879871bd0.png":::

> [!NOTE]
> Gelişmiş sorun giderme parametreleri kullanıldığında çözümleyici, Microsoft Defender Virüsten Koruma ile ilgili destek günlüklerini toplamak için [MpCmdRun.exe](/microsoft-365/security/defender-endpoint/command-line-arguments-microsoft-defender-antivirus) da çağırır.

**-h** - Standart günlük kümesine ek olarak ayrıntılı bir genel performans izlemesi toplamak için [Windows Performans Kaydedicisi'ne](/windows-hardware/test/wpt/wpr-command-line-options) çağrılar.

**-l** - Basit bir perfmon izlemesi toplamak için yerleşik [Windows Performans İzleyicisi](/windows-server/remote/remote-desktop-services/rds-rdsh-performance-counters) çağrıları. Bu, zaman içinde ortaya çıkan ancak isteğe bağlı olarak yeniden üretilmesi zor olan yavaş performans düşüşü sorunlarını tanılarken yararlı olabilir.

**-c** - Gerçek zamanlı dosya sistemi, kayıt defteri ve işlem/iş parçacığı etkinliğinin gelişmiş izlenmesi için işlem [izleyicisine](/sysinternals/downloads/procmon) çağrılar. Bu, özellikle çeşitli uygulama uyumluluk senaryolarında sorun giderme sırasında kullanışlıdır.

**-i** - Ağla ilgili çeşitli sorunları giderirken yararlı olan bir ağ ve Windows güvenlik duvarı izlemesi başlatmak için yerleşik [netsh.exe](/windows/win32/winsock/netsh-exe) komutuna çağrılar.

**-b** - '-c' ile aynıdır, ancak işlem izleyicisi izlemesi sonraki önyükleme sırasında başlatılır ve yalnızca -b yeniden kullanıldığında durdurulur.

**-a** - Virüsten koruma işlemiyle ilgili yüksek CPU sorunlarının (MsMpEng.exe) analizine özgü ayrıntılı bir performans izlemesi toplamak için [Windows Performans Kaydedicisi'ne](/windows-hardware/test/wpt/wpr-command-line-options) çağrılar.

**-v** - Çoğu ayrıntılı -trace bayrağıyla virüsten koruma [MpCmdRun.exe komut satırı bağımsız değişkeni](/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus) kullanır.

**-t** - Uç Nokta DLP'sine uygun tüm istemci tarafı bileşenlerinin ayrıntılı izlemesini başlatır. Bu, dosyalar için [DLP eylemlerinin](/microsoft-365/compliance/endpoint-dlp-learn-about#endpoint-activities-you-can-monitor-and-take-action-on) beklendiği gibi gerçekleşmediği senaryolar için kullanışlıdır.

**-q** - Uç Nokta DLP'sinin temel yapılandırmasını ve gereksinimlerini doğrulayan çözümleyici 'Araçlar' dizininden DLPDiagnose.ps1 betiğine çağrılar.

**-d** - MsSense **S**.exe (Windows Server 2016 veya daha eski işletim sistemindeki algılayıcı işlemi) ve ilgili işlemlerin bellek dökümünü toplar.

- \* Bu bayrak yukarıda belirtilen bayraklarla birlikte kullanılabilir.
- \*\* MsSense.exe veya MsMpEng.exe gibi [PPL korumalı işlemlerin](/windows-hardware/drivers/install/early-launch-antimalware) bellek dökümünün yakalanması şu anda çözümleyici tarafından desteklenmiyor.

**-z** - [CrashOnCtrlScroll](/windows-hardware/drivers/debugger/forcing-a-system-crash-from-the-keyboard) aracılığıyla tam makine bellek dökümü toplamaya hazırlamak için makinedeki kayıt defteri anahtarlarını yapılandırır. Bu, bilgisayar donması sorunlarının analizi için yararlı olabilir.

\* En sağdaki CTRL tuşunu basılı tutun, ardından SCROLL LOCK tuşuna iki kez basın.

**-k** - Sistemi kilitlenmeye zorlamak ve bir makine bellek dökümü oluşturmak için [NotMyFault](/sysinternals/downloads/notmyfault) aracını kullanır. Bu, çeşitli işletim sistemi kararlılığı sorunlarının analizi için yararlı olabilir.

Çözümleyici ve yukarıdaki tüm senaryo bayrakları, çözümleyici araç kümesine de paketlenmiş olan 'RemoteMDEClientAnalyzer.cmd' çalıştırılarak uzaktan başlatılabilir:

:::image type="content" source="images/57cab9d82d08f672a92bf9e748ac9572.png" alt-text="RemoteMDEClientAnalyzer.cmd parametreleri" lightbox="images/57cab9d82d08f672a92bf9e748ac9572.png":::

> [!NOTE]
>
> - RemoteMDEClientAnalyzer.cmd kullanırken aracı yapılandırılmış dosya paylaşımından indirmek ve ardından PsExec.exe aracılığıyla yerel olarak çalıştırmak için psexec'e çağrır.
    CMD betiği, SISTEM bağlamında uzaktan çalıştığını belirtmek için '-r' bayrağını kullanır ve bu nedenle kullanıcıya hiçbir istem sunulmaz.
> - Aynı bayrak, kullanıcıya veri toplama için dakika sayısını belirtme isteğinde bulunan bir istemden kaçınmak için MDEClientAnalyzer.cmd ile kullanılabilir. Örneğin:
>
>    **MDEClientAnalyzer.cmd -r -i -m 5**
>
>   - **-r** - Aracın uzak (veya etkileşimli olmayan bağlamdan) çalıştırıldığını gösterir
>   - **-i** - Diğer ilgili günlüklerle birlikte ağ izlemesinin toplanması için senaryo bayrağı
>   - **-m** \# - Çalıştırılacak dakika sayısı (yukarıdaki örnekte 5 dakika)
