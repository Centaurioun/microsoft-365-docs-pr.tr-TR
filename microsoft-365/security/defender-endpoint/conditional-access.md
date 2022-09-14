---
title: Kullanıcıları, cihazları ve verileri daha iyi korumak için Koşullu Erişimi etkinleştirme
description: Bir cihaz risk altında kabul edilirse ve bir uygulamanın uyumsuz olduğu belirlenirse uygulamaların çalışmasını önlemek için Koşullu Erişim'i etkinleştirin.
keywords: koşullu erişim, uygulamaları engelleme, güvenlik düzeyi, intune,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: c1791285917beef8dc881eda2852edf91de2738b
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67679240"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a>Kullanıcıları, cihazları ve verileri daha iyi korumak için Koşullu Erişimi etkinleştirme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-conditionalaccess-abovefoldlink)

Koşullu Erişim, yalnızca güvenli cihazların uygulamalara erişimi olduğundan emin olarak kullanıcılarınızı ve kurumsal bilgilerinizi daha iyi korumanıza yardımcı olan bir özelliktir.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4byD1]

Koşullu Erişim ile, bir cihazın risk düzeyine göre kurumsal bilgilere erişimi denetleyebilirsiniz. Bu, güvenilen uygulamaları kullanarak güvenilen cihazlarda güvenilen kullanıcıların tutulmasına yardımcı olur.

Bir cihaz uyumlu duruma dönene kadar uygulamaların çalışmasını durdurmak için ilkeleri zorunlu kılarak cihazların ve uygulamaların ağınızdan çalıştırabileceği ve bilgilere erişebileceği güvenlik koşulları tanımlayabilirsiniz.

Uç Nokta için Defender'da Koşullu Erişim uygulaması, Microsoft Intune (Intune) cihaz uyumluluk ilkelerini ve Azure Active Directory (Azure AD) koşullu erişim ilkelerini temel alır.

Uyumluluk ilkesi, yalnızca bir veya daha fazla cihaz uyumluluk ilkesi kuralını yerine getiren cihazların uygulamalara erişmesine izin vermek için Koşullu Erişim ile birlikte kullanılır.

## <a name="understand-the-conditional-access-flow"></a>Koşullu Erişim akışını anlama

Koşullu Erişim, cihazda bir tehdit görüldüğünde tehdit düzeltilinceye kadar hassas içeriğe erişimin engellenmesi için uygulanır.

Akış, cihazların düşük, orta veya yüksek riskli olduğu görülerek başlar. Bu risk belirlemeleri daha sonra Intune gönderilir.

Intune'de ilkeleri nasıl yapılandırdığınıza bağlı olarak Koşullu Erişim, belirli koşullar karşılandığında ilkenin uygulanması için ayarlanabilir.

Örneğin, yüksek riskli cihazlara Koşullu Erişim uygulamak için Intune yapılandırabilirsiniz.

Intune'de, uygulamalara erişimi engellemek için Azure AD Koşullu Erişim ile birlikte bir cihaz uyumluluk ilkesi kullanılır. Paralel olarak otomatik bir araştırma ve düzeltme işlemi başlatılır.

 Otomatik araştırma ve düzeltme yapılırken kullanıcı cihazı kullanmaya devam edebilir, ancak tehdit tamamen düzeltilinceye kadar kurumsal verilere erişim engellenir.

Bir cihazda bulunan riski çözmek için cihazı uyumlu bir duruma döndürmeniz gerekir. Cihaz üzerinde hiçbir risk görülmediğinde uyumlu duruma döner.

Riski ele almanın üç yolu vardır:

1. El ile veya otomatik düzeltmeyi kullanın.
2. Cihazdaki etkin uyarıları çözme. Bu işlem cihazdan riski ortadan kaldırır.
3. Cihazı etkin ilkelerden kaldırabilirsiniz ve sonuç olarak, Cihaza Koşullu Erişim uygulanmaz.

El ile düzeltme için bir secops yöneticisinin bir uyarıyı incelemesi ve cihazda görülen riski ele almaları gerekir. Otomatik düzeltme, aşağıdaki Koşullu [Erişimi Yapılandırma](configure-conditional-access.md) bölümünde sağlanan yapılandırma ayarları aracılığıyla yapılandırılır.

Risk el ile veya otomatik düzeltme yoluyla kaldırıldığında cihaz uyumlu duruma döner ve uygulamalara erişim verilir.

Aşağıdaki örnek olay dizisi Koşullu Erişim'i uygulamada açıklar:

1. Kullanıcı kötü amaçlı bir dosya açar ve Uç Nokta için Defender cihazı yüksek riskli olarak işaretler.
2. Yüksek risk değerlendirmesi Intune geçirilir. Paralel olarak, tanımlanan tehdidi düzeltmek için otomatik bir araştırma başlatılır. Tanımlanan tehdidi düzeltmek için el ile düzeltme de yapılabilir.
3. Intune'de oluşturulan ilkeye bağlı olarak cihaz uyumlu değil olarak işaretlenir. Daha sonra değerlendirme, Intune Koşullu Erişim ilkesi tarafından Azure AD iletilir. Azure AD, uygulamalara erişimi engellemek için ilgili ilke uygulanır.
4. El ile veya otomatik araştırma ve düzeltme tamamlanır ve tehdit kaldırılır. Uç Nokta için Defender cihazda hiçbir risk olmadığını görür ve Intune cihazı uyumlu durumda olacak şekilde değerlendirir. Azure AD uygulamalara erişime izin veren ilkeyi uygular.
5. Kullanıcılar artık uygulamalara erişebilir.

## <a name="related-topic"></a>İlgili konu

- [Uç Nokta için Microsoft Defender'de Koşullu Erişimi Yapılandırma](configure-conditional-access.md)
