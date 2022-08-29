---
title: Windows'ta Microsoft Defender Çevrimdışı
description: Microsoft Defender Çevrimdışı'nı doğrudan Microsoft Defender Virüsten Koruma uygulamasından kullanabilirsiniz. Ayrıca ağınızda nasıl dağıtılacağı da yönetilebilir.
keywords: tarama, defender, çevrimdışı
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.date: 07/28/2022
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 33f41114c0647de2987a5ed5abdaec4c885fcbfd
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2022
ms.locfileid: "67387451"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>Microsoft Defender çevrimdışı tarama sonuçlarını gözden geçirin ve çalıştırın

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

Microsoft Defender Çevrimdışı, güvenilir bir ortamdan önyükleme yapmanıza ve tarama çalıştırmanıza olanak tanıyan bir kötü amaçlı yazılımdan koruma tarama aracıdır. Tarama normal Windows çekirdeğinin dışından çalıştırılır, böylece ana önyükleme kaydını (MBR) etkileyen veya üzerine yazan virüsler ve rootkit'ler gibi Windows kabuğunu atlama girişiminde bulunan kötü amaçlı yazılımları hedefleyebilir.

Kötü amaçlı yazılım bulaştığından şüpheleniyorsanız veya kötü amaçlı yazılım salgınından sonra uç noktanın kapsamlı bir şekilde temizlenip temizlenmediğini onaylamak istiyorsanız Microsoft Defender Çevrimdışı'nı kullanabilirsiniz.

Windows 10 ve Windows 11'da, Microsoft Defender Çevrimdışı doğrudan [Windows Güvenliği uygulamasından](microsoft-defender-security-center-antivirus.md) tek tıklamayla çalıştırılabilir. Windows'un önceki sürümlerinde, bir kullanıcının önyüklenebilir medya için Microsoft Defender Çevrimdışı'nı yüklemesi, uç noktayı yeniden başlatması ve önyüklenebilir medyayı yüklemesi gerekiyordu.

## <a name="prerequisites-and-requirements"></a>önkoşullar ve gereksinimler

Windows 10 ve Windows 11'da Microsoft Defender Çevrimdışı, Windows 10 ile aynı donanım gereksinimlerine sahiptir.

Windows 10 ve Windows 11 gereksinimleri hakkında daha fazla bilgi için aşağıdaki konulara bakın:

- [En düşük donanım gereksinimleri](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)
- [Donanım bileşeni yönergeleri](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> Microsoft Defender Çevrimdışı, ARM işlemcili makinelerde veya Windows Server Stok Tutma Birimlerinde desteklenmez.

Microsoft Defender Çevrimdışı'nı uç noktadan çalıştırmak için kullanıcının yönetici ayrıcalıklarıyla oturum açması gerekir.

## <a name="microsoft-defender-offline-updates"></a>Microsoft Defender Çevrimdışı güncelleştirmeleri

Microsoft Defender Çevrimdışı, uç noktada bulunan en son koruma güncelleştirmelerini kullanır; Microsoft Defender Virüsten Koruma her güncelleştirildiğinde güncelleştirilir.

> [!NOTE]
> Çevrimdışı taramayı çalıştırmadan önce Microsoft Defender Virüsten Koruma korumasını güncelleştirmeyi denemeniz gerekir. bir güncelleştirmeyi grup ilkesi ile zorlayabilirsiniz veya normalde uç noktalara güncelleştirme dağıtabilirsiniz ya da [Microsoft Kötü Amaçlı Yazılımdan Koruma Merkezi'nden](https://www.microsoft.com/security/portal/definitions/adl.aspx) en son koruma güncelleştirmelerini el ile indirip yükleyebilirsiniz.

Daha fazla bilgi için [Microsoft Defender Virüsten Koruma Güvenlik bilgileri güncelleştirmelerini yönetme](manage-protection-updates-microsoft-defender-antivirus.md) konusuna bakın.

## <a name="usage-scenarios"></a>Kullanım senaryoları

Windows 10 sürüm 1607'de çevrimdışı taramayı el ile zorlayabilirsiniz. Alternatif olarak, Windows Defender Microsoft Defender Çevrimdışı'nın çalıştırılması gerektiğini belirlerse, kullanıcıdan uç noktada istemde bulunur.

Uç noktalarınızı yönetmek için kullanıyorsanız çevrimdışı tarama gerçekleştirme gereksinimi Microsoft Endpoint Manager'da da ortaya çıkar.

İstem, aşağıdakine benzer bir bildirim aracılığıyla gerçekleşebilir:

:::image type="content" source="../../media/notification.png" alt-text="Microsoft Defender Çevrimdışı çalıştırma bildirimi" lightbox="../../media/notification.png":::

Kullanıcıya Windows Defender istemcisinde de bildirim gönderilir.

Configuration Manager'da İzleme **> Genel Bakış > Güvenlik > Endpoint Protection Durumu > System Center Endpoint Protection Durumu'na giderek uç noktaların durumunu** belirleyebilirsiniz.

Microsoft Defender Çevrimdışı taramaları **, Kötü amaçlı yazılım düzeltme durumu** altında **Çevrimdışı tarama gerekiyor** olarak belirtilir.

:::image type="content" source="../../media/sccm-wdo.png" alt-text="Microsoft Defender Çevrimdışı tarama göstergesi" lightbox="../../media/sccm-wdo.png":::

## <a name="configure-notifications"></a>Bildirimleri yapılandırma

Microsoft Defender Çevrimdışı bildirimleri, diğer Microsoft Defender Virüsten Koruma bildirimleriyle aynı ilke ayarında yapılandırılır.

Windows Defender'deki bildirimler hakkında daha fazla bilgi için [Uç noktalarda görünen bildirimleri yapılandırma](configure-notifications-microsoft-defender-antivirus.md) konusuna bakın.

## <a name="run-a-scan"></a>Tarama çalıştırma

> [!IMPORTANT]
> Microsoft Defender Çevrimdışı'yı kullanmadan önce tüm dosyaları kaydettiğinizden ve çalışan programları kapattığınıza emin olun. Microsoft Defender Çevrimdışı taramasının çalıştırılması yaklaşık 15 dakika sürer. Tarama tamamlandığında uç noktayı yeniden başlatır. Tarama, normal Windows işletim ortamı dışında gerçekleştirilir. Kullanıcı arabirimi, Windows Defender tarafından gerçekleştirilen normal taramadan farklı görünür. Tarama tamamlandıktan sonra uç nokta yeniden başlatılır ve Windows normal şekilde yüklenir.

Aşağıdakilerle bir Microsoft Defender Çevrimdışı taraması çalıştırabilirsiniz:

- PowerShell
- Windows Yönetim Araçları (WMI)
- Windows Güvenliği uygulaması

### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>Çevrimdışı tarama çalıştırmak için PowerShell cmdlet'lerini kullanma

Aşağıdaki cmdlet'leri kullanın:

```PowerShell
Start-MpWDOScan
```

[PowerShell'i Microsoft Defender Virüsten Koruma ile](use-powershell-cmdlets-microsoft-defender-antivirus.md) kullanma hakkında daha fazla bilgi için bkz. Microsoft Defender [Virüsten Koruma ve Defender Virüsten Koruma cmdlet'lerini](/powershell/module/defender/) yapılandırmak ve çalıştırmak için PowerShell cmdlet'lerini kullanma.

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>Çevrimdışı tarama çalıştırmak için Windows Yönetim Yönergesi'ni (WMI) kullanma

Çevrimdışı tarama çalıştırmak için [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) sınıfını kullanın.

Aşağıdaki WMI betik parçacığı hemen bir Microsoft Defender Çevrimdışı taraması çalıştırır ve bu da uç noktanın yeniden başlatılmasına, çevrimdışı taramayı çalıştırmasına ve ardından windows'da yeniden başlatılıp önyüklemesine neden olur.

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start
```

Daha fazla bilgi için aşağıdakilere bakın:

- [WMIv2 API'lerini Windows Defender](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>Çevrimdışı tarama çalıştırmak için Windows Defender Güvenlik uygulamasını kullanma

1. Görev çubuğundaki kalkan simgesine tıklayarak veya **Bulut için Defender** başlangıç menüsünde arama yaparak Windows Güvenliği uygulamasını açın.

2. **Virüs & tehdit koruması** kutucuğuna (veya sol menü çubuğundaki kalkan simgesine) ve ardından **Gelişmiş tarama** etiketine tıklayın:

3. **Microsoft Defender Çevrimdışı tarama'ya** tıklayın ve **Şimdi tara'ya** tıklayın.

    > [!NOTE]
    > Windows 10 sürüm 1607'de, çevrimdışı tarama **Windows Ayarlar** \> **Güncelleştirmesi & güvenlik** \> **Windows Defender** altından veya Windows Defender istemcisinden çalıştırılabilir.

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)

## <a name="related-articles"></a>İlgili makaleler

- [Taramaların ve düzeltmelerin sonuçlarını özelleştirme, başlatma ve gözden geçirme](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10'da Microsoft Defender Virüsten Koruma](microsoft-defender-antivirus-in-windows-10.md)
