---
title: İçeriden risk yönetimi
description: Insider risk yönetimini yapılandırmayı öğrenin. Insider risk yönetimi, risk göstergelerini tanımlamak için belirli ilkeler tanımlamanızı sağlar.
keywords: Microsoft 365, Microsoft Purview, insider riski, risk yönetimi, uyumluluk
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- tier1
- purview-compliance
- m365solution-insiderrisk
- m365initiative-compliance
- m365solution-scenario
- highpri
ms.openlocfilehash: c3d4e6662806cbf2a821e0ef4228e5efa87a012e
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68733603"
---
# <a name="insider-risk-management"></a>İçeriden risk yönetimi

> [!IMPORTANT]
> Microsoft Purview İçeriden Risk Yönetimi IP hırsızlığı, veri sızıntısı ve güvenlik ihlalleri gibi olası kötü amaçlı veya yanlışlıkla insider risklerini belirlemek için çeşitli sinyalleri ilişkilendirmektedir. Insider risk yönetimi, müşterilerin güvenlik ve uyumluluğu yönetmek için ilkeler oluşturmasına olanak tanır. Tasarım gereği gizlilikle oluşturulan kullanıcılar varsayılan olarak takma ad kullanır ve kullanıcı düzeyinde gizlilik sağlamaya yardımcı olmak için rol tabanlı erişim denetimleri ve denetim günlükleri kullanılır.

Çalışanlar artık geniş bir platform ve hizmet yelpazesinde veri oluşturmak, yönetmek ve paylaşmak için daha fazla erişime sahip. Çoğu durumda kuruluşlar, uyumluluk gereksinimlerini ve çalışan gizlilik standartlarını karşılarken kuruluş genelindeki riskleri belirlemek ve azaltmak için sınırlı kaynaklara ve araçlara sahiptir. Bu riskler, çalışanları terk ederek olası veri hırsızlığını ve yanlışlıkla fazla paylaşım veya kötü amaçlı olarak kuruluşunuzun dışındaki bilgilerin veri sızıntısı riskini içerir.

Microsoft Purview İçeriden Risk Yönetimi, riskli olabilecek etkinlikleri hızla tanımlamanıza, önceliklendirmenize ve harekete geçirmenize yardımcı olmak için hizmetin ve üçüncü taraf göstergelerin tamamını kullanır. Insider risk yönetimi, Microsoft 365 ve Microsoft Graph günlüklerini kullanarak risk göstergelerini tanımlamak için belirli ilkeler tanımlamanızı sağlar. Riskleri belirledikten sonra, bu riskleri azaltmak için eylem gerçekleştirebilir ve gerekirse açık soruşturma davaları açabilir ve uygun yasal işlemleri gerçekleştirebilirsiniz.

Insider risk yönetiminin kuruluşunuzun riskleri engellemesine, algılamasına ve içermesine nasıl yardımcı olabileceğini öğrenmek için aşağıdaki videoları izleyin:


**Insider risk yönetimi çözümü geliştirme &**:
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4j9CN]
<br>

**Insider risk yönetimi iş akışı**:
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OUXB]

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="configure-insider-risk-management"></a>Insider risk yönetimini yapılandırma

Kuruluşunuzda insider risk yönetimini yapılandırmak için aşağıdaki adımları kullanın:

![Insider risk çözümü insider risk yönetimi adımları](../media/ir-solution-ir-steps.png)

1. [Insider risk yönetimi](insider-risk-management.md) hakkında bilgi edinin
2. [Insider risk yönetimini planlama ve lisanslama doğrulama](insider-risk-management-plan.md)
3. [Insider risk yönetimi ayarlarını yapılandırma](insider-risk-management-settings.md)
4. [bağlayıcılar & izinleri ve ilke önkoşullarını](insider-risk-management-configure.md#step-4-recommended-configure-prerequisites-for-policies) yapılandırma [](insider-risk-management-configure.md#step-1-required-enable-permissions-for-insider-risk-management)
5. [Insider risk yönetimi ilkeleri](insider-risk-management-configure.md#step-6-required-create-an-insider-risk-management-policy) oluşturma ve yapılandırma

## <a name="more-information-about-insider-risk-management"></a>Insider risk yönetimi hakkında daha fazla bilgi

- [Insider risk ilkelerini yönetme](insider-risk-management-policies.md)
- [İçeriden risk etkinliklerini araştırma](insider-risk-management-activities.md)
- [İçeriden gelen risk durumlarına göre işlem yapma](insider-risk-management-cases.md)
