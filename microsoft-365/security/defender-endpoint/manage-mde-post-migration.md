---
title: İlk kurulum veya geçiş sonrasında Uç Nokta için Microsoft Defender yönetme
description: artık Uç Nokta için Microsoft Defender geçiş yaptığınıza göre, sonraki adımınız tehdit koruması özelliklerinizi yönetmektir
keywords: geçiş sonrası, yönetme, işlemler, bakım, kullanım, Uç Nokta için Microsoft Defender, edr
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.date: 07/01/2022
ms.reviewer: chventou
search.appverid: met150
ms.openlocfilehash: 879a5881ecf34c74a1f7cffb774a85bc734eec0d
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68225074"
---
# <a name="manage-microsoft-defender-for-endpoint-after-initial-setup-or-migration"></a>İlk kurulum veya geçiş sonrasında Uç Nokta için Microsoft Defender yönetme

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Uç Nokta için Microsoft Defender ayarlayıp yapılandırdıktan sonra, sonraki adımınız özelliklerinizi ve yeteneklerinizi yönetmektir. Kuruluşunuzun cihazlarını [](/mem/endpoint-manager-overview)ve güvenlik ayarlarını yönetmek için [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) ve [Microsoft Endpoint Configuration Manager içeren Microsoft Endpoint Manager](/mem/configmgr/core/understand/introduction) kullanmanızı öneririz. Ancak[, Azure Active Directory Domain Services'daki grup ilkesi Nesneleri](/azure/active-directory-domain-services/manage-group-policy) gibi diğer araçları/yöntemleri kullanabilirsiniz.

Aşağıdaki tabloda, daha fazla bilgi edinmek için kullanabileceğiniz çeşitli araçlar/yöntemler ve bağlantılar listelemektedir.

|Araç/Yöntem|Açıklama|
|---|---|
|Microsoft 365 Defender portalında **[pano içgörülerini](/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)** [Microsoft Defender Güvenlik Açığı Yönetimi](https://security.microsoft.com/)|Defender Güvenlik Açığı Yönetimi panosu, güvenlik operasyonları ekibinizin ifşayı azaltmak ve kuruluşunuzun güvenlik duruşunu geliştirmek için kullanabileceği eyleme dönüştürülebilir bilgiler sağlar. <br/><br/> Bkz. [Defender Güvenlik Açığı Yönetimi](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) ve [Microsoft 365 Defender Genel Bakış](/microsoft-365/security/defender-endpoint/use).|
|**[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)** (önerilir)|Microsoft Endpoint Manager'nin bir bileşeni olan [Microsoft Intune (Intune](/mem/endpoint-manager-overview)), mobil cihaz yönetimine (MDM) ve mobil uygulama yönetimine (MAM) odaklanır. Intune ile cep telefonları, tabletler ve dizüstü bilgisayarlar dahil olmak üzere kuruluşunuzun cihazlarının nasıl kullanılacağını denetleyebilirsiniz. Uygulamaları denetlemek için belirli ilkeleri de yapılandırabilirsiniz. <br/><br/> Bkz. [Intune kullanarak Uç Nokta için Microsoft Defender yönetme](manage-mde-post-migration-intune.md).|
|**[Microsoft Uç Noktası Yapılandırma Yöneticisi](/mem/configmgr/core/understand/introduction)**|Eski adıyla System Center Configuration Manager olan Microsoft Endpoint Manager (Configuration Manager), [Microsoft Endpoint Manager'nin](/mem/endpoint-manager-overview) bir bileşenidir. Configuration Manager, kullanıcılarınızı, cihazlarınızı ve yazılımınızı yönetmek için güçlü bir araçtır. <br/><br/> Bkz. [Configuration Manager ile Uç Nokta için Microsoft Defender yönetme](manage-mde-post-migration-configuration-manager.md).|
|**[Azure Active Directory Domain Services'da Nesneleri grup ilkesi](/azure/active-directory-domain-services/manage-group-policy)**|[Azure Active Directory Domain Services](/azure/active-directory-domain-services/overview), kullanıcılar ve cihazlar için yerleşik grup ilkesi Nesneleri içerir. Yerleşik grup ilkesi Nesnelerini ortamınız için gerektiği gibi özelleştirebilir, ayrıca özel grup ilkesi Nesneleri ve kuruluş birimleri (OU) oluşturabilirsiniz. <br/><br/> Bkz. [grup ilkesi Nesnelerle Uç Nokta için Microsoft Defender Yönetme](manage-mde-post-migration-group-policy-objects.md).|
|**[PowerShell, WMI ve MPCmdRun.exe](manage-mde-post-migration-other-tools.md)**|*Kuruluşunuzun cihazlarında tehdit koruması özelliklerini yönetmek için Microsoft Endpoint Manager (Intune ve Configuration Manager içerir) kullanmanızı öneririz. Ancak, PowerShell, WMI veya MPCmdRun.exe aracıyla tek tek cihazlarda (uç noktalar) Microsoft Defender Virüsten Koruma ayarları gibi bazı ayarları yapılandırabilirsiniz.* <br/><br/> Microsoft Defender Virüsten Koruma, yararlanma koruması ve saldırı yüzeyi azaltma kurallarınızı yönetmek için PowerShell'i kullanabilirsiniz. Bkz[. PowerShell ile Uç Nokta için Microsoft Defender yapılandırma](manage-mde-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell). <br/><br/> Microsoft Defender Virüsten Koruma ve dışlamaları yönetmek için Windows Yönetim Araçları'na (WMI) sahip olabilirsiniz. Bkz[. WMI ile Uç Nokta için Microsoft Defender yapılandırma](manage-mde-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi). <br/><br/> Microsoft Defender Virüsten Koruma ve dışlamaları yönetmek ve ağınızla bulut arasındaki bağlantıları doğrulamak için Microsoft Kötü Amaçlı Yazılımdan Koruma Command-Line Yardımcı Programı'nı (MPCmdRun.exe) kullanabilirsiniz. Bkz[. MPCmdRun.exeile Uç Nokta için Microsoft Defender yapılandırma](manage-mde-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe).|


## <a name="see-also"></a>Ayrıca bkz.

- [Uç Nokta için Microsoft Defender'da yanlış pozitifleri/negatifleri ele alın](defender-endpoint-false-positives-negatives.md)
