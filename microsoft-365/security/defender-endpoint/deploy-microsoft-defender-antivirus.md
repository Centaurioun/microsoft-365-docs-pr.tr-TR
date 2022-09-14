---
title: Microsoft Defender Virüsten Koruma’yı dağıtın ve etkinleştirin
description: Microsoft Intune, Microsoft Endpoint Configuration Manager, grup ilkesi, PowerShell cmdlet'leri veya WMI ile uç noktalarınızın korunması için Microsoft Defender Virüsten Koruma'yı dağıtın.
keywords: dağıtma, etkinleştirme, Microsoft Defender Virüsten Koruma
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
ms.collection: m365-security-compliance
ms.openlocfilehash: 8c8bef490889bd21cd526e9dd46c40ae53b7d289
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67680031"
---
# <a name="deploy-and-enable-microsoft-defender-antivirus"></a>Microsoft Defender Virüsten Koruma’yı dağıtın ve etkinleştirin

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

Kullandığınız yönetim aracına bağlı olarak, Microsoft Defender Virüsten Koruma korumasını özel olarak etkinleştirmeniz veya yapılandırmanız gerekebilir. 

Microsoft Intune, Microsoft Endpoint Configuration Manager, grup ilkesi, Active Directory, Microsoft Azure, PowerShell cmdlet'leri ve Windows Yönetim Yönergeleri (WMI) ile korumayı etkinleştirme yönergeleri için Microsoft [Defender Virüsten Koruma'yı dağıtma, yönetme ve raporlama](deploy-manage-report-microsoft-defender-antivirus.md#ref2) başlığı altında yer alan tabloya bakın.

Bazı senaryolar, Sanal Masaüstü Altyapısı (VDI) ortamları gibi Microsoft Defender Virüsten Koruma korumasını başarıyla dağıtma veya yapılandırma konusunda daha fazla kılavuz gerektirir.

Bu bölümdeki kalan makale, [VDI veya Uzak Masaüstü Hizmetleri (RDS) ortamındaki sanal makinelerde (VM) Microsoft Defender Virüsten Koruma'nın ayarlanması](deployment-vdi-microsoft-defender-antivirus.md) için uçtan uca öneriler ve en iyi yöntemler sağlar.

## <a name="related-articles"></a>İlgili makaleler

- [Windows 10'da Microsoft Defender Virüsten Koruma](microsoft-defender-antivirus-in-windows-10.md)
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