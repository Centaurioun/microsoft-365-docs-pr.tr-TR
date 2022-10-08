---
title: Microsoft Defender Virüsten Koruma’yı dağıtın ve etkinleştirin
description: Microsoft Intune, Microsoft Endpoint Configuration Manager, grup ilkesi, PowerShell cmdlet'leri veya WMI ile uç noktalarınızın korunması için Microsoft Defender Virüsten Koruma'yı dağıtın.
keywords: virüsten korumayı dağıtma, etkinleştirme Microsoft Defender
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: a11ac1c31a283b2dda4ad64e6bcd6d9ce38b592a
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68198921"
---
# <a name="deploy-and-enable-microsoft-defender-antivirus"></a>Microsoft Defender Virüsten Koruma’yı dağıtın ve etkinleştirin

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

Kullandığınız yönetim aracına bağlı olarak, Microsoft Defender Virüsten Koruma'yı özel olarak etkinleştirmeniz veya yapılandırmanız gerekebilir. 

Microsoft Intune, Microsoft Endpoint Configuration Manager ile korumayı etkinleştirme yönergeleri için [Microsoft Defender Virüsten Koruma'yı dağıtma, yönetme ve raporlama](deploy-manage-report-microsoft-defender-antivirus.md#ref2) sayfasındaki tabloya bakın grup ilkesi , Active Directory, Microsoft Azure, PowerShell cmdlet'leri ve Windows Yönetim Yönergesi (WMI).

Bazı senaryolar, Sanal Masaüstü Altyapısı (VDI) ortamları gibi Microsoft Defender Virüsten Koruma'yı başarıyla dağıtma veya yapılandırma konusunda daha fazla kılavuz gerektirir.

Bu bölümdeki diğer makale, [VDI veya Uzak Masaüstü Hizmetleri (RDS) ortamında sanal makinelerde (VM) Microsoft Defender Virüsten Koruma'nın ayarlanmasına](deployment-vdi-microsoft-defender-antivirus.md) yönelik uçtan uca öneriler ve en iyi yöntemler sağlar.

## <a name="related-articles"></a>İlgili makaleler

- [Windows 10'de virüsten koruma Microsoft Defender](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Virüsten Koruma'da güncelleştirmeleri dağıtma, yönetme ve raporlama](deploy-manage-report-microsoft-defender-antivirus.md)
- [Sanal Masaüstü Altyapısı (VDI) ortamında Microsoft Defender Virüsten Koruma için dağıtım klavuzu](deployment-vdi-microsoft-defender-antivirus.md)

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)