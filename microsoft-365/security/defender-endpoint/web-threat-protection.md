---
title: Kuruluşunuzu web tehditlerine karşı koruma
description: Uç Nokta için Microsoft Defender'da web koruması ve kuruluşunuzu nasıl koruyabileceği hakkında bilgi edinin.
keywords: web koruması, web tehdit koruması, web'e göz atma, güvenlik, kimlik avı, kötü amaçlı yazılım, yararlanma, web siteleri, ağ koruması, Edge, Internet Explorer, Chrome, Firefox, web tarayıcısı
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
ms.date: 08/22/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: ceef4631ca578e7fc091989a83fb3fa2362ece15
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68637276"
---
# <a name="protect-your-organization-against-web-threats"></a>Kuruluşunuzu web tehditlerine karşı koruma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Web tehdit koruması, Uç Nokta için Defender'da [Web korumasının](web-protection-overview.md) bir parçasıdır. Cihazlarınızın web tehditlerine karşı güvenliğini sağlamak için [ağ koruması](network-protection.md) kullanır. Web tehdit koruması, Microsoft Edge ve Chrome ve Firefox gibi popüler üçüncü taraf tarayıcılarla tümleştirilerek web proxy'si olmadan web tehditlerini durdurur ve cihazları dışarıda veya şirket içindeyken koruyabilir. Web tehdit koruması, kimlik avı sitelerine, kötü amaçlı yazılım vektörlerine, güvenlik açığından yararlanma sitelerine, güvenilmeyen veya saygınlığı düşük sitelere ve [özel gösterge listenizde](manage-indicators.md) engellediğiniz sitelere erişimi durdurur.

> [!NOTE]
> Cihazların yeni özel göstergeler alması iki saate kadar sürebilir.

## <a name="prerequisites"></a>Önkoşullar

Web koruması, Microsoft Edge ve üçüncü taraf web tarayıcılarında web'e gözatma güvenliği sağlamak için ağ korumasını kullanır.

Cihazlarınızda ağ korumasını açmak için:

- Dağıtmadan veya yeniden dağıtmadan önce ağ korumasını etkinleştirmek için **Web & Ağ Koruması** altında Uç Nokta için Defender güvenlik temelini düzenleyin. [Uç Nokta için Defender güvenlik temelini gözden geçirme ve atama hakkında bilgi edinin](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- Intune cihaz yapılandırması, SCCM, grup ilkesi veya MDM çözümünüzü kullanarak ağ korumasını açın. [Ağ korumasını etkinleştirme hakkında daha fazla bilgi edinin](enable-network-protection.md)

> [!NOTE]
> Ağ korumasını **Yalnızca denetle** olarak ayarlarsanız engelleme kullanılamaz. Ayrıca, yalnızca Microsoft Edge'de kötü amaçlı ve istenmeyen web sitelerine erişme girişimlerini algılayabilir ve günlüğe kaydedebilirsiniz.

## <a name="configure-web-threat-protection"></a>Web tehdit korumasını yapılandırma

Aşağıdaki yordamda, Microsoft Endpoint Manager yönetim merkezini kullanarak web tehdit korumasının nasıl yapılandırıldığı açıklanmaktadır.

1. Microsoft Endpoint Manager yönetim merkezine ()[https://endpoint.microsoft.com](https://endpoint.microsoft.com) gidin ve oturum açın.
 
2. **Uç nokta güvenliği** \> **Saldırı yüzeyi azaltma'yı** ve ardından **+ İlke oluştur'u** seçin.

3. **Windows 10 ve üzeri** gibi bir platform seçin, **Web koruma** profilini ve ardından **Oluştur'u** seçin. 

4. **Temel Bilgiler** sekmesinde, bir ad ve açıklama belirtin ve ardından **İleri'yi** seçin.

5. **Yapılandırma ayarları** sekmesinde **Web Koruması'nı** genişletin, ayarlarınızı belirtin ve **ardından İleri'yi** seçin.

   - **Web korumasının açık olması için Ağ korumasını etkinleştir** **seçeneğini Etkin** olarak ayarlayın. Alternatif olarak, ortamınızda nasıl çalışacağını görmek için ağ korumasını **Denetim moduna** ayarlayabilirsiniz. Denetim modunda ağ koruması kullanıcıların siteleri veya etki alanlarını ziyaret etmesini engellemez, ancak algılamaları olay olarak izler. 
   - Kullanıcıları olası kimlik avı dolandırıcılığına ve kötü amaçlı yazılımlara karşı korumak **için Microsoft Edge'in eski sürümü için SmartScreen iste** seçeneğini **Evet** olarak ayarlayın.
   - Kullanıcıların kötü amaçlı olabilecek sitelerle ilgili uyarıları atlamasını önlemek için **Kötü amaçlı site erişimini engelle** seçeneğini **Evet** olarak ayarlayın.
   - Kullanıcıların uyarıları atlamasını ve doğrulanmamış dosyaları indirmesini önlemek için **Doğrulanmamış dosya indirmeyi engelle** seçeneğini **Evet** olarak ayarlayın. 

6. **Kapsam etiketleri** sekmesinde, kuruluşunuz kapsam etiketleri kullanıyorsa **+ Kapsam etiketlerini seçin'i** ve ardından **İleri'yi** seçin. (Kapsam etiketleri kullanmıyorsanız **İleri'yi** seçin.) Kapsam etiketleri hakkında daha fazla bilgi edinmek için bkz. [Dağıtılmış BT için rol tabanlı erişim denetimi (RBAC) ve kapsam etiketlerini kullanma](/mem/intune/fundamentals/scope-tags).

7. **Atamalar** sekmesinde, web koruma ilkesini alacak kullanıcıları ve cihazları belirtin ve ardından **İleri'yi** seçin.

8. **Gözden Geçir + oluştur** sekmesinde ilke ayarlarınızı gözden geçirin ve **oluştur'u** seçin.

## <a name="related-topics"></a>İlgili konular

- [Web korumasına genel bakış](web-protection-overview.md)
- [Web tehdit koruması](web-threat-protection.md)
- [Web güvenliğini izleyin](web-protection-monitoring.md)
- [Web tehditlerine yanıt verin](web-protection-response.md)
- [Ağ koruması](network-protection.md)
