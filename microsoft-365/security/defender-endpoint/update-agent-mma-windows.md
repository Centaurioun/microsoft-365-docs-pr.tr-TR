---
title: Uç Nokta için Microsoft Defender için cihazlarda aracınızı güncelleştirme
description: Uç Nokta için Defender için Windows cihazlarında MMA aracınızı güncelleştirme veya değiştirme seçenekleriniz hakkında bilgi edinin.
keywords: MMA, aracı, azure günlüğü
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
ms.date: 10/24/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.reviewer: pahuijbr
search.appverid: met150
ms.openlocfilehash: 48642c497be5b379e5d72c4e6538ffd1997b30bf
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2022
ms.locfileid: "68688968"
---
# <a name="updating-mma-on-windows-devices-for-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender için Windows cihazlarında MMA'nın güncelleştirilmesi

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Windows cihazlarında Microsoft Monitoring Agent (MMA) kullanıyorsanız, bu aracıyı güncel tutmalısınız. Windows Server 2012 R2 ve Windows Server 2016 için modern, birleşik aracıyla bunun yerine yeni çözüme geçmeniz gerekir. 

- [Cihazlarınızda Microsoft Monitoring Agent'ı (MMA) güncelleştirme](#option-1-update-mma-on-your-devices)
- [Windows Server 2012 R2 veya Windows Server 2016 üzerinde yeni aracı kullanma](#option-2-use-a-new-agent-on-windows-server-2012-r2-or-windows-server-2016)

Bu makalede hem seçenekler açıklanır hem de ek bilgilerin bağlantıları yer alır.

## <a name="option-1-update-mma-on-your-devices"></a>1. Seçenek: Cihazlarınızda MMA'ya güncelleştirme

*Bu seçenek Windows 7 SP1 Enterprise, Windows 7 SP1 Pro, Windows 8.1 Pro, Windows 8.1 Enterprise ve Windows Server 2008 R2 SP1 çalıştıran cihazlar için geçerlidir.* 

- Azure Otomasyonu veya kullanabileceğiniz çeşitli dağıtım araçları ve yöntemleriyle kullanmak üzere bir komut satırı yaklaşımı kullanarak aracıyı yükseltme yönergeleri için bkz. [Windows ve Linux için Log Analytics aracısını yönetme ve koruma](/azure/azure-monitor/agents/agent-manage?tabs=PowerShellLinux). 

- [MMA'yı Windows Server Update Services](/windows/deployment/update/waas-manage-updates-wsus) veya [Configuration Manager](/mem/configmgr/osd/deploy-use/manage-windows-as-a-service) aracılığıyla [Microsoft](/windows/deployment/update/how-windows-update-works) Update kullanarak güncelleştirin. Cihaza MMA ilk yüklendiğinde yapılandırılan yöntemi kullanın.

- MMA kurulum dosyasını indirin:

   - **Windows 64 bit aracısı**: [https://go.microsoft.com/fwlink/?LinkId=828603](https://go.microsoft.com/fwlink/?LinkId=828603)
   - **Windows 32 bit aracısı**: [https://go.microsoft.com/fwlink/?LinkId=828604](https://go.microsoft.com/fwlink/?LinkId=828604)

## <a name="option-2-use-a-new-agent-on-windows-server-2012-r2-or-windows-server-2016"></a>2. Seçenek: Windows Server 2012 R2 veya Windows Server 2016 üzerinde yeni aracı kullanma

*Bu seçenek R2 ve Windows Server 2016 Windows Server 2012 çalıştıran sunucular için geçerlidir.*

Nisan 2022'de Windows Server 2012 R2 ve Windows Server 2016 için yeni bir aracı kullanıma sunuldu. Yeni aracı MMA'ya bağımlı değildir. Bu yeni aracıya geçmenin, büyük ölçüde genişletilmiş bir özellik kümesi gibi önemli avantajları vardır. Daha fazla bilgi edinmek için bkz[. Teknik Topluluk Blogu: Windows Server 2012 R2 ve 2016'yı Savunma](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/defending-windows-server-2012-r2-and-2016/ba-p/2783292).

- Microsoft Defender Güvenlik Açığı Yönetimi, R2 ve 2016 makinelerinin henüz Windows Server 2012 izlemenizi sağlayacak "Uç Nokta için Microsoft Defender çekirdek bileşenlerini güncelleştirme" başlıklı bir değerlendirme (SCID-2030) sağlar Yükseltilmiş.

- Yeni aracıya yükseltme seçeneklerinizi anlamak için bkz. [Önceki MMA tabanlı Uç Nokta için Microsoft Defender çözümünden sunucu geçişi senaryoları](server-migration.md).

- Windows Server 2012 R2 veya Windows Server 2016 çalıştıran sunucularınızı yönetmek için Microsoft Endpoint Configuration Manager (SCCM/ConfigMgr) 2107 veya sonraki bir sürümünü kullanıyorsanız, **bkz. Microsoft** [Monitoring Agent'tan birleşik çözüme sunucuları](application-deployment-via-mecm.md) geçirme.

- Windows Server 2012 R2 veya Windows Server 2016 çalıştıran sunucularınızı yönetmek için Microsoft Endpoint Configuration Manager (SCCM/ConfigMgr) 2207 veya sonraki bir sürümünü kullanıyorsanız bkz. [Uç Nokta için Microsoft Defender ekleme otomatik yükseltme gerçekleştirmek için Configuration Manager 2207 ve üzeri sürümlerle](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).

- Windows Server 2012 R2 veya Windows Server 2016 çalıştıran sunucularla Bulut için Microsoft Defender kullanıyorsanız, **Birleşik çözümü etkinleştir'i** seçerek yükseltmeyi otomatikleştirebilirsiniz. Bkz[. Sunucular için Defender etkinleştirilmiş ve Uç Nokta için Microsoft Defender dağıtılmış kullanıcılar](/azure/defender-for-cloud/integration-defender-for-endpoint?tabs=windows).

## <a name="important-information-about-mma"></a>MMA hakkında önemli bilgiler

- Uç Nokta için Defender için MMA kullanmadığını belirlediyseniz veya aracınızı zaten güncelleştirdiyseniz, başka bir adıma gerek yoktur. 

- Ancak MMA'yı başka amaçlarla (Log Analytics gibi) kullanmaya devam ediyorsanız MMA şu anda Ağustos 2024'te kullanımdan kaldırmaya ayarlanmıştır. Bkz [. 31 Ağustos 2024'te Azure İzleyici'de Log Analytics aracısını kullanımdan kaldırıyoruz](https://azure.microsoft.com/updates/were-retiring-the-log-analytics-agent-in-azure-monitor-on-31-august-2024/). Özel senaryonuza bağlı olarak, [MMA'nın ardılı olan Azure İzleme Aracısı'na](/azure/azure-monitor/agents/azure-monitor-agent-migration) yükseltmek için uygun bir zaman olabilir. 

> [!IMPORTANT]
> Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2 veya [yeni, birleşik çözüme](application-deployment-via-mecm.md) yükseltilmemiş Windows Server 2016 çalıştıran cihazlar MMA'ya bağımlı kalır. Bu gibi durumlarda [AMA](/azure/azure-monitor/agents/agents-overview) , Uç Nokta için Defender'ın yerine kullanılamaz. 