---
title: İşletmenizde Microsoft Defender Virüsten Koruma'ları yönetme
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
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: dcf6baf8c2c161d5b8390ef62f08307daa3f7715
ms.sourcegitcommit: b9282493c371d59c2e583b9803825096499b5e2c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68151573"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a>İşletmenizde Microsoft Defender Virüsten Koruma'ları yönetme

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

Aşağıdaki makaleler, virüsten koruma Microsoft Defender yönetmek ve yapılandırmak için bu araçları kullanmaya yönelik daha fazla bilgi, bağlantı ve kaynak sağlar.

|Makale|Açıklama|
|:---|:---|
|[Microsoft Intune ve Microsoft Endpoint Configuration Manager ile Microsoft Defender Virüsten Koruma'ı yönetme](use-intune-config-manager-microsoft-defender-antivirus.md)|Microsoft Defender Virüsten Koruma'yı dağıtmak, yönetmek, raporlamak ve yapılandırmak için Intune ve Configuration Manager kullanma hakkında bilgi|
|[Microsoft Defender Virüsten Koruma'grup ilkesi ayarlarıyla yönetme](use-group-policy-microsoft-defender-antivirus.md)|ADMX şablonlarında bulunan tüm grup ilkesi ayarlarının listesi|
|[PowerShell cmdlet'leriyle Microsoft Defender Virüsten Koruma'ya yönetme](use-powershell-cmdlets-microsoft-defender-antivirus.md)|Microsoft Defender Virüsten Koruma'yı yönetmek için PowerShell cmdlet'lerini kullanma yönergelerinin yanı sıra tüm cmdlet'ler ve izin verilen parametrelerin belgelerine bağlantılar|
|[Windows Yönetim Araçları (WMI) ile Microsoft Defender Virüsten Koruma'yi yönetme](use-wmi-microsoft-defender-antivirus.md)|Microsoft Defender Virüsten Koruma'yı yönetmek için WMI kullanma yönergelerinin yanı sıra WMIv2 API'lerinin belgelerine bağlantılar (tüm sınıflar, yöntemler ve özellikler dahil)|
|[MpCmdRun.exe komut satırı aracıyla Microsoft Defender Virüsten Koruma'yi yönetme](command-line-arguments-microsoft-defender-antivirus.md)|Microsoft Defender Virüsten Koruma'Microsoft Defender yönetmek ve kullanmak için ayrılmış komut satırı aracını kullanma yönergeleri|

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)