---
title: Microsoft Intune kullanarak kuruluşunuz için kurcalama korumasını yönetme
ms.reviewer: mattcall, pahuijbr, hayhov, oogunrinde
manager: dansimp
description: Microsoft Intune'da kuruluşunuz için kurcalama korumasını açın veya kapatın.
keywords: kötü amaçlı yazılım, defender, virüsten koruma, kurcalama koruması, Microsoft Intune
ms.pagetype: security
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.date: 10/14/2022
audience: ITPro
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom:
- nextgen
- admindeeplinkDEFENDER
ms.subservice: mde
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: c9e1113e20402fce066213861a4e0063f45a5e39
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68623704"
---
# <a name="manage-tamper-protection-for-your-organization-using-microsoft-intune"></a>Microsoft Intune kullanarak kuruluşunuz için kurcalama korumasını yönetme

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

Kuruluşunuz [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) kullanıyorsa, [Microsoft Endpoint Manager yönetim merkezinde](https://endpoint.microsoft.com) kuruluşunuz için kurcalama korumasını açabilir (veya kapatabilirsiniz). Kurcalama koruması ayarlarına ince ayar yapmak istediğinizde Intune kullanın. Örneğin, tüm cihazlarda değil bazı cihazlarda kurcalama korumasını etkinleştirmek istiyorsanız Intune kullanın.

## <a name="requirements-for-managing-tamper-protection-in-intune"></a>Intune'de kurcalama korumasını yönetme gereksinimleri

- Genel yönetici, güvenlik yöneticisi veya güvenlik işlemleri gibi uygun [izinlere](/microsoft-365/security/defender-endpoint/assign-portal-access) sahip olmanız gerekir.
- Kuruluşunuz [cihazları yönetmek için Intune](/mem/endpoint-manager-getting-started) kullanıyor. (Intune lisanslar gereklidir; Intune Microsoft 365 E3/E5, Enterprise Mobility + Security E3/E5, Microsoft 365 İş Ekstra, Microsoft 365 F1/F3, Microsoft 365 Kamu G3/G5 ve ilgili eğitim lisansları.)
- Windows cihazlarınız Windows 10 [sürüm 1709 veya üzeri ya da](/lifecycle/announcements/revised-end-of-service-windows-10-1709) Windows 11 çalıştırıyor olmalıdır. (Sürümler hakkında daha fazla bilgi için bkz. [Windows 10 sürüm bilgileri](/windows/release-health/release-information).)
- Windows güvenliğini [güvenlik bilgileri](https://www.microsoft.com/wdsi/definitions) 1.287.60.0 (veya üzeri) sürümüne güncelleştirilmiş olarak kullanıyor olmanız gerekir.
- Cihazlarınız kötü amaçlı yazılımdan koruma platformu sürüm 4.18.1906.3 (veya üzeri) ve kötü amaçlı yazılımdan koruma altyapısı sürümünü `1.1.15500.X` (veya üzeri) kullanıyor olmalıdır. ([Microsoft Defender Virüsten Koruma güncelleştirmelerini yönetin ve temelleri uygulayın](manage-updates-baselines-microsoft-defender-antivirus.md).)
- Intune ve Uç Nokta için Defender kiracılarınızın aynı Microsoft Entra (Azure Active Directory) altyapısını paylaşması gerekir.
- Cihazlarınız Uç Nokta için Defender'a eklenmelidir.

> [!NOTE]
> Cihazlarınız Uç Nokta için Microsoft Defender kayıtlı değilse, ekleme işlemi tamamlanana kadar kurcalama koruması **Uygulanamaz** olarak gösterilir.

## <a name="turn-tamper-protection-on-or-off-in-microsoft-intune"></a>Microsoft Intune'de kurcalama korumasını açma (veya kapatma)

:::image type="content" source="images/turnontamperprotectinmem.png" alt-text="Intune ile kurcalama korumasını açma" lightbox="images/turnontamperprotectinmem.png":::

1. [Microsoft Endpoint Manager yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431) **Endpoint security** \> **Virüsten Koruma'ya** gidin ve **+ İlke Oluştur'u** seçin.

   - **Platform** listesinde **Windows 10, Windows 11 ve Windows Server'ı** seçin.
   - **Profil** listesinde **Windows Güvenliği deneyim'i** seçin.

2. Aşağıdaki ayarı içeren bir profil oluşturun:

    - **TamperProtection (Cihaz): Etkinleştir**

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