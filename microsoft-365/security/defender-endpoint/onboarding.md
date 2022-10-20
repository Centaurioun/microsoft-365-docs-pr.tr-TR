---
title: Uç Nokta için Microsoft Defender hizmetine ekleme
description: Uç noktaları Uç Nokta için Microsoft Defender hizmetine eklemeyi öğrenin
keywords: uç nokta için microsoft defender, ekleme, dağıtma
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-endpointprotect
- m365solution-scenario
- m365-initiative-defender-endpoint
- highpri
- tier1
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: d4bb3297fda9f748a17a8d1018a18f71527d9293
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68637804"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a>Uç Nokta için Microsoft Defender hizmetine ekleme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Uç Nokta için Microsoft Defender dağıtmanın çeşitli aşamaları ve çözüm içindeki özelliklerin nasıl yapılandırılacağı hakkında bilgi edinin.


Uç Nokta için Defender'ı dağıtmak için uygulamanız gereken adımlar şunlardır:

- 1. Adım: Uç noktaları hizmete ekleme
- 2. Adım: Özellikleri yapılandırma

:::image type="content" source="images/deployment-steps.png" alt-text="Dağıtım adımları" lightbox="images/deployment-steps.png":::




## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a>1. Adım: Desteklenen yönetim araçlarından herhangi birini kullanarak uç noktaları ekleme

[Plan dağıtımı](deployment-strategy.md) konusunda, Uç Nokta için Defender'ı dağıtmak için uygulamanız gereken genel adımlar özetlenmiştir.

Ekleme işlemine hızlı bir genel bakış için bu videoyu izleyin ve kullanılabilir araçlar ve yöntemler hakkında bilgi edinin.


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

Mimarinizi tanımladıktan sonra hangi dağıtım yöntemini kullanacağınıza karar vermeniz gerekir. Seçtiğiniz dağıtım aracı, uç noktaları hizmete ekleme yönteminizi etkiler.

### <a name="onboarding-tool-options"></a>Ekleme aracı seçenekleri

Aşağıdaki tabloda, eklemeniz gereken uç noktayı temel alan kullanılabilir araçlar listelenir.

| Uç nokta     | Araç seçenekleri                       |
|--------------|------------------------------------------|
| **Windows**  |  [Yerel betik (en fazla 10 cihaz)](configure-endpoints-script.md) <br>  [Grup İlkesi](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ Mobile Aygıt Yöneticisi](configure-endpoints-mdm.md) <br> [Microsoft Uç Noktası Yapılandırma Yöneticisi](configure-endpoints-sccm.md) <br> [VDI betikleri](configure-endpoints-vdi.md) <br> [Bulut için Microsoft Defender ile tümleştirme](azure-server-integration.md) |
| **macOS**    | [Yerel betikler](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Mobil Cihaz Yönetimi](mac-install-with-other-mdm.md) |
| **Linux Server** | [Yerel betik](linux-install-manually.md) <br> [Kukla](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [Microsoft Endpoint Manager](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a>2. Adım: Özellikleri yapılandırma
Uç noktaları ekledikten sonra özellikleri yapılandıracaksınız. Aşağıdaki tabloda yapılandırabileceğiniz bileşenler listelenmiştir. Kullanmak istediğiniz bileşenleri seçin ve geçerli olmayan bileşenleri kaldırın.

| Yeteneği | Açıklama |
|-|-|
| [Uç Nokta Algılama & Yanıtı (EDR)](overview-endpoint-detection-response.md) | Uç nokta için Defender uç nokta algılama ve yanıt özellikleri, neredeyse gerçek zamanlı ve eyleme dönüştürülebilir gelişmiş saldırı algılamaları sağlar. Güvenlik analistleri uyarıların önceliklerini etkili bir şekilde belirleyebilir, ihlal kapsamının tamamını görebilir ve tehditleri düzeltmek için yanıt eylemleri gerçekleştirebilir. |
| [Microsoft Defender Güvenlik Açığı Yönetimi (MDVM)](next-gen-threat-and-vuln-mgt.md) | Defender Güvenlik Açığı Yönetimi, Uç Nokta için Microsoft Defender bir bileşenidir ve güvenlik yöneticilerine ve güvenlik operasyonları ekiplerine aşağıdakiler dahil olmak üzere benzersiz değer sağlar: - Uç nokta güvenlik açıklarıyla ilişkili gerçek zamanlı uç nokta algılama ve yanıt (EDR) içgörüleri - Olay incelemeleri sırasında çok değerli cihaz güvenlik açığı bağlamı - Yerleşik düzeltme işlemleri Microsoft Intune ve Microsoft System Center Configuration Manager.  |
| [Yeni nesil koruma (NGP)](microsoft-defender-antivirus-windows.md) | Microsoft Defender Virüsten Koruma, masaüstleri, taşınabilir bilgisayarlar ve sunucular için yeni nesil koruma sağlayan yerleşik bir kötü amaçlı yazılımdan koruma çözümüdür. Microsoft Defender Virüsten Koruma şunları içerir:<br> <br>-Yeni ve yeni tehditlerin neredeyse anında algılanması ve engellenmesi için bulut tabanlı koruma. Bulut tabanlı koruma, makine öğrenmesi ve Akıllı Güvenlik Grafı ile birlikte Microsoft Defender Virüsten Koruma'yı destekleyen yeni nesil teknolojilerin bir parçasıdır.<br> <br> - Gelişmiş dosya ve işlem davranışı izleme ve diğer buluşsal yöntemler kullanılarak her zaman açık tarama ("gerçek zamanlı koruma" olarak da bilinir).<br><br> - Makine öğrenmesi, insan ve otomatik büyük veri analizi ve derinlemesine tehdit direnci araştırmalarına dayalı ayrılmış koruma güncelleştirmeleri. |
| [Saldırı Yüzeyini Azaltma (ASR)](overview-attack-surface-reduction.md) | Uç Nokta için Microsoft Defender'daki saldırı yüzeyi azaltma özellikleri, kuruluştaki cihazların ve uygulamaların yeni ve yeni tehditlere karşı korunmasına yardımcı olur. |
| [Otomatik Araştırma & Düzeltme (AIR)](automated-investigations.md) | Uç Nokta için Microsoft Defender, tek tek araştırılması gereken uyarı hacmini önemli ölçüde azaltmak için Otomatik araştırma kullanır. Otomatik araştırma özelliği, uyarıları incelemek ve ihlalleri çözmek için anında düzeltme eylemi uygulamak için analistler tarafından kullanılan çeşitli inceleme algoritmalarından ve işlemlerden (playbook'lar gibi) yararlanır. Bu, uyarı hacmini önemli ölçüde azaltarak güvenlik operasyonları uzmanlarının daha karmaşık tehditlere ve diğer yüksek değerli girişimlere odaklanmasına olanak sağlar. |
| [Microsoft Defender Uzmanları](microsoft-threat-experts.md) | Microsoft Defender Uzmanları, benzersiz ortamlarındaki kritik tehditlerin kaçırılmamasını sağlamaya yardımcı olmak için Güvenlik operasyon merkezlerine (SOC) uzman düzeyinde izleme ve analiz sağlayan yönetilen bir avcılık hizmetidir.      |

Uç noktaları ekledikten sonra uç nokta algılama ve yanıt, yeni nesil koruma ve saldırı yüzeyini azaltma gibi çeşitli özellikleri yapılandıracaksınız.

## <a name="example-deployments"></a>Örnek dağıtımlar

Bu dağıtım kılavuzunda uç noktaları eklemek için iki dağıtım aracı kullanma ve özellikleri yapılandırma konusunda size yol göstereceğiz.

Örnek dağıtımlardaki araçlar şunlardır:

- [Microsoft Endpoint Configuration Manager aracılığı ile katılım](onboarding-endpoint-configuration-manager.md)
- [Microsoft Endpoint Manager aracılığı ile katılım](onboarding-endpoint-manager.md)

Yukarıda bahsedilen dağıtım araçlarını kullanarak aşağıdaki Uç Nokta için Defender özelliklerini yapılandırma konusunda size yol gösterecektir:

- Uç nokta algılama ve yanıt yapılandırması
- Yeni nesil koruma yapılandırması
- Saldırı yüzeyi azaltma yapılandırması

## <a name="related-topics"></a>İlgili konular

- [Microsoft Endpoint Configuration Manager aracılığı ile katılım](onboarding-endpoint-configuration-manager.md)
- [Microsoft Endpoint Manager aracılığı ile katılım](onboarding-endpoint-manager.md)
- [Microsoft 365 E5 aboneliğinde Güvenli Belgeler](../office-365-security/safe-docs.md)
