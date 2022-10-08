---
title: Microsoft Tehdit Uzmanları
ms.reviewer: ''
description: Microsoft Tehdit Uzmanları, Uç Nokta için Microsoft Defender için ek bir uzmanlık katmanı sağlar.
keywords: yönetilen tehdit avcılığı hizmeti, yönetilen tehdit avcılığı, yönetilen algılama ve yanıt (MDR) hizmeti, MTE, Microsoft Tehdit Uzmanları, uç nokta saldırı bildirimi, Uç Nokta Saldırısı Bildirimi, Defender Uzmanlarına Sorun
search.product: Windows 10
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 08ab7a523b13620403931fd0b28e7d51a370ebe1
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68227624"
---
# <a name="microsoft-threat-experts"></a>Microsoft Tehdit Uzmanları

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> Ağustos 2022 itibarıyla, **Bir tehdit uzmanına danışmak** için İsteğe Bağlı Uzmanlar seçeneği **Defender Uzmanlara Sor** olarak yeniden tanımlanmıştır.

Microsoft Tehdit Uzmanları, güvenlik operasyon merkezlerinize (SOC) benzersiz ortamlarınızdaki kritik tehditlerin kaçırılmamasını sağlamaya yardımcı olmak için uzman düzeyinde izleme ve analiz sağlayan bir yönetilen tehdit avcılığı hizmetidir.

Bu yönetilen tehdit avcılığı hizmeti, şu iki özellik aracılığıyla uzman odaklı içgörüler ve veriler sağlar: uç nokta saldırısı bildirimi ve isteğe bağlı uzmanlara erişim.

Microsoft Tehdit Uzmanları güvenlik operasyon merkezlerine (SOC) uzman düzeyinde izleme ve analiz sağlamayı ve kritik bir tehdidin kaçırılmamasını sağlamayı öğrenmek için bu videoyu izleyin. 
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qZ0B]

## <a name="before-you-begin"></a>Başlamadan önce

> [!NOTE]
> Yönetilen tehdit avcılığı hizmetine başvurmadan önce Microsoft Teknik Hizmet sağlayıcınız ve hesap ekibinizle uygunluk gereksinimlerini tartışın.
> Tehdit Uzmanları şu anda ABD Kamu bulutları için Microsoft 365'te kullanılamaz.

Uç Nokta için Microsoft Defender müşterisiyseniz, ortamınızdaki en kritik tehditleri hızla yanıtlamanıza yardımcı olan özel içgörüler ve analizler elde etmek için **Uç Nokta Saldırısı Bildirimleri'ne** başvurmanız gerekir.

Endpoint Attack Notifications avantajlarına kaydolmak için, uygulanacak **Ayarlar** \> **Uç Noktaları** \> **Genel** \> **Gelişmiş özellikler** \> **Uç Nokta Saldırısı Bildirimleri'ne** gidin. Kabul edildikten sonra Uç Nokta Saldırısı Bildirimleri'nin avantajlarından yararlanırsınız.

kuruluşunuzun karşılaştığı ilgili algılamalar ve saldırganlar hakkında tehdit uzmanlarımıza danışmak üzere **Microsoft Tehdit Uzmanları - İsteğe Bağlı Uzmanlar'a** abone olmak için hesap ekibinize veya Microsoft temsilcinize başvurun.

Ayrıntılar için bkz[. Microsoft Tehdit Uzmanları özelliklerini yapılandırma](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin).

## <a name="endpoint-attack-notification"></a>Uç nokta saldırısı bildirimi

Endpoint Attack Notifications (daha önce Microsoft Tehdit Uzmanları - Hedefli Saldırı Bildirimi olarak adlandırılıyordu), insan saldırgan saldırılar, uygulamalı klavye saldırıları veya siber casusluk gibi gelişmiş saldırılar da dahil olmak üzere ağınıza yönelik en önemli tehditler için proaktif avcılık sağlar. Bu bildirimler yeni bir uyarı olarak gösterilir. Yönetilen tehdit avcılığı hizmeti şunları içerir:

- Tehdit izleme ve analiz, işletme için bekleme süresini ve riski azaltma
- Hem bilinen hem de bilinmeyen saldırıları keşfetmek ve önceliklerini belirlemeye yönelik avcı tarafından eğitilmiş yapay zeka
- En önemli riskleri belirleme, SOC'ların zamanı ve enerjiyi en üst düzeye çıkarmasını sağlama
- Hızlı SOC yanıtını etkinleştirmek için güvenliğin aşılması ve mümkün olduğunca çok bağlamın hızlı bir şekilde teslim edilmesi.

## <a name="microsoft-threat-experts---experts-on-demand"></a>Microsoft Tehdit Uzmanları - İsteğe Bağlı Uzmanlar
> [!NOTE]
> İsteğe Bağlı Uzmanlar bir güvenlik olayı yanıt hizmeti değildir. Kuruluşunuzu etkileyen karmaşık tehditlerin daha iyi anlaşılmasını sağlamak için tasarlanmıştır. Acil güvenlik olayı yanıt sorunlarını çözmek için kendi güvenlik olayı yanıt ekibinizle etkileşime geçin. Kendi güvenlik olayı yanıt ekibiniz yoksa ve Microsoft'un yardımını istiyorsanız [Premier Services Hub'da](/services-hub/) bir destek isteği oluşturun.

Müşteriler, yanıtlarını almak için doğrudan Microsoft 365 Defender portalından güvenlik uzmanlarımızla etkileşime geçebilir. Uzmanlar, uyarı sorgularından, risk altındaki cihazlardan, şüpheli ağ bağlantısının kök nedenlerinden devam eden gelişmiş kalıcı tehdit kampanyalarıyla ilgili daha fazla tehdit zekasına kadar kuruluşunuzu etkileyen karmaşık tehditleri daha iyi anlamak için gereken içgörüleri sağlar. Bu özellik ile şunları yapabilirsiniz:

- Olayın kök nedeni veya kapsamı da dahil olmak üzere uyarılar hakkında daha fazla açıklama alın
- Şüpheli cihaz davranışına ve gelişmiş bir saldırganla karşılaşılması durumunda sonraki adımlara açıklık kazandırma
- Tehdit aktörleri, kampanyalar veya yeni ortaya çıkan saldırgan teknikleri ile ilgili risk ve korumayı belirleme

> [!NOTE]
> Ağustos 2022 itibarıyla, **Bir tehdit uzmanına danışmak** için İsteğe Bağlı Uzmanlar seçeneği **Defender Uzmanlara Sor** olarak yeniden tanımlanmıştır.

**Defender Uzmanlarına Sor** seçeneği, araştırmanız bağlamında uzmanlarla etkileşim kurabilmeniz için portalda çeşitli yerlerde kullanılabilir:

- ***Cihaz sayfası eylemleri menüsü***

![Microsoft 365 Defender portalındaki Cihaz sayfası eylem menüsündeki Defender Uzmanlarına Sor menü seçeneğinin ekran görüntüsü.](../../media/mte/device-page-actions-menu.png)

- ***Uyarılar sayfası eylemleri menüsü***

![Microsoft 365 Defender portalındaki Uyarılar sayfası eylem menüsündeki Defender Uzmanlarına Sor menü seçeneğinin ekran görüntüsü.](../../media/mte/alerts-page-actions-menu.png)

- ***Dosya sayfası eylemleri menüsü***

![Microsoft 365 Defender portalındaki Olaylar sayfası eylem menüsündeki Defender Uzmanlarına Sor menü seçeneğinin ekran görüntüsü.](../../media/mte/incidents-page-actions-menu.png)

> [!NOTE]
> İsteğe Bağlı Uzmanlar servis taleplerinizin durumunu Microsoft Services Hub aracılığıyla izlemek isterseniz Müşteri Başarısı Hesap Yöneticinize ulaşın.

Microsoft Services Hub'a hızlı bir genel bakış için bu videoyu izleyin.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f]

## <a name="see-also"></a>Ayrıca bkz.

- [Microsoft Tehdit Uzmanları özelliklerini yapılandırma](configure-microsoft-threat-experts.md)
