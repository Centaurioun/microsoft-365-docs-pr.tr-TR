---
title: Microsoft Defender Virüsten Koruma koruma güncelleştirmelerini zamanlama
description: Koruma güncelleştirmelerinin indirileceği gün, saat ve aralığı zamanlama
keywords: güncelleştirmeler, güvenlik temelleri, güncelleştirmeleri zamanlama
ms.service: microsoft-365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.subservice: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 6222ea1102fd57a9cba3cfca5d4f2f8bc90bd20b
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67521169"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a>Koruma güncelleştirmelerinin indirilme ve kullanılma zamanlamasını yönetin

> [!IMPORTANT]
> Mart 2022 Microsoft Defender altyapı güncelleştirmesini (**1.1.19100.5**) uygulayan müşteriler yüksek kaynak kullanımıyla (CPU ve/veya bellek) karşılaşmış olabilir. Microsoft, önceki sürümde sunulan hataları gideren bir güncelleştirme (**1.1.19200.5**) yayımladı. Müşterilerin Virüsten Koruma Altyapısı'nın bu yeni altyapı derlemesine (**1.1.19200.5**) güncelleştirmeleri önerilir. Performans sorunlarının tamamen düzeltildiğinden emin olmak için, güncelleştirme uygulandıktan sonra makinelerin yeniden başlatılması önerilir. Daha fazla bilgi için bkz. [Aylık platform ve altyapı sürümleri](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions).

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

Microsoft Defender Virüsten Koruma, güncelleştirmeleri ne zaman arayıp indirmesi gerektiğini belirlemenizi sağlar.

Uç noktalarınız için güncelleştirmeleri şu şekilde zamanlayabilirsiniz:

- Koruma güncelleştirmelerini denetlemek için haftanın gününü belirtme
- Koruma güncelleştirmelerinin denetlenme aralığını belirtme
- Koruma güncelleştirmelerinin denetlenme zamanını belirtme

Ayrıca, her uç noktanın koruma güncelleştirmelerini denetleyebileceği ve indirebileceği saatleri de rastgele ayarlayabilirsiniz. Daha fazla bilgi için [Taramaları zamanlama](scheduled-catch-up-scans-microsoft-defender-antivirus.md) konusuna bakın.

## <a name="use-configuration-manager-to-schedule-protection-updates"></a>Koruma güncelleştirmelerini zamanlamak için Configuration Manager kullanma

1. Microsoft Endpoint Manager konsolunuzda, değiştirmek istediğiniz kötü amaçlı yazılımdan koruma ilkesini açın (soldaki gezinti bölmesinde **Varlıklar ve Uyumluluk'a** tıklayın, sonra ağacı **Genel Bakış** \> **Endpoint Protection** \> **Kötü Amaçlı Yazılımdan Koruma İlkeleri** olarak genişletin)

2. **Güvenlik bilgileri güncelleştirmeleri** bölümüne gidin.

3. Güncelleştirmeleri belirli bir zamanda denetlemek ve indirmek için:
      1. **Endpoint Protection güvenlik bilgileri güncelleştirmelerini belirli bir aralıkta denetle...** değerini **0** olarak ayarlayın.
      2. **Endpoint Protection güvenlik bilgileri güncelleştirmelerini günlük olarak güncelleştirmelerin** denetlenmesi gereken zamana ayarlayın.
      3
4. Güncelleştirmeleri sürekli aralıklarla denetlemek ve indirmek **için Endpoint Protection güvenlik bilgileri güncelleştirmelerini belirli bir aralıkta denetle...** değerini güncelleştirmeler arasında gerçekleşmesi gereken saat sayısına ayarlayın.

5. [Güncelleştirilmiş ilkeyi her zamanki gibi dağıtın](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).

## <a name="use-group-policy-to-schedule-protection-updates"></a>Koruma güncelleştirmelerini zamanlamak için grup ilkesi kullanma

> [!IMPORTANT]
> Varsayılan olarak, "SignatureScheduleDay" "8" olarak, "SignatureUpdateInterval" ise "0" olarak ayarlandığından Microsoft Defender Virüsten Koruma koruma güncelleştirmelerini zamanlamaz.
Bu ayarların etkinleştirilmesi bu varsayılanı geçersiz kılar.

1. grup ilkesi yönetim makinenizde [grup ilkesi Yönetim Konsolu'nu](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) açın, yapılandırmak istediğiniz grup ilkesi Nesnesine sağ tıklayın ve **Düzenle'ye** tıklayın.

2. **grup ilkesi Yönetim Düzenleyicisi'nde** **Bilgisayar yapılandırması'na** gidin.

3. **İlkeler'e** ve ardından **Yönetim şablonları'nı** tıklatın.

4. Ağacı **Windows bileşenleri** \> **Microsoft Defender Virüsten Koruma** \> **İmzası Güncelleştirmeler** genişletin ve aşağıdaki ayarları yapılandırın:

    1. **Güvenlik bilgileri güncelleştirmelerini denetlemek için Haftanın gününü belirtin ayarına** çift tıklayın ve seçeneği **Etkin** olarak ayarlayın. Güncelleştirmeleri denetlemek için haftanın gününü girin. **Tamam**'a tıklayın.

    2. **Tanım güncelleştirmelerini denetlemek için aralığı belirtin ayarına** çift tıklayın ve seçeneği **Etkin** olarak ayarlayın. Güncelleştirmeler arasındaki saat sayısını girin. **Tamam**'a tıklayın.

    3. **Tanım güncelleştirmelerinin denetlenme zamanını belirtin ayarına** çift tıklayın ve seçeneği **Etkin** olarak ayarlayın. Güncelleştirmelerin denetlenmesi gereken zamanı girin. Zaman, uç noktanın yerel saatini temel alır. **Tamam**'a tıklayın.

## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a>Koruma güncelleştirmelerini zamanlamak için PowerShell cmdlet'lerini kullanma

Aşağıdaki cmdlet'leri kullanın:

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

[PowerShell'i Microsoft Defender Virüsten Koruma ile](use-powershell-cmdlets-microsoft-defender-antivirus.md) kullanma hakkında daha fazla bilgi için bkz. Microsoft Defender [Virüsten Koruma ve Defender Virüsten Koruma cmdlet'lerini](/powershell/module/defender/) yapılandırmak ve çalıştırmak için PowerShell cmdlet'lerini kullanma.

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a>Koruma güncelleştirmelerini zamanlamak için Windows Yönetim Yönergesi'ni (WMI) kullanma

Aşağıdaki özellikler için [**MSFT_MpPreference** sınıfının **Set** yöntemini](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) kullanın:

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

Daha fazla bilgi ve izin verilen parametreler için aşağıdakilere bakın:

- [WMIv2 API'lerini Windows Defender](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)

## <a name="related-articles"></a>İlgili makaleler

- [Microsoft Defender Virüsten Koruma'yi dağıtma](deploy-manage-report-microsoft-defender-antivirus.md)
- [Microsoft Defender Virüsten Koruma güncelleştirmelerini yönetme ve temelleri uygulama](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Güncel olmayan uç noktalar için güncelleştirmeleri yönetme](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Olay tabanlı zorunlu güncelleştirmeleri yönetin](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Mobil cihaz ve sanal makine (VM) güncelleştirmelerini yönetin](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Windows 10 ve 11'de Microsoft Defender Virüsten Koruma](microsoft-defender-antivirus-in-windows-10.md)
