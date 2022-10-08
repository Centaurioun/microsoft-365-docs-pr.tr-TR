---
title: Microsoft Defender Virüsten Koruma’yı değerlendirin
description: Tüm boyutlardaki işletmeler, Windows'ta Microsoft Defender Virüsten Koruma tarafından sunulan korumayı değerlendirmek ve test etmek için bu kılavuzu kullanabilir.
keywords: Microsoft Defender Virüsten Koruma, bulut koruması, bulut, kötü amaçlı yazılımdan koruma, güvenlik, defender, değerlendirme, test, koruma, karşılaştırma, gerçek zamanlı koruma
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2018
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: aef89bd9543d16ef63cf44396baa866cbb1739e5
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68200307"
---
# <a name="evaluate-microsoft-defender-antivirus"></a>Microsoft Defender Virüsten Koruma’yı değerlendirin

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**

- Microsoft Defender Virüsten Koruma
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)

**Platform**
- Windows

Virüsten Koruma Microsoft Defender'nın sizi virüslerden, kötü amaçlı yazılımlardan ve istenmeyebilecek uygulamalardan ne kadar iyi koruyup korumadığını belirlemek için bu kılavuzu kullanın. Hem küçük hem de büyük kuruluşlar için kullanılabilen Microsoft Defender Virüsten Koruma'nın önemli yeni nesil koruma özellikleri ve bunların ağınızdaki kötü amaçlı yazılım algılama ve korumayı nasıl artırdıkları açıklanmaktadır.

Her ayarı bağımsız olarak veya tümünü aynı anda yapılandırmayı ve değerlendirmeyi seçebilirsiniz. Benzer ayarları tipik değerlendirme senaryolarına göre gruplandırdık ve ayarları etkinleştirmek için PowerShell kullanma yönergelerini de dahil ettik.

Kılavuz, çevrimdışı görüntüleme için PDF biçiminde kullanılabilir:

- [Kılavuzu PDF biçiminde indirme](https://www.microsoft.com/download/details.aspx?id=54795)

Ayrıca kılavuzda açıklanan tüm ayarları otomatik olarak etkinleştirecek bir PowerShell indirebilirsiniz. Betiği yukarıdaki PDF indirme işleminin yanı sıra veya PowerShell Galerisi'dan tek tek edinebilirsiniz:

- [Ayarları otomatik olarak yapılandırmak için PowerShell betiğini indirin](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> Kılavuz şu anda Microsoft Defender Virüsten Koruma'nın tek makineli değerlendirmesine yöneliktir. Bu kılavuzdaki tüm ayarların etkinleştirilmesi gerçek dünya dağıtımı için uygun olmayabilir.
>
> Ağ üzerinden Microsoft Defender Virüsten Koruma'nın gerçek dünya dağıtımı ve izlenmesine yönelik en son öneriler için bkz. [Microsoft Defender Virüsten Koruma Dağıtma](deploy-manage-report-microsoft-defender-antivirus.md).

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

- [Windows 10'de virüsten koruma Microsoft Defender](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Virüsten Koruma Dağıtma](deploy-manage-report-microsoft-defender-antivirus.md)