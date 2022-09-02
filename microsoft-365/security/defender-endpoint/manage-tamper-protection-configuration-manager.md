---
title: Configuration Manager, sürüm 2006 ile kiracı ekleme kullanarak kurcalama korumasını yönetme
ms.reviewer: mattcall, pahuijbr, hayhov, oogunrinde
manager: dansimp
description: Configuration Manager ile kiracı ekleme özelliğini kullanarak kurcalama korumasını açın veya kapatın.
keywords: kötü amaçlı yazılım, defender, virüsten koruma, kurcalama koruması, Configuration Manager
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
ms.openlocfilehash: 32ea905c1ab6aaaa3a49cd7e2e40b0cadbf05284
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67521937"
---
# <a name="manage-tamper-protection-using-tenant-attach-with-configuration-manager-version-2006"></a>Configuration Manager, sürüm 2006 ile kiracı ekleme kullanarak kurcalama korumasını yönetme

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

[Configuration Manager 2006 sürümünü](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006) kullanıyorsanız çoklu oturum, Windows 11 Windows 11 Enterprise çoklu oturum Windows 10 Enterprise Windows 10 üzerinde kurcalama koruma ayarlarını yönetebilirsiniz. *Kiracı ekleme* adlı bir yöntem kullanarak R2, Windows Server 2016, Windows Server 2019 ve Windows Server 2022'yi Windows Server 2012. Kiracı ekleme, yalnızca şirket içi Configuration Manager cihazlarınızı Microsoft Endpoint Manager yönetim merkeziyle eşitlemenize ve ardından uç nokta güvenlik yapılandırma ilkelerini şirket içi koleksiyonlara & cihazlara sunmanıza olanak tanır.

> [!NOTE]
> Bu yordam, çok oturumlu, Windows 11 Windows 11 Enterprise çoklu oturum, Windows Server 2019 ve Windows Server 2022 Windows 10 Enterprise Windows 10 çalıştıran cihazlara kurcalama korumasını genişletmek için kullanılabilir. Bu yordamda belirtilen kaynaklarda yer alan önkoşulları ve diğer bilgileri gözden geçirmeyi unutmayın. Windows Server 2012 R2 için Configuration Manager'nin modern, birleşik çözüm [sürümü 2203](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2203) gereklidir.

1. Kiracı eklemeyi ayarlayın. Daha fazla bilgi edinmek için bkz [. Kullanmaya başlama: Yönetim merkezinden uç nokta güvenlik ilkeleri oluşturma ve dağıtma](/mem/configmgr/tenant-attach/endpoint-security-get-started).

2. [Microsoft Endpoint Manager yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431) **Endpoint security** \> **Virüsten Koruma'ya** gidin ve **+ İlke Oluştur'u** seçin.

   - **Platform** listesinde **Windows 10, Windows 11 ve Windows Server (ConfigMgr)** seçeneğini belirleyin.
   - **Profil** listesinde **Windows Güvenliği deneyimi (önizleme)** seçeneğini belirleyin.

3. İlkeyi cihaz koleksiyonunuz için dağıtın.

## <a name="need-help-with-this-method"></a>Bu yöntemle ilgili yardıma mı ihtiyacınız var?

Aşağıdaki kaynaklara bakın:

- [Microsoft Intune'da Windows Güvenliği deneyimi profilinin ayarları](/mem/intune/protect/antivirus-security-experience-windows-settings)
- [Teknoloji Topluluğu Blogu: Configuration Manager Kiracı Ekleme istemcileri için Kurcalama Koruması Duyuruları](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)