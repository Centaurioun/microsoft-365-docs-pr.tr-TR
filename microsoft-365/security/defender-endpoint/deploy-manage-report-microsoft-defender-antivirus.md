---
title: Microsoft Defender Virüsten Koruma'yı dağıtma, yönetme ve raporlama
description: Intune, Microsoft Endpoint Configuration Manager, grup ilkesi, PowerShell veya WMI ile Microsoft Defender Virüsten Koruma'yı dağıtabilir ve yönetebilirsiniz
keywords: dağıtım, yönetme, güncelleştirme, koruma Microsoft Defender Virüsten Koruma
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.date: 09/02/2022
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 1914435028b4565f7b77e0925270691d30d15211
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68174852"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>Microsoft Defender Virüsten Koruma'yı dağıtma, yönetme ve raporlama

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma 

**Platform**

- Windows

Microsoft Defender Virüsten Koruma'yı birçok yolla dağıtabilir, yönetebilir ve raporlayabilirsiniz.

Microsoft Defender Virüsten Koruma istemcisi Windows 10 ve Windows 11 temel bir parçası olarak yüklendiğinden, istemcinin uç noktalarınıza geleneksel dağıtımı geçerli değildir.

Ancak çoğu durumda, aşağıdaki tabloda açıklanan Microsoft Intune, Microsoft Endpoint Configuration Manager, Bulut için Microsoft Defender veya grup ilkesi Nesneleri ile uç noktalarınızda koruma hizmetini etkinleştirmeniz gerekir.

Ayrıca şu bağlantılar için başka bağlantılar da görürsünüz:

- Ürün ve koruma güncelleştirmelerini yönetme de dahil olmak üzere Microsoft Defender Virüsten Koruma korumasını yönetme
- Microsoft Defender Virüsten Koruma bildirimi

> [!IMPORTANT]
> Çoğu durumda, Windows 10 veya Windows 11, çalışan ve güncel olan başka bir virüsten koruma ürünü bulursa Microsoft Defender Virüsten Koruma'yı devre dışı bırakır. Virüsten koruma Microsoft Defender çalışmadan önce üçüncü taraf virüsten koruma ürünlerini devre dışı bırakmanız veya kaldırmanız gerekir. Üçüncü taraf virüsten koruma ürünlerini yeniden etkinleştirir veya yüklerseniz Windows 10 veya Windows 11 Microsoft Defender Virüsten Koruma'yı otomatik olarak devre dışı bırakır.

| Araç|Dağıtım seçenekleri (<a href="#fn2" id="ref2">2</a>)|Yönetim seçenekleri (ağ genelinde yapılandırma ve ilke veya temel dağıtım) ([3](#fn3))|Raporlama seçenekleri |
---|---|---|---
| Microsoft Intune|[Intune'de uç nokta koruma ayarları ekleme](/intune/endpoint-protection-configure)|[Intune'de cihaz kısıtlama ayarlarını yapılandırma](/intune/device-restrictions-configure)| [Cihazları yönetmek için Intune konsolunu kullanma](/intune/device-management)
Microsoft Endpoint Manager ([1](#fn1))|[Endpoint Protection noktası site sistemi rolünü](/mem/configmgr/protect/deploy-use/endpoint-protection-site-role) kullanın ve [özel istemci ayarlarıyla Endpoint Protection'ı etkinleştirin](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client).|[Varsayılan ve özelleştirilmiş kötü amaçlı yazılımdan koruma ilkeleri](/microsoft-365/security/office-365-security/configure-anti-malware-policies) ve istemci yönetimi ile.|Varsayılan [Configuration Manager İzleme çalışma alanı](/mem/configmgr/apps/deploy-use/monitor-applications-from-the-console) ve e-posta uyarıları ile. |
| grup ilkesi ve Active Directory (etki alanına katılmış)|Yapılandırma değişikliklerini dağıtmak ve Microsoft Defender Virüsten Koruma'nın etkinleştirildiğinden emin olmak için grup ilkesi Nesnesi kullanın.|Microsoft Defender [Virüsten Koruma için güncelleştirme seçeneklerini yapılandırmak ve Windows Defender](/microsoft-365/security/defender-endpoint/manage-protection-update-schedule-microsoft-defender-antivirus) [özelliklerini yapılandırmak](/microsoft-365/security/defender-endpoint/configure-microsoft-defender-antivirus-features) için grup ilkesi Nesneleri'ni (GPO' lar) kullanın.|Uç nokta raporlama, grup ilkesi ile kullanılamaz. Herhangi bir ayarın veya ilkenin uygulanmadığını belirlemek için Grup İlkelerinin listesini oluşturabilirsiniz. |
| PowerShell|grup ilkesi, Microsoft Endpoint Configuration Manager ile veya tek tek uç noktalarda el ile dağıtın.|Defender modülünde bulunan [Set-MpPreference](/powershell/module/defender/set-mppreference) ve [Update-MpSignature](/powershell/module/defender/update-mpsignature) cmdlet'lerini kullanın.|[Defender modülünde bulunan uygun Get- cmdlet'lerini](/powershell/module/defender) kullanın. |
| Windows Yönetim Araçları|grup ilkesi, Microsoft Endpoint Configuration Manager ile veya tek tek uç noktalarda el ile dağıtın.|[MSFT_MpPreference sınıfının Set yöntemini ve MSFT_MpSignature sınıfının](/previous-versions/windows/desktop/defender/set-msft-mppreference) [Update yöntemini](/previous-versions/windows/desktop/defender/update-msft-mpsignature) kullanın.|[MSFT_MpComputerStatus](/previous-versions/windows/desktop/defender/msft-mpcomputerstatus) sınıfını ve [Windows Defender WMIv2 Sağlayıcısındaki](/windows/win32/wmisdk/wmi-providers) ilişkili sınıfların get yöntemini kullanın. |
| Microsoft Azure|[Visual Studio sanal makine yapılandırmasını veya Azure PowerShell cmdlet'lerini kullanarak Azure portal Azure için Microsoft Antimalware dağıtın](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios). Uç [nokta korumasını Bulut için Microsoft Defender'da da yükleyebilirsiniz](/azure/defender-for-cloud/endpoint-protection-recommendations-technical).|[Azure PowerShell cmdlet'leri ile Sanal Makineler ve Cloud Services için Microsoft Antimalware](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) yapılandırın veya [kod örnekleri kullanın](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe).|İzlemeyi etkinleştirmek [için Sanal Makineler ve Azure PowerShell cmdlet'lerle Cloud Services için Microsoft Antimalware](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) kullanın. Ayrıca, Virüs bulaşmış olabilecek cihazlar raporu da dahil olmak üzere şüpheli etkinlikleri belirlemek için Azure Active Directory'deki kullanım raporlarını gözden geçirebilir ve [Microsoft Defender Virüsten Koruma'daki olay günlüklerini ve hata kodlarını](troubleshoot-microsoft-defender-antivirus.md) raporlamak için bir SIEM aracı yapılandırabilir ve bu aracı Azure AD'da bir uygulama olarak ekleyebilirsiniz. |

1. <span id="fn1" />Özellikle bulut tabanlı korumayla ilgili bazı işlevlerin ve özelliklerin kullanılabilirliği Microsoft Endpoint Manager (Güncel Dal) ile System Center 2012 Configuration Manager arasında farklılık gösterir. Bu kitaplıkta Windows 10, Windows 11, Windows Server 2016 ve Microsoft Endpoint Manager (Güncel Dalı) üzerine odaklandık. Başlıca farklılıkları açıklayan bir tablo için bkz. [Microsoft Defender Virüsten Koruma'da Microsoft bulut tarafından sağlanan korumayı kullanma](cloud-protection-microsoft-defender-antivirus.md). [(Tabloya dön)](#ref2)

2. <span id="fn2" />Windows 10 ve Windows 11'da Microsoft Defender Virüsten Koruma, başka bir istemci veya hizmet yüklemeden veya dağıtmadan kullanılabilen bir bileşendir. Üçüncü taraf virüsten koruma ürünleri kaldırıldığında veya güncel olmadığında (Windows Server 2016 hariç) otomatik olarak etkinleştirilir. Bu nedenle geleneksel dağıtım gerekli değildir. Burada dağıtım, Microsoft Defender Virüsten Koruma bileşeninin uç noktalarda veya sunucularda kullanılabilir ve etkin olduğundan emin olmak anlamına gelir. [(Tabloya dön)](#ref2)

3. <span id="fn3" />Ürün ve koruma güncelleştirmelerini yapılandırma da dahil olmak üzere özelliklerin ve korumanın yapılandırması, bu kitaplığın [Microsoft Defender Virüsten Koruma özelliklerini yapılandırma](configure-notifications-microsoft-defender-antivirus.md) bölümünde daha ayrıntılı olarak açıklanmıştır. [(Tabloya dön)](#ref2)

## <a name="in-this-section"></a>Bu bölümde

Makale | Açıklama
---|---
[Microsoft Defender Virüsten Koruma'yı dağıtma ve etkinleştirme](deploy-microsoft-defender-antivirus.md) | İstemci Windows 10 veya Windows 11 temel bir parçası olarak yüklenmiş olsa da ve geleneksel dağıtım geçerli olmasa da, microsoft endpoint Configuration Manager, Microsoft Intune veya grup ilkesi Nesneleri ile uç noktalarınızda istemciyi etkinleştirmeniz gerekir.
[Microsoft Defender Virüsten Koruma güncelleştirmelerini yönetme ve temelleri uygulama](manage-updates-baselines-microsoft-defender-antivirus.md) | virüsten koruma Microsoft Defender güncelleştirmenin iki bölümü vardır: uç noktalarda istemciyi güncelleştirme (ürün güncelleştirmeleri) ve Güvenlik bilgilerini güncelleştirme (koruma güncelleştirmeleri). Microsoft Endpoint Configuration Manager, grup ilkesi, PowerShell ve WMI kullanarak Güvenlik bilgilerini birçok şekilde güncelleştirebilirsiniz.
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
    
