---
title: Microsoft Endpoint Manager kullanarak kuruluşunuz için kurcalama korumasını yönetme
ms.reviewer: mattcall, pahuijbr, hayhov, oogunrinde
manager: dansimp
description: Microsoft Endpoint Manager'da kuruluşunuz için kurcalama korumasını açın veya kapatın.
keywords: kötü amaçlı yazılım, defender, virüsten koruma, kurcalama koruması, Microsoft Endpoint Manager
ms.pagetype: security
ms.prod: m365-security
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
ms.technology: mde
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: f4946191ab6483e42f84faa8aa56cf4227714976
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2022
ms.locfileid: "67389478"
---
# <a name="manage-tamper-protection-for-your-organization-using-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager kullanarak kuruluşunuz için kurcalama korumasını yönetme

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows


Kuruluşunuz Microsoft Endpoint Manager (MEM) kullanıyorsa, Microsoft Endpoint Manager yönetim merkezinde ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) kuruluşunuz için kurcalama korumasını açabilir (veya kapatabilirsiniz). Kurcalama koruması ayarlarına ince ayar yapmak istediğinizde Intune kullanın. Örneğin, tüm cihazlarda değil bazı cihazlarda kurcalama korumasını etkinleştirmek istiyorsanız Intune kullanın.

## <a name="requirements-for-managing-tamper-protection-in-endpoint-manager"></a>Endpoint Manager'de kurcalama korumasını yönetme gereksinimleri

- Genel yönetici, güvenlik yöneticisi veya güvenlik işlemleri gibi uygun [izinlere](/microsoft-365/security/defender-endpoint/assign-portal-access) sahip olmanız gerekir.
- Kuruluşunuz [cihazları yönetmek için Microsoft Endpoint Manager](/mem/endpoint-manager-getting-started) kullanıyor. (Microsoft Endpoint Manager (MEM) lisansları gereklidir; MEM, Microsoft 365 E3/E5, Enterprise Mobility + Security E3/E5, Microsoft 365 İş Ekstra, Microsoft 365 F1/F3, Microsoft 365 Kamu G3/G5 ve ilgili eğitim lisanslarına dahildir.)
- Windows cihazlarınız Windows 11 veya Windows 10 [1709, 1803](/lifecycle/announcements/revised-end-of-service-windows-10-1709), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) veya üzerini çalıştırıyor olmalıdır. [](/lifecycle/announcements/windows-server-1803-end-of-servicing) (Sürümler hakkında daha fazla bilgi için bkz. [Windows 10 sürüm bilgileri](/windows/release-health/release-information).)
- Windows güvenliğini [güvenlik bilgileri](https://www.microsoft.com/wdsi/definitions) 1.287.60.0 (veya üzeri) sürümüne güncelleştirilmiş olarak kullanıyor olmanız gerekir.
- Cihazlarınız kötü amaçlı yazılımdan koruma platformu sürüm 4.18.1906.3 (veya üzeri) ve kötü amaçlı yazılımdan koruma altyapısı sürümünü `1.1.15500.X` (veya üzeri) kullanıyor olmalıdır. ([Microsoft Defender Virüsten Koruma güncelleştirmelerini yönetin ve temelleri uygulayın](manage-updates-baselines-microsoft-defender-antivirus.md).)

## <a name="turn-tamper-protection-on-or-off-in-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager'da kurcalama korumasını açma (veya kapatma)

:::image type="content" source="images/turnontamperprotectinmem.png" alt-text="Intune ile kurcalama korumasını açma" lightbox="images/turnontamperprotectinmem.png":::

1. [Microsoft Endpoint Manager yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431) **Endpoint security** \> **Virüsten Koruma'ya** gidin ve **+ İlke Oluştur'u** seçin.

   - **Platform** listesinde **Windows 10 ve üzerini** seçin.
   - **Profil** listesinde **Windows Güvenliği deneyim'i** seçin.

2. Aşağıdaki ayarı içeren bir profil oluşturun:

    - **Microsoft Defender'ın devre dışı bırakılmasını önlemek için kurcalama korumasını etkinleştirme: Etkinleştir**

3. Profili bir veya daha fazla gruba atayın.

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)