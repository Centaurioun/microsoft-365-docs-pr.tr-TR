---
title: Uç Nokta için Microsoft Defender İnternet erişimi olmayan cihazları ekleme
ms.reviewer: ''
description: algılayıcı verilerini Uç Nokta için Microsoft Defender algılayıcıya gönderebilmeleri için İnternet erişimi olmayan cihazları ekleme
keywords: ekleme, sunucular, vm, şirket içi, oms ağ geçidi, log analytics, azure log analytics, mma
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 79d2109da8822d3859155f4b3b2867bdf3a8a15d
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68232176"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender İnternet erişimi olmayan cihazları ekleme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

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

### <a name="azure-virtual-machines"></a>Azure sanal makineleri

- Önceki MMA tabanlı çözümü çalıştıran cihazlar için, Azure Log Analytics Ağ Geçidi'ni (eski adıyla OMS Ağ Geçidi) ara sunucu veya hub olarak davranacak şekilde ayarlayın:
    - [Azure Log Analytics Ağ Geçidi](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
    - [Microsoft Monitoring Agent'ı (MMA) yükleme ve yapılandırma](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma) , Uç Nokta çalışma alanı anahtarı & kimliği için Defender'ı işaret ediyor
- Aynı OMS Ağ Geçidi ağındaki çevrimdışı Azure VM'leri
    - Azure Log Analytics IP'sini ara sunucu olarak yapılandırma
    - Azure Log Analytics Çalışma Alanı Anahtarı & Kimliği
- Bulut için Microsoft Defender
    - [Güvenlik İlkesi \> Log Analytics Çalışma Alanı](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
    - [Tehdit Algılama \> Uç Nokta için Defender'ın verilerime erişmesine izin ver](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

    Daha fazla bilgi için bkz [. Güvenlik ilkeleriyle çalışma](/azure/security-center/tutorial-security-policy).

> [!NOTE]
> İnternet erişimi olmayan istemciler Microsoft Defender Uç Noktasına eklenemez. İstemcinin gerekli URL'lere doğrudan erişmesi veya bir ara sunucu üzerinden erişimi olması gerekir.
