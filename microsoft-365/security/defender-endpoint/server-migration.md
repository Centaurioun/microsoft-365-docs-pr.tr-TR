---
title: yeni Uç Nokta için Microsoft Defender sürümü için sunucu geçişi senaryoları
description: Sunucularınızı önceki MMA tabanlı çözümden geçerli Uç Nokta için Defender birleşik çözüm paketine geçirme hakkında genel bir bakış edinmek için bu makaleyi okuyun.
keywords: sunucuyu geçirme, sunucu, 2012r2, 2016, sunucu geçişi, cihaz yönetimi, Uç Nokta için Microsoft Defender sunucuları yapılandırma, Uç Nokta için Microsoft Defender sunucuları ekleme
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
ms.localizationpriority: medium
ms.date: 09/19/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 0720eb69c37b9767d96819cdea431422bed145a1
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68625973"
---
# <a name="server-migration-scenarios-from-the-previous-mma-based-microsoft-defender-for-endpoint-solution"></a>Önceki MMA tabanlı Uç Nokta için Microsoft Defender çözümünden sunucu geçişi senaryoları

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- Windows Server 2012 R2
- Windows Server 2016
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> [!NOTE]
> Yükleme veya yükseltme işlemine devam etmeden önce her zaman işletim sisteminin ve Windows Server 2016 virüsten koruma Microsoft Defender tam olarak güncelleştirildiğinden emin olun. EDR Algılayıcı bileşenine yönelik düzenli ürün iyileştirmeleri ve düzeltmeleri almak için[, Windows Update KB5005292'nin](https://go.microsoft.com/fwlink/?linkid=2168277) yüklendiğinden veya yüklendikten sonra onay aldığından emin olun. Ayrıca, koruma bileşenlerini güncel tutmak için lütfen [Virüsten koruma güncelleştirmelerini yönetme ve temelleri uygulama Microsoft Defender](/microsoft-365/security/defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) başvurun.

Bu yönergeler, Windows Server 2012 R2 ve Windows Server 2016 için Uç Nokta için Microsoft Defender yeni birleşik çözüm ve yükleyici (MSI) paketi için geçerlidir. Bu makale, öncekinden geçerli çözüme çeşitli olası geçiş senaryoları için üst düzey yönergeler içerir. Bu üst düzey adımlar, ortamınızda bulunan dağıtım ve yapılandırma araçlarına ayarlanacak yönergeler olarak tasarlanmıştır. 

**Dağıtımı gerçekleştirmek için Bulut için Microsoft Defender kullanıyorsanız, yüklemeyi ve yükseltmeyi otomatikleştirebilirsiniz. Bkz [. Sunucular için Defender Plan 2 artık MDE birleşik çözümüyle tümleşiyor](https://techcommunity.microsoft.com/t5/microsoft-defender-for-cloud/defender-for-servers-plan-2-now-integrates-with-mde-unified/ba-p/3527534)**

> [!NOTE]
> Uç Nokta için Microsoft Defender yüklü işletim sistemi yükseltmeleri desteklenmez. Lütfen çıkarma ve kaldırma, işletim sistemini yükseltme ve ardından yükleme işlemine devam edin.

> [!NOTE]
> Otomatik yükseltme gerçekleştirmek için tam Microsoft Endpoint Configuration Manager otomasyonu ve tümleştirmesi, MECM'nin sonraki bir sürümünde kullanıma sunulacaktır. En son düzeltme paketine sahip 2107 sürümünden, yapılandırmanın yanı sıra grup ilkesi, PowerShell, Microsoft Endpoint Manager kiracı ekleme veya yerel yapılandırma için Endpoint Protection düğümünü kullanabilirsiniz. Ayrıca, el ile yükseltme adımlarını otomatikleştirmek için Microsoft Endpoint Configuration Manager'daki mevcut işlevlerden yararlanabilirsiniz; yöntemleri aşağıda açıklanmıştır.

## <a name="installer-script"></a>Yükleyici betiği

>[!NOTE]
>Betiği çalıştırdığınız makinelerin betiğin yürütülmesini engellemediğinden emin olun. PowerShell için önerilen yürütme ilkesi ayarı Allsigned'dır. Betik uç noktada SYSTEM olarak çalışıyorsa bu, betiğin imzalama sertifikasının Yerel Bilgisayar Güvenilen Yayımcılar deposuna aktarılmasını gerektirir.

Microsoft Endpoint Configuration Manager henüz kullanılabilir olmadığında veya otomatik yükseltmeyi gerçekleştirecek şekilde güncelleştirilmediğinde yükseltmeleri kolaylaştırmak için bu [yükseltme betiğini](https://github.com/microsoft/mdefordownlevelserver/archive/refs/heads/main.zip) kullanabilirsiniz. "Kod" düğmesini seçip .zip dosyasını indirdikten sonra install.ps1 ayıklayarak indirin. Aşağıdaki gerekli adımları otomatikleştirmeye yardımcı olabilir:

1. Uç Nokta için Microsoft Defender için OMS çalışma alanını kaldırın (İsteğE BAĞLI).
2. Yüklüyse System Center Endpoint Protection (SCEP) istemcisini kaldırın.
3. Gerekirse (R2 Windows Server 2012) [önkoşullarını](configure-server-endpoints.md#prerequisites) indirin ve yükleyin.
4. Uç Nokta için Microsoft Defender yükleyin.
5. [Microsoft 365 Defender'dan indirilen](https://security.microsoft.com) **grup ilkesi kullanmak için** ekleme betiğini uygulayın.

Betiği kullanmak için, yükleme ve ekleme paketlerini de yerleştirdiğiniz bir yükleme dizinine indirin (bkz. [Sunucu uç noktalarını yapılandırma](configure-server-endpoints.md)).

ÖRNEK: .\install.ps1 -RemoveMMA <YOUR_WORKSPACE_ID> -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd"

Betiği kullanma hakkında daha fazla bilgi için PowerShell komutunu "get-help .\install.ps1" kullanın.

## <a name="microsoft-endpoint-configuration-manager-migration-scenarios"></a>Microsoft Endpoint Configuration Manager geçiş senaryoları 

>[!NOTE]
>Endpoint Protection ilke yapılandırmasını uygulamak için Microsoft Endpoint Configuration Manager, sürüm 2107 veya üzeri gerekir.

2207 sürümünden eski Configuration Manager Microsoft Endpoint kullanarak geçiş yapma yönergeleri için bkz[. Sunucuları Microsoft Monitoring Agent'tan birleşik çözüme geçirme.](/microsoft-365/security/defender-endpoint/application-deployment-via-mecm)

## <a name="if-you-are-running-a-non-microsoft-antivirus-solution"></a>Microsoft dışı bir virüsten koruma çözümü çalıştırıyorsanız

1. [Önkoşulların](configure-server-endpoints.md#prerequisites) karşılandığından emin olmak için Microsoft Defender Virüsten Koruma (Windows Server 2016) dahil olmak üzere makineyi tam olarak güncelleştirin. Karşılanması gereken önkoşullar hakkında daha fazla bilgi için bkz. [Windows Server 2016 önkoşulları](configure-server-endpoints.md#prerequisites-for-windows-server-2016).
2. Üçüncü taraf virüsten koruma yönetiminin artık virüsten koruma aracılarını bu makinelere göndermediğinden emin olun.*
3. Uç Nokta için Microsoft Defender koruma özellikleri için ilkelerinizi yazın ve bunları istediğiniz araçta makineye hedefleyin.*
4. Windows Server 2012 R2 ve 2016 paketi için Uç Nokta için Microsoft Defender yükleyin ve **pasif modu etkinleştirin**. Bkz[. Komut satırını kullanarak Microsoft Defender Virüsten Koruma yükleme](configure-server-endpoints.md#install-microsoft-defender-for-endpoint-using-the-command-line).
   a. [Microsoft 365 Defender'dan indirilen](https://security.microsoft.com) **grup ilkesi kullanmak için** ekleme betiğini uygulayın.
5. Güncelleştirmeleri uygulama.
6. Microsoft olmayan virüsten koruma konsolunu veya uygun şekilde Microsoft Endpoint Configuration Manager kullanarak Microsoft dışı virüsten koruma yazılımınızı kaldırın. Pasif mod yapılandırmasını kaldırdığınızdan emin olun.*

> [!TIP]
> Yukarıdaki adımları otomatikleştirmek için [yükleyici betiğini](server-migration.md#installer script) uygulamanızın bir parçası olarak kullanabilirsiniz. Pasif modu etkinleştirmek için -Passive bayrağını uygulayın. Örneğin, .\install.ps1 -RemoveMMA <YOUR_WORKSPACE_ID> -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd" -Passive

*Bu adımlar yalnızca Microsoft dışı virüsten koruma çözümünüzü değiştirmek istiyorsanız geçerlidir. [Bkz. Birlikte daha iyi: Virüsten koruma ve Uç Nokta için Microsoft Defender Microsoft Defender](why-use-microsoft-defender-antivirus.md).

Bir makineyi pasif moddan çıkarmak için aşağıdaki anahtarı 0 olarak ayarlayın:

Yol: HKLM\SOFTWARE\Policies\Microsoft\Windows Gelişmiş Tehdit Koruması Adı: ForceDefenderPassiveMode Türü: REG_DWORD Değer: 0

## <a name="if-you-are-running-system-center-endpoint-protection-but-are-not-managing-the-machine-using-microsoft-endpoint-configuration-manager-mecmconfigmgr"></a>System Center Endpoint Protection çalıştırıyorsanız ancak Makineyi Microsoft Endpoint Configuration Manager (MECM/ConfigMgr) kullanarak yönetmiyorsanız

1. [Önkoşulların](configure-server-endpoints.md#prerequisites) karşılandığından emin olmak için Microsoft Defender Virüsten Koruma (Windows Server 2016) dahil olmak üzere makineyi tam olarak güncelleştirin.
2. grup ilkesi, PowerShell veya üçüncü taraf bir yönetim çözümü kullanarak ilkeler oluşturun ve uygulayın.
3. System Center Endpoint Protection kaldırın (R2 Windows Server 2012).
5. Uç Nokta için Microsoft Defender yükleme (bkz[. Sunucu uç noktalarını yapılandırma](configure-server-endpoints.md).)
6. [Microsoft 365 Defender'dan indirilen](https://security.microsoft.com) **grup ilkesi kullanmak için** ekleme betiğini uygulayın. 
7. Güncelleştirmeleri uygulama.

> [!TIP]
> Yukarıdaki adımları otomatikleştirmek için yükleyici betiğini kullanabilirsiniz.

## <a name="microsoft-defender-for-cloud-scenarios"></a>Bulut senaryoları için Microsoft Defender

### <a name="youre-using-microsoft-defender-for-cloud-the-microsoft-monitoring-agent-mma-andor-microsoft-antimalware-for-azure-scep-are-installed-and-you-want-to-upgrade"></a>Bulut için Microsoft Defender kullanıyorsunuz. Azure için Microsoft Monitoring Agent (MMA) ve/veya Microsoft Antimalware (SCEP) yüklüdür ve yükseltmek istiyorsunuz.
Bulut için Microsoft Defender kullanıyorsanız otomatik yükseltme işleminden yararlanabilirsiniz. Bkz. [Bulut için Defender'ın tümleşik EDR çözümüyle uç noktalarınızı koruma: Uç Nokta için Microsoft Defender](/azure/security-center/security-center-wdatp#enable-the-microsoft-defender-for-endpoint-integration).

## <a name="group-policy-configuration"></a>grup ilkesi yapılandırması
grup ilkesi kullanarak yapılandırma için, doğru Uç Nokta için Defender ilke seçeneklerine erişmek için merkezi deponuzdaki en son ADMX dosyalarını kullandığınızdan emin olun. Lütfen [Windows'da grup ilkesi Yönetim Şablonları için Merkezi Mağaza oluşturma ve yönetme](/troubleshoot/windows-client/group-policy/create-and-manage-central-store) makalesine başvurun ve **Windows 10 ile kullanmak üzere** en son dosyaları indirin.
