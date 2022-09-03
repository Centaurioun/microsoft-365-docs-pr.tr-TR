---
title: Microsoft Defender Virüsten Koruma'nın yapılandırılması ve çalıştırılması için PowerShell cmdlet'lerini kullanma
description: Windows 10 ve Windows 11'da Taramalar çalıştırmak, Güvenlik zekasını güncelleştirmek ve Microsoft Defender Virüsten Koruma'da ayarları değiştirmek için PowerShell cmdlet'lerini kullanabilirsiniz.
keywords: tarama, komut satırı, mpcmdrun, defender
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2020
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: bb63bb3ec898e7ba6f7b957288e95da7ec49f17c
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67585894"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a>Microsoft Defender Virüsten Koruma'nın yapılandırılması ve yönetilmesi için PowerShell cmdlet'lerini kullanma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

PowerShell'i kullanarak Windows Defender'da çeşitli işlevler gerçekleştirebilirsiniz. Komut istemine veya komut satırına benzer şekilde PowerShell, özellikle sistem yönetimi için tasarlanmış görev tabanlı bir komut satırı kabuğu ve betik dilidir. Msdn'deki [PowerShell hub'ında](/previous-versions/msdn10/mt173057(v=msdn.10)) bu konuda daha fazla bilgi edinebilirsiniz.

Cmdlet'lerin, işlevlerinin ve kullanılabilir parametrelerin listesi için [Defender Virüsten Koruma cmdlet'leri](/powershell/module/defender) konusuna bakın.

PowerShell cmdlet'leri en çok, yazılımı yapılandırmak için grafik kullanıcı arabirimine (GUI) güvenmeyen Windows Server ortamlarında kullanışlıdır.

> [!NOTE]
> PowerShell cmdlet'leri [Microsoft Endpoint Configuration Manager, grup ilkesi](/configmgr) [Yönetim Konsolu](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) veya [Microsoft Defender Virüsten Koruma grup ilkesi ADMX şablonları](https://www.microsoft.com/download/101445) gibi tam ağ ilkesi yönetim altyapısının yerine kullanılmamalıdır.

PowerShell ile yapılan değişiklikler, değişikliklerin dağıtıldığı veya yapıldığı uç noktadaki yerel ayarları etkiler. Bu, grup ilkesi, Microsoft Endpoint Configuration Manager veya Microsoft Intune ile ilke dağıtımlarının PowerShell ile yapılan değişikliklerin üzerine yazabileceği anlamına gelir.

[Yerel ilke geçersiz kılmaları ile hangi ayarların yerel olarak geçersiz kılınabileceğini yapılandırabilirsiniz](configure-local-policy-overrides-microsoft-defender-antivirus.md).

PowerShell genellikle klasörünün `%SystemRoot%\system32\WindowsPowerShell`altına yüklenir.

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a>Microsoft Defender Virüsten Koruma PowerShell cmdlet'lerini kullanma

1. Windows arama çubuğuna **powershell** yazın.
2. Arabirimi açmak için sonuçlardan **Windows PowerShell** seçin.
3. PowerShell komutunu ve tüm parametreleri girin.

> [!NOTE]
> PowerShell'i yönetici modunda açmanız gerekebilir. Başlat menüsünde öğeye sağ tıklayın, **Yönetici olarak çalıştır'a** tıklayın ve izin isteminde **Evet'e** tıklayın.

Cmdlet'lerden herhangi biri için çevrimiçi yardım açmak için aşağıdakileri yazın:

```PowerShell
Get-Help <cmdlet> -Online
```

Yerel olarak önbelleğe `-online` alınmış yardım almak için parametresini atlar.

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
- [Microsoft Defender Virüsten Koruma Cmdlet'leri](/powershell/module/defender)
