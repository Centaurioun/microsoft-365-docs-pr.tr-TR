---
title: Microsoft Defender Virüsten Koruma özelliklerini yapılandırın
description: Intune, Microsoft Endpoint Configuration Manager, grup ilkesi ve PowerShell ile Microsoft Defender Virüsten Koruma özelliklerini yapılandırabilirsiniz.
keywords: Microsoft Defender Virüsten Koruma, kötü amaçlı yazılımdan koruma, güvenlik, defender, yapılandırma, yapılandırma, Config Manager, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, mobil cihaz yönetimi, GP, grup ilkesi, PowerShell
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: conceptual
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 13777ebdc54c27814dfefc2ea81efa4d6e66d042
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68620491"
---
# <a name="configure-microsoft-defender-antivirus-features"></a>Microsoft Defender Virüsten Koruma özelliklerini yapılandırın


**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

Microsoft Defender Virüsten Koruma'yı şu gibi çeşitli araçlarla yapılandırabilirsiniz:

- Microsoft Endpoint Manager (Microsoft Intune ve Microsoft Endpoint Configuration Manager içerir)
- Grup İlkesi
- PowerShell cmdlet'leri
- Windows Yönetim Araçları (WMI)
- [Kiracı ekleme](/mem/configmgr/tenant-attach/)

Aşağıdaki geniş özellik kategorileri yapılandırılabilir:

- Bulut tabanlı koruma. Bkz[. Bulut tabanlı koruma ve Microsoft Defender Virüsten Koruma](cloud-protection-microsoft-defender-antivirus.md)

- Davranışsal, buluşsal ve makine öğrenmesi tabanlı koruma da dahil olmak üzere her zaman açık gerçek zamanlı koruma. Bkz [. Davranışsal, buluşsal ve gerçek zamanlı korumayı yapılandırma](configure-protection-features-microsoft-defender-antivirus.md).

- Son kullanıcıların tek tek uç noktalarda istemciyle etkileşim kurma şekli. Aşağıdaki kaynaklara bakın:
  - [Kullanıcıların Microsoft Defender Virüsten Koruma kullanıcı arabirimini görmesini veya bunlarla etkileşim kurmasını engelleme](prevent-end-user-interaction-microsoft-defender-antivirus.md)
  - [Kullanıcıların Microsoft Defender Virüsten Koruma ilkesi ayarlarını yerel olarak değiştirmesini engelleme veya izin verme](configure-local-policy-overrides-microsoft-defender-antivirus.md)

> [!TIP]
> [Yönetim ve yapılandırma araçları için Başvuru konularını](configuration-management-reference-microsoft-defender-antivirus.md) gözden geçirin.
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)
