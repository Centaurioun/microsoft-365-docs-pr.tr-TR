---
title: ASR kuralı dağıtım ve algılamalarını iyileştirme
description: Tipik kötü amaçlı yazılım kötüye kullanımlarını belirlemek ve önlemek için saldırı yüzeyi azaltma (ASR) kurallarınızı iyileştirin.
keywords: ekleme, Intune yönetimi, Uç Nokta için Microsoft Defender, Microsoft Defender, Windows Defender, saldırı yüzeyini azaltma, ASR, güvenlik temeli
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 2ffb34994d37cff3d729b54bfa3e65911f98e21f
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67701444"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a>ASR kuralı dağıtım ve algılamalarını iyileştirme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

[Saldırı yüzeyini azaltma (ASR) kuralları](./attack-surface-reduction.md) , tipik kötü amaçlı yazılım açıklarını tanımlar ve önler. Kötü amaçlı olabilecek kodun ne zaman ve nasıl çalışabileceğini denetler. Örneğin, JavaScript veya VBScript'in indirilen yürütülebilir dosyayı başlatmasını engelleyebilir, Office makrolarından Win32 API çağrılarını engelleyebilir ve USB sürücülerden çalışan işlemleri engelleyebilir.


:::image type="content" source="../../media/attack-surface-mgmt.png" alt-text="Saldırı yüzeyi yönetim kartı" lightbox="../../media/attack-surface-mgmt.png":::
<br>
*Saldırı yüzeyi yönetim kartı*

*Saldırı yüzeyi yönetim kartı*, <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalındaki</a> araçlara giriş noktasıdır ve şunları yapmak için kullanabilirsiniz:

* ASR kurallarının kuruluşunuzda şu anda nasıl dağıtıldığından emin olun.
* ASR algılamalarını gözden geçirin ve olası yanlış algılamaları belirleyin.
* Dışlamaların etkisini analiz edin ve dışlamak için dosya yollarının listesini oluşturun.

**Saldırı yüzeyi yönetimi** \> **Raporları** \> **Saldırı yüzeyi azaltma kuralları** \> **Dışlama ekle'yi** seçin. Buradan, Microsoft 365 Defender portalın diğer bölümlerine gidebilirsiniz.

:::image type="content" source="images/secconmgmt_asr_m365exlusions.png" alt-text="Microsoft 365 Defender portalındaki Saldırı yüzeyi azaltma kuralları sayfasında dışlamalar ekleme sekmesi" lightbox="images/secconmgmt_asr_m365exlusions.png":::<br>
*Microsoft 365 Defender portalındaki Saldırı yüzeyi azaltma kuralları sayfasındaki **Dışlama ekle** sekmesi*

> [!NOTE]
> Microsoft 365 Defender portalına erişmek için Microsoft 365 E3 veya E5 lisansına ve Azure Active Directory'de belirli rollere sahip bir hesaba ihtiyacınız vardır. [Gerekli lisanslar ve izinler hakkında bilgi edinin](/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalında</a> ASR kuralı dağıtımı hakkında daha fazla bilgi için bkz. [ASR kuralı dağıtımını ve algılamalarını izleme ve yönetme](/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections).

**İlgili konular**

* [Cihazlarınızı doğru yapılandırıldığından emin olun](configure-machines.md)
* [cihazları Uç Nokta için Microsoft Defender ekleme](configure-machines-onboarding.md)
* [Uç Nokta için Microsoft Defender güvenlik temeline uyumluluğu izleme](configure-machines-security-baseline.md)
