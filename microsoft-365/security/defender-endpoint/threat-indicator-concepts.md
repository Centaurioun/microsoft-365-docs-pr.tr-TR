---
title: Uç Nokta için Microsoft Defender'daki tehdit bilgileri kavramlarını anlama
description: Kuruluşunuz için özel tehdit uyarıları oluşturun ve Uç Nokta için Microsoft Defender'de tehdit bilgileriyle ilgili kavramları öğrenin
keywords: tehdit bilgileri, uyarı tanımları, güvenliğin aşılmasına ilişkin göstergeler, ioc
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: d22f71e732f98bc84816eee4863209905928c7a8
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67689327"
---
# <a name="understand-threat-intelligence-concepts"></a>Tehdit bilgileri kavramlarını anlayın

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-threatindicator-abovefoldlink)

Gelişmiş siber güvenlik saldırıları birden fazla karmaşık kötü amaçlı olay, öznitelik ve bağlamsal bilgiden oluşur. Bu etkinliklerden hangilerinin şüpheli olarak nitelendirildiğine karar vermek zor bir görev olabilir. Sektörünüzle ilgili bilinen öznitelikler ve anormal etkinlikler hakkında bilgi sahibi olmak, gözlemlenen bir davranışın ne zaman şüpheli olarak adlandırıldığını bilmeniz açısından önemlidir.

Microsoft 365 Defender ile kuruluşunuzdaki olası saldırı etkinliklerini izlemenize yardımcı olabilecek özel tehdit uyarıları oluşturabilirsiniz. Şüpheli olayları işaretleyebilir ve ipuçlarını bir araya getirerek bir saldırı zincirini durdurabilirsiniz. Bu özel tehdit uyarıları yalnızca kuruluşunuzda görünür ve izlemek üzere ayarladığınız olayları bayrakla işaretler.

Özel tehdit uyarıları oluşturmadan önce, uyarı tanımlarının ve güvenlik ihlal göstergelerinin (ICS) arkasındaki kavramların ve aralarındaki ilişkinin bilinmesi önemlidir.

## <a name="alert-definitions"></a>Uyarı tanımları
Uyarı tanımları, olası bir siber güvenlik saldırısıyla ilgili erken ipuçlarını belirlemek için toplu olarak kullanılabilecek bağlamsal özniteliklerdir. Bu göstergeler genellikle bir saldırganın saldırı hedefine başarıyla ulaşmak için gerçekleştirilen etkinliklerin, özelliklerin ve eylemlerin bir birleşimidir. Bu öznitelik birleşimlerinin izlenmesi, saldırılara karşı bir bakış noktası elde etme ve bir saldırganın amacına ulaşılamadan önce olay zincirine müdahale etme açısından kritik öneme sahiptir.

## <a name="indicators-of-compromise-ioc"></a>Güvenliğin aşılmasına ilişkin göstergeler (IOC)
GÇC'ler, bir ağ veya cihazın zaten ihlal edildiğini gösteren tek tek bilinen kötü amaçlı olaylardır. Uyarı tanımlarından farklı olarak, bu göstergeler ihlal kanıtı olarak kabul edilir. Genellikle bir saldırı yapıldıktan ve filtrasyon gibi hedefe ulaşıldıktan sonra görülürler. Adli araştırmalar sırasında GÇC'lerin izlenmesi de önemlidir. Bir saldırı zincirine müdahale edemeyebilir ancak bu göstergeleri toplamak, gelecekteki olası saldırılar için daha iyi savunmalar oluşturmada yararlı olabilir.

## <a name="relationship-between-alert-definitions-and-iocs"></a>Uyarı tanımları ile ICS arasındaki ilişki
Microsoft 365 Defender ve Uç Nokta için Microsoft Defender bağlamında, uyarı tanımları IOC'ler için kapsayıcılardır ve belirli bir IOC eşleşmesi için tetiklenen meta veriler de dahil olmak üzere uyarıyı tanımlar. Uyarı tanımlarının bir parçası olarak çeşitli meta veriler sağlanır. Saldırının uyarı tanımı adı, önem derecesi ve açıklama gibi meta veriler diğer seçeneklerle birlikte sağlanır.

Her IOC, somut algılama mantığını türüne, değerine ve eylemine göre tanımlar ve bunun nasıl eşleştirileceğini belirler. Algılamanın Microsoft 365 Defender konsolunda uyarı olarak nasıl görüntüleneceğini tanımlayan belirli bir uyarı tanımına bağlıdır.

IOC örneği aşağıda verilmiştir:
- Tür: Sha1
- Değer: 92cfceb39d57d914ed8b14d0e37643de0797ae56
- Eylem: Eşittir

IOC'lerin uyarı tanımlarıyla çoka bir ilişkisi vardır. Bu ilişki uyarı tanımına karşılık gelen birçok GÇ'ye sahip olabilir.


## <a name="related-topics"></a>İlgili konular
- [Göstergeleri yönetin](manage-indicators.md)
