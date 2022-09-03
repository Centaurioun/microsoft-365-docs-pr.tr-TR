---
title: Adım 4. Cihazları koruyun
author: dansimp
f1.keywords:
- NOCSH
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- ransomware
- m365solution-ransomware
ms.custom: seo-marvel-jun2020
keywords: fidye yazılımı, insan tarafından çalıştırılan fidye yazılımı, insan tarafından çalıştırılan fidye yazılımı, HumOR, gasp saldırısı, fidye yazılımı saldırısı, şifreleme, kriptoviroloji, sıfır güven
description: MDA ve MAM sağlayıcısı olarak Windows Intune kullanın ve Microsoft 365 kaynaklarınızı fidye yazılımı saldırılarına karşı korumak için güvenlik özelliklerini Windows 10.
ms.openlocfilehash: 9f19831391316e22cb6403b4fd55ba59a3f9f07e
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67581234"
---
# <a name="step-4-protect-devices"></a>Adım 4. Cihazları koruyun

Cihazları (uç noktaları) fidye yazılımı saldırısının ilk erişim bölümüne karşı korumaya yardımcı olmak için:

- [Intune](/mem/intune/fundamentals/what-is-intune) cihazlarınız için mobil cihaz yönetimi (MDM) ve mobil uygulama yönetimi (MAM) sağlayıcısı olarak dağıtın ve kuruluşunuzun sahip olduğu cihazları kaydedin.
- Kullanıcı hesabı kimlik bilgilerini doğrulamak ve cihaz sistem durumu ve uyumluluk gereksinimlerini zorunlu kılmak için [Ortak kimlik ve cihaz erişim ilkelerini](/microsoft-365/security/office-365-security/identity-access-policies) uygulayın.
- Uç Nokta için Microsoft Defender ve Microsoft 365 Defender'de [Ağ Koruması'nı](/microsoft-365/security/defender-endpoint/network-protection) etkinleştirin.
- Engellemek [veya](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings) uyarmak için Microsoft Defender SmartScreen'te site [ve indirme denetimini, uygulama ve dosya denetimini](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings) yapılandırın.
- İndirilen dosya ve eklerde [Microsoft Defender Virüsten Koruma taramasını](/microsoft-365/security/defender-endpoint/configure-advanced-scan-types-microsoft-defender-antivirus) etkinleştirin.
- **uzak masaüstü güvenlik düzeyini** Uç Nokta için Microsoft Defender ve Microsoft 365 Defender **TLS** olarak ayarlayın.

## <a name="windows-11-or-10-devices"></a>Windows 11 veya 10 cihaz

Bir saldırının yanal hareket parçasına karşı Windows 11 veya 10 cihazdan korunmaya yardımcı olmak için:

- [Microsoft Defender Güvenlik Duvarı'nı açın](https://support.microsoft.com/windows/turn-microsoft-defender-firewall-on-or-off-ec0844f7-aebd-0583-67fe-601ecf5d774f).
- [Microsoft Defender Virüsten Koruma tanımlarını güncelleştirin](/microsoft-365/security/defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus).

Saldırının etkisini azaltmak için:

- [Saldırı yüzeyi azaltma kurallarını ve fidye yazılımlara karşı gelişmiş korumayı](/microsoft-365/security/defender-endpoint/attack-surface-reduction-rules-reference#use-advanced-protection-against-ransomware) kullanın.

Güvenlik savunmalarınızı atlatan bir saldırgana karşı korunmaya yardımcı olmak için:

- Microsoft Defender Virüsten Koruma'da [bulut tabanlı korumayı](/microsoft-365/security/defender-endpoint/enable-cloud-protection-microsoft-defender-antivirus) açık tutun.
- Microsoft Defender Virüsten Koruma [gerçek zamanlı davranış izleme özelliğini](/microsoft-365/security/defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus) açık tutun.
- [Gerçek zamanlı korumayı](/microsoft-365/security/defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus) açın.
- Güvenlik ayarlarında kötü amaçlı değişiklikler yapılmasını önlemek için [Uç Nokta için Microsoft Defender'de kurcalama korumasını](/microsoft-365/security/defender-endpoint/prevent-changes-to-security-settings-with-tamper-protection) açın.

Bir saldırının parçası olarak kod yürüten bir saldırgana karşı korunmaya yardımcı olmak için:

- [Microsoft Defender Virüsten Koruma'nı](/mem/intune/user-help/turn-on-defender-windows) açın.
- [Office makrolarından Win32 API çağrılarını engelleyin](/microsoft-365/security/defender-endpoint/attack-surface-reduction-rules#block-win32-api-calls-from-office-macros).
- [Bu işlemi](https://www.microsoft.com/microsoft-365/blog/2010/02/16/migrating-excel-4-macros-to-vba/) kullanarak Excel 4.0 makroları gerektiren tüm eski çalışma kitaplarını güncelleştirilmiş VBA makro biçimine geçirin.
- [İmzalanmamış makroların kullanımını devre dışı bırakın](https://support.microsoft.com/topic/enable-or-disable-macros-in-office-files-12b036fd-d140-4e74-b45e-16fed1a7e5c6). ortamınızda bilinmeyen makroların çalışmadığından emin olmak için iş gereksinimi olan tüm iç makroların imzalandığından ve [güvenilen konumlardan](/deployoffice/security/designate-trusted-locations-for-files-in-office) yararlanıldığından emin olun.
- [Kötü Amaçlı Yazılımdan Koruma Tarama Arabirimi](https://www.microsoft.com/security/blog/2021/03/03/xlm-amsi-new-runtime-defense-against-excel-4-0-macro-malware/) (AMSI) tarafından çalışma zamanı makro taramasının açık olduğundan emin olarak kötü amaçlı XLM veya VBA makrolarını durdurun. **Makro Çalışma Zamanı Tarama Kapsamı** için grup ilkesi ayarı **Tüm Dosyalar için Etkinleştir** veya **Düşük Güven Dosyaları için Etkinleştir** olarak ayarlandıysa, bu özellik (varsayılan olarak etkindir) açıktır. En son grup ilkesi şablon dosyalarını alın.

## <a name="impact-on-users-and-change-management"></a>Kullanıcılar ve değişiklik yönetimi üzerindeki etkisi

Bu korumaları uygularken aşağıdakiler için değişiklik yönetimi gerçekleştirin:

- [Yaygın Sıfır Güven kimlik ve cihaz erişim ilkeleri](/microsoft-365/security/office-365-security/identity-access-policies), uyumlu olmayan cihazlara sahip kullanıcılara erişimi reddedebilir.
- Dosyaların indirilmesi, indirmeden önce kullanıcıları uyarabilir veya engellenebilir.
- Bazı Office, Excel 4.0, XLM veya VBA makroları artık çalışmayabilir.

## <a name="resulting-configuration"></a>Sonuçta elde edilen yapılandırma

1-4 arası adımlar için kiracınız için fidye yazılımı koruması aşağıdadır.

![4. Adımdan sonra Microsoft 365 kiracınız için fidye yazılımı koruması](../media/ransomware-protection-microsoft-365/ransomware-protection-microsoft-365-architecture-step4.png)

## <a name="next-step"></a>Sonraki adım

[![Microsoft 365 ile fidye yazılımı koruması için 5. Adım](../media/ransomware-protection-microsoft-365/ransomware-protection-microsoft-365-step5.png)](ransomware-protection-microsoft-365-information.md)

Microsoft 365 kiracınızdaki bilgileri korumak için [5. Adımla](ransomware-protection-microsoft-365-information.md) devam edin. 
