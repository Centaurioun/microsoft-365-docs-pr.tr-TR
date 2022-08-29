---
title: Microsoft dışı uç nokta korumasından Uç Nokta için Microsoft Defender geçiş yapma
description: Uç nokta koruma çözümünüz için Microsoft Defender Virüsten Koruma'yı içeren Uç Nokta için Microsoft Defender geçiş yapın.
keywords: geçiş, windows defender, gelişmiş uç nokta koruması, virüsten koruma, kötü amaçlı yazılımdan koruma, pasif mod, etkin mod
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
- m365solution-overview
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
- m365initiative-defender-endpoint
ms.topic: overview
ms.custom: migrationguides
ms.date: 11/29/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 63b932df7337a757a0358719e32409ab8c6ea117
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2022
ms.locfileid: "67331307"
---
# <a name="make-the-switch-from-non-microsoft-endpoint-protection-to-microsoft-defender-for-endpoint"></a>Microsoft dışı uç nokta korumasından Uç Nokta için Microsoft Defender geçiş yapma

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Microsoft dışı bir uç nokta koruma çözümünden [Uç Nokta için Microsoft Defender](microsoft-defender-endpoint.md) 'a (Uç Nokta için Defender) geçmeyi düşünüyorsanız veya planlama aşamasındaysanız, bu makaleyi kılavuz olarak kullanın. Bu makalede, Uç Nokta için Defender'a genel geçiş işlemi açıklanmaktadır.

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Uç nokta koruma çözümünüzü Uç Nokta için Defender'a geçirme işlemi" lightbox="images/nonms-mde-migration.png":::

Uç Nokta için Defender'a geçiş yaptığınızda, etkin modda Microsoft dışı virüsten koruma/kötü amaçlı yazılımdan koruma ile başlarsınız. Ardından, Microsoft Defender Virüsten Koruma'yı pasif modda yapılandırıp cihazlarınızı Uç Nokta için Defender'a eklersiniz. Ardından uç nokta koruma özelliklerinizi yapılandıracak, Microsoft Defender Virüsten Koruma'yı etkin moda ayarlayacak ve her şeyin düzgün çalıştığını doğrulaacaksınız. Son olarak, Microsoft dışı çözümü kaldırırsınız.

## <a name="the-migration-process"></a>Geçiş işlemi

Uç Nokta için Defender'a geçiş işlemi, aşağıdaki tabloda açıklandığı gibi üç aşamaya ayrılabilir:

:::image type="content" source="images/phase-diagrams/migration-phases.png" alt-text="MDE geçiş işlemi" lightbox="images/phase-diagrams/migration-phases.png":::


<br/><br/>

|Aşama|Açıklama|
|--|--|
|[Geçişiniz için hazırlanma](switch-to-mde-phase-1.md)|[**Hazırlama** aşamasında](switch-to-mde-phase-1.md): <br/>1. Kuruluşunuzun cihazlarını güncelleştirin.<br/>2. Uç Nokta için Defender'ı edinin.<br/>3. Rolleri ve izinleri planlayın ve Microsoft 365 Defender portalına erişim verin.<br/>4. Kuruluşunuzun cihazlarıyla Uç Nokta için Defender arasında iletişimi etkinleştirmek için cihaz proxy'nizi ve İnternet ayarlarınızı yapılandırın. |
|[Uç Nokta için Defender'ın ayarlanması](switch-to-mde-phase-2.md)|[**Kurulum** aşamasında](switch-to-mde-phase-2.md): <br/>1. Microsoft Defender Virüsten Koruma'yı etkinleştirin/yeniden yükleyin ve pasif moda ayarlayın.<br/>2. Uç Nokta için Defender'ı yapılandırın.<br/>3. Uç Nokta için Defender'ı mevcut çözümünüz için dışlama listesine ekleyin.<br/>4. Mevcut çözümünüzü Microsoft Defender Virüsten Koruma için dışlama listesine ekleyin.<br/>5. Cihaz gruplarınızı, koleksiyonlarınızı ve kuruluş birimlerinizi ayarlayın.<br/>6. Kötü amaçlı yazılımdan koruma ilkelerinizi ve gerçek zamanlı koruma ayarlarınızı yapılandırın.|
|[Uç Nokta için Defender'a ekleme](switch-to-mde-phase-3.md)|[**Ekleme** aşamasında](switch-to-mde-phase-3.md): <br/>1. Cihazlarınızı Uç Nokta için Defender'a ekleme.<br/>2. Algılama testi çalıştırın.<br/>3. Microsoft Defender Virüsten Koruma'nın pasif modda çalıştığını onaylayın.<br/>4. Microsoft Defender Virüsten Koruma güncelleştirmelerini alın.<br/>5. Mevcut uç nokta koruma çözümünüzü kaldırın.<br/>6. Uç Nokta için Defender'ın düzgün çalıştığından emin olun.|

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender neler dahildir?

Bu geçiş kılavuzunda, Uç Nokta için Defender'a geçiş için başlangıç noktası olarak [yeni nesil koruma](microsoft-defender-antivirus-in-windows-10.md) [ve uç nokta algılama ve yanıt](overview-endpoint-detection-response.md) özelliklerine odaklanacağız. Ancak Uç Nokta için Defender, virüsten koruma ve uç nokta korumasından çok daha fazlasını içerir. Uç Nokta için Defender, önleyici koruma, ihlal sonrası algılama, otomatik araştırma ve yanıt için birleşik bir platformdur. Aşağıdaki tabloda Uç Nokta için Defender'daki özellikler ve özellikler özetlenmiştir.

<br/><br/>

|Özellik/Yetenek|Açıklama|
|---|---|
|[Microsoft Defender Güvenlik Açığı Yönetimi](next-gen-threat-and-vuln-mgt.md)|Defender Güvenlik Açığı Yönetimi özellikleri uç noktalarınızdaki (cihazlar gibi) zayıf noktaları belirlemenize, değerlendirmenize ve düzeltmenize yardımcı olur.|
|[Saldırı yüzeyini azaltma](overview-attack-surface-reduction.md)|Saldırı yüzeyi azaltma kuralları, kuruluşunuzun cihazlarını ve uygulamalarını siber tehditlere ve saldırılara karşı korumaya yardımcı olur.|
|[Yeni nesil koruma](microsoft-defender-antivirus-in-windows-10.md)|Yeni nesil koruma, tehditleri ve kötü amaçlı yazılımları engellemeye yardımcı olmak için Microsoft Defender Virüsten Koruma içerir.|
|[Uç nokta algılama ve yanıt](overview-endpoint-detection-response.md)|Uç nokta algılama ve yanıt özellikleri, yetkisiz erişim girişimlerini ve etkin ihlalleri algılar, araştırır ve yanıtlar.|
|[Gelişmiş avcılık örneği](advanced-hunting-overview.md)|Gelişmiş tehdit avcılığı özellikleri, güvenlik operasyonları ekibinizin bilinen veya olası tehditlerin göstergelerini ve varlıklarını bulmasını sağlar.|
|[Davranışsal engelleme ve kapsama](behavioral-blocking-containment.md)|Davranış engelleme ve kapsama özellikleri, tehdit yürütmeye başladığında bile davranışlarına ve işlem ağaçlarına bağlı olarak tehditleri tanımlamaya ve durdurmaya yardımcı olur.|
|[Otomatik araştırma ve düzeltme](automated-investigations.md)|Otomatik araştırma ve yanıt özellikleri uyarıları inceler ve ihlalleri çözmek için anında düzeltme eylemi gerçekleştirin.|
|[Tehdit avcılığı hizmeti](microsoft-threat-experts.md) (Microsoft Tehdit Uzmanları)|Tehdit avcılığı hizmetleri, güvenlik operasyonları ekiplerine uzman düzeyinde izleme ve analiz sağlar ve kritik tehditlerin kaçırılmamasını sağlamaya yardımcı olur.|

**Daha fazla bilgi edinmek ister misiniz? Bkz [. Uç Nokta için Defender](microsoft-defender-endpoint.md).**

## <a name="next-step"></a>Sonraki adım

- [Geçişiniz için hazırlanma'ya](switch-to-mde-phase-1.md) geçin.
