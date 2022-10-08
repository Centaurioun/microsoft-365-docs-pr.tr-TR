---
title: Windows’da Microsoft Defender Virüsten Koruma
description: Kötü amaçlı yazılımlardan ve virüslerden koruyan yerleşik Microsoft Defender Virüsten Koruma’yı yönetmeyi, yapılandırmayı ve kullanmayı öğrenin.
keywords: Microsoft Defender Virüsten Koruma, windows defender, kötü amaçlı yazılımdan koruma, scep, system center endpoint protection, system center configuration manager, virüs, kötü amaçlı yazılım, tehdit, algılama, koruma, güvenlik
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: high
ms.date: 10/03/2022
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.subservice: mde
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 0e58a119cfd6dae272d5eae18a284e928f99235b
ms.sourcegitcommit: 2ff545246fec060ea7829da5afbc1cdc698d51ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68363661"
---
# <a name="microsoft-defender-antivirus-in-windows"></a>Windows’da Microsoft Defender Virüsten Koruma

**Şunlar için geçerlidir:**

- Uç Nokta için Microsoft Defender Plan 1 ve 2
- İş için Microsoft Defender
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows 

Microsoft Defender Virüsten Koruma; Windows 10, Windows 11 ve Windows Sunucusu sürümlerinde kullanılabilir.

Microsoft Defender Virüsten Koruma, Uç Nokta için Microsoft Defender’da yeni nesil korumanın önemli bir bileşenidir. Bu koruma, makine öğrenimi, büyük veri çözümlemesi, ayrıntılı tehdit direnci araştırması ve Microsoft bulut altyapısını bir araya getirerek kuruluşunuzdaki cihazları (veya uç noktaları) korur. Microsoft Defender Virüsten Koruma, Windows'da yerleşik olarak bulunur ve Uç Nokta için Microsoft Defender ile birlikte çalışarak cihazınızda ve bulutta koruma sağlar.

## <a name="compatibility-with-other-antivirus-products"></a>Diğer virüsten koruma ürünleriyle uyumluluk

Aygıtınızda Microsoft dışı virüsten koruma/kötü amaçlı yazılımlardan koruma ürünü kullanıyorsanız, Microsoft Defender Virüsten Koruma’yı, Microsoft dışı virüsten koruma çözümüyle birlikte pasif modda çalıştırmanız mümkün olabilir. Bu, kullanılan işletim sistemine ve cihazınıza Uç Nokta için Defender eklenip eklenmediğine bağlıdır. Daha fazla bilgi edinmek için [Microsoft Defender Virüsten Koruma uyumluluğuna](microsoft-defender-antivirus-compatibility.md) bakın.

## <a name="comparing-active-mode-passive-mode-and-disabled-mode"></a>Etkin, pasif ve devre dışı modlarını karşılaştırma

Aşağıdaki tabloda, Microsoft Defender Virüsten Koruma etkin, pasif veya devre dışı modda olduğunda neler beklenebileceği açıklanmıştır.

| Mod | Neler olur? |
|---|---|
| Etkin mod | Etkin modda, Microsoft Defender Virüsten Koruma, cihazda virüsten birincil koruma uygulaması olarak kullanılır. Dosyalar taranır, tehditler düzeltilir ve algılanan tehditler, kuruluşunuzun güvenlik raporlarında ve Windows Güvenliği uygulamanıza listelenir. |
| Pasif mod | Pasif modda, Microsoft Defender Virüsten Koruma, cihazda virüsten birincil koruma uygulaması olarak kullanılamaz. Dosyalar taranır ve algılanan tehditler rapor edilir ancak tehditler Microsoft Defender Virüsten Koruma ile düzeltilmez. <br/><br/> **ÖNEMLİ**: Microsoft Defender Virüsten Koruma, pasif modda sadece Uç Nokta için Microsoft Defender’a eklenmiş uç noktalarda çalıştırılabilir. [Microsoft Defender Virüsten Koruma’nın pasif modda çalıştırılması için gereksinimlere](microsoft-defender-antivirus-compatibility.md#requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode) bakın. |
| Devre dışı bırakılmış veya kaldırılmış | Microsoft Defender Virüsten Koruma, devre dışı bırakıldığında veya kaldırıldığında kullanılmaz. Dosyalar taranmaz, tehditler düzeltilmez. Genel olarak, Microsoft Defender Virüsten Koruma’yı devre dışı bırakmanızı veya kaldırmanızı önermeyiz. |

Daha fazla bilgi edinmek için [Microsoft Defender Virüsten Koruma uyumluluğuna](microsoft-defender-antivirus-compatibility.md) bakın.

## <a name="check-the-state-of-microsoft-defender-antivirus-on-your-device"></a>Cihazınızın Microsoft Defender Virüsten Koruma durumunu kontrol etme

Cihazınızın Microsoft Defender Virüsten Koruma durumunu kontrol etmek için Windows Güvenliği uygulaması veya Windows PowerShell gibi çeşitli yöntemlerden birini kullanabilirsiniz.

### <a name="use-the-windows-security-app-to-check-the-status-of-microsoft-defender-antivirus"></a>Microsoft Defender Virüsten Koruma durumunu kontrol etmek için Windows Güvenliği uygulamasını kullanma

1. Windows cihazınızda **Başlat** menüsünü seçip `Security` yazın. Ardından, sonuçlarda Windows Güvenliği uygulamasını açın.

2. **Virüs ve tehdit koruması**’nı seçin.

3. **Beni kim koruyor?** altında, **Sağlayıcıları Yönet**’i seçin.

Güvenlik sağlayıcıları sayfasında virüsten koruma/kötü amaçlı yazılımdan koruma çözümünüzün adını görürsünüz.

### <a name="use-powershell-to-check-the-status-of-microsoft-defender-antivirus"></a>Microsoft Defender Virüsten Koruma durumunu kontrol etmek için PowerShell’i kullanma

1. **Başlat** menüsünü seçip `PowerShell` yazın. Ardından, sonuçlarda Windows PowerShell’i açın.

2. `Get-MpComputerStatus` yazın.

3. Sonuç listesinde **AMRunningMode** satırına bakın.

   - **Normal**, Microsoft Defender Virüsten Koruma’nın etkin modda çalıştığı anlamına gelir.

   - **Pasif mod**, Microsoft Defender Virüsten Koruma’nın çalıştığı ancak cihazınızda virüsten birincil koruma/kötü amaçlı yazılımdan koruma ürünü olmadığı anlamına gelir. Pasif mod, yalnızca Uç Nokta için Microsoft Defender'a eklenen ve belirli gereksinimleri karşılayan cihazlar için kullanılabilir. Daha fazla bilgi edinmek için [Microsoft Defender Virüsten Koruma’nın pasif modda çalıştırılması gereksinimlere](microsoft-defender-antivirus-compatibility.md#requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode) bakın.

   - **EDR Engelleme Modu**, Microsoft Defender Virüsten Koruma'nın çalıştığı ve Uç Nokta için Microsoft Defender’in bir özelliği olan [Uç nokta algılama ve yanıt’ın (EDR) engelleme modunda](edr-in-block-mode.md) etkinleştirildiği anlamına gelir. **ForceDefenderPassiveMode** kayıt defteri anahtarını denetleyin. Değeri 0 ise normal modda çalışır; aksi takdirde pasif modda çalışır.

   - **SxS Pasif Modu**, Microsoft Defender Virüsten Koruma'nın başka bir virüsten koruma/kötü amaçlı yazılımdan koruma ürünüyle birlikte çalıştığı ve [sınırlı düzenli tarama kullanıldığı](limited-periodic-scanning-microsoft-defender-antivirus.md) anlamına gelir.

> [!TIP]
> Get-MpComputerStatus PowerShell cmdlet hakkında daha fazla bilgi edinmek için [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) başvuru makalesine bakın.

## <a name="get-your-antivirusantimalware-platform-updates"></a>Virüsten koruma/kötü amaçlı yazılımdan koruma platform güncellemelerinizi alın

Microsoft Defender Virüsten Koruma programını (veya diğer virüsten koruma/kötü amaçlı yazılımdan koruma çözümlerini) güncel tutmanız önemlidir. Microsoft, cihazlarınızın kötü amaçlı yeni yazılımlara ve saldırı tekniklerine karşı korunması için en son teknolojiye sahip olmalarını sağlamak amacıyla düzenli güncelleştirmeler yayımlar. Daha fazla bilgi için [Microsoft Defender Virüsten Koruma güncelleştirmelerine bakın ve temelleri uygulayın](manage-updates-baselines-microsoft-defender-antivirus.md).

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

- [Microsoft Defender Virüsten Koruma yönetimi ve yapılandırması](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Virüsten Koruma değerlendirmesi](evaluate-microsoft-defender-antivirus.md)
