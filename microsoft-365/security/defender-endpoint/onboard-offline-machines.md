---
title: Uç Nokta için Microsoft Defender İnternet erişimi olmayan cihazları ekleme
ms.reviewer: ''
description: algılayıcı verilerini Uç Nokta için Microsoft Defender algılayıcıya gönderebilmeleri için İnternet erişimi olmayan cihazları ekleme
keywords: ekleme, sunucular, vm, şirket içi, oms ağ geçidi, log analytics, azure log analytics, mma
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 33b539018f479c1b023a656ab056ca892d27e526
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66822191"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender İnternet erişimi olmayan cihazları ekleme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender mı yaşamak istiyorsunuz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Doğrudan İnternet bağlantısı olmayan cihazlar için önerilen yaklaşım ara sunucu çözümünün kullanılmasıdır. Önceki MMA tabanlı çözüm kullanılarak eklenen eski Windows cihazları için OMS ağ geçidi çözümünün kullanılması alternatif bir yaklaşım sağlar. Ekleme yöntemleri hakkında daha fazla bilgi için aşağıdaki makalelere bakın:
- [Windows'un önceki sürümlerini ekleyin](/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [Sunucuları Uç Nokta için Microsoft Defender hizmetine ekleme](/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)

> [!IMPORTANT]
> - Bağlantısız ortamlardaKi Windows veya Windows Server'ın sertifika güven listelerini bir iç dosya veya web sunucusu aracılığıyla çevrimdışı olarak güncelleştirebilmesi gerekir.
> - CTL'leri çevrimdışı güncelleştirme hakkında daha fazla bilgi için bkz. [CTL dosyalarını indirmek için dosya veya web sunucusu yapılandırma](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).

## <a name="devices-running-windows-10-or-later-windows-server-2012-r2-or-later-linux-and-macos"></a>R2 veya üzeri, Linux ve macOS Windows Server 2012 Windows 10 veya üzerini çalıştıran cihazlar

İşletim sistemine bağlı olarak, Uç Nokta için Microsoft Defender için kullanılacak ara sunucu, genellikle otomatik bulma veya otomatik yapılandırma dosyası kullanılarak ya da cihazda çalışan Uç Nokta için Defender hizmetlerine statik olarak özel olarak otomatik olarak yapılandırılabilir.

- Windows cihazları için lütfen [Cihaz ara sunucusu ve İnternet bağlantı ayarlarını yapılandırma](/microsoft-365/security/defender-endpoint/configure-proxy-internet) bölümüne başvurun
- Linux cihazları için bkz[. Linux'ta statik proxy bulma için Uç Nokta için Microsoft Defender yapılandırma](/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration)
- macOS cihazları için lütfen [Mac'te Uç Nokta için Microsoft Defender](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac#network-connections) başvurun

## <a name="windows-devices-running-the-previous-mma-based-solution"></a>Önceki MMA tabanlı çözümü çalıştıran Windows cihazları

> [!NOTE]
> - OMS ağ geçidi sunucusu, 'TelemetryProxyServer' kayıt defteri veya GPO aracılığıyla yapılandırıldığında bağlantısı kesilmiş Windows veya Windows Server cihazları için ara sunucu olarak kullanılamaz.
> - Windows veya Windows Server için - TelemetryProxyServer'ı kullanabilirsiniz ancak standart bir ara sunucu cihazına veya aletine işaret etmelidir.

- Azure Log Analytics'i (eski adıyla OMS Ağ Geçidi) ara sunucu veya hub olarak davranacak şekilde ayarlayın:
  - [Azure Log Analytics Aracısı](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - [Microsoft Monitoring Agent'ı (MMA) yükleme ve yapılandırma](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma) , Uç Nokta çalışma alanı anahtarı & kimliği için Defender'ı işaret ediyor

[Windows'un önceki sürümlerini ekleyin](onboard-downlevel.md)

### <a name="microsoft-defender-for-cloud"></a>Bulut için Microsoft Defender

- [Bulut için Defender'ın tümleşik EDR çözümüyle uç noktalarınızı koruma bölümündeki önkoşullar](/azure/defender-for-cloud/integration-defender-for-endpoint?tabs=windows#prerequisites) bölümünü gözden geçirin: Uç Nokta için Microsoft Defender
