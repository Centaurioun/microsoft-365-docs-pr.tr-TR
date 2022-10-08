---
title: Uç Nokta için Microsoft Defender'de sorun giderme modu senaryoları
description: Çeşitli virüsten koruma sorunlarını gidermek için Uç Nokta için Microsoft Defender sorun giderme modunu kullanın.
keywords: virüsten koruma, sorun giderme, sorun giderme modu, kurcalama koruması, uyumluluk
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 87f73410cfe5eef6d6e161f1943d5af3737cc087
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68227360"
---
# <a name="troubleshooting-mode-scenarios-in-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender'de sorun giderme modu senaryoları 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

Uç Nokta için Microsoft Defender sorun giderme modu, çeşitli Microsoft Defender Virüsten Koruma özelliklerini cihazdan etkinleştirerek ve kuruluş ilkesi tarafından denetlense bile farklı senaryoları test ederek sorun gidermenize olanak tanır. Sorun giderme modu varsayılan olarak devre dışıdır ve bir cihaz (ve/veya cihaz grubu) için sınırlı bir süre için açmanızı gerektirir. Bunun yalnızca kurumsal bir özellik olduğunu ve Microsoft 365 Defender erişim gerektirdiğini unutmayın.

## <a name="scenario-1-unable-to-install-application"></a>Senaryo 1: Uygulama yüklenemiyor

Bir uygulama yüklemek istiyorsanız ancak Virüsten Koruma ve kurcalama korumasının açık Microsoft Defender bir hata iletisi alıyorsanız, sorunu gidermek için aşağıdaki adımları izleyin.

1. Güvenlik yöneticisinden sorun giderme modunu açmasını isteyin. Sorun giderme modu başladıktan sonra Windows Güvenliği bildirimi alırsınız.  

2. Yerel yönetici izinleriyle cihaza bağlanın (örneğin Terminal Hizmetleri'ni kullanarak).  

3. İşlem İzleyicisi'ni (ProcMon) başlatın. [Gerçek zamanlı korumayla ilgili performans sorunlarını giderme](troubleshoot-performance-issues.md) başlığında açıklanan adımlara bakın.  

4. **Windows güvenliği** > **Tehdit & virüs koruması** > **Ayarları** >  yönet **Kurcalama koruması** > **Kapalı'ya** gidin.  

5. Yükseltilmiş bir PowerShell komut istemi başlatın ve RTP'yi kapatın. 

    - RealTimeProtection durumunu denetlemek için komutunu çalıştırın `Get-MpComputerStatus` .
    - RTP'yi kapatmak için komutunu çalıştırın `Set-mppreference -DisableRealtimeMonitoring $true` .
    - RealTimeProtection durumunu doğrulamak için yeniden çalıştırın `Get-MpComputerStatus` .

6. Uygulamayı yüklemeyi deneyin.

## <a name="scenario-2-high-cpu-usage-due-to-windows-defender-msmpengexe"></a>Senaryo 2: Windows Defender nedeniyle yüksek CPU kullanımı (MsMpEng.exe)

Bazen zamanlanmış tarama sırasında MsMpEng.exe yüksek CPU kullanabilir.

1. Yüksek CPU kullanımının ardındaki nedenin MsMpEng.exe olduğunu onaylamak için **Görev Yöneticisi** > **Ayrıntıları** sekmesine gidin. Ayrıca, zamanlanmış taramanın şu anda devam ediyor olup olmadığını denetleyin.

2. Cpu ani artışı sırasında yaklaşık 5 dakika boyunca ProcMon çalıştırın ve ardından ipuçları için ProcMon günlüğünü gözden geçirin. 

3. Kök neden belirlendikten sonra sorun giderme modunu açın. 

4. Makinede oturum açın ve yükseltilmiş bir PowerShell komut istemi başlatın. 

5. Aşağıdaki komutlardan birini kullanarak ProcMon bulgularına göre işlem/dosya/klasör/uzantı dışlamaları ekleyin (aşağıda belirtilen yol, uzantı ve işlem dışlamaları yalnızca örneklerdir): 

    - `Set-mppreference -ExclusionPath` (örneğin, C:\DB\DataFiles) 
    
    - `Set-mppreference –ExclusionExtension` (örneğin, .dbx) 
    
    - `Set-mppreference –ExclusionProcess` (örneğin, C:\DB\Bin\Convertdb.exe) 

6. Dışlama ekledikten sonra CPU kullanımının bırakılıp bırakılmadığını denetleyin. 

Windows Defender taramaları ve güncelleştirmeleri için Set-MpPreference cmdlet yapılandırma tercihleri hakkında daha fazla bilgi için bkz. [Set-MpPreference](/powershell/module/defender/set-mppreference). 

## <a name="scenario-3-application-taking-longer-to-perform-an-action"></a>Senaryo 3: Uygulamanın eylem gerçekleştirmesi daha uzun sürüyor

Microsoft Defender Virüsten Koruma gerçek zamanlı koruma etkinleştirildiğinde uygulamanın temel görevleri gerçekleştirmesi uzun sürer. Gerçek zamanlı korumayı kapatmak ve sorunu gidermek için aşağıdaki adımları izleyin. 

1. Güvenlik yöneticisinden cihazda sorun giderme modunu açmasını isteyin. 

2. Bu senaryo için RTP'yi devre dışı bırakmak için önce kurcalama korumasını kapatın. Daha fazla bilgi için bkz [. Kurcalama koruması ile güvenlik ayarlarını koruma](prevent-changes-to-security-settings-with-tamper-protection.md). 

3. Kurcalama koruması devre dışı bırakıldıktan sonra cihazda oturum açın. 

4. Yükseltilmiş bir PowerShell komut istemi başlatın. 

    - `Set-mppreference -DisableRealtimeMonitoring $true` 

5. RTP'yi devre dışı bırakdıktan sonra uygulamanın yavaş olup olmadığını denetleyin. 

## <a name="scenario-4-microsoft-office-plugin-blocked-by-attack-surface-reduction"></a>Senaryo 4: Microsoft Office eklentisi Saldırı Yüzeyi Azaltma tarafından engellendi

Saldırı Yüzeyi Azaltma (ASR), **Tüm Office uygulamalarının alt işlemler oluşturmasını engelle** ayarı blok moduna ayarlandığından Microsoft Office eklentisinin düzgün çalışmasına izin vermiyor. 

1. Sorun giderme modunu açın ve cihazda oturum açın. 

2. Yükseltilmiş bir PowerShell komut istemi başlatın. 

    - `Set-MpPreference -AttackSurfaceReductionRules_Ids D4F940AB-401B-4EFC-AADC-AD5F3C50688A -AttackSurfaceReductionRules_Actions Disabled` 

3. ASR Kuralını devre dışı bırakdıktan sonra, Microsoft Office eklentisinin artık çalıştığını onaylayın.

Daha fazla bilgi için bkz. [Saldırı yüzeyini azaltmaya genel bakış](overview-attack-surface-reduction.md). 

## <a name="scenario-5-domain-blocked-by-network-protection"></a>Senaryo 5: Ağ Koruması tarafından engellenen etki alanı

Ağ Koruması Microsoft etki alanını engelleyerek kullanıcıların etki alanına erişmesini engelliyor. 

1. Sorun giderme modunu açın ve cihazda oturum açın. 

2. Yükseltilmiş bir PowerShell komut istemi başlatın. 

    - `Set-MpPreference -EnableNetworkProtection Disabled` 

3. Ağ Koruması'nı devre dışı bırakdıktan sonra etki alanına artık izin verilip verilmediğini denetleyin. 

Daha fazla bilgi için bkz. [Hatalı sitelerle bağlantıları önlemeye yardımcı olmak için ağ korumasını kullanma](network-protection.md). 

## <a name="related-topics"></a>İlgili konular

- [Sorun giderme modunu etkinleştirme](enable-troubleshooting-mode.md)
- [Değişiklik korumasıyla güvenlik ayarlarını koruyun](prevent-changes-to-security-settings-with-tamper-protection.md)
- [Set-MpPreference](/powershell/module/defender/set-mppreference)
- [Ağınızı koruyun](network-protection.md)
- [Saldırı yüzeyini azaltmaya genel bakış](overview-attack-surface-reduction.md)
- [İstenmeyen olası uygulamaları tespit edin ve engelleyin](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)
- [Uç Nokta için Microsoft Defender genel bakışını edinin](/microsoft-365/security/defender-endpoint/)
- [Birlikte daha iyi: Microsoft Defender Virüsten Koruma ve Uç Nokta için Microsoft Defender](why-use-microsoft-defender-antivirus.md)
