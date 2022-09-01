---
title: Microsoft 365 Defender kullanarak kuruluşunuz için kurcalama korumasını yönetme
ms.reviewer: mattcall, pahuijbr, hayhov, oogunrinde
manager: dansimp
description: Microsoft 365 Defender portalını kullanarak kiracınız için kurcalama korumasını açın veya kapatın.
keywords: kötü amaçlı yazılım, defender, virüsten koruma, kurcalama koruması, Microsoft 365 Defender
ms.pagetype: security
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom:
- nextgen
- admindeeplinkDEFENDER
ms.subservice: mde
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: ca5099e62cbfc50c8a2c3f20b4dab6f4401262db
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67520697"
---
# <a name="manage-tamper-protection-for-your-organization-using-microsoft-365-defender-portal"></a>Microsoft 365 Defender portalını kullanarak kuruluşunuz için kurcalama korumasını yönetme

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

Microsoft 365 Defender portalı ([https://security.microsoft.com](https://security.microsoft.com) ) kullanılarak kiracınız için kurcalama koruması açılabilir veya kapatılabilir. Aklınızda bulundurmak istediğiniz birkaç nokta şunlardır:

- Şu anda, yeni dağıtımlar için Microsoft 365 Defender portalında 'kurcalama korumasını' yönetme seçeneği varsayılan olarak açıktır. Mevcut dağıtımlar için , 'kurcalama koruması' kabul temelinde kullanılabilir. Kabul etmek için <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalında</a> **Ayarlar** \> **Uç Noktaları** \> **Gelişmiş özellikler** \> **Kurcalama koruması'nı** seçin.
- 'Kurcalama korumasını' yönetmek için Microsoft 365 Defender portalını kullandığınızda, Intune veya kiracı ekleme yöntemini kullanmanız gerekmez.
- Microsoft 365 Defender portalında 'kurcalama korumasını' yönettiğinizde, bu ayar kiracı genelinde uygulanır ve Windows 10 çalıştıran tüm cihazlarınızı Windows 10 Enterprise çok oturumlu, Windows 11 Windows 11 Enterprise  çok oturumlu, Windows Server 2012 R2, Windows Server 2016, Windows Server 2019 veya Windows Server 2022. 'Kurcalama koruması'na ince ayar yapmak için (bazı cihazlarda kurcalama korumasının açık olması, diğerleri için kapalı olması gibi), [Microsoft Endpoint Manager kullanarak kuruluşunuz için kurcalama korumasını yönetme](manage-tamper-protection-microsoft-endpoint-manager.md) veya [Configuration Manager, sürüm 2006 ile kiracı ekleme kullanarak kurcalama korumasını yönetme'yi](manage-tamper-protection-configuration-manager.md) kullanın.
- Karma bir ortamınız varsa, Intune'de yapılandırılan kurcalama koruma ayarları, Microsoft 365 Defender portalında yapılandırılan ayarlardan önceliklidir.

## <a name="requirements-for-managing-tamper-protection-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender portalında kurcalama korumasını yönetme gereksinimleri

- Genel yönetici, güvenlik yöneticisi veya güvenlik işlemleri gibi uygun [izinlere](/microsoft-365/security/defender-endpoint/assign-portal-access) sahip olmanız gerekir.

- Windows cihazlarınız aşağıdaki Windows sürümlerinden birini çalıştırıyor olmalıdır:
  
  - Windows 11
  - Çoklu oturum Windows 11 Enterprise 
  - Windows 10
  - Çoklu oturum Windows 10 Enterprise
  - Windows Server 2022
  - Windows Server 2019
  - Windows Server, sürüm 1803 veya üzeri
  - Windows Server 2016
  - Windows Server 2012 R2

Sürümler hakkında daha fazla bilgi için bkz. [Windows 10 sürüm bilgileri](/windows/release-health/release-information).

- Cihazlarınız [Uç Nokta için Microsoft Defender](/microsoft-365/security/defender-endpoint/onboarding) eklenmelidir.
- Cihazlarınız kötü amaçlı yazılımdan koruma platformu sürümünü `4.18.2010.7` (veya üzeri) ve kötü amaçlı yazılımdan koruma altyapısı sürümünü `1.1.17600.5` (veya üzerini) kullanıyor olmalıdır. ([Microsoft Defender Virüsten Koruma güncelleştirmelerini yönetin ve temelleri uygulayın](manage-updates-baselines-microsoft-defender-antivirus.md).)
- [Bulut tabanlı koruma](enable-cloud-protection-microsoft-defender-antivirus.md) açık olmalıdır.

> [!NOTE]
> Microsoft 365 Defender portalı aracılığıyla kurcalama koruması etkinleştirildiğinde, kurcalama korumasının etkin durumunun denetlenebilmesi için bulut tabanlı koruma gerekir.  
> Kasım 2021 güncelleştirmesi (platform sürümü`4.18.2111.5`) ile başlayarak, bir cihaz için bulut tabanlı koruma açık değilse ve Microsoft 365 Defender portalında kurcalama koruması açıksa, bu cihaz için üzerinde değişiklik korumasının yanı sıra bulut tabanlı koruma da otomatik olarak açılır.   

## <a name="turn-tamper-protection-on-or-off-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender portalında kurcalama korumasını açma (veya kapatma)

:::image type="content" source="../../media/mde-turn-tamperprotectionon.png" alt-text="Microsoft 365 Defender portalında kurcalama korumasını açma" lightbox="../../media/mde-turn-tamperprotectionon.png":::

1. Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com)) gidin ve oturum açın.

2. **Ayarlar** \> **Uç Noktaları'nı** seçin.

3. **Genel** \> **Gelişmiş özellikler'e** gidin ve kurcalama korumasını açın.

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)