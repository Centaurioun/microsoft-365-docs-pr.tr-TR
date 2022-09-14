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
ms.date: 09/06/2022
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
search.appverid: met150
ms.openlocfilehash: 6214a8bdfd3f2d5e3fcd05ac06bc99699bf4b7a8
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67691529"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a>Microsoft Defender Virüsten Koruma'nın yapılandırılması ve yönetilmesi için PowerShell cmdlet'lerini kullanma

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

PowerShell'i kullanarak Windows Defender'da çeşitli işlevler gerçekleştirebilirsiniz. Komut istemine veya komut satırına benzer şekilde PowerShell, özellikle sistem yönetimi için tasarlanmış görev tabanlı bir komut satırı kabuğu ve betik dilidir. [PowerShell belgelerinde](/powershell/scripting/overview) bu konuda daha fazla bilgi edinebilirsiniz.

Cmdlet'lerin, işlevlerinin ve kullanılabilir parametrelerin listesi için [Defender Virüsten Koruma cmdlet'leri](/powershell/module/defender) konusuna bakın.

PowerShell cmdlet'leri en çok, yazılımı yapılandırmak için grafik kullanıcı arabirimine (GUI) güvenmeyen Windows Server ortamlarında kullanışlıdır.

> [!NOTE]
> PowerShell cmdlet'leri [Microsoft Endpoint Configuration Manager, grup ilkesi](/configmgr) [Yönetim Konsolu](use-group-policy-microsoft-defender-antivirus.md) veya [Microsoft Defender Virüsten Koruma grup ilkesi ADMX şablonları](https://www.microsoft.com/download/101445) gibi tam ağ ilkesi yönetim altyapısının yerine kullanılmamalıdır.

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
