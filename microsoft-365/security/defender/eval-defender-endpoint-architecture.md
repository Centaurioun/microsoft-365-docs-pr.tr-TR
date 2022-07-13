---
title: Uç Nokta için Microsoft Defender mimari gereksinimlerini ve temel kavramları gözden geçirin
description: Microsoft 365 Defender'daki Uç Nokta için Microsoft Defender için teknik diyagram, deneme laboratuvarınızı veya pilot ortamınızı oluşturmadan önce Microsoft 365'teki kimliği anlamanıza yardımcı olur.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 5197acd8ceb3a2dea7c03b0ef076bca5dc9138dd
ms.sourcegitcommit: 61b22df76e0f81e5ef11c587b129287886151c79
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2022
ms.locfileid: "66749143"
---
# <a name="review-microsoft-defender-for-endpoint-architecture-requirements-and-key-concepts"></a>Uç Nokta için Microsoft Defender mimari gereksinimlerini ve temel kavramları gözden geçirin

**Şunlar için geçerlidir:** Microsoft 365 Defender

Bu makale, Uç Nokta için Microsoft Defender ortamı için değerlendirmeyi ayarlama sürecinde size yol gösterir.

Bu işlem hakkında daha fazla bilgi için [genel bakış makalesine](eval-defender-endpoint-overview.md) bakın.

Uç Nokta için Microsoft Defender etkinleştirmeden önce mimariyi anladığınızdan ve gereksinimleri karşılayabildiğinize emin olun.

## <a name="understand-the-architecture"></a>Mimariyi anlama

Aşağıdaki diyagramda Uç Nokta için Microsoft Defender mimarisi ve tümleştirmeleri gösterilmektedir. 

:::image type="content" source="../../media/defender/m365-defender-endpoint-architecture.png" alt-text="Office için Microsoft Defender'ı Defender değerlendirme ortamına ekleme adımları" lightbox="../../media/defender/m365-defender-endpoint-architecture.png":::

Aşağıdaki tabloda çizim açıklanmaktadır.

Açıklama balonu | Açıklama
:---|:---|
1 | Cihazlar, desteklenen yönetim araçlarından biri aracılığıyla eklenir. 
2 | Yerleşik cihazlar, Uç Nokta için Microsoft Defender sinyal verilerini sağlar ve yanıtlar.
3 | Yönetilen cihazlar Azure Active Directory'ye katılır ve/veya kaydedilir.
4 | Etki alanına katılmış Windows cihazları, Azure Active Directory Connect kullanılarak Azure Active Directory ile eşitlenir.
5 | Uç Nokta için Microsoft Defender uyarılar, araştırmalar ve yanıtlar Microsoft 365 Defender yönetilir.

## <a name="understand-key-concepts"></a>Temel kavramları anlama

Aşağıdaki tabloda, Uç Nokta için Microsoft Defender değerlendirilirken, yapılandırılırken ve dağıtılırken anlaşılması gereken önemli kavramlar tanımlanmıştır: 

Kavram | Açıklama | Daha fazla bilgi
:---|:---|:---|
Yönetim Portalı | Olası gelişmiş kalıcı tehdit etkinliği veya veri ihlalleri uyarılarını izlemek ve yanıtlamak için portal Microsoft 365 Defender. | [Uç Nokta için Microsoft Defender portalına genel bakış](/microsoft-365/security/defender-endpoint/portal-overview)
Saldırı Yüzeyi Azaltma | Kuruluşunuzun siber tehditlere ve saldırılara karşı savunmasız olduğu yerleri en aza indirerek saldırı yüzeylerinizi azaltmaya yardımcı olun. | [Saldırı yüzeyini azaltmaya genel bakış](/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction)
Uç Nokta Algılama ve Yanıt | Uç nokta algılama ve yanıt özellikleri, neredeyse gerçek zamanlı ve eyleme dönüştürülebilir gelişmiş saldırı algılamaları sağlar. | [Uç nokta algılama ve yanıt özelliklerine genel bakış](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)
Davranış Engelleme ve Kapsama | Davranış engelleme ve kapsama özellikleri, tehdit yürütmeye başladığında bile davranışlarına ve işlem ağaçlarına bağlı olarak tehditleri tanımlamaya ve durdurmaya yardımcı olabilir. | [Davranışsal engelleme ve kapsama](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment)
Otomatik Araştırma ve Yanıt | Otomatik araştırma, güvenlik analistleri tarafından kullanılan ve uyarıları incelemek ve ihlalleri çözmek için anında işlem yapmak üzere tasarlanmış işlemlere dayalı çeşitli inceleme algoritmaları kullanır. | [Tehditleri araştırmak ve düzeltmek için otomatik araştırma kullanma](/microsoft-365/security/defender-endpoint/automated-investigations)
Gelişmiş Avcılık | Gelişmiş tehdit avcılığı, tehdit göstergelerini ve varlıkları bulmak için ağınızdaki olayları proaktif olarak inceleyebilmeniz için 30 güne kadar ham verileri keşfetmenizi sağlayan sorgu tabanlı bir tehdit avcılığı aracıdır. | [Gelişmiş avlanmaya genel bakış](/microsoft-365/security/defender-endpoint/advanced-hunting-overview)
Tehdit Analizi | Tehdit analizi, uzman Microsoft güvenlik araştırmacılarının en ilgili tehditleri kapsayan bir dizi raporudur. | [Ortaya çıkan tehditleri izleyin ve yanıtlayın](/microsoft-365/security/defender-endpoint/threat-analytics)


Uç Nokta için Microsoft Defender özellikleri hakkında daha ayrıntılı bilgi için bkz. [Uç Nokta için Microsoft Defender nedir](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)?

## <a name="siem-integration"></a>SIEM tümleştirmesi

Kuruluşunuz genelindeki güvenlik olaylarını daha kapsamlı bir şekilde analiz etmek ve etkili ve anında yanıt almak için playbook'lar oluşturmak için Uç Nokta için Microsoft Defender Microsoft Sentinel ile tümleştirebilirsiniz. 

Uç Nokta için Microsoft Defender diğer Güvenlik Bilgileri ve Olay Yönetimi (SIEM) çözümleriyle de tümleştirilebilir. Daha fazla bilgi için bkz. [Uç Nokta için Microsoft Defender'de SIEM tümleştirmesini etkinleştirme](/microsoft-365/security/defender-endpoint/enable-siem-integration).


## <a name="next-steps"></a>Sonraki adımlar
[Değerlendirmeyi etkinleştirin](eval-defender-endpoint-enable-eval.md)

[Değerlendirme Uç Nokta için Microsoft Defender](eval-defender-endpoint-overview.md) için genel bakışa dönün

[Değerlendirme ve pilot Microsoft 365 Defender](eval-overview.md) genel bakışa dönün
