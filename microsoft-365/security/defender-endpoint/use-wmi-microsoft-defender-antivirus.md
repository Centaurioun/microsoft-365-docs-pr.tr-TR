---
title: Microsoft Defender Virüsten Koruma'yi WMI ile yapılandırma
description: Uç Nokta için Microsoft Defender'da ayarları almak, değiştirmek ve güncelleştirmek için WMI betiklerini kullanarak Microsoft Defender Virüsten Koruma'yı yapılandırmayı ve yönetmeyi öğrenin.
keywords: wmi, betikler, windows yönetim araçları, yapılandırma
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2018
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: 9d18838f64d693caba643c0939a21abb66b2a284
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67577507"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a>Microsoft Defender Virüsten Koruma'nın yapılandırılması ve yönetilmesi için Windows Yönetim Araçları'nın (WMI) kullanılması

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

Windows Yönetim Araçları (WMI), ayarları almanıza, değiştirmenize ve güncelleştirmenize olanak tanıyan bir betik arabirimidir.

WMI hakkında daha fazla bilgi için [Bkz. Microsoft Developer Network System Administration library](/windows/win32/wmisdk/wmi-start-page).

Microsoft Defender Virüsten Koruma, grup ilkesi ve diğer yönetim araçlarıyla aynı işlevlerin çoğunu gerçekleştirmek için kullanılabilecek bir dizi belirli WMI sınıfına sahiptir. Sınıfların çoğu [Bulut için Defender PowerShell cmdlet'lerine](use-powershell-cmdlets-microsoft-defender-antivirus.md) benzer.

[MSDN Windows Defender WMIv2 Sağlayıcısı başvuru kitaplığı](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal), Microsoft Defender Virüsten Koruma için kullanılabilir WMI sınıflarını listeler ve örnek betikler içerir.

WMI ile yapılan değişiklikler, değişikliklerin dağıtıldığı veya yapıldığı uç noktadaki yerel ayarları etkiler. Bu, grup ilkesi, Microsoft Endpoint Configuration Manager veya Microsoft Intune ile ilke dağıtımlarının WMI ile yapılan değişikliklerin üzerine yazabileceği anlamına gelir. 

[Yerel ilke geçersiz kılmaları ile hangi ayarların yerel olarak geçersiz kılınabileceğini yapılandırabilirsiniz](configure-local-policy-overrides-microsoft-defender-antivirus.md).

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)

## <a name="related-topics"></a>İlgili konular

- [Yönetim ve yapılandırma araçları için başvuru konuları](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10'da Microsoft Defender Virüsten Koruma](microsoft-defender-antivirus-in-windows-10.md)
