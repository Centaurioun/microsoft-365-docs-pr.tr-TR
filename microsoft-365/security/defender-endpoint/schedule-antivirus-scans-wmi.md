---
title: Windows Yönetim Araçları'nı kullanarak virüsten koruma taramaları zamanlama
description: WMI kullanarak virüsten koruma taramaları zamanlama
keywords: hızlı tarama, tam tarama, WMI, zamanlama, virüsten koruma
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.subservice: mde
ms.topic: how-to
ms.collection: M365-security-compliance
search.appverid: met150
ms.openlocfilehash: 19612e81aad9b7437b677e6d48a0a2a05d48f83e
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67686625"
---
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a>Windows Yönetim Araçları'nı (WMI) kullanarak virüsten koruma taramaları zamanlama

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

Bu makalede WMI kullanılarak zamanlanmış taramaların nasıl yapılandırıldığı açıklanır. Taramaları zamanlama ve tarama türleri hakkında daha fazla bilgi edinmek için bkz [. Zamanlanmış hızlı veya tam Microsoft Defender Virüsten Koruma taramalarını yapılandırma](schedule-antivirus-scans.md). 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Taramaları zamanlamak için Windows Yönetim Yönergesi'ni (WMI) kullanma

Aşağıdaki özellikler için [**MSFT_MpPreference** sınıfının **Set** yöntemini](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) kullanın:

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

Daha fazla bilgi ve izin verilen parametreler için bkz. [Windows Defender WMIv2 API'leri](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>Bir uç nokta kullanımda olmadığında taramaları zamanlamak için WMI

Aşağıdaki özellikler için [MSFT_MpPreference sınıfının Set yöntemini](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) kullanın:

```WMI
ScanOnlyIfIdleEnabled
```

API'ler ve izin verilen parametreler hakkında daha fazla bilgi için bkz. [WMIv2 API'lerini Windows Defender](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

> [!NOTE]
> Uç noktaların kullanımda olmadığı zamanlar için taramalar zamanladığınızda, taramalar CPU azaltma yapılandırmasına uygun değildir ve taramayı mümkün olan en hızlı şekilde tamamlamak için kullanılabilir kaynaklardan tam olarak yararlanır.


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a>Düzeltmeyi tamamlamak için taramaları zamanlamak için WMI

Aşağıdaki özellikler için [**MSFT_MpPreference** sınıfının **Set** yöntemini](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) kullanın:

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

Daha fazla bilgi ve izin verilen parametreler için bkz. [Windows Defender WMIv2 API'leri](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

## <a name="wmi-for-scheduling-daily-scans"></a>Günlük taramaları zamanlamak için WMI

Aşağıdaki özellikler için [**MSFT_MpPreference** sınıfının **Set** yöntemini](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) kullanın:

```WMI
ScanScheduleQuickScanTime
```

Daha fazla bilgi ve izin verilen parametreler için bkz. [Windows Defender WMIv2 API'leri](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)