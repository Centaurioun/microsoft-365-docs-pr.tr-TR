---
title: Microsoft Endpoint Manager kullanarak Microsoft Defender Virüsten Koruma'yi yapılandırma
description: Microsoft Defender Virüsten Koruma ve Endpoint Protection'ı yapılandırmak için Microsoft Endpoint Manager ve Microsoft Intune kullanma
keywords: scep, intune, uç nokta koruması, yapılandırma
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/16/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.subservice: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
search.appverid: met150
ms.openlocfilehash: ffe94273778a5920d8d4bfcd1dfe7ca310690909
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67687581"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a>Microsoft Defender Virüsten Koruma'Endpoint Manager yapılandırmak ve yönetmek için Microsoft Endpoint Manager kullanma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

Microsoft Defender Virüsten Koruma taramalarını yapılandırmak için Microsoft [Endpoint Manager](/mem/endpoint-manager-overview) kullanabilirsiniz. [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) ve [Configuration Manager](/mem/configmgr/core/understand/introduction) artık Endpoint Manager bir parçasıdır.

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a>Endpoint Manager'de Microsoft Defender Virüsten Koruma taramalarını yapılandırma

1. Microsoft Endpoint Manager yönetim merkezine ()[https://endpoint.microsoft.com](https://endpoint.microsoft.com) gidin ve oturum açın.

2. **Endpoint Security'ye** gidin.

3. **Yönet'in** altında **Virüsten Koruma'yı** seçin.

4. Microsoft Defender Virüsten Koruma ilkenizi seçin.

5. **Yönet'in** altında **Özellikler'i** seçin.

6. **Yapılandırma ayarları'nın** yanında **Düzenle'yi** seçin.

   > [!IMPORTANT]
   > AllowOnAccessProtection ve AllowIntrusionPreventionSystem virüsten koruma ayarları resmi olarak kullanım dışı bırakılmıştır ve bu nedenle yapılandırılamaz. 

7. **Tarama** bölümünü genişletin ve tarama ayarlarınızı gözden geçirin veya düzenleyin.

8. **Gözden Geçir ve kaydet'i** seçin.

> [!TIP]
> Yardıma mı ihtiyacınız var? Bkz. [Microsoft Intune'de uç nokta güvenliğini yönetme](/mem/intune/protect/endpoint-security).

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)

## <a name="related-articles"></a>İlgili makaleler

- [Yönetim ve yapılandırma araçları için başvuru makaleleri](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10'da Microsoft Defender Virüsten Koruma](microsoft-defender-antivirus-in-windows-10.md)
