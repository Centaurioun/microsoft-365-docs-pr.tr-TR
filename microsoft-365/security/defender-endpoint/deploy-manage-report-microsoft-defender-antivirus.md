---
title: Microsoft Defender Virüsten Koruma'yı dağıtma, yönetme ve raporlama
description: Microsoft Defender Virüsten Koruma'yı Intune, Microsoft Endpoint Configuration Manager, grup ilkesi, PowerShell veya WMI ile dağıtabilir ve yönetebilirsiniz
keywords: dağıtma, yönetme, güncelleştirme, koruma, Microsoft Defender Virüsten Koruma
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.date: 08/05/2022
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 64a7bc6a95fa9f49da57bf14b6aebcb2e27c6d18
ms.sourcegitcommit: cd9df1a681265905eef99c039f7036b2fa6e8b6d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67274671"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>Microsoft Defender Virüsten Koruma'yı dağıtma, yönetme ve raporlama

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma 

**Platform**

- Windows

Microsoft Defender Virüsten Koruma'yı çeşitli yollarla dağıtabilir, yönetebilir ve raporlayabilirsiniz.

Microsoft Defender Virüsten Koruma istemcisi Windows 10 ve Windows 11 temel bir parçası olarak yüklendiğinden, istemcinin uç noktalarınıza geleneksel dağıtımı geçerli değildir.

Ancak çoğu durumda, aşağıdaki tabloda açıklanan Microsoft Intune, Microsoft Endpoint Configuration Manager, Bulut için Microsoft Defender veya grup ilkesi Nesneleri ile uç noktalarınızda koruma hizmetini etkinleştirmeniz gerekir.

Ayrıca şunların ek bağlantılarını da görürsünüz:

- Ürün ve koruma güncelleştirmelerini yönetme de dahil olmak üzere Microsoft Defender Virüsten Koruma korumasını yönetme
- Microsoft Defender Virüsten Koruma koruması hakkında raporlama

> [!IMPORTANT]
> Çoğu durumda Windows 10 veya Windows 11, çalışan ve güncel olan başka bir virüsten koruma ürünü bulursa Microsoft Defender Virüsten Koruma'yı devre dışı bırakır. Microsoft Defender Virüsten Koruma'nın çalışması için önce üçüncü taraf virüsten koruma ürünlerini devre dışı bırakmanız veya kaldırmanız gerekir. Üçüncü taraf virüsten koruma ürünlerini yeniden etkinleştirir veya yüklerseniz Windows 10 veya Windows 11 Microsoft Defender Virüsten Koruma'yı otomatik olarak devre dışı bırakır.

Araç|Dağıtım seçenekleri (<a href="#fn2" id="ref2">2</a>)|Yönetim seçenekleri (ağ genelinde yapılandırma ve ilke veya temel dağıtım) ([3](#fn3))|Raporlama seçenekleri
---|---|---|---
Microsoft Intune|[Intune'de uç nokta koruma ayarları ekleme](/intune/endpoint-protection-configure)|[Intune'de cihaz kısıtlama ayarlarını yapılandırma](/intune/device-restrictions-configure)| [Cihazları yönetmek için Intune konsolunu kullanma](/intune/device-management)
Microsoft Endpoint Manager ([1](#fn1))|[Endpoint Protection noktası site sistemi rolünü](/mem/configmgr/protect/deploy-use/endpoint-protection-site-role) kullanın ve [özel istemci ayarlarıyla Endpoint Protection'ı etkinleştirin](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client).|[Varsayılan ve özelleştirilmiş kötü amaçlı yazılımdan koruma ilkeleri](/microsoft-365/security/office-365-security/configure-anti-malware-policies) ve istemci yönetimi ile.|Varsayılan [Configuration Manager İzleme çalışma alanı](/mem/configmgr/apps/deploy-use/monitor-applications-from-the-console) ve e-posta uyarıları ile.
grup ilkesi ve Active Directory (etki alanına katılmış)|Yapılandırma değişikliklerini dağıtmak ve Microsoft Defender Virüsten Koruma'nın etkinleştirildiğinden emin olmak için bir grup ilkesi Nesnesi kullanın.|[Microsoft Defender Virüsten Koruma için güncelleştirme seçeneklerini yapılandırmak](/microsoft-365/security/defender-endpoint/manage-protection-update-schedule-microsoft-defender-antivirus) ve [Windows Defender özelliklerini yapılandırmak için grup ilkesi](/microsoft-365/security/defender-endpoint/configure-microsoft-defender-antivirus-features) Nesneleri'ni (GPO' lar) kullanın.|Uç nokta raporlaması grup ilkesi ile kullanılamaz. Herhangi bir ayarın veya ilkenin uygulanmadığını belirlemek için Grup İlkelerinin listesini oluşturabilirsiniz.
PowerShell|grup ilkesi, Microsoft Endpoint Configuration Manager ile veya tek tek uç noktalarda el ile dağıtın.|Defender modülünde bulunan [Set-MpPreference] ve [Update-MpSignature] cmdlet'lerini kullanın.|[Defender modülünde bulunan uygun Get- cmdlet'lerini](/powershell/module/defender) kullanın.
Windows Yönetim Araçları|grup ilkesi, Microsoft Endpoint Configuration Manager ile veya tek tek uç noktalarda el ile dağıtın.|[MSFT_MpPreference sınıfının Set yöntemini ve MSFT_MpSignature sınıfının](/previous-versions/windows/desktop/defender/set-msft-mppreference) [Update yöntemini](/previous-versions/windows/desktop/defender/update-msft-mpsignature) kullanın.|[MSFT_MpComputerStatus](/previous-versions/windows/desktop/defender/msft-mpcomputerstatus) sınıfını ve [Windows Defender WMIv2 Sağlayıcısındaki](/windows/win32/wmisdk/wmi-providers) ilişkili sınıfların get yöntemini kullanın.
Microsoft Azure|[Visual Studio sanal makine yapılandırmasını veya Azure PowerShell cmdlet'lerini kullanarak Azure portal Azure için Microsoft Antimalware dağıtın](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios). [Uç nokta korumasını Bulut için Microsoft Defender'a da yükleyebilirsiniz](/azure/defender-for-cloud/endpoint-protection-recommendations-technical).|[Azure PowerShell cmdlet'leri ile Sanal Makineler ve Cloud Services için Microsoft Antimalware](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) yapılandırın veya [kod örnekleri kullanın](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe).|İzlemeyi etkinleştirmek [için Sanal Makineler ve Azure PowerShell cmdlet'lerle Cloud Services için Microsoft Antimalware](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) kullanın. Ayrıca Azure Active Directory'deki kullanım raporlarını gözden geçirerek olası virüslü cihazlar raporu da dahil olmak üzere şüpheli etkinlikleri belirleyebilir ve bir SIEM aracını [Microsoft Defender Virüsten Koruma olayları][/microsoft-365/security/defender-endpoint/troubleshoot-microsoft-defender-antivirus] hakkında rapor vermek üzere yapılandırabilir ve bu aracı AAD'ye uygulama olarak ekleyebilirsiniz.

1. <span id="fn1" />Özellikle bulut tabanlı korumayla ilgili bazı işlevlerin ve özelliklerin kullanılabilirliği Microsoft Endpoint Manager (Güncel Dal) ile System Center 2012 Configuration Manager arasında farklılık gösterir. Bu kitaplıkta Windows 10, Windows 11, Windows Server 2016 ve Microsoft Endpoint Manager (Güncel Dalı) üzerine odaklandık. Önemli farkları açıklayan bir tablo için bkz. [Microsoft Defender Virüsten Koruma'da Microsoft bulut tarafından sağlanan korumayı kullanma](cloud-protection-microsoft-defender-antivirus.md) . [(Tabloya dön)](#ref2)

2. <span id="fn2" />Windows 10 ve Windows 11'de Microsoft Defender Virüsten Koruma, ek bir istemci veya hizmet yüklemeden veya dağıtmadan kullanılabilen bir bileşendir. Üçüncü taraf virüsten koruma ürünleri kaldırıldığında veya güncel olmadığında (Windows Server 2016 hariç) otomatik olarak etkinleştirilir. Bu nedenle geleneksel dağıtım gerekli değildir. Burada dağıtım, Microsoft Defender Virüsten Koruma bileşeninin uç noktalarda veya sunucularda kullanılabilir ve etkin olduğundan emin olmak anlamına gelir. [(Tabloya dön)](#ref2)

3. <span id="fn3" />Ürün ve koruma güncelleştirmelerini yapılandırma da dahil olmak üzere özelliklerin ve korumanın yapılandırması, bu kitaplığın [Microsoft Defender Virüsten Koruma özelliklerini yapılandırma](configure-notifications-microsoft-defender-antivirus.md) bölümünde daha ayrıntılı olarak açıklanmıştır. [(Tabloya dön)](#ref2)

## <a name="in-this-section"></a>Bu bölümde

Makale | Açıklama
---|---
[Microsoft Defender Virüsten Koruma'yı dağıtma ve etkinleştirme](deploy-microsoft-defender-antivirus.md) | İstemci Windows 10 veya Windows 11 temel bir parçası olarak yüklenmiş olsa da ve geleneksel dağıtım geçerli olmasa da, Configuration Manager, Microsoft Intune veya grup ilkesi Nesneleri ile uç noktalarınızda istemciyi etkinleştirmeniz gerekir.
[Microsoft Defender Virüsten Koruma güncelleştirmelerini yönetme ve temelleri uygulama](manage-updates-baselines-microsoft-defender-antivirus.md) | Microsoft Defender Virüsten Koruma'nın güncelleştirilmesi için iki bölüm vardır: uç noktalarda istemciyi güncelleştirme (ürün güncelleştirmeleri) ve Güvenlik bilgileri (koruma güncelleştirmeleri) güncelleştirme. Microsoft Endpoint Configuration Manager, grup ilkesi, PowerShell ve WMI kullanarak Güvenlik bilgilerini çeşitli yollarla güncelleştirebilirsiniz.
[Microsoft Defender Virüsten Koruma korumasını izleme ve raporlama](report-monitor-microsoft-defender-antivirus.md) | Koruma durumunu izlemek ve uç nokta koruması hakkında raporlar oluşturmak için Microsoft Intune, Microsoft Endpoint Configuration Manager, Microsoft Operations Management Suite için Güncelleştirme Uyumluluğu eklentisini veya üçüncü taraf bir SIEM ürününü (Windows olay günlüklerini kullanarak) kullanabilirsiniz.

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)
    
