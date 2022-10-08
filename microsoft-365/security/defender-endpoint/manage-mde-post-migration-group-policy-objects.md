---
title: grup ilkesi Nesneleri kullanarak Uç Nokta için Microsoft Defender yönetme
description: grup ilkesi Nesneleri ile Uç Nokta için Microsoft Defender yönetmeyi öğrenin
keywords: geçiş sonrası, yönetme, işlemler, bakım, kullanım, PowerShell, Uç Nokta için Microsoft Defender, edr
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
ms.topic: article
ms.reviewer: chventou
search.appverid: met150
ms.openlocfilehash: 049d1358b600981fbaaf6d6f232e662f58890e64
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68232968"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a>grup ilkesi Nesneleri ile Uç Nokta için Microsoft Defender yönetme

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> Kuruluşunuzun cihazlar için tehdit koruması özelliklerini yönetmek için [Microsoft Endpoint Manager](/mem) kullanmanızı öneririz (uç noktalar olarak da adlandırılır). Endpoint Manager [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) ve [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction) içerir. **[Endpoint Manager hakkında daha fazla bilgi edinin](/mem/endpoint-manager-overview)**.

Uç Nokta için Microsoft Defender'daki bazı ayarları yönetmek için Azure Active Directory Domain Services'da grup ilkesi Nesneleri'ni kullanabilirsiniz.

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a>grup ilkesi Nesneleriyle Uç Nokta için Microsoft Defender Yapılandırma

> [!NOTE]
> [Windows Server 2012 R2 ve 2016 için yeni, birleşik Uç Nokta için Microsoft Defender çözümünü](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview) kullanıyorsanız, doğru Uç Nokta için Microsoft Defender ilkesi seçeneklerine erişmek için lütfen merkezi mağazanızdaki en son ADMX dosyalarını kullandığınızdan emin olun . Lütfen [Windows'da grup ilkesi Yönetim Şablonları için Merkezi Mağaza oluşturma ve yönetme](/troubleshoot/windows-client/group-policy/create-and-manage-central-store) makalesine başvurun ve **Windows 10 ile kullanmak üzere** en son dosyaları indirin. 

Aşağıdaki tabloda, grup ilkesi Nesneleri ile Uç Nokta için Microsoft Defender yapılandırmak için gerçekleştirebileceğiniz çeşitli görevler listelenir.

|Görev|Daha fazla bilgi edinmek için kaynaklar|
|---|---|
|**Kullanıcı ve bilgisayar nesneleri için ayarları yönetme** <br/><br/> *Yerleşik grup ilkesi Nesnelerini özelleştirin veya özel grup ilkesi Nesneleri ve kuruluş birimlerini kuruluş gereksinimlerinize uyacak şekilde oluşturun.*|[Azure Active Directory Domain Services yönetilen etki alanında grup ilkesi yönetme](/azure/active-directory-domain-services/manage-group-policy)|
|**Microsoft Defender Virüsten Koruma'Microsoft Defender yapılandırma** <br/><br/> *Kuruluşunuzun cihazlarında (uç noktalar olarak da adlandırılır) ilke ayarları, dışlamalar, düzeltme ve zamanlanmış taramalar gibi virüsten koruma özelliklerini & özellikleri yapılandırın.*|[Microsoft Defender Virüsten Koruma'grup ilkesi ayarlarını kullanarak yapılandırma ve yönetme](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/> [Bulut tabanlı korumayı etkinleştirmek için grup ilkesi kullanma](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)|
|**Kuruluşunuzun saldırı yüzeyi azaltma kurallarını yönetme** <br/><br/> *Dosyaları & klasörleri hariç tutarak veya kullanıcıların cihazlarında görünen bildirim uyarılarına özel metin ekleyerek saldırı yüzeyi azaltma kurallarınızı özelleştirin.*|[grup ilkesi Nesneleri ile saldırı yüzeyi azaltma kurallarını özelleştirme](/microsoft-365/security/defender-endpoint/attack-surface-reduction-rules-deployment-implement)|
|**Güvenlik açığından yararlanma koruması ayarlarını yönetme** <br/><br/> *Yararlanma koruması ayarlarınızı özelleştirebilir, bir yapılandırma dosyasını içeri aktarabilir ve ardından grup ilkesi kullanarak bu yapılandırma dosyasını dağıtabilirsiniz.*|[Yararlanma koruması ayarlarını özelleştirme](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/> [Exploit Protection yapılandırmalarını içeri aktarma, dışarı aktarma ve dağıtma](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml) <br/><br/> [Yapılandırmayı dağıtmak için Grup İlkesi'ni kullanma](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)|
|Çalışanların İnternet'te kötü amaçlı içerik kullanan uygulamaları kullanmasını önlemeye yardımcı olmak için **Ağ Koruması'nı etkinleştirin** <br/><br/> *Dağıtımdan önce hangi uygulamaların engellendiğini görmek için bir test ortamında ağ koruması için ilk olarak [denetim modunu](/microsoft-365/security/defender-endpoint/evaluate-network-protection) kullanmanızı öneririz.*|[grup ilkesi kullanarak ağ korumasını açma](/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)|
|Fidye yazılımlarına karşı korunmak için **denetimli klasör erişimini yapılandırma** <br/><br/> *[Denetimli klasör erişimi](/microsoft-365/security/defender-endpoint/controlled-folders) , antiransomware koruması olarak da adlandırılır.*|[grup ilkesi kullanarak denetimli klasör erişimini etkinleştirme](/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy)|
|Microsoft Defender **SmartScreen'i**, internet üzerindeki kötü amaçlı sitelere ve dosyalara karşı korumak için yapılandırın.|[grup ilkesi kullanarak SmartScreen grup ilkesi ve mobil cihaz yönetimi (MDM) ayarlarını Microsoft Defender yapılandırma](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)|
|Kuruluşunuzun Windows çalıştıran cihazlarındaki bilgileri korumak için **şifrelemeyi ve BitLocker'ı yapılandırma**|[BitLocker grup ilkesi ayarları](/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings)|
|Kimlik bilgisi hırsızlığı saldırılarına karşı korumak için **Microsoft Defender Credential Guard'ı yapılandırma**|[grup ilkesi kullanarak Windows Defender Credential Guard'ı etkinleştirme](/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy)|

## <a name="configure-your-microsoft-365-defender-portal"></a>Microsoft 365 Defender portalınızı yapılandırma

Henüz yapmadıysanız, Microsoft 365 Defender portalınızı uyarıları görüntülemek, tehdit koruması özelliklerini yapılandırmak ve kuruluşunuzun genel güvenlik duruşu hakkında ayrıntılı bilgileri görüntülemek için yapılandırın. [bkz. Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender). Ayrıca son kullanıcıların Microsoft 365 Defender portalında görüp göremeyeceğini ve hangi özellikleri görebileceğini de yapılandırabilirsiniz.

- [Microsoft 365 Defender genel bakış](/microsoft-365/security/defender-endpoint/use)
- [Uç nokta koruması: Microsoft 365 Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Sonraki adımlar

- [Defender Güvenlik Açığı Yönetimi'ne genel bakış edinin](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Intune ile Uç Nokta için Microsoft Defender yönetme](manage-mde-post-migration-intune.md)
