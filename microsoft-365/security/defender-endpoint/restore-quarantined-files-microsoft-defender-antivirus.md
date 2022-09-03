---
title: Microsoft Defender Virüsten Koruma’da karantinaya alınan dosyaları geri yükleyin
description: Microsoft Defender Virüsten Koruma tarafından karantinaya alınan dosya ve klasörleri geri yükleyebilirsiniz.
keywords: ''
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/19/2021
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 415c16677669277e75f88ec91d1ef18cefd00ee0
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67585586"
---
# <a name="restore-quarantined-files-in-microsoft-defender-antivirus"></a>Microsoft Defender Virüsten Koruma’da karantinaya alınan dosyaları geri yükleyin

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

Microsoft Defender Virüsten Koruma, cihazınızdaki tehditleri algılayıp düzeltecek şekilde yapılandırılmışsa, Microsoft Defender Virüsten Koruma şüpheli dosyaları karantinaya alır. Karantinaya alınan bir dosyanın tehdit oluşturmadığından eminseniz dosyayı geri yükleyebilirsiniz.

1. **Windows Güvenliği** açın.
2. **Virüs & tehdit koruması'nın** ardından **Koruma geçmişi'ne** tıklayın.
3. Tüm son öğeler listesinde **, Karantinaya Alınan Öğeler'e** filtreleyin.
4. Saklamak istediğiniz öğeyi seçin ve geri yükleme gibi bir eylem gerçekleştirin.

> [!TIP]
> Bir dosyayı karantinadan geri yükleme işlemi Komut İstemi kullanılarak da yapılabilir. Bkz. [Dosyayı karantinadan geri yükleme](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine). 

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

- [Taramalar için düzeltmeyi yapılandırma](configure-remediation-microsoft-defender-antivirus.md)
- [Tarama sonuçlarını gözden geçirme](review-scan-results-microsoft-defender-antivirus.md)
- [Dosya adı, uzantı ve klasör konumuna göre dışlamaları yapılandırma ve doğrulama](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [İşlemler tarafından açılan dosyalar için dışlamaları yapılandırma ve doğrulama](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Windows Server'da Microsoft Defender Virüsten Koruma dışlamalarını yapılandırma](configure-server-exclusions-microsoft-defender-antivirus.md)