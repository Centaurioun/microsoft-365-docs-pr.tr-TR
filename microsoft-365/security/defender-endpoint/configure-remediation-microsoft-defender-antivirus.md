---
title: Microsoft Defender Virüsten Koruma algılamaları için düzeltmeleri yapılandırın
description: Microsoft Defender Virüsten Koruma'nın bir tehdit algıladığında ne yapacağını ve karantinaya alınan dosyaların karantina klasöründe ne kadar süreyle tutulacaklarını yapılandırın
keywords: düzeltme, düzeltme, kaldırma, tehditler, karantina, tarama, geri yükleme
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.collection: m365-security
search.appverid: met150
ms.openlocfilehash: 30c21e93f4370025a3dd4dba9bd14d96a2deeaae
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68061736"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a>Microsoft Defender Virüsten Koruma algılamaları için düzeltmeleri yapılandırın


**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

Microsoft Defender Virüsten Koruma bir tarama çalıştırdığında algılanan tehditleri düzeltmeye veya kaldırmaya çalışır. Microsoft Defender Virüsten Koruma'nın belirli tehditleri nasıl ele alması gerektiğini, düzeltmeden önce bir geri yükleme noktası oluşturulup oluşturulmayacağını ve tehditlerin ne zaman kaldırılması gerektiğini yapılandırabilirsiniz.

Bu makalede, grup ilkesi kullanarak bu ayarların nasıl yapılandırıldığı açıklanır, ancak [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) ve [Microsoft Intune](/intune/device-restrictions-configure) de kullanabilirsiniz.

Bu ayarları yapılandırmak için [PowerShell cmdlet'ini veya WMI sınıfını da kullanabilirsiniz`Set-MpPreference`](/powershell/module/defender/set-mppreference).[`MSFT_MpPreference`](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="configure-remediation-options"></a>Düzeltme seçeneklerini yapılandırma

1. grup ilkesi yönetim bilgisayarınızda [grup ilkesi Yönetim Konsolu'nu](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) açın, yapılandırmak istediğiniz grup ilkesi Nesnesine sağ tıklayın ve **Düzenle'ye** tıklayın.

2. **Grup İlkesi Yönetimi Düzenleyicisi**'nde **Bilgisayar yapılandırması**'na gidin ve **Yönetim şablonları**'nı seçin.

3. Ağacı **Virüsten Koruma Microsoft Defender** **Windows bileşenlerine** \> genişletin.

4. Aşağıdaki tabloyu kullanarak bir konum seçin ve ilkeyi gerektiği gibi düzenleyin.

5. **Tamam**'ı seçin.

<br/><br/>

|Konum|Ayar|Açıklama|Varsayılan ayar (yapılandırılmadıysa)|
|---|---|---|---|
|Tarama|Sistem geri yükleme noktası oluşturma|Temizleme veya tarama denenmeden önce her gün bir sistem geri yükleme noktası oluşturulur|Devre dışı|
|Tarama|Tarama geçmişi klasöründeki öğelerin kaldırılmasını açma|Tarama geçmişinde öğelerin kaç gün tutulacağını belirtin|30 gün|
|Kök|Rutin düzeltmeyi kapatma|Microsoft Defender Virüsten Koruma'nın tehditleri otomatik olarak düzeltip düzeltmediğini veya uç nokta kullanıcısına ne yapacağını sorması gerektiğini belirtebilirsiniz.|Devre dışı bırakıldı (tehditler otomatik olarak düzeltilir)|
|Karantina|Karantina klasöründeki öğelerin kaldırılmasını yapılandırma|Öğelerin kaldırılmadan önce kaç gün karantinada tutulacağını belirtin|90 gün|
|Tehdit|Algılandığında varsayılan eylemin gerçekleştirilmemesi gereken tehdit uyarısı düzeylerini belirtin|Microsoft Defender Virüsten Koruma tarafından algılanan her tehdide bir tehdit düzeyi (düşük, orta, yüksek veya ciddi) atanır. Tehdit düzeylerinin her biri için tüm tehditlerin nasıl düzeltilmesi gerektiğini (karantinaya alma, kaldırma veya yoksayma) tanımlamak için bu ayarı kullanabilirsiniz|Geçerli değil|
|Tehdit|Algılandığında varsayılan eylemin gerçekleştirilmemesi gereken tehditleri belirtin|Belirli tehditlerin (tehdit kimliklerini kullanarak) nasıl düzeltileceğini belirtin. Belirli bir tehdidin karantinaya alınması, kaldırılması veya yoksayılması gerektiğini belirtebilirsiniz|Geçerli değil|

> [!IMPORTANT]
> Microsoft Defender Virüsten Koruma birçok faktöre göre dosyaları algılar ve düzelter. Bazen bir düzeltmenin tamamlanması için yeniden başlatma gerekir. Algılamanın daha sonra hatalı pozitif olduğu belirlense bile, tüm ek düzeltme adımlarının tamamlandığından emin olmak için yeniden başlatmanın tamamlanması gerekir.
>
> Microsoft Defender Virüsten Koruma'nın bir dosyayı hatalı pozitife göre karantinaya olduğundan eminseniz, cihaz yeniden başlatıldıktan sonra dosyayı karantinadan geri yükleyebilirsiniz. Bkz. [Microsoft Defender Virüsten Koruma'da karantinaya alınan dosyaları geri yükleme](restore-quarantined-files-microsoft-defender-antivirus.md).
>
> Gelecekte bu sorundan kaçınmak için dosyaları taramaların dışında tutabilirsiniz. Bkz[. Microsoft Defender Virüsten Koruma taramaları için dışlamaları yapılandırma ve doğrulama](configure-exclusions-microsoft-defender-antivirus.md).

Ayrıca düzeltmeyle ilgili daha fazla ayar için bkz. Düzeltme [gerekli zamanlanmış tam Microsoft Defender Virüsten Koruma taramalarını](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) yapılandırma.

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

- [Microsoft Defender Virüsten Koruma tarama seçeneklerini yapılandırın](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Zamanlanmış Microsoft Defender Virüsten Koruma taramalarını yapılandırma](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [İsteğe bağlı Microsoft Defender Virüsten Koruma taramalarını yapılandırın ve çalıştırın](run-scan-microsoft-defender-antivirus.md)
- [Uç noktalarda görünen bildirimleri yapılandırın](configure-notifications-microsoft-defender-antivirus.md)
- [Son kullanıcı Microsoft Defender Virüsten Koruma etkileşimlerini yapılandırma](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [Microsoft Defender Virüsten Koruma taramalarının ve düzeltmelerinin sonuçlarını özelleştirme, başlatma ve gözden geçirme](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10'de virüsten koruma Microsoft Defender](microsoft-defender-antivirus-in-windows-10.md)
