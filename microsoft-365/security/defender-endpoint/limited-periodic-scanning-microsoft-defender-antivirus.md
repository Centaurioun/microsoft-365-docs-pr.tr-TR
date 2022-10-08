---
title: Sınırlı düzenli Microsoft Defender Virüsten Koruma tarama özelliğini etkinleştirme
description: Sınırlı düzenli tarama, Microsoft Defender Virüsten Koruma'nın yanı sıra diğer yüklü AV sağlayıcılarınızı da kullanmanızı sağlar
keywords: lps, sınırlı, periyodik, tarama, tarama, uyumluluk, 3. taraf, diğer av, devre dışı
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2018
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.collection:
- m365-security
- tier3
search.appverid: met150
ms.openlocfilehash: 5f897e84e5ce174e88565b9cce5712cb66e00819
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68224942"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a>Microsoft Defender Virüsten Koruma’da sınırlı düzenli taramayı kullanın 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

Sınırlı düzenli tarama, bir Windows 10 veya Windows 11 cihaza başka bir virüsten koruma ürünü yüklediğinizde etkinleştirilebilen özel bir tehdit algılama ve düzeltme türüdür.

Yalnızca belirli durumlarda etkinleştirilebilir. Sınırlı düzenli tarama ve Microsoft Defender Virüsten Koruma'nın diğer virüsten koruma ürünleriyle nasıl çalıştığı hakkında daha fazla bilgi için bkz[. Virüsten Koruma uyumluluğu Microsoft Defender](microsoft-defender-antivirus-compatibility.md).

**Microsoft bu özelliğin kurumsal ortamlarda kullanılmasını önermez. Bu, öncelikli olarak tüketicilere yönelik bir özelliktir.** Bu özellik, kötü amaçlı yazılımları algılamak için yalnızca Microsoft Defender Virüsten Koruma özelliklerinin sınırlı bir alt kümesini kullanır ve çoğu kötü amaçlı yazılımı ve istenmeyebilecek yazılımları algılayamaz. Ayrıca, yönetim ve raporlama özellikleri sınırlı olacaktır. Microsoft, kuruluşların birincil virüsten koruma çözümünü seçmelerini ve özel olarak kullanmasını önerir.

## <a name="how-to-enable-limited-periodic-scanning"></a>Sınırlı düzenli taramayı etkinleştirme

Varsayılan olarak, Microsoft Defender Virüsten Koruma başka bir virüsten koruma ürünü yüklü değilse veya diğer ürün güncel değilse, süresi dolmuşsa veya düzgün çalışmıyorsa bir Windows 10 veya Windows 11 cihazında kendini etkinleştirir.

Microsoft Defender Virüsten Koruma etkinse, söz konusu cihazda yapılandırmak için her zamanki seçenekler görünür:

:::image type="content" source="images/vtp-wdav.png" alt-text="Tarama seçenekleri, ayarlar ve güncelleştirme seçenekleri dahil Microsoft Defender Virüsten Koruma seçeneklerini gösteren Windows Güvenliği uygulaması" lightbox="images/vtp-wdav.png":::

Başka bir virüsten koruma ürünü yüklüyse ve düzgün çalışıyorsa, Microsoft Defender Virüsten Koruma kendisini devre dışı bırakır. Windows Güvenliği uygulaması **Virüs & tehdit koruması** bölümünü AV ürünüyle ilgili durumu gösterecek şekilde değiştirecek ve ürünün yapılandırma seçeneklerine bir bağlantı sağlayacaktır.

Tüm üçüncü taraf AV ürünlerinin altında Microsoft Defender **Virüsten Koruma seçenekleri** olarak yeni bir bağlantı görünür. Bu bağlantıya tıklanması, sınırlı düzenli taramayı etkinleştiren iki durumlu düğmeyi göstermek için genişler. Sınırlı düzenli seçeneğin düzenli taramayı etkinleştirmek veya devre dışı bırakmak için kullanabileceğiniz bir geçiş noktası olduğunu unutmayın. 

Anahtarı **Açık** olarak kaydırarak üçüncü taraf AV ürününün altında standart Microsoft Defender Virüsten Koruma seçenekleri gösterilir. Sınırlı düzenli tarama seçeneği sayfanın en altında görünür.

## <a name="related-articles"></a>İlgili makaleler

- [Davranışsal, buluşsal ve gerçek zamanlı korumayı yapılandırın](configure-protection-features-microsoft-defender-antivirus.md)
- [Windows 10'de virüsten koruma Microsoft Defender](microsoft-defender-antivirus-in-windows-10.md)

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)