---
title: Microsoft 365 İş Ekstra'da yönetilmeyen Windows bilgisayarlarını ve Mac'leri koruma
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-security
ms.subservice: other
ms.date: 09/15/2022
ms.localizationpriority: high
ms.collection:
- M365-Campaigns
- m365solution-smb
- highpri
- tier1
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
description: yönetilmeyen veya kendi cihazını getir (KCG) Microsoft 365 İş Ekstra ile siber saldırılara karşı koruyun. Windows bilgisayarlar ve Mac'ler için siber güvenliği ayarlama.
ms.openlocfilehash: 7d2bcacf0ff2bb68309eb5482a87594de494feda
ms.sourcegitcommit: 0283c436f3ba61a708b52b57a1955f5ea74376a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2022
ms.locfileid: "68097434"
---
# <a name="protect-unmanaged-windows-pcs-and-macs-in-microsoft-365-business-premium"></a>Microsoft 365 İş Ekstra'da yönetilmeyen Windows bilgisayarlarını ve Mac'leri koruma

Bu amaç, Microsoft Intune kayıtlı olmayan yönetilmeyen Windows 10 bilgisayarlar ve Mac'ler için koruma oluşturmaya odaklanmıştır. Büyük olasılıkla küçük işletmeniz veya kampanyanızda kendi cihazlarını (KCG) getiren personel olabilir ve bu cihazlar yönetilmiyor olabilir. KCG kişisel telefonları, tabletleri ve bilgisayarları içerir.

> [!NOTE]
> KCG kullanıcılarının bu cihazları kaydetmek ve şirket kaynaklarına erişim almak için Şirket Portalı uygulamasını yüklemesi ve çalıştırması gerekir.

Ön cephe kullanıcılarınızın tüm KCG cihazlarında en düşük güvenlik özelliklerinin yapılandırılması için bu yönergeleri izlemeniz kritik önem taşır.

## <a name="windows-10-or-11"></a>[Windows 10 veya 11](#tab/Windows10-11)

## <a name="windows-10-or-11"></a>Windows 10 veya 11

### <a name="turn-on-device-encryption"></a>Cihaz şifrelemeyi açma

Cihaz şifrelemesi çok çeşitli Windows cihazlarında kullanılabilir ve verilerinizi şifreleyerek korunmasına yardımcı olur. Cihaz şifrelemeyi açarsanız, cihazınıza ve verilerinize yalnızca yetkili kişiler erişebilir. Yönergeler için bkz. [Cihaz şifrelemesini açma](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) .

 Cihazınızda cihaz şifrelemesi kullanılamıyorsa bunun yerine standart [BitLocker şifrelemeyi](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) açabilirsiniz. (BitLocker Windows 10 Home sürümünde kullanılamaz.) 

### <a name="protect-your-device-with-windows-security"></a>Cihazınızı Windows Güvenliği ile koruma

Windows 10 veya 11'iniz varsa, Windows Güvenliği ile en son virüsten korumayı alırsınız. Windows 10 ilk kez başlattığınızda, Windows Güvenliği açık olur ve kötü amaçlı yazılım, virüs ve güvenlik tehditlerini tarayarak bilgisayarınızın korunmasına etkin bir şekilde yardımcı olur. Windows Güvenliği, bilgisayarınızda indirdiğiniz veya çalıştırdığınız her şeyi taramak için gerçek zamanlı koruma kullanır.

Windows Update, bilgisayarınızın güvende kalmasına ve tehditlere karşı korunmasına yardımcı olmak için Windows Güvenliği güncelleştirmelerini otomatik olarak indirir.

Windows'un önceki bir sürümüne sahipseniz ve Microsoft Security Essentials kullanıyorsanız, Windows Güvenliği geçmek iyi bir fikirdir. Daha fazla bilgi için bkz. [Windows Güvenliği ile cihazımın korunmasına yardımcı olun](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).

### <a name="turn-on-windows-defender-firewall"></a>Windows Defender Güvenlik Duvarı'nı açma

Başka bir güvenlik duvarı açık olsa bile Windows Defender Güvenlik Duvarı'nı her zaman çalıştırmanız gerekir. Windows Defender Güvenlik Duvarı'nı kapatmak cihazınızı (ve varsa ağınızı) yetkisiz erişime karşı daha savunmasız hale getirir. Yönergeler için bkz [. Windows Güvenlik Duvarı'nı açma veya kapatma](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) .

## <a name="next-mission"></a>Sonraki görev

Tamam, görev tamamlandı! Şimdi [e-posta sisteminin](m365bp-protect-email-overview.md) kimlik avına ve diğer saldırılara karşı güvenliğini sağlamaya çalışalım.

## <a name="mac"></a>[Mac](#tab/Mac)

## <a name="mac"></a>Mac

### <a name="use-filevault-to-encrypt-your-mac-disk"></a>Mac diskinizi şifrelemek için FileVault kullanma

Disk şifrelemesi, cihazlar kaybolduğunda veya çalındığında verileri korur. FileVault tam disk şifrelemesi, başlangıç diskinizde bilgilere yetkisiz erişimi önlemeye yardımcı olur. Yönergeler için bkz. [Mac'inizdeki başlangıç diskini şifrelemek için FileVault kullanma](https://support.apple.com/HT204837) .

### <a name="protect-your-mac-from-malware"></a>Mac'inizi kötü amaçlı yazılımlardan koruma

Microsoft, Mac bilgisayarınıza güvenilir virüsten koruma yazılımı yüklemenizi ve kullanmanızı önerir. Seçeneklerin listesi için aşağıdaki makaleye bakın: [En iyi Mac virüsten koruma 2019](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).

Ayrıca, yalnızca güvenilir kaynaklardan gelen yazılımları kullanarak kötü amaçlı yazılım riskini azaltabilirsiniz. Güvenlik & Gizlilik tercihleri'ndeki ayarlar, Mac bilgisayarınızda yüklü olan yazılım kaynaklarını belirtmenize olanak sağlar. Daha fazla bilgi için bkz. [Mac'inizi kötü amaçlı yazılımlardan koruma](https://support.apple.com/kb/PH25087).

### <a name="turn-on-firewall-protection"></a>Güvenlik duvarı korumasını açma

Mac'inizi İnternet'e veya ağa bağlı olduğunuzda diğer bilgisayarlar tarafından başlatılan istenmeyen kişilerden korumak için güvenlik duvarı ayarlarını kullanın. Bu koruma olmadan, Mac'iniz yetkisiz erişime karşı daha savunmasız olabilir. Yönergeler için [uygulama güvenlik duvarı hakkında](https://support.apple.com/HT201642) bilgi alın.

## <a name="next-mission"></a>Sonraki görev

Tamam, görev tamamlandı! Şimdi kimlik avı ve diğer [saldırılara karşı e-posta kullanımını güvenli hale getirme](m365bp-protect-email-overview.md) üzerinde çalışalım.