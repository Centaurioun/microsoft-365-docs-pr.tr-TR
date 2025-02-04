---
title: Windows Server'da Microsoft Defender Virüsten Koruma'yı etkinleştirme ve güncelleştirme
description: Windows Server'da Microsoft Defender Virüsten Koruma'yı etkinleştirmeyi ve güncelleştirmeyi öğrenin
keywords: Windows Server, Defender Virüsten Koruma
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-smandalika
author: v-smandalika
ms.localizationpriority: high
ms.date: 08/10/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.custom: intro-overview
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 16c1dc690ad6cf297059b8589818cb57596b7a9e
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68203673"
---
# <a name="enable-and-update-defender-antivirus-to-the-latest-version-on-windows-server"></a>Defender Virüsten Koruma'yı etkinleştirme ve Windows Server'da en son sürüme güncelleştirme

Windows Server'ınızda Microsoft Defender Virüsten Koruma'yı kullanmak istiyorsanız ve daha önce devre dışı bırakılmış veya kaldırılmışsa, yeniden etkinleştirmek ve tam olarak güncelleştirildiğinden emin olmak için daha fazla adım uygulamanız gerekebilir.

Windows Server'da virüsten koruma Microsoft Defender etkinleştirmek ve güncelleştirmek için aşağıdaki adımları uygulayın:

1. En son Hizmet Yığını Güncelleştirmesini (SSU) yükleyin.
2. En son toplu güncelleştirmeyi (LCU) yükleyin.
3. Virüsten koruma Microsoft Defender yeniden yükleyin veya yeniden etkinleştirin. Windows Server'da Microsoft Defender Virüsten Koruma'yı yeniden yükleme veya yeniden etkinleştirme hakkında daha fazla bilgi için bkz. [Windows Server'da Microsoft Defender Virüsten Koruma'yı devre dışı bırakıldıysa](#re-enable-microsoft-defender-antivirus-on-windows-server-if-it-was-disabled) [yeniden etkinleştirme ve kaldırılmışsa Windows Server'da Microsoft Defender Virüsten Koruma'yı yeniden etkinleştirme](#re-enable-microsoft-defender-antivirus-on-windows-server-if-it-was-uninstalled).
4. Sistemi yeniden başlatın.
5. Platform güncelleştirmesinin en son sürümünü yükleyin.

   > [!NOTE]
   > Microsoft Defender Virüsten Koruma'nın yeniden etkinleştirilmesi platform güncelleştirmesini otomatik olarak yüklemez. Windows update'i kullanarak en son platform sürümünü indirip yükleyebilirsiniz. Alternatif olarak, güncelleştirme paketini [Microsoft Update Kataloğu'ndan](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4052623) veya [Kötü amaçlı yazılımdan koruma ve siber güvenlik portalından](https://go.microsoft.com/fwlink/?linkid=870379&arch=x64) indirebilirsiniz.
   >  
   > modern, birleşik çözümü Windows Server 2016 yüklemeye hazırlanıyorsanız, platform güncelleştirmesini ve sonraki yükleme ve ekleme işlemini otomatikleştirmek için [Yükleyici yardım betiğinden](https://github.com/microsoft/mdefordownlevelserver/blob/main/Install.ps1) yararlanabilirsiniz. Bu betik, virüsten koruma Microsoft Defender yeniden etkinleştirmeye de yardımcı olabilir.

## <a name="re-enable-microsoft-defender-antivirus-on-windows-server-if-it-was-disabled"></a>Devre dışı bırakıldıysa Windows Server'da Microsoft Defender Virüsten Koruma'yı yeniden etkinleştirme

İlk olarak, Microsoft Defender Virüsten Koruma'nın grup ilkesi veya kayıt defteri aracılığıyla devre dışı bırakılmadığından emin olun. Daha fazla bilgi için bkz[. Üçüncü taraf çözümden geçiş yaparken virüsten koruma Microsoft Defender sorunlarını giderme](/microsoft-365/security/defender-endpoint/troubleshoot-microsoft-defender-antivirus-when-migrating).

Windows Server 2016 bazı durumlarda, Microsoft Defender Virüsten Koruma'yı yeniden etkinleştirmek için [Kötü Amaçlı Yazılımdan Koruma Command-Line Yardımcı Programı'nı](command-line-arguments-microsoft-defender-antivirus.md) kullanmanız gerekebilir.

Sunucuda yerel yönetici olarak aşağıdaki adımları gerçekleştirin:

1. Komut İstemi'ni açın.
2. Aşağıdaki komutu çalıştırın: `MpCmdRun.exe -wdenable`.
3. Cihazı yeniden başlatın.

## <a name="re-enable-microsoft-defender-antivirus-on-windows-server-if-it-was-uninstalled"></a>Kaldırılmışsa Windows Server'da Microsoft Defender Virüsten Koruma'yı yeniden etkinleştirme

Defender özelliğinin kaldırılması/kaldırılması durumunda geri ekleyebilirsiniz.

Sunucuda yerel yönetici olarak aşağıdaki adımları gerçekleştirin:

1. Windows PowerShell açın.

2. Aşağıdaki komutları çalıştırın:

   ```powershell
   # For Windows Server 2016
   Dism /Online /Enable-Feature /FeatureName:Windows-Defender-Features
   Dism /Online /Enable-Feature /FeatureName:Windows-Defender
   Dism /Online /Enable-Feature /FeatureName:Windows-Defender-Gui
   
   # For Windows Server 1803 and later, including Windows Server 2019 and 2022
   Dism /Online /Enable-Feature /FeatureName:Windows-Defender
   ```

   DISM komutu PowerShell çalıştıran bir görev dizisi içinde kullanıldığında, aşağıdaki cmd.exe yolu gereklidir.
   
   ```powershell
   C:\Windows\System32\cmd.exe /c Dism /Online /Enable-Feature /FeatureName:Windows-Defender-Features
   C:\Windows\System32\cmd.exe /c Dism /Online /Enable-Feature /FeatureName:Windows-Defender
   ```

   > [!NOTE]
   > Microsoft Defender Virüsten Koruma özelliğini yüklemek için Sunucu Yöneticisi veya PowerShell cmdlet'lerini de kullanabilirsiniz.

3. Sistemi yeniden başlatın.
