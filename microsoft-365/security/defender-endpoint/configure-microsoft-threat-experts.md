---
title: Microsoft Tehdit Uzmanları özelliklerini yapılandırın ve yönetin
ms.reviewer: ''
description: Günlük güvenlik işlemlerinizde ve güvenlik yönetimi çalışmanızda yapılandırmak, yönetmek ve kullanmak için Microsoft Threats Uzmanlarına kaydolun.
keywords: Microsoft Tehdit Uzmanları, yönetilen tehdit avcılığı hizmeti, MTE, Microsoft yönetilen tehdit avcılığı hizmeti
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
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 89a554cc1f016425e74e0fb6ad6f3aca9f81b292
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67680383"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities"></a>Microsoft Tehdit Uzmanları özelliklerini yapılandırın ve yönetin

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="before-you-begin"></a>Başlamadan önce

> [!NOTE]
> Endpoint Attack Notifications yönetilen tehdit avcılığı hizmetine başvurmadan önce Microsoft Teknik Hizmet sağlayıcınız ve hesap ekibinizle uygunluk gereksinimlerini tartışın.

Yalnızca laboratuvar kurulumunda değil, kayıtlı cihazlarla ortamınızda Uç Nokta için Defender'ın dağıtıldığından emin olun.

Uç Nokta için Defender müşterisiyseniz, en kritik tehditleri hızla yanıtlayabileceğiniz özel içgörüler ve analizler almak için **Uç Nokta Saldırısı Bildirimleri'ne** başvurmanız gerekir. İlgili algılamalar ve saldırganlar konusunda tehdit uzmanlarımıza danışmak üzere **Microsoft Tehdit Uzmanları - İsteğe Bağlı Uzmanlar'a** abone olmak için hesap ekibinize veya Microsoft temsilcinize başvurun.

## <a name="apply-for-endpoint-attack-notifications-service"></a>Endpoint Attack Notifications hizmetine uygula

Zaten bir Uç Nokta için Defender müşterisiyseniz, Microsoft 365 Defender portalı üzerinden başvurabilirsiniz.

1. Gezinti bölmesinden **Ayarlar > Genel > Gelişmiş özellikler > Uç Nokta Saldırı Bildirimleri'ne** gidin.

2. **Uygula**'ya tıklayın.

   :::image type="content" source="images/mte-collaboratewithmte.png" alt-text="Microsoft Tehdit Uzmanları ayarları" lightbox="images/mte-collaboratewithmte.png":::

3. Microsoft'un uygulamanızda size geri dönebilmesi için adınızı ve e-posta adresinizi girin.

   :::image type="content" source="images/mte-apply.png" alt-text="Microsoft Tehdit Uzmanları uygulama sayfasındaki Ad alanı" lightbox="images/mte-apply.png":::

4. [Gizlilik bildirimini](https://privacy.microsoft.com/privacystatement) okuyun ve işiniz bittiğinde **Gönder'e** tıklayın. Uygulamanız onaylandıktan sonra bir karşılama e-postası alırsınız.

   :::image type="content" source="images/mte-applicationconfirmation.png" alt-text="Microsoft Tehdit Uzmanları uygulama onay iletisi" lightbox="images/mte-applicationconfirmation.png":::

Kabul edildiğinde bir karşılama e-postası alırsınız ve **Uygula** düğmesinin "açık" bir geçiş olarak değiştiğini görürsünüz. Kendinizi Endpoint Attack Notifications hizmetinden çıkarmak istiyorsanız, iki durumlu düğmeyi "kapalı" kaydırın ve sayfanın en altındaki **Tercihleri kaydet'e** tıklayın.

## <a name="where-youll-see-the-endpoint-attack-notifications-from-microsoft-threat-experts"></a>Microsoft Tehdit Uzmanları'dan Uç Nokta Saldırısı Bildirimlerini göreceğiniz yer

Microsoft Tehdit Uzmanları hedefli saldırı bildirimini aşağıdaki ortam üzerinden alabilirsiniz:

- Uç Nokta için Defender portalının **Olaylar** sayfası
- Uç Nokta için Defender **portalının Uyarılar** panosu
- OData uyarı [API'si](/windows/security/threat-protection/microsoft-defender-atp/get-alerts) ve [REST API](/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)
- Gelişmiş avcılıkta [DeviceAlertEvents](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) tablosu
- E-postanızı yapılandırmayı seçerseniz

Uç Nokta Saldırısı Bildirimlerini e-postayla almak için bir e-posta bildirim kuralı oluşturun.

### <a name="create-an-email-notification-rule"></a>E-posta bildirim kuralı oluşturma

Bildirim alıcıları için e-posta bildirimleri göndermek için kurallar oluşturabilirsiniz. Ayrıntılar için bkz. E-posta bildirimi oluşturmak, düzenlemek, silmek veya sorunlarını gidermek için uyarı bildirimlerini  [yapılandırma](configure-email-notifications.md) .

## <a name="view-the-endpoint-attack-notifications"></a>Uç Nokta Saldırısı Bildirimlerini Görüntüleme

Sisteminizi e-posta bildirimi alacak şekilde yapılandırdıktan sonra e-postanızdaki Microsoft Tehdit Uzmanları Uç Nokta Saldırısı Bildirimleri almaya başlayacaksınız.

1. **Tehdit uzmanlarıyla** etiketlenmiş panodaki ilgili uyarı bağlamını görmek için e-postadaki bağlantıya tıklayın.

2. Panodan, ayrıntıları görüntülemek için e-postadan edindiğiniz uyarı konusunun aynısını seçin.

### <a name="filter-to-view-just-the-endpoint-attack-notifications"></a>Yalnızca Uç Nokta Saldırısı Bildirimlerini görüntülemek için filtreleyin

Birçok uyarı arasında yalnızca Uç Nokta Saldırısı Bildirimlerini görmek istiyorsanız olaylarınızı ve uyarılarınızı filtreleyebilirsiniz. Bunu yapmak için:

1. Gezinti menüsünde **Olaylar & uyarılar** > **Olay**/**Uyarıları'na** gidin > Defender Uzmanları bildirimlerini](../../media/mte/defenderexperts/filter.png) görüntülemek için filtrele simgesini seçin![.
2. Aşağı kaydırarak Etiketler alanına gidin > **Defender Uzmanları** onay kutusunu seçin.
3. **Uygula'yı** seçin.

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a>Microsoft Tehdit Uzmanları Abone Olma - İsteğe Bağlı Uzmanlar

Bu, abonelik hizmeti olarak kullanılabilir. Zaten bir Uç Nokta için Defender müşterisiyseniz, Microsoft Tehdit Uzmanları - İsteğe Bağlı Uzmanlar'a abone olması için Microsoft temsilcinizle iletişime geçebilirsiniz.
> [!NOTE]
> İsteğe Bağlı Uzmanlar bir güvenlik olayı yanıt hizmeti değildir. Kuruluşunuzu etkileyen karmaşık tehditlerin daha iyi anlaşılmasını sağlamak için tasarlanmıştır. Acil güvenlik olayı yanıt sorunlarını çözmek için kendi güvenlik olayı yanıt ekibinizle etkileşime geçin. Kendi güvenlik olayı yanıt ekibiniz yoksa ve Microsoft'un yardımını istiyorsanız [Premier Services Hub'da](/services-hub/) bir destek isteği oluşturun.

## <a name="ask-defender-experts-about-suspicious-cybersecurity-activities-in-your-organization"></a>Kuruluşunuzdaki şüpheli siber güvenlik etkinlikleri hakkında Defender Uzmanlarına sorun

Yanıt için doğrudan Microsoft 365 Defender portalından etkileşime geçen Microsoft Tehdit Uzmanları ile iş ortaklığı yapabilirsiniz. Uzmanlar karmaşık tehditleri, aldığınız hedefli saldırı bildirimlerini daha iyi anlamak için içgörüler sağlar veya uyarılar, güvenliği aşılmış olabilecek bir cihaz veya portal panonuzda gördüğünüz tehdit bilgileri bağlamı hakkında daha fazla bilgiye ihtiyacınız varsa.

> [!NOTE]
>
> - Kuruluşunuzun özelleştirilmiş tehdit bilgileri verileriyle ilgili uyarı sorguları şu anda desteklenmiyor. Ayrıntılar için güvenlik operasyonlarınıza veya olay yanıt ekibinize başvurun.
> - **Defender Uzmanlarına Sor** sorgusunu gönderebilmek için Microsoft 365 Defender portalında **Güvenlik ayarlarını yönet** iznine sahip olmanız gerekir.

1. Araştırmak istediğiniz ilgili bilgileri (örneğin **Olay** sayfası) içeren portal sayfasına gidin. Araştırma isteği göndermeden önce ilgili uyarı veya cihazın sayfasının görüntülendiğinden emin olun.

2. Sağ üst menüden **?** simgesini seçin. Ardından **Defender Uzmanlarına Sorun'a** tıklayın

![Microsoft Ask Defender Uzmanları deneme aboneliği sayfası](../../media/mte/flyout-screen-trial-subscription.png)

Açılır ekran açılır. Aşağıdaki ekranda bir deneme aboneliğinde olduğunuzda gösterilir. Aşağıdaki ekranda tam bir Microsoft Tehdit Uzmanları - İsteğe Bağlı Uzmanlar aboneliğiniz gösterilir.

**Sorgulama konusu** alanı, araştırma isteğiniz için ilgili sayfanın bağlantısıyla önceden doldurulur. Örneğin, isteği yaparken bulunduğun olay, uyarı veya cihaz ayrıntıları sayfasının bağlantısı.

3. Sonraki alanda, Microsoft Tehdit Uzmanları araştırmayı başlatmak için yeterli bağlamı sağlamak için yeterli bilgi sağlayın.

4. Microsoft Tehdit Uzmanları karşılık olarak kullanmak istediğiniz e-posta adresini girin.

> [!NOTE]
> İsteğe Bağlı Uzmanlar servis taleplerinizin durumunu Microsoft Services Hub aracılığıyla izlemek isterseniz Müşteri Başarısı Hesap Yöneticinize ulaşın.

Microsoft Services Hub'a hızlı bir genel bakış için bu videoyu izleyin.

> [!VIDEO <https://www.microsoft.com/videoplayer/embed/RE4pk9f>]

## <a name="sample-investigation-topics-that-you-can-consult-with-microsoft-threat-experts---experts-on-demand"></a>Microsoft Tehdit Uzmanları ile danışabileceğiniz örnek araştırma konuları - İsteğe Bağlı Uzmanlar

### <a name="alert-information"></a>Uyarı bilgileri

- Arazi dışında yaşayan bir ikili dosya için yeni bir uyarı türü görüyoruz: [AlertID]. Bu uyarı hakkında bize daha fazla bilgi verebilir misiniz ve nasıl daha fazla araştırma yapabiliriz?
- Kötü amaçlı PowerShell betiklerini yürütmeye çalışan ancak farklı uyarılar oluşturan iki benzer saldırı gözlemledik. Biri "Şüpheli PowerShell komut satırı" diğeri ise "O365 tarafından sağlanan göstergeye göre kötü amaçlı bir dosya algılandı". Ne fark var?
- Bugün yüksek profilli bir kullanıcının cihazından olağan dışı sayıda başarısız oturum açma için tek bir uyarı alıyorum. Bu oturum açma girişimleriyle ilgili başka kanıt bulamıyorum. Uç Nokta için Defender bu girişimleri nasıl görebilir? Ne tür oturum açma işlemleri izleniyor?
- Bu uyarı hakkında daha fazla bağlam veya içgörü verebilir misiniz: "Sistem yardımcı programı tarafından şüpheli davranış gözlemlendi".

### <a name="possible-device-compromise"></a>Olası cihaz güvenliğinin aşılmasına neden olabilir

- Neden "Bilinmeyen işlem gözlemlendi?" sorusunu yanıtlamamıza yardımcı olabilir misiniz? Bu ileti veya uyarı birçok cihazda sık görülür. Bu iletinin veya uyarının kötü amaçlı etkinliklerle ilgili olup olmadığını netleştirmek için her türlü girişi takdir ediyoruz.
- [date] tarihinde [date] tarihinde aynı sistemdeki önceki [kötü amaçlı yazılım adı] kötü amaçlı yazılım algılamasıyla benzer davranışlarla [month] içinde aşağıdaki sistemde olası bir güvenliğin aşılmış olduğunu doğrulamaya yardımcı olabilir misiniz?

### <a name="threat-intelligence-details"></a>Tehdit bilgileri ayrıntıları

- Kullanıcıya kötü amaçlı bir Word belgesi teslim eden bir kimlik avı e-postası algılandı. Kötü amaçlı Word belgesi, [kötü amaçlı yazılım adı] kötü amaçlı yazılım için birden çok Endpoint Attack Notifications uyarısını tetikleyen bir dizi şüpheli olaya neden oldu. Bu kötü amaçlı yazılım hakkında herhangi bir bilginiz var mı? Evet ise, bana bir bağlantı gönderebilir misiniz?
- Kısa süre önce sektörümü hedefleyen bir tehditle ilgili bir [sosyal medya başvurusu, örneğin Twitter veya blog] gönderisi gördüm. Uç Nokta için Defender'ın bu tehdit aktörü karşısında sağladığı korumayı anlamama yardımcı olabilir misiniz?

### <a name="defender-experts-alert-communications"></a>Defender Uzmanlarının uyarı iletişimleri

- Olay yanıtı ekibiniz, aldığımız Uç Nokta Saldırısı Bildirimlerini ele almamıza yardımcı olabilir mi?
- Bu Uç Nokta Saldırısı Bildirimlerini Microsoft Tehdit Uzmanları aldım. Kendi olay müdahale ekibimiz yok. Şimdi ne yapabiliriz ve olayı nasıl kapsayabiliriz?
- Microsoft Tehdit Uzmanları'dan Uç Nokta Saldırısı Bildirimleri aldım. Olay yanıtı ekibimize geçirebileceğimiz hangi verileri bize sağlayabilirsiniz?

  > [!NOTE]
  > Microsoft Tehdit Uzmanları, olay yanıtı hizmeti değil yönetilen bir siber güvenlik avcılığı hizmetidir. Ancak, olay yanıtı gerektiren sorunları gidermek için kendi olay yanıt ekibinizle etkileşim kurabilirsiniz. Kendi olay yanıt ekibiniz yoksa ve Microsoft'un yardımını istiyorsanız CSS Siber Güvenlik Olayı Yanıt Ekibi (CIRT) ile etkileşime geçebilirsiniz. Sorgunuzu ele almak için bir bilet açabilirler.

## <a name="scenario"></a>Senaryo

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a>Yönetilen tehdit avcılığı sorgunuz hakkında bir ilerleme raporu alma

Microsoft Tehdit Uzmanları yanıtı sorgunuza göre değişir. Araştırma durumunu aşağıdaki kategorilerden iletmek için iki gün içinde **Defender Uzmanlarına Sorun** sorgunuz hakkında size bir ilerleme raporu e-posta ile gönderilir:

- Araştırmaya devam etmek için daha fazla bilgi gerekiyor
- Teknik bağlamı belirlemek için bir dosya veya birkaç dosya örneği gerekir
- Araştırma daha fazla zaman gerektirir
- İlk bilgiler soruşturmayı sonuçlandırmak için yeterliydi

Araştırmayı devam ettirmek için hızlı bir şekilde yanıt vermek çok önemlidir.

#### <a name="to-proactively-hunt-threats-across-endpoints-office-365-cloud-applications-and-identity-refer-to"></a>Uç noktalar, Office 365, bulut uygulamaları ve kimlik genelinde tehditleri proaktif olarak avlamak için bkz.

- [Microsoft 365'te Microsoft Defender Uzmanlarına Genel Bakış](../defender/defender-experts-for-hunting.md)
