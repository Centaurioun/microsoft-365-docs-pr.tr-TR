---
title: Adım 4. Intune ile iyi durumda ve uyumlu cihazlar gerektirme
ms.author: bcarter
author: brendacarter
f1.keywords:
- Conditional access policy
- Microsoft Intune
- Intune device management
manager: dougeby
audience: ITPro
description: kullanıcılar herhangi bir konumdaki herhangi bir cihazdan çalışırken şirket verilerinin güvenliğini sağlayarak uyumlu cihazlar gerektirmek için Azure AD'de bir koşullu erişim ilkesi oluşturun.
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- Conditional access policy
- Microsoft Intune
- M365-security-compliance
- m365solution-managedevices
- m365solution-scenario
- zerotrust-solution
ms.custom: ''
ms.openlocfilehash: 61191da794c065a46d709d443982849ec4c4d3e3
ms.sourcegitcommit: 61b22df76e0f81e5ef11c587b129287886151c79
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2022
ms.locfileid: "66747955"
---
# <a name="step-4-require-healthy-and-compliant-devices-with-intune"></a>Adım 4. Intune ile iyi durumda ve uyumlu cihazlar gerektirme

Koşullu Erişim, hizmete erişime izin vermeden önce cihaz durumunun ek olarak doğrulanmasını sağlar. Koşullu Erişim, koşulları belirtmediğiniz sürece çalışmaz. [3. Adımda. Uyumluluk ilkelerini ayarlayın](manage-devices-with-intune-compliance-policies.md), bir cihazın ortamınıza erişmek için karşılaması gereken minimum gereksinimleri belirten uyumluluk ilkeleri tanımlamıştınız. Bu makalede, uyumlu cihazlar gerektirmek için Azure AD'de ilgili Koşullu Erişim ilkesini oluşturacaksınız. Bu, kullanıcılara herhangi bir cihazdan ve herhangi bir konumdan çalışma olanağı sağlarken kurumsal verilerinizin güvenliğini korumaya yardımcı olur.

Cihaz uyumluluk ilkelerini ayarladıktan ve bunları kullanıcı gruplarına atadıktan sonra Intune cihazın uyumlu olup olmadığını Azure AD sağlar. Bu durumu erişim koşulu olarak kullanmak için Azure AD yöneticinizle birlikte çalışarak uyumlu bilgisayarlar ve mobil cihazlar gerektirmek üzere bir Koşullu Erişim kuralı oluşturmanız gerekir.


![Cihazları yönetme adımları](../media/devices/intune-mdm-step-3.png#lightbox)

Önerilen Sıfır Güven kimliği ve cihaz erişim kuralı kümesi bu kuralı içerir. Aşağıda gösterildiği gibi bkz [. Uyumlu bilgisayarlar ve mobil cihazlar gerektirme](../security/office-365-security/identity-access-policies.md#require-compliant-pcs-and-mobile-devices).


[![kimlik ve cihaz erişim ilkelerini Sıfır Güven](../media/devices/identity-device-require-compliance.png#lightbox)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/devices/identity-device-require-compliance.png)



Şu adımlara özen gösterin:
- Uyumluluk ilkelerinize atadığınız kullanıcı gruplarını Koşullu Erişim ilkesine atanan kullanıcı gruplarıyla koordine edin.
- Koşullu Erişim ilkesini tam olarak atamadan önce Durum ve Denetim Modu özelliklerini kullanarak Koşullu Erişim ilkelerinizi test edin. Bu, ilkenin sonuçlarını anlamanıza yardımcı olur.
- Erişilen verilerin ve/veya uygulamanın gizliliğine uygun bir yetkisiz kullanım süresi ayarlayın. 
- Uyumluluk ilkelerinizin herhangi bir mevzuat veya diğer uyumluluk gereksinimlerini engellemediğinden emin olun. 
- Uyumluluk ilkeleri için cihaz iade aralıklarını anlama.
- Uyumluluk ilkeleriyle yapılandırma profilleri arasındaki çakışmaları önleyin. İsterseniz sonuçları anlayın.

Intune'da ilkeler arasındaki çakışmalar da dahil olmak üzere cihaz profilleriyle ilgili sorunları gidermek için bkz. [Microsoft Intune'da cihaz ilkeleri ve profilleriyle ilgili yaygın sorular ve yanıtlar](/mem/intune/configuration/device-profile-troubleshoot).

Not: Uyumlu bilgisayarlara ihtiyaç duymadan mobil cihazlara ihtiyaç duymadan başlamak istiyorsanız bkz. [Uyumlu bilgisayarlar gerektirme (ancak telefonlar ve tabletler gerekmez)](../security/office-365-security/identity-access-policies.md) 

## <a name="next-steps"></a>Sonraki adımlar

5. Adım'a gidin[. Microsoft Intune'de cihaz profillerini dağıtma](manage-devices-with-intune-configuration-profiles.md)
