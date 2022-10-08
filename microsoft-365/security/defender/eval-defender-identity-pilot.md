---
title: Pilot Kimlik için Microsoft Defender
description: Pilot Kimlik için Microsoft Defender, kıyaslamalar ayarlayın, keşif, güvenliği aşılmış kimlik bilgileri, yanal hareket, etki alanı hakimiyeti ve sızdırma uyarıları hakkında öğreticiler alın.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
- tier1
ms.topic: conceptual
ms.openlocfilehash: c5ca701732bd76eff22eeeadf64502f11e2ca5cc
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68086101"
---
# <a name="pilot-microsoft-defender-for-identity"></a>Pilot Kimlik için Microsoft Defender


**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Bu makale, Kimlik için Microsoft Defender için değerlendirme ortamını ayarlama sürecindeki [adım 3/3'tür](eval-defender-identity-overview.md). Bu işlem hakkında daha fazla bilgi için [genel bakış makalesine](eval-defender-identity-overview.md) bakın.

Kimlik için Microsoft Defender pilotunu ayarlamak ve yapılandırmak için aşağıdaki adımları kullanın. Önerilerin pilot grubu ayarlamayı içermediğini unutmayın. En iyi yöntem, algılayıcıyı Active Directory Domain Services (AD DS) ve Active Directory Federasyon Hizmetleri (AD FS) çalıştıran tüm sunucularınıza yüklemektir.

:::image type="content" source="../../media/defender/m365-defender-identity-pilot-steps.png" alt-text="Microsoft Defender değerlendirme ortamında Kimlik için Microsoft Defender pilot oluşturma adımları" lightbox="../../media/defender/m365-defender-identity-pilot-steps.png":::

Aşağıdaki tabloda çizimdeki adımlar açıklanmaktadır.

- [1. Adım: Kimlik ortamınız için karşılaştırma önerilerini yapılandırma](#step-1-configure-benchmark-recommendations-for-your-identity-environment)
- [2. Adım: Özellikleri deneme — Farklı saldırı türlerini tanımlama ve düzeltme öğreticilerinde adım adım ilerleyin ](#step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types)

## <a name="step-1-configure-benchmark-recommendations-for-your-identity-environment"></a>Adım 1. Kimlik ortamınız için karşılaştırma önerilerini yapılandırma

Microsoft, Microsoft Bulut hizmetlerini kullanan müşteriler için güvenlik karşılaştırması önerileri sağlar. [Azure Güvenlik Karşılaştırması](/security/benchmark/azure/overview) (ASB), Azure'da iş yüklerinin, verilerin ve hizmetlerin güvenliğini geliştirmeye yardımcı olmak için açıklayıcı en iyi yöntemler ve öneriler sağlar.

Bu karşılaştırma önerileri [arasında Kimlik için Microsoft Defender için Azure güvenlik temeli yer](/security/benchmark/azure/baselines/defender-for-identity-security-baseline) alır. Bu önerilerin uygulanması planlamak ve uygulamak biraz zaman alabilir. Bunlar kimlik ortamınızın güvenliğini büyük ölçüde artıracak olsa da, Kimlik için Microsoft Defender değerlendirmeye ve uygulamaya devam etmenizi engellememelidir. Bunlar farkındalığınız için burada sağlanır.

## <a name="step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types"></a>Adım 2. Özellikleri deneyin — Farklı saldırı türlerini tanımlama ve düzeltme öğreticilerinde adım adım ilerleyin

Kimlik için Microsoft Defender belgeleri, çeşitli saldırı türlerini tanımlama ve düzeltme sürecinde yol gösteren bir dizi öğretici içerir.

Kimlik için Defender öğreticilerini deneyin:
- [Keşif uyarıları](/defender-for-identity/reconnaissance-alerts)
- [Güvenliği aşılmış kimlik bilgileri uyarıları](/defender-for-identity/compromised-credentials-alerts)
- [Yanal hareket uyarıları](/defender-for-identity/lateral-movement-alerts)
- [Etki alanı hakimiyeti uyarıları](/defender-for-identity/domain-dominance-alerts)
- [Sızdırma uyarıları](/defender-for-identity/exfiltration-alerts)
- [Kullanıcıyı araştırma](/defender-for-identity/investigate-a-user)
- [Bilgisayarı araştırma](/defender-for-identity/investigate-a-computer)
- [Yanal hareket yollarını araştırma](/defender-for-identity/investigate-lateral-movement-path)
- [Varlıkları araştırma](/defender-for-identity/investigate-entity)

## <a name="next-steps"></a>Sonraki adımlar

[Office 365 için Microsoft Defender değerlendirme](eval-defender-office-365-overview.md)

[Değerlendirme Office 365 için Microsoft Defender](eval-defender-office-365-overview.md) için genel bakışa dönün

[Değerlendirme ve pilot Microsoft 365 Defender](eval-overview.md) genel bakışa dönün