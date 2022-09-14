---
title: İşletmenizde Microsoft Defender Virüsten Koruma'ya yönetme
description: Microsoft Defender Virüsten Koruma'yı yönetmek için grup ilkesi, Configuration Manager, PowerShell, WMI, Intune ve komut satırını kullanmayı öğrenin
keywords: grup ilkesi, gpo, yapılandırma yöneticisi, sccm, scep, powershell, wmi, intune, defender, virüsten koruma, kötü amaçlı yazılımdan koruma, güvenlik, koruma
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: c3b446989a6146245ceb9bbadb34cad1b3c5835e
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67679031"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a>İşletmenizde Microsoft Defender Virüsten Koruma'ya yönetme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

Microsoft Defender Virüsten Koruma'yi aşağıdaki araçlarla yönetebilir ve yapılandırabilirsiniz:

- [Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (artık Microsoft Endpoint Manager'nin bir parçası)
- [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (artık Microsoft Endpoint Manager'nin bir parçası)
- [Grup İlkesi](./use-group-policy-microsoft-defender-antivirus.md)
- [PowerShell cmdlet'leri](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Windows Yönetim Araçları (WMI)](./use-wmi-microsoft-defender-antivirus.md)
- [Microsoft Kötü Amaçlı Yazılımdan Koruma Komut Satırı Yardımcı Programı](./command-line-arguments-microsoft-defender-antivirus.md) (*mpcmdrun.exe* yardımcı programı olarak adlandırılır)

Aşağıdaki makaleler, Microsoft Defender Virüsten Koruma'yı yönetmek ve yapılandırmak için bu araçları kullanmaya yönelik daha fazla bilgi, bağlantı ve kaynak sağlar.

|Makale|Açıklama|
|:---|:---|
|[microsoft defender virüsten korumayı Microsoft Intune ve Microsoft Endpoint Configuration Manager ile yönetme](use-intune-config-manager-microsoft-defender-antivirus.md)|Microsoft Defender Virüsten Koruma'yı dağıtmak, yönetmek, raporlamak ve yapılandırmak için Intune ve Configuration Manager kullanma hakkında bilgi|
|[microsoft defender virüsten korumayı grup ilkesi ayarlarıyla yönetme](use-group-policy-microsoft-defender-antivirus.md)|ADMX şablonlarında bulunan tüm grup ilkesi ayarlarının listesi|
|[Microsoft Defender Virüsten Koruma'nın PowerShell cmdlet'lerini yönetme](use-powershell-cmdlets-microsoft-defender-antivirus.md)|Microsoft Defender Virüsten Koruma'yı yönetmek için PowerShell cmdlet'lerini kullanma yönergelerinin yanı sıra tüm cmdlet'ler ve izin verilen parametrelerin belgelerine bağlantılar|
|[Microsoft Defender Virüsten Koruma'yi Windows Yönetim Araçları ile Yönetme (WMI)](use-wmi-microsoft-defender-antivirus.md)|Microsoft Defender Virüsten Koruma'yı yönetmek için WMI kullanma yönergelerinin yanı sıra WMIv2 API'lerinin belgelerine bağlantılar (tüm sınıflar, yöntemler ve özellikler dahil)|
|[microsoft defender virüsten korumayı MpCmdRun.exe komut satırı aracıyla yönetme](command-line-arguments-microsoft-defender-antivirus.md)|Microsoft Defender Virüsten Koruma'yi yönetmek ve kullanmak için ayrılmış komut satırı aracını kullanma yönergeleri|

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)