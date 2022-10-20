---
title: mobil cihazların Microsoft Defender Virüsten Koruma tarafından nasıl güncelleştirildiği tanımlama
description: Dizüstü bilgisayarlar gibi mobil cihazların Microsoft Defender Virüsten Koruma güncelleştirmeleriyle nasıl güncelleştirilmesi gerektiğini yönetin.
keywords: güncelleştirmeler, koruma, güncelleştirmeleri zamanlama, pil, mobil cihaz, dizüstü bilgisayar, not defteri, kabul etme, microsoft update, wsus, geçersiz kılma
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
ms.openlocfilehash: d85a35740b9ccdc11aedcb46ded9e43971002873
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68620051"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a>Mobil cihaz ve sanal makine (VM) güncelleştirmelerini yönetin

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

Performansın güncelleştirmelerden etkilenmediğinden emin olmak için mobil cihazlar ve VM'ler daha fazla yapılandırma gerektirebilir.

Bu cihazlar için yararlı olan iki ayar vardır:

- WSUS bağlantısı olmayan mobil bilgisayarlarda Microsoft Update'e katılma
- Pil gücüyle çalışırken güvenlik bilgileri güncelleştirmelerini engelleme

Aşağıdaki makaleler bu durumlarda da yararlı olabilir:
- [Zamanlanmış ve yakalama taramalarını yapılandırma](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Güncel olmayan uç noktalar için güncelleştirmeleri yönetme](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Sanal Masaüstü Altyapısı (VDI) ortamında Microsoft Defender Virüsten Koruma için dağıtım klavuzu](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a>WSUS bağlantısı olmayan mobil bilgisayarlarda Microsoft Update'e katılma

Şirket ağına bağlı olmayan veya WSUS bağlantısı olmayan Microsoft Defender Virüsten Koruma çalıştıran mobil cihazlarda Güvenlik bilgilerini güncel tutmak için Microsoft Update'i kullanabilirsiniz.

Bu, WSUS'yi Microsoft Update'i geçersiz kılacak şekilde ayarlamış olsanız bile koruma güncelleştirmelerinin cihazlara (Microsoft Update aracılığıyla) teslim edilebileceği anlamına gelir.

Mobil cihazda Microsoft Update'i aşağıdaki yollardan biriyle kabul edebilirsiniz:

- ayarı grup ilkesi ile değiştirin.
- Bir betik oluşturmak için VBScript kullanın, ardından bunu ağınızdaki her bilgisayarda çalıştırın.
- **Ayarlar** menüsü aracılığıyla ağınızdaki her bilgisayarı el ile kabul edin.

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a>Microsoft Update'i kabul etmek için grup ilkesi kullanma

1. grup ilkesi yönetim makinenizde [grup ilkesi Yönetim Konsolu'nu](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) açın, yapılandırmak istediğiniz grup ilkesi Nesnesine sağ tıklayın ve **Düzenle'yi** seçin.

2. **grup ilkesi Yönetim Düzenleyicisi'nde** **Bilgisayar yapılandırması'na** gidin.

3. **İlkeler'i** ve ardından **Yönetim şablonları'nı** seçin.

4. Ağacı **Windows bileşenleri** \> **Microsoft Defender Virüsten Koruma** \> **İmzası Güncelleştirmeler** genişletin.

5. **Microsoft Update'ten Güvenlik bilgileri güncelleştirmelerine izin ver** seçeneğini **Etkin** olarak ayarlayın ve **ardından Tamam'ı** seçin.

### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a>Microsoft Update'i kabul etmek için VBScript kullanma

1. VBScript'i oluşturmak için MSDN [makalesindeki yönergeleri kullanarak Microsoft Update'i](/windows/win32/wua_sdk/opt-in-to-microsoft-update) kabul edin.

2. Ağınızdaki her bilgisayarda oluşturduğunuz VBScript'i çalıştırın.

### <a name="manually-opt-in-to-microsoft-update"></a>Microsoft Update'i el ile kabul etme

1. **Windows Update** açmak istediğiniz bilgisayardaki **Güncelleştirme & güvenlik** ayarlarını açın.

2. **Gelişmiş seçenekler'i** seçin.

3. **Windows'u güncelleştirdiğimde diğer Microsoft ürünleri için güncelleştirmeler ver** onay kutusunu seçin.

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a>Pil gücüyle çalışırken güvenlik bilgileri güncelleştirmelerini engelleme

Microsoft Defender Virüsten Koruma'yi yalnızca bilgisayar kablolu bir güç kaynağına bağlıyken koruma güncelleştirmelerini indirecek şekilde yapılandırabilirsiniz.

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a>Pil gücünde güvenlik zekası güncelleştirmelerini önlemek için grup ilkesi kullanın

1. grup ilkesi yönetim makinenizde [grup ilkesi Yönetim Konsolu'nu](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) açın, yapılandırmak istediğiniz grup ilkesi Nesnesini seçin ve düzenlemek üzere açın.

2. **grup ilkesi Yönetim Düzenleyicisi'nde** **Bilgisayar yapılandırması'na** gidin.

3. **İlkeler'i** ve ardından **Yönetim şablonları'nı** seçin.

4. Ağacı **Virüsten Koruma** \> **İmzası** Güncelleştirmeler Microsoft Defender **Windows bileşenlerine** \> genişletin ve **pil gücüyle çalışırken güvenlik zekası güncelleştirmelerine izin ver** seçeneğini **Devre Dışı** olarak ayarlayın. Sonra **Tamam**’ı seçin.

Bu eylem, bilgisayar pil gücündeyken koruma güncelleştirmelerinin indirilmesini engeller.

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

- [Microsoft Defender Virüsten Koruma güncelleştirmelerini yönetme ve temelleri uygulama](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Windows 10'da Microsoft Defender Virüsten Koruma'Windows 10 güncelleştirme ve yönetme](deploy-manage-report-microsoft-defender-antivirus.md)