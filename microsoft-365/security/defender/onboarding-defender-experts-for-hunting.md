---
title: Tehdit Avcılığı için Microsoft Defender Uzmanlarına abone olma
ms.reviewer: ''
description: Microsoft 365 Defender ve Avcılık için Defender Uzmanları'na yeniyseniz, abone olma yönteminiz budur
keywords: yönetilen tehdit avcılığı hizmeti, yönetilen tehdit avcılığı, yönetilen algılama ve yanıt (MDR) hizmeti, MTE, Microsoft Tehdit Uzmanları, MTE-TAN, hedefli saldırı bildirimi, defender uzmanları bildirimleri, uç nokta saldırı bildirimleri, tehdit avcılığı ve analiz için Microsoft Defender Uzmanları.
search.product: Windows 10
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: vpattnaik
author: vpattnai
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.openlocfilehash: 298bba9601d87887b839b7b0c5f0a33c7616caa4
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67497435"
---
# <a name="start-using-microsoft-defender-experts-for-hunting"></a>Avlanmak için Microsoft Defender Uzmanlarını kullanmaya başlama

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="onboarding"></a>Ekleme

Microsoft 365 Defender ve Avcılık için Defender Uzmanları'na yeniyseniz:  

1. Hoş geldiniz e-postanızı aldıktan sonra **Microsoft 365 Defender oturum aç'ı** seçin.
2. Zaten bir Microsoft hesabınız varsa oturum açın. Yoksa bir tane oluşturun.
3. Microsoft 365 Defender hızlı tur güvenlik paketini, özelliklerin nerede olduğunu ve ne kadar önemli olduğunu öğreneceksiniz. **Hızlı bir tura katılın'ı** seçin.  
4. Microsoft Defender Uzmanlar hizmetinin ne olduğu ve sağladığı özellikler hakkında kısa açıklamaları okuyun. **İleri**'yi seçin. Hoş geldiniz sayfasını görürsünüz:

![Avcılık için Defender Uzmanları hizmeti için bir kart içeren Microsoft 365 Defender karşılama sayfasının ekran görüntüsü.](../../media/mte/defenderexperts/start-using-defender-experts-for-hunting.png)

## <a name="receive-defender-experts-notifications"></a>Defender Uzman Bildirimlerini Alma

Defender Uzmanlar Bildirimleri hizmeti şunları içerir:
- Tehdit izleme ve analiz, bekleme süresini ve işletmeniz için riski azaltma
- Hem bilinen saldırıları hem de yeni ortaya çıkan tehditleri keşfetmek ve hedeflemek için Avcı tarafından eğitilmiş yapay zeka 
- En uygun risklerin belirlenmesi, SOC'lerin etkinliklerini en üst düzeye çıkarmalarına yardımcı olma 
- Hızlı bir SOC yanıtı sağlamak için kapsam belirleme konusunda yardım ve mümkün olduğunca çok bağlam hızlı bir şekilde teslim edilebilir 

Örnek Defender Uzmanları Bildirimi'ni görmek için aşağıdaki ekran görüntüsüne bakın:

![Microsoft 365 Defender'da Defender Uzmanlar Bildirimi'nin ekran görüntüsü. Defender Uzman Bildirimi, gözlemlenen tehdidi veya etkinliği, yönetici özetini ve öneri listesini açıklayan bir başlık içerir.](../../media/mte/defenderexperts/receive-defender-experts-notification.png)

### <a name="where-youll-find-defender-experts-notifications"></a>Defender Uzmanları Bildirimlerini nerede bulabilirsiniz?

Defender Uzmanlarından Aşağıdaki ortamlar aracılığıyla Defender Uzmanları Bildirimleri alabilirsiniz: 

- Microsoft 365 Defender portalın [Olaylar](https://security.microsoft.com/incidents?tid=f839b112-d9d7-4d27-9bf6-94542403f21c) sayfası
- Microsoft 365 Defender portalın [Uyarılar](https://security.microsoft.com/alerts?tid=f839b112-d9d7-4d27-9bf6-94542403f21c) sayfası
- OData uyarı [API'si](../../security/defender-endpoint/get-alerts.md) ve [REST API](../defender-endpoint/configure-siem.md)
- Gelişmiş avcılıkta [DeviceAlertEvents](../../security/defender-endpoint/advanced-hunting-devicealertevents-table.md) tablosu

### <a name="filter-to-view-just-the-defender-experts-notifications"></a>Yalnızca Defender Uzmanları Bildirimlerini görüntülemek için filtreleyin

Birçok uyarı arasında yalnızca Defender Uzman Bildirimleri'ni görmek istiyorsanız olaylarınızı ve uyarılarınızı filtreleyebilirsiniz. Bunu yapmak için:

1. Gezinti menüsünde **Olaylar & uyarılar** > **Olaylar'a** gidin > Filtre simgesi](../../media/mte/defenderexperts/filter.png) simgesini seçin![.
2. Aşağı kaydırarak **Etiketler** alanına gidin > **Defender Uzmanları** onay kutusunu seçin.
3. **Uygula'yı** seçin.

### <a name="collaborate-with-experts-on-demand"></a>İsteğe Bağlı Uzmanlarla İşbirliği Yapma

> [!NOTE]
> İsteğe Bağlı Uzmanlar, aylık ayırmalarla Avcılık için Defender Uzmanlar aboneliğinize dahildir. Ancak bu bir güvenlik olayı yanıt hizmeti değildir. Kuruluşunuzu etkileyen karmaşık tehditlerin daha iyi anlaşılmasını sağlamak için tasarlanmıştır. Acil güvenlik olayı yanıt sorunlarını çözmek için kendi güvenlik olayı yanıt ekibinizle etkileşime geçin. Kendi güvenlik olayı yanıt ekibiniz yoksa ve Microsoft'un yardımını istiyorsanız [Premier Services Hub'da](/services-hub/) bir destek isteği oluşturun.

Tehdit avcılığıyla ilgili tüm sorularınıza hızlı ve doğru yanıtlar almak için Doğrudan Microsoft 365 güvenlik portalının içinden **Defender Uzmanlarına Sorun'u** seçin. Uzmanlar, kuruluşunuzun karşılaşabileceği karmaşık tehditleri daha iyi anlamak için içgörü sağlayabilir. İsteğe Bağlı Uzmanlar aşağıdakilere yardımcı olabilir: 

- Uyarılar ve olaylar hakkında kök nedenler ve kapsam da dahil olmak üzere ek bilgi toplama
- Şüpheli cihazlara, uyarılara veya olaylara açıklık getirin ve gelişmiş bir saldırganla karşılaşılması durumunda sonraki adımları uygulayın
- Tehdit aktörleri, kampanyalar veya yeni ortaya çıkan saldırgan teknikleri ile ilgili riskleri ve kullanılabilir korumaları belirleme

**Defender Uzmanlarına Sor** seçeneği portal genelinde çeşitli yerlerde kullanılabilir:

- ***Cihaz sayfası eylemleri menüsü***

![Microsoft 365 Defender portalındaki Cihaz sayfası eylem menüsündeki Defender Uzmanlarına Sor menü seçeneğinin ekran görüntüsü.](../../media/mte/defenderexperts/device-page-actions-menu.png)

- ***Cihaz envanteri sayfası açılır menüsü***

![Microsoft 365 Defender portalındaki Cihaz envanteri sayfası açılır menüsündeki Defender Uzmanlarına Sor menü seçeneğinin ekran görüntüsü.](../../media/mte/defenderexperts/device-inventory-flyout-menu.png)

- ***Uyarılar sayfası açılır menüsü***

![Microsoft 365 Defender portalındaki Uyarılar sayfası açılır menüsündeki Defender Uzmanlarına Sor menü seçeneğinin ekran görüntüsü.](../../media/mte/defenderexperts/alerts-flyout-menu.png)

- ***Olaylar sayfası eylemleri menüsü***

![Microsoft 365 Defender portalındaki Olaylar sayfası eylemleri menüsündeki Defender Uzmanlarına Sor menü seçeneğinin ekran görüntüsü.](../../media/mte/defenderexperts/incidents-page-actions-menu.png)

> [!NOTE]
> İsteğe Bağlı Uzmanlar servis taleplerinizin durumunu Microsoft Services Hub aracılığıyla izlemek isterseniz Müşteri Başarısı Hesap Yöneticinize ulaşın. Microsoft Services Hub'a hızlı bir genel bakış için bu [videoyu](https://www.microsoft.com/videoplayer/embed/RE4pk9f) izleyin.

## <a name="sample-questions-you-can-ask-from-defender-experts"></a>Defender Uzmanlarından sorabileceğiniz örnek sorular

### <a name="alert-information"></a>Uyarı bilgileri

- Arazi dışında yaşayan ikili dosya için yeni bir uyarı türü gördük. Uyarı kimliğini sağlayabiliriz. Bu uyarı ve herhangi bir olayla ilgili olup olmadığını ve daha fazla nasıl araştırabiliriz?
- Her ikisi de kötü amaçlı PowerShell betiklerini yürütmeye çalışan ancak farklı uyarılar oluşturan iki benzer saldırı gözlemledik. Biri "Şüpheli PowerShell komut satırı" diğeri ise "Office 365 tarafından sağlanan göstergeye göre kötü amaçlı bir dosya algılandı." Ne fark var?
- Bugün, yüksek profilli bir kullanıcının cihazından olağan dışı sayıda başarısız oturum açma işlemiyle ilgili garip bir uyarı aldık. Bu girişimler için başka kanıt bulamıyoruz. Microsoft 365 Defender bu girişimleri nasıl görebilir? Ne tür oturum açma işlemleri izleniyor?
- Uyarı ve "Bir sistem yardımcı programı tarafından şüpheli davranış gözlemlendi" ile ilgili olaylar hakkında daha fazla bağlam veya içgörü verebilir misiniz?
- "İletme/yeniden yönlendirme kuralı oluşturma" başlıklı bir uyarı gözlemledim. Etkinliğin zararsız olduğuna inanıyorum. Neden uyarı aldığımdan bahsedebilir misiniz?

### <a name="possible-device-compromise"></a>Olası cihaz güvenliğinin aşılmasına neden olabilir

- Kuruluşumuzdaki birçok cihazda neden "Bilinmeyen işlem gözlemlendi" iletisini veya uyarısını gördüğümüzu açıklamaya yardımcı olabilir misiniz? Bu iletinin veya uyarının kötü amaçlı etkinlikler veya olaylarla ilgili olup olmadığını netleştirmek için her türlü girişi takdir ediyoruz.
- Geçen haftadan kalma aşağıdaki sistemde olası bir güvenliğin aşılmış olduğunu doğrulamaya yardımcı olabilir misiniz? Altı ay önce aynı sistemde önceki kötü amaçlı yazılım algılama işlemine benzer şekilde davranıyor.

### <a name="threat-intelligence-details"></a>Tehdit bilgileri ayrıntıları

- Kullanıcıya kötü amaçlı bir Word belgesi teslim eden bir kimlik avı e-postası algılandı. Belge, belirli bir kötü amaçlı yazılım ailesi için birden çok uyarı tetikleyen bir dizi şüpheli olaya neden oldu. Bu kötü amaçlı yazılım hakkında herhangi bir bilginiz var mı? Evet ise, bize bir bağlantı gönderebilir misiniz?
- Kısa süre önce sektörümüzü hedefleyen bir tehditle ilgili bir blog gönderisi gördük. Microsoft 365 Defender bu tehdit aktörü karşısında hangi korumayı sağladığını anlamamıza yardımcı olabilir misiniz?
- Kısa süre önce kuruluşumuza karşı yürütülen bir kimlik avı kampanyası gözlemledik. Bunun özel olarak şirketimize mi yoksa dikey mi hedeflendiğini söyleyebilir misiniz?

### <a name="microsoft-defender-experts-for-hunting-alert-communications"></a>Tehdit Avcılığı için Microsoft Defender Uzmanları uyarı iletişimleri

- Olay yanıtı ekibiniz, aldığımız Defender Uzmanlar Bildirimi'ni ele almamıza yardımcı olabilir mi?
- Bu Defender Uzmanlar Bildirimini Avcılık için Microsoft Defender Uzmanlarından aldık. Kendi olay müdahale ekibimiz yok. Şimdi ne yapabiliriz ve olayı nasıl kapsayabiliriz?
- Avcılık için Microsoft Defender Uzmanlarından Bir Defender Uzmanları Bildirimi aldık. Olay yanıtı ekibimize geçirebileceğimiz hangi verileri bize sağlayabilirsiniz?

### <a name="next-step"></a>Sonraki adım

- [Microsoft 365 Defender'da Avcılık için Defender Uzmanları raporunu anlama](defender-experts-report.md)
