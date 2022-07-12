---
title: Uç Nokta için Microsoft Defender geçiş yapma - Ekleme
description: Uç Nokta için Microsoft Defender geçişini yapın. Cihazları ekleyin ve ardından Microsoft dışı çözümünüzü kaldırın.
keywords: geçiş, Uç Nokta için Microsoft Defender, edr
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.custom:
- migrationguides
- admindeeplinkDEFENDER
ms.topic: article
ms.date: 04/01/2022
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: d927f1a5972e24c3bae0329bd866a4b56b0a5d95
ms.sourcegitcommit: c314e989202dc1c9c260fffd459d53bc1f08514e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2022
ms.locfileid: "66717260"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>Uç Nokta için Microsoft Defender Geçiş - 3. Aşama: Ekleme

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![1. Aşama: Hazırlama3.](images/phase-diagrams/prepare.png#lightbox)](switch-to-mde-phase-1.md)<br/>[Aşama 1: Hazırlık](switch-to-mde-phase-1.md) | [![Aşama 2: Kurulum](images/phase-diagrams/setup.png#lightbox)](switch-to-mde-phase-2.md)<br/>[Aşama 2: Kurulum](switch-to-mde-phase-2.md) | ![Aşama 3: Katılım](images/phase-diagrams/onboard.png#lightbox)<br/>Aşama 3: Katılım |
|--|--|--|
|| |*Buradasınız!* |

**[Uç Nokta için Defender'a geçmenin 3. Aşamasına](switch-to-mde-overview.md#the-migration-process) hoş geldiniz**. Bu geçiş aşaması aşağıdaki adımları içerir:

1. [Uç Nokta için Defender'a cihaz ekleme](#onboard-devices-to-microsoft-defender-for-endpoint).
2. [Algılama testi çalıştırın](#run-a-detection-test).
3. [Microsoft Defender Virüsten Koruma'nın uç noktalarınızda pasif modda olduğunu onaylayın](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints).
4. [Microsoft Defender Virüsten Koruma güncelleştirmelerini alın](#get-updates-for-microsoft-defender-antivirus).
5. [Microsoft dışı çözümünüzü kaldırın](#uninstall-your-non-microsoft-solution).
6. [Uç Nokta için Defender'ın düzgün çalıştığından emin olun](#make-sure-defender-for-endpoint-is-working-correctly).

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Cihazları Uç Nokta için Microsoft Defender ekleme

1. Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com)) gidin ve oturum açın.

2. **Ayarlar** \> **Uç Noktaları** \> **Ekleme'yi** seçin (**Cihaz yönetimi'nin** altında).

3. **Ekleme işlemini başlatmak için işletim sistemini seçin** listesinde bir işletim sistemi seçin.

4. **Dağıtım yöntemi'nin** altında bir seçenek belirleyin. Kuruluşunuzun cihazlarını eklemek için bağlantıları ve istemleri izleyin. Yardıma mı ihtiyacınız var? Bkz [. Ekleme yöntemleri](#onboarding-methods) (bu makalede).

> [!NOTE]
> Ekleme sırasında bir sorun olursa bkz. [Ekleme sorunlarını giderme Uç Nokta için Microsoft Defender](troubleshoot-onboarding.md). Bu makalede, uç noktalarda ekleme sorunlarının ve yaygın hataların nasıl çözüleceğini açıklar.

### <a name="onboarding-methods"></a>Ekleme yöntemleri

> [!IMPORTANT]
> Bulut için Microsoft Defender kullanıyorsanız bkz. [Bulut için Microsoft Defender ile tümleştirme](configure-server-endpoints.md#integration-with-microsoft-defender-for-cloud).

Dağıtım yöntemleri, işletim sistemine ve tercih edilen yöntemlere bağlı olarak değişir. Aşağıdaki tabloda Uç Nokta için Defender'a eklemeye yardımcı olacak kaynaklar listeleniyor:

|İşletim sistemleri  |Yöntemler  |
|---------|---------|
|Windows 10 veya üzeri<br/><br/>Windows Server 2019 veya üzeri<br/><br/>Windows Server, sürüm 1803 veya üzeri<br/><br/>Windows Server 2012 R2 ve 2016<sup>[[1](#fn1)]<sup>  |   [Yerel betik (en fazla 10 cihaz)](configure-endpoints-script.md)<br><br/>   [Grup İlkesi](configure-endpoints-gp.md)<br/><br/>[Microsoft Uç Noktası Yapılandırma Yöneticisi](configure-endpoints-sccm.md)<br/><br/>[Microsoft Endpoint Manager/ Mobile Cihaz Yönetimi (Intune)](configure-endpoints-mdm.md)<br>    [VDI betikleri](configure-endpoints-vdi.md) <br><br> **NOT**: Yerel betik kavram kanıtı için uygundur ancak üretim dağıtımı için kullanılmamalıdır. Üretim dağıtımı için grup ilkesi, Microsoft Endpoint Configuration Manager veya Intune kullanmanızı öneririz. |
|Windows Server 2008 R2 SP1 | [Microsoft Monitoring Agent (MMA)](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma)  veya [Bulut için Microsoft Defender](/azure/security-center/security-center-wdatp) <br><br> **NOT**: Microsoft Monitoring Agent artık Azure Log Analytics aracısıdır. Daha fazla bilgi için bkz [. Log Analytics aracısına genel bakış](/azure/azure-monitor/platform/log-analytics-agent).  |
|Windows 8.1 Enterprise<br/><br/>Windows 8.1 Pro<br/><br/>Windows 7 SP1 Pro<br/><br/>Windows 7 SP1| [Microsoft Monitoring Agent (MMA)](onboard-downlevel.md) <br><br> **NOT**: Microsoft Monitoring Agent artık Azure Log Analytics aracısıdır. Daha fazla bilgi için bkz [. Log Analytics aracısına genel bakış](/azure/azure-monitor/platform/log-analytics-agent).  
| macOS (bkz [. Sistem gereksinimleri](microsoft-defender-endpoint-mac.md) | [Yerel betik](mac-install-manually.md)<br/><br/>[Microsoft Endpoint Manager](mac-install-with-intune.md)<br/><br/>[JAMF Pro](mac-install-with-jamf.md)<br/><br/>[Mobil Cihaz Yönetimi](mac-install-with-other-mdm.md)   |
| Linux (bkz [. Sistem gereksinimleri](microsoft-defender-endpoint-linux.md#system-requirements)) |  [Yerel betik](linux-install-manually.md) <br><br/> [Kukla](linux-install-with-puppet.md) <br><br/> [Ansible](linux-install-with-ansible.md)|  
| iOS | [Microsoft Endpoint Manager](ios-install.md)     |
|Android  | [Microsoft Endpoint Manager](android-intune.md)  | 

(<a id="fn1">1</a>) Windows Server 2016 ve Windows Server 2012 R2'nin [Windows sunucularında](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016) ekleme yönergeleri kullanılarak eklenmesi gerekir.

## <a name="run-a-detection-test"></a>Algılama testi çalıştırma

Eklenen cihazlarınızın Uç Nokta için Defender'a düzgün şekilde bağlandığını doğrulamak için bir algılama testi çalıştırabilirsiniz.

|İşletim sistemi|Rehberlik|
|---|---|
|Windows 10 veya üzeri<br/><br/>Windows Server 2022<br/><br/>Windows Server 2019<br/><br/>Windows Server, sürüm 1803 veya üzeri<br/><br/>Windows Server 2016<br/><br/>Windows Server 2012 R2|Bkz [. Algılama testi çalıştırma](run-detection-test.md).|
|macOS (bkz [. Sistem gereksinimleri](microsoft-defender-endpoint-mac.md)|adresinden DIY uygulamasını <https://aka.ms/mdatpmacosdiy>indirin ve kullanın. <br/><br/> Daha fazla bilgi için bkz. [macOS'ta Uç Nokta için Defender](microsoft-defender-endpoint-mac.md).|
|Linux (bkz [. Sistem gereksinimleri](microsoft-defender-endpoint-linux.md#system-requirements))|1. Aşağıdaki komutu çalıştırın ve **1** sonucunu arayın: `mdatp health --field real_time_protection_enabled`.<br/><br/>2. Bir Terminal penceresi açın ve şu komutu çalıştırın: `curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`.<br/><br/>3. Algılanan tehditleri listelemek için aşağıdaki komutu çalıştırın: `mdatp threat list`.<br/><br/>Daha fazla bilgi için bkz. [Linux'ta Uç Nokta için Defender](microsoft-defender-endpoint-linux.md).|

## <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints"></a>Microsoft Defender Virüsten Koruma'nın uç noktalarınızda pasif modda olduğunu onaylayın

Uç noktalarınızın Uç Nokta için Defender'a eklendiğine göre, sonraki adımınız Microsoft Defender Virüsten Koruma'nın pasif modda çalıştığından emin olmaktır. Aşağıdaki tabloda açıklandığı gibi çeşitli yöntemlerden birini kullanabilirsiniz:

|Yöntem|Yapılması gerekenler|
|---|---|
|Komut|1. Bir Windows cihazında Komut İstemi'ni açın.<br/><br/>2. yazın `sc query windefend`ve Enter tuşuna basın.<br/><br/>3. Microsoft Defender Virüsten Koruma'nın pasif modda çalıştığını onaylamak için sonuçları gözden geçirin.|
|PowerShell|1. Bir Windows cihazında Windows PowerShell yönetici olarak açın.<br/><br/>2. Aşağıdaki PowerShell cmdlet'ini çalıştırın: `Get-MpComputerStatus|select AMRunningMode`. <br/><br/>3. Sonuçları gözden geçirin. **Pasif modu** görmeniz gerekir.|
|Windows Güvenliği uygulaması|1. Windows cihazında Windows Güvenliği uygulamasını açın.<br/><br/>2. **Virüs & tehdit koruması'ı** seçin.<br/><br/>3. **Beni kim koruyor?** altında **Sağlayıcıları yönet'i** seçin.<br/><br/>4. **Güvenlik sağlayıcıları** sayfasındaki **Virüsten Koruma'nın** altında **Microsoft Defender Virüsten Koruma'nın açık olup olmadığını** denetleyin.|
|Görev Yöneticisi|1. Bir Windows cihazında Görev Yöneticisi uygulamasını açın.<br/><br/>2. **Ayrıntılar** sekmesini seçin. Listede **MsMpEng.exe** arayın.|

> [!NOTE]
> Bazı Windows sürümlerinde *Microsoft Defender Virüsten Koruma* yerine *Windows Defender Virüsten Koruma* görebilirsiniz.
> Pasif mod ve etkin mod hakkında daha fazla bilgi edinmek için bkz. [Microsoft Defender Virüsten Koruma durumları hakkında daha fazla ayrıntı](microsoft-defender-antivirus-compatibility.md#more-details-about-microsoft-defender-antivirus-states).

### <a name="set-microsoft-defender-antivirus-on-windows-server-to-passive-mode-manually"></a>Windows Server'da Microsoft Defender Virüsten Koruma'yı pasif moda el ile ayarlama

Microsoft Defender Virüsten Koruma'yı Windows Server, sürüm 1803 veya üzeri ya da Windows Server 2019 ya da Windows Server 2022'de pasif moda ayarlamak için şu adımları izleyin:

1. Kayıt Defteri Düzenleyicisi'ni açın ve öğesine `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`gidin.

2. **ForceDefenderPassiveMode** adlı bir DWORD girdisini düzenleyin (veya oluşturun) ve aşağıdaki ayarları belirtin:

   - DWORD değerini **1** olarak ayarlayın.

   - **Temel'in** altında **Onaltılık** seçeneğini belirleyin.

> [!NOTE]
> Kayıt defteri anahtarını ayarlamak için aşağıdakiler gibi diğer yöntemleri kullanabilirsiniz:
>
> - [grup ilkesi Tercihi](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
> - [Yerel grup ilkesi Nesnesi aracı](/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
> - [Configuration Manager'da bir paket](/mem/configmgr/apps/deploy-use/packages-and-programs)

### <a name="start-microsoft-defender-antivirus-on-windows-server-2016"></a>Windows Server 2016'de Microsoft Defender Virüsten Koruma'ya başlama

Windows Server 2016 kullanıyorsanız Microsoft Defender Virüsten Koruma'yı el ile başlatmanız gerekebilir. Bu görevi, cihazdaki PowerShell cmdlet'ini `mpcmdrun.exe -wdenable` kullanarak gerçekleştirebilirsiniz.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Microsoft Defender Virüsten Koruma güncelleştirmelerini alma

Microsoft Defender Virüsten Koruma'nın güncel tutulması, Microsoft Defender Virüsten Koruma pasif modda çalışıyor olsa bile cihazlarınızın yeni kötü amaçlı yazılımlara ve saldırı tekniklerine karşı korunmak için gereken en son teknolojiye ve özelliklere sahip olduğundan emin olmak açısından kritik öneme sahiptir. (Bkz [. Microsoft Defender Virüsten Koruma uyumluluğu](microsoft-defender-antivirus-compatibility.md).)

Microsoft Defender Virüsten Koruma'nın güncel tutulmasıyla ilgili iki tür güncelleştirme vardır:

- Güvenlik bilgileri güncelleştirmeleri

- Ürün güncelleştirmeleri

Güncelleştirmelerinizi almak için [Microsoft Defender Virüsten Koruma güncelleştirmelerini yönetme ve temelleri uygulama](manage-updates-baselines-microsoft-defender-antivirus.md) makalesindeki yönergeleri izleyin.

## <a name="uninstall-your-non-microsoft-solution"></a>Microsoft dışı çözümünüzü kaldırma

Bu noktada aşağıdakilere sahipseniz:

- Kuruluşunuzun cihazlarını Uç Nokta için Defender'a ekleyip

- Microsoft Defender Virüsten Koruma yüklü ve etkin,

Sonraki adımınız Microsoft dışı virüsten koruma, kötü amaçlı yazılımdan koruma ve uç nokta koruma çözümünüzü kaldırmaktır. Microsoft dışı çözümünüzü kaldırdığınızda, Microsoft Defender Virüsten Koruma pasif moddan etkin moda geçer. Çoğu durumda, bu otomatik olarak gerçekleşir. 

> [!IMPORTANT]
> Herhangi bir nedenle, Microsoft dışı virüsten koruma/kötü amaçlı yazılımdan koruma çözümünüzü kaldırdıktan sonra Microsoft Defender Virüsten Koruma etkin moda geçmezse bkz. [Microsoft Defender Virüsten Koruma pasif modda takılı kalmış gibi görünüyor](switch-to-mde-troubleshooting.md#microsoft-defender-antivirus-seems-to-be-stuck-in-passive-mode).

Microsoft dışı çözümünüzü kaldırma konusunda yardım almak için teknik destek ekibine başvurun.

## <a name="make-sure-defender-for-endpoint-is-working-correctly"></a>Uç Nokta için Defender'ın düzgün çalıştığından emin olun

Uç Nokta için Defender'a eklediğinize ve eski Microsoft dışı çözümünüzü kaldırdığınıza göre, sonraki adımınız Uç Nokta için Defender'ın düzgün çalıştığından emin olmaktır. 

1. Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com)) gidin ve oturum açın.

2. Gezinti bölmesinde **Uç Noktalar****Cihaz envanteri'ni** >  seçin. Burada, cihazlar için koruma durumunu görebilirsiniz.

Daha fazla bilgi için bkz [. Cihaz envanteri](machines-view-overview.md).

## <a name="next-steps"></a>Sonraki adımlar

**Tebrikler**! [Uç Nokta için Defender'a geçişinizi](switch-to-mde-overview.md#the-migration-process) tamamladınız!

- Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com) ) [güvenlik işlemleri panonuzu ziyaret edin](security-operations-dashboard.md).

- [Geçiş sonrasında Uç Nokta için Defender'ı yönetin](manage-mde-post-migration.md).
