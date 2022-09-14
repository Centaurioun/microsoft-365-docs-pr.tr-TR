---
title: PowerShell kullanarak virüsten koruma taramaları zamanlama
description: PowerShell kullanarak virüsten koruma taramaları zamanlama
keywords: hızlı tarama, tam tarama, virüsten koruma, zamanlama, PowerShell
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
ms.openlocfilehash: cdf9d45848cb2510b704d2933e86768682458466
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67687691"
---
# <a name="schedule-antivirus-scans-using-powershell"></a>PowerShell kullanarak virüsten koruma taramaları zamanlama

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

Bu makalede, PowerShell cmdlet'lerini kullanarak zamanlanmış taramaların nasıl yapılandırıldığı açıklanır. Taramaları zamanlama ve tarama türleri hakkında daha fazla bilgi edinmek için bkz [. Zamanlanmış hızlı veya tam Microsoft Defender Virüsten Koruma taramalarını yapılandırma](schedule-antivirus-scans.md). 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a>Taramaları zamanlamak için PowerShell cmdlet'lerini kullanma

Aşağıdaki cmdlet'leri kullanın:

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Daha fazla bilgi için Bkz. [Microsoft Defender Virüsten Koruma ve Defender Virüsten Koruma cmdlet'lerini yapılandırmak ve çalıştırmak](use-powershell-cmdlets-microsoft-defender-antivirus.md) için PowerShell [cmdlet'lerini kullanma Microsoft Defender Virüsten Koruma](/powershell/module/defender/) ile PowerShell'i kullanma.

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>Bir uç nokta kullanımda olmadığında taramaları zamanlamak için PowerShell cmdlet'leri

Aşağıdaki cmdlet'leri kullanın:

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

Daha fazla bilgi için bkz. [Microsoft Defender Virüsten Koruma ve Defender Virüsten Koruma cmdlet'lerini yapılandırmak ve çalıştırmak için PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) [cmdlet'lerini](/powershell/module/defender/) kullanma.

> [!NOTE]
> Uç noktaların kullanımda olmadığı zamanlar için taramalar zamanladığınızda, taramalar CPU azaltma yapılandırmasına uygun değildir ve taramayı mümkün olan en hızlı şekilde tamamlamak için kullanılabilir kaynaklardan tam olarak yararlanır.

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a>Düzeltmeyi tamamlamak için taramaları zamanlamak için PowerShell cmdlet'leri

Aşağıdaki cmdlet'leri kullanın:

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

[PowerShell'i Microsoft Defender Virüsten Koruma ile](use-powershell-cmdlets-microsoft-defender-antivirus.md) kullanma hakkında daha fazla bilgi için bkz. Microsoft Defender [Virüsten Koruma ve Defender Virüsten Koruma cmdlet'lerini](/powershell/module/defender/) yapılandırmak ve çalıştırmak için PowerShell cmdlet'lerini kullanma.

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a>Günlük taramaları zamanlamak için PowerShell cmdlet'leri

Aşağıdaki cmdlet'leri kullanın:

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

PowerShell'i Microsoft Defender Virüsten Koruma ile kullanma hakkında daha fazla bilgi için bkz. [Microsoft Defender Virüsten Koruma ve Defender Virüsten Koruma cmdlet'lerini yapılandırmak ve çalıştırmak için PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) [cmdlet'lerini](/powershell/module/defender/) kullanma.

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)