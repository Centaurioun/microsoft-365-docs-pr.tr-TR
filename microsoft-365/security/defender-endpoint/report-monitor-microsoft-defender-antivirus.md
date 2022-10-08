---
title: Microsoft Defender Virüsten Koruma korumasını izleme ve raporlama
description: Raporları kullanmak ve Microsoft Defender Virüsten Koruma'yı PowerShell ve WMI ile izlemek için Configuration Manager veya güvenlik bilgileri ve olay yönetimi (SIEM) araçlarını kullanın.
keywords: siem, monitor, report, Microsoft Defender AV, Microsoft Defender Antivirus
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.topic: article
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: e07c89d2f6f2fa59d79f5bad1274ebcdeaef2c9a
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68232638"
---
# <a name="report-on-microsoft-defender-antivirus"></a>Defender Virüsten Koruma’yı raporlayın

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

Microsoft Defender Virüsten Koruma Windows 10, Windows 11, Windows Server 2019, Windows Server 2022 ve Windows Server 2016 yerleşik olarak bulunur. Microsoft Defender Virüsten Koruma, Uç Nokta için Microsoft Defender'da yeni nesil korumanızdır. Yeni nesil koruma, cihazlarınızı e-posta, uygulamalar, bulut ve web'de virüs, kötü amaçlı yazılım ve casus yazılım gibi yazılım tehditlerinden korumaya yardımcı olur.

Microsoft Defender Virüsten Koruma ile koruma durumunu ve uyarılarını gözden geçirmek için çeşitli seçenekleriniz vardır. Microsoft Defender [Virüsten Koruma'Endpoint Manager izlemek](/configmgr/protect/deploy-use/monitor-endpoint-protection) veya [e-posta uyarıları oluşturmak için Microsoft Endpoint Manager kullanabilirsiniz](/configmgr/protect/deploy-use/endpoint-configure-alerts). Ya da [Microsoft Intune](/intune/introduction-intune) kullanarak korumayı izleyebilirsiniz.

Üçüncü taraf güvenlik bilgileriniz ve olay yönetimi (SIEM) sunucunuz varsa, [Windows Defender istemci olaylarını](/windows/win32/events/windows-events) da kullanabilirsiniz.

Windows olayları, Güvenlik Hesabı Yöneticisi (SAM) olayları ([Windows 10 için geliştirilmiş](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), [Güvenlik denetimi](/windows/security/threat-protection/auditing/security-auditing-overview) konusuna da bakın) ve [Windows Defender olayları](troubleshoot-microsoft-defender-antivirus.md) da dahil olmak üzere çeşitli güvenlik olay kaynaklarından oluşur.

Bu olaylar [Windows olay toplayıcısı](/windows/win32/wec/windows-event-collector) kullanılarak merkezi olarak toplanabilir. SIEM sunucuları genellikle Windows olayları için bağlayıcılara sahiptir ve SIEM sunucunuzdaki tüm güvenlik olaylarını ilişkilendirmenize olanak sağlar.

[Log Analytics'teki Kötü Amaçlı Yazılım Değerlendirmesi çözümünü kullanarak kötü amaçlı yazılım olaylarını da izleyebilirsiniz](/security/benchmark/azure/security-control-logging-monitoring).

PowerShell, WMI veya Microsoft Azure ile durumu izlemek veya belirlemek için [bkz. (Dağıtım, yönetim ve raporlama seçenekleri tablosu)](deploy-manage-report-microsoft-defender-antivirus.md#ref2).

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Windows 10'de virüsten koruma Microsoft Defender](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Virüsten Koruma Dağıtma](deploy-manage-report-microsoft-defender-antivirus.md)
