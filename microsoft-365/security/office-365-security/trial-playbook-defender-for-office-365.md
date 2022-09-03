---
title: Office 365 için Microsoft Defender deneme playbook'u
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.collection: m365-security-compliance
ms.localizationpriority: high
ROBOTS: NOINDEX, NOFOLLOW
ms.service: microsoft-365-security
search.appverid:
- MOE150
- MET150
description: Office 365 için Microsoft Defender çözümleri deneme playbook'u.
ms.subservice: mdo
ms.custom: trial-playbook
ms.openlocfilehash: 0fcd44b3bf82e4eca1322bf1c8ceaff1613a04cd
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67598273"
---
# <a name="trial-playbook-microsoft-defender-for-office-365"></a>Deneme playbook'u: Office 365 için Microsoft Defender

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Şunlar için geçerlidir:**
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Office 365 için Microsoft Defender deneme playbook'una hoş geldiniz! Bu playbook, Office 365 için Defender ile kuruluşunuzu nasıl koruyacağınızı öğreterek 90 günlük ücretsiz denemenizden en iyi şekilde yararlanabilirsiniz.

Artık iki yoldan biriyle Office 365 için Defender deneme seçeneğiniz vardır:

- **Engelleme modu (önerilen)**: Posta değiştirici (MX) kaydınız Microsoft 365'i işaret ederse, engelleme modundaki Office 365 için Defender özelliklerini değerlendirebilirsiniz. Office 365 için Defender, Standart [önceden ayarlanmış güvenlik ilkesi](preset-security-policies.md) ayarlarını otomatik olarak uygular.

  Değerlendirme süresi boyunca, istediğiniz zaman daha yüksek bir koruma şablonunu (Katı önceden belirlenmiş güvenlik ilkesi ayarlarımız) tercih edebilir veya ihtiyaçlarınıza uygun kendi bireysel koruma ilkelerinizi oluşturabilirsiniz.

- **Denetim modu**: MX kaydınız Microsoft 365 dışında bir yere (örneğin, üçüncü taraf e-posta ağ geçidi) işaret ederse, Office 365 için Defender denetim modunda değerlendirebilirsiniz. Office 365 için Defender, zararlı olduğunu belirlediğimiz iletilerde engelleme eylemi gerçekleştirmez.

  Bu tehditler günlüğe kaydedilir ve Algılanan tehdit türleri, tehditlerin hedeflediği kişiler ve çok daha fazlası hakkında ayrıntılı bilgi sağlayan [Tehdit koruma durumu raporu](view-email-security-reports.md#threat-protection-status-report) aracılığıyla gözden geçirilebilir. Bu ek "yakalamalar", standart Exchange Online Protection (EOP) özelliklerine veya diğer üçüncü taraf e-posta ağ geçitlerinin özelliklerine göre Office 365 için Defender ek koruma özelliklerini gösterir. Memnun olduğunuzda ve Office 365 için Defender kullanmaya hazır olduğunuzda [Office 365 için Defender geçirebilirsiniz](migrate-to-defender-for-office-365.md).

:::image type="content" source="../../media/mdo-trial-playbook-what-is-mdo.png" alt-text="Office 365 için Microsoft Defender tüm bileşenlerinin grafik gösterimi." lightbox="../../media/mdo-trial-playbook-what-is-mdo.png":::

Bu kılavuzdaki önerileri kullanarak Office 365 için Defender koruma ilkeleri tanımlamanıza, kuruluşunuza yönelik tehditleri analiz etmeye ve saldırılara yanıt vermenize nasıl yardımcı olabileceğini öğreneceksiniz.

Başlayalım!

## <a name="blocking-mode"></a>Engelleme modu

### <a name="step-1-getting-started-in-blocking-mode"></a>1. Adım: Engelleme modunda çalışmaya başlama

#### <a name="start-your-microsoft-defender-for-office-365-trial"></a>Office 365 için Microsoft Defender denemenizi başlatın

Deneme sürümünü başlattıktan ve [kurulum işlemini](try-microsoft-defender-for-office-365.md#set-up-an-evaluation-in-blocking-mode) tamamladıktan sonra değişikliklerin geçerli olması 2 saate kadar sürebilir.

Ortamınızda [önceden ayarlanmış güvenlik ilkelerini](preset-security-policies.md) otomatik olarak yapılandırdık. Bu ilkeler, çoğu kullanıcı için uygun bir temel koruma profilini temsil eder. Standart koruma şunları içerir:

- Güvenli Bağlantılar, Güvenli Ekler ve kimlik avı önleme ilkeleri, deneme kurulum işlemi sırasında seçmiş olabileceğiniz tüm kiracı veya kullanıcı alt kümesi kapsamındadır.
- SharePoint, OneDrive ve Microsoft Teams için Güvenli Ekler koruması.
- Desteklenen Office 365 uygulamaları için Güvenli Bağlantılar koruması.

Daha fazla bilgi edinmek için bu videoyu izleyin: [Office 365 için Microsoft Defender - YouTube'da Güvenli Bağlantılar ile kötü amaçlı bağlantılara karşı koruma](https://www.youtube.com/watch?v=vhIJ1Veq36Y&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=9).

#### <a name="enable-users-to-report-suspicious-content-in-blocking-mode"></a>Kullanıcıların engelleme modunda şüpheli içeriği bildirmesini sağlama

Office 365 için Defender, kullanıcıların güvenlik ekiplerine ileti bildirmesine olanak tanır ve yöneticilerin analiz için Microsoft'a ileti göndermesine olanak tanır.

- [Rapor İletisi eklentisini veya Rapor Kimlik Avı eklentisini dağıtın](enable-the-report-message-add-in.md).
- [Hatalı pozitifleri ve hatalı negatifleri raporlamak](report-false-positives-and-false-negatives.md) için bir iş akışı oluşturun.
- [Gönderimler portalını](admin-submission.md) kullanın.

Daha fazla bilgi edinmek için bu videoyu izleyin: [Analiz için ileti göndermek için Gönderimler portalını kullanmayı öğrenin - YouTube](https://www.youtube.com/watch?v=ta5S09Yz6Ks&ab_channel=MicrosoftSecurit).

#### <a name="review-reports-to-understand-the-threat-landscape-in-blocking-mode"></a>Engelleme modundaki tehdit ortamını anlamak için raporları gözden geçirin

Ortamınız hakkında daha fazla bilgi edinmek için Office 365 için Defender'deki raporlama özelliklerini kullanın.

- [Tehdit koruması durum raporuyla](view-email-security-reports.md#threat-protection-status-report) e-posta ve işbirliği araçlarına alınan tehditleri anlayın.
- [Posta akışı durum raporuyla](view-email-security-reports.md#mailflow-status-report) tehditlerin nerede engellendiğini görün.
- Kullanıcılar tarafından görüntülenen veya sistem tarafından engellenen [bağlantıları gözden geçirin](view-reports-for-mdo.md#url-protection-report).

:::image type="content" source="../../media/mdo-trial-playbook-reporting.png" alt-text="Microsoft 365 Defender portalında Email & işbirliği raporları." lightbox="../../media/mdo-trial-playbook-reporting.png":::

### <a name="step-2-intermediate-steps-in-blocking-mode"></a>2. Adım: Engelleme modunda ara adımlar

#### <a name="prioritize-focus-on-your-most-targeted-users"></a>Odağı en çok hedeflenen kullanıcılarınıza önceliklendirme

Office 365 için Defender'da Öncelik Hesabı Koruması ile en çok hedeflenen ve en görünür kullanıcılarınızı koruyun. Bu, bu kullanıcıların güvende olduğundan emin olmak için iş akışınızı önceliklendirmenize yardımcı olur.

- En çok hedeflenen veya en görünür kullanıcılarınızı belirleyin.
- [Bu kullanıcıları](../../admin/setup/priority-accounts.md#add-priority-accounts-from-the-setup-page) öncelik hesapları olarak etiketleyin.
- Portal genelinde öncelik hesabına yönelik tehditleri izleyin.

Daha fazla bilgi edinmek için bu videoyu izleyin: [Office 365 için Microsoft Defender 'de öncelik hesaplarını koruma - YouTube](https://www.youtube.com/watch?v=tqnj0TlzQcI&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=11).

:::image type="content" source="../../media/mdo-trial-playbook-alerts.png" alt-text="Microsoft 365 Defender portalındaki Uyarılar." lightbox="../../media/mdo-trial-playbook-alerts.png":::

### <a name="avoid-costly-breaches-by-preventing-user-compromise"></a>Kullanıcı güvenliğinin aşılmasını önleyerek yüksek maliyetli ihlallerden kaçının

Olası risklere karşı uyarı alın ve saldırganların ortamınıza daha derin erişim elde etmesini önlemek için bu tehditlerin etkisini otomatik olarak sınırlayın.

- [Güvenliği aşılmış kullanıcı uyarılarını](address-compromised-users-quickly.md#compromised-user-alerts) gözden geçirin.
- Güvenliği aşılmış kullanıcıları [araştırın ve yanıt verin](address-compromised-users-quickly.md).

:::image type="content" source="../../media/mdo-trial-playbook-investigation.png" alt-text="Güvenliği aşılmış kullanıcıları araştırma." lightbox="../../media/mdo-trial-playbook-investigation.png":::

Daha fazla bilgi edinmek için bu videoyu izleyin: [Office 365 için Microsoft Defender - YouTube'da güvenliği aşmayı algılama ve yanıtlama](https://www.youtube.com/watch?v=Pc7y3a-wdR0&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=5).

#### <a name="use-threat-explorer-to-investigate-malicious-email"></a>Kötü amaçlı e-postayı araştırmak için Tehdit Gezgini'ni kullanma

Office 365 için Defender, kuruluşunuzdaki kişileri riske atacak etkinlikleri araştırmanıza ve kuruluşunuzu korumak için eylem gerçekleştirmenize olanak tanır. Bunu [Tehdit Gezgini'ne](threat-explorer.md) kullanarak yapabilirsiniz.

- [Teslim edilen şüpheli e-postayı bulma](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered): İletileri bulun ve silin, kötü amaçlı e-posta gönderenin IP adresini tanımlayın veya daha fazla araştırma için bir olay başlatın.
- [Teslim eylemini ve konumunu denetleyin](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location): Bu denetim, sorunlu e-posta iletilerinin konumunu öğrenmenizi sağlar.
- [E-postanızın zaman çizelgesini görüntüleyin](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email): Yalnızca güvenlik operasyonları ekibiniz için avlanma.

#### <a name="see-campaigns-targeting-your-organization"></a>Kuruluşunuzu hedefleyen kampanyaları görme

Kuruluşunuzu hedef alan saldırı kampanyalarının ve bunların kullanıcılarınız üzerindeki etkisinin bir görünümünü sunan Office 365 için Defender'de Kampanya Görünümleri ile daha büyük resme bakın.

- Kullanıcılarınızı hedefleyen [kampanyaları belirleyin](campaigns.md#what-is-a-campaign).
- [Saldırının kapsamını görselleştirin](campaigns.md#campaign-views-in-the-microsoft-365-defender-portal) .
- Bu iletilerle [kullanıcı etkileşimlerini izleyin](campaigns.md#campaign-details).

  :::image type="content" source="../../media/mdo-trial-playbook-campaign-details.png" alt-text="Microsoft 365 Defender portalındaki Kampanya ayrıntıları." lightbox="../../media/mdo-trial-playbook-campaign-details.png":::

Daha fazla bilgi edinmek için bu videoyu izleyin: [Office 365 için Microsoft Defender Kampanya Görünümleri - YouTube](https://www.youtube.com/watch?v=DvqzzYKu7cQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=14).

#### <a name="use-automation-to-remediate-risks"></a>Riskleri düzeltmek için otomasyonu kullanma

Tehditleri gözden geçirmek, önceliklendirmek ve yanıtlamak için Otomatik araştırma ve yanıt (AIR) kullanarak verimli bir şekilde yanıt verin.

- Araştırma playbook'ları hakkında [daha fazla bilgi edinin](automated-investigation-response-office.md).
- [Araştırmanın ayrıntılarını ve sonuçlarını görüntüleyin](email-analysis-investigations.md) .
- [Düzeltme eylemlerini onaylayarak](air-remediation-actions.md) tehditleri ortadan kaldırın.

:::image type="content" source="../../media/mdo-trial-playbook-investigation-results.png" alt-text="Araştırma sonuçları." lightbox="../../media/mdo-trial-playbook-investigation-results.png":::

### <a name="step-3-advanced-content-in-blocking-mode"></a>3. Adım: Engelleme modunda gelişmiş içerik

#### <a name="dive-deep-into-data-with-query-based-hunting"></a>Sorgu tabanlı avcılık ile verileri derinlemesine inceleme

Özel algılama kuralları yazmak, ortamınızdaki olayları proaktif olarak incelemek ve tehdit göstergelerini bulmak için Gelişmiş tehdit avcılığı kullanın. Ortamınızdaki ham verileri keşfedin.

- [Özel algılama kuralları oluşturun](../defender/custom-detections-overview.md).
- Başkaları tarafından oluşturulan [paylaşılan sorgulara erişin](../defender/advanced-hunting-shared-queries.md).

Daha fazla bilgi edinmek için bu videoyu izleyin: [Microsoft 365 Defender ile tehdit avcılığı - YouTube](https://www.youtube.com/watch?v=l3OmH4U6XAs&list=PL3ZTgFEc7Lyt1O81TZol31YXve4e6lyQu&index=4).

#### <a name="train-users-to-spot-threats-by-simulating-attacks"></a>Saldırıların benzetimlerini yaparak kullanıcıları tehditleri tespit etmeye eğitin

Tehditleri tanımlamak ve şüpheli iletileri Office 365 için Defender Saldırı simülasyonu eğitimi bildirmek için kullanıcılarınızı doğru bilgiyle donatın.

- Savunmasız kullanıcıları tanımlamak için [gerçekçi tehditlerin benzetimini](attack-simulation-training.md) yapmak.
- Simülasyon sonuçlarına göre kullanıcılara [eğitim atayın](attack-simulation-training.md#assign-training).
- Simülasyonlar ve eğitim tamamlama aşamasında kuruluşunuzun [ilerleme durumunu izleyin](attack-simulation-training-insights.md).

  :::image type="content" source="../../media/mdo-trial-playbook-attack-simulation-training-results.png" alt-text="Microsoft 365 Defender portalındaki saldırı simülasyonu eğitim içgörüleri." lightbox="../../media/mdo-trial-playbook-attack-simulation-training-results.png":::

## <a name="auditing-mode"></a>Denetim modu

### <a name="step-1-get-started-in-auditing-mode"></a>1. Adım: Denetim modunda çalışmaya başlama

#### <a name="start-your-defender-for-office-365-evaluation"></a>Office 365 için Defender değerlendirmenizi başlatın

[Kurulum işlemini](try-microsoft-defender-for-office-365.md#set-up-an-evaluation-in-audit-mode) tamamladıktan sonra değişikliklerin etkili olması 2 saat kadar sürebilir. Ortamınızda Önceden Belirlenmiş Değerlendirme ilkelerini otomatik olarak yapılandırdık.

Değerlendirme ilkeleri, Office 365 için Defender tarafından algılanan e-postalarda hiçbir işlem yapılmamasını sağlar.

#### <a name="enable-users-to-report-suspicious-content-in-auditing-mode"></a>Kullanıcıların denetim modunda şüpheli içeriği bildirmesini sağlama

Office 365 için Defender, kullanıcıların güvenlik ekiplerine ileti bildirmesine olanak tanır ve yöneticilerin analiz için Microsoft'a ileti göndermesine olanak tanır.

- [Rapor İletisi eklentisini veya Rapor Kimlik Avı eklentisini dağıtın](enable-the-report-message-add-in.md).
- [Hatalı pozitifleri ve hatalı negatifleri raporlamak](report-false-positives-and-false-negatives.md) için bir iş akışı oluşturun.
- [Gönderimler portalını](admin-submission.md) kullanın.

Daha fazla bilgi edinmek için bu videoyu izleyin: [Analiz için ileti göndermek için Gönderimler portalını kullanmayı öğrenin - YouTube](https://www.youtube.com/watch?v=ta5S09Yz6Ks&ab_channel=MicrosoftSecurit).

#### <a name="review-reports-to-understand-the-threat-landscape-in-auditing-mode"></a>Denetim modundaki tehdit ortamını anlamak için raporları gözden geçirin

Ortamınız hakkında daha fazla bilgi edinmek için Office 365 için Defender'deki raporlama özelliklerini kullanın.

- [Değerlendirme panosu](try-microsoft-defender-for-office-365.md#reporting-in-audit-mode), değerlendirme sırasında Office 365 için Defender tarafından algılanan tehditlerin kolay bir görünümünü sağlar.
- [Tehdit koruması durum raporuyla](view-email-security-reports.md#threat-protection-status-report) e-posta ve işbirliği araçlarına alınan tehditleri anlayın.

### <a name="step-2-intermediate-steps-in-auditing-mode"></a>2. Adım: Denetim modunda ara adımlar

#### <a name="use-threat-explorer-to-investigate-malicious-email-in-auditing-mode"></a>Denetim modunda kötü amaçlı e-postaları araştırmak için Tehdit Gezgini'ni kullanma

Office 365 için Defender, kuruluşunuzdaki kişileri riske atacak etkinlikleri araştırmanıza ve kuruluşunuzu korumak için eylem gerçekleştirmenize olanak tanır. Bunu [Tehdit Gezgini'ne](threat-explorer.md) kullanarak yapabilirsiniz.

- [Teslim edilen şüpheli e-postayı bulma](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered): İletileri bulun ve silin, kötü amaçlı e-posta gönderenin IP adresini tanımlayın veya daha fazla araştırma için bir olay başlatın.
- [Teslim eylemini ve konumunu denetleyin](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location): Bu denetim, sorunlu e-posta iletilerinin konumunu öğrenmenizi sağlar.
- [E-postanızın zaman çizelgesini görüntüleyin](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email): Yalnızca güvenlik operasyonları ekibiniz için avlanma.

#### <a name="convert-to-standard-protection-at-the-end-of-evaluation-period"></a>Değerlendirme döneminin sonunda Standart Koruma'ya dönüştürün

Üretimde Office 365 için Defender ilkelerini etkinleştirmeye hazır olduğunuzda, [önceden ayarlanmış güvenlik ilkelerinde](preset-security-policies.md) standart korumaya kolayca geçmek için değerlendirme yönetimi deneyiminde "Standart Korumaya Dönüştür"ü kullanabilirsiniz.

1. konumundaki **Office 365 için Microsoft Defender değerlendirme** sayfasında **Yönet'e**<https://security.microsoft.com/atpEvaluation> tıklayın.

   :::image type="content" source="../../media/mdo-trial-playbook-mdo-evaluation-page.png" alt-text="Microsoft 365 Defender portalındaki Office 365 için Defender değerlendirme sayfasında Yönet'e tıklayın." lightbox="../../media/mdo-trial-playbook-mdo-evaluation-page.png":::

2. Açılan açılır öğede **Standart korumaya dönüştür'e** tıklayın

   :::image type="content" source="../../media/mdo-trial-playbook-manage-flyout.png" alt-text="Office 365 için Defender değerlendirme sayfasının Yönet açılır öğesinde Standart korumaya dönüştür'e tıklayın." lightbox="../../media/mdo-trial-playbook-manage-flyout.png":::

3. Açılan **Standart korumaya dönüştür** iletişim kutusunda, kurulumu başlatmak için **Devam'a** tıklayın.

#### <a name="migrate-from-a-third-party-protection-service-or-device-to-defender-for-office-365"></a>Üçüncü taraf koruma hizmetinden veya cihazından Office 365 için Defender'a geçiş yapma

Zaten Microsoft 365'in önünde duran bir üçüncü taraf koruma hizmetiniz veya cihazınız varsa, birleştirilmiş bir yönetim deneyiminin avantajlarından, potansiyel olarak düşük maliyetlerden (zaten ödeme yaptığınız ürünleri kullanarak) ve tümleşik güvenlik korumasına sahip olgun bir üründen yararlanmak için korumanızı Office 365 için Microsoft Defender geçirebilirsiniz.

Daha fazla bilgi için bkz. [Üçüncü taraf koruma hizmetinden veya cihazından Office 365 için Microsoft Defender geçirme](migrate-to-defender-for-office-365.md).

### <a name="step-3-advanced-content-in-auditing-mode"></a>3. Adım: Denetim modunda gelişmiş içerik

#### <a name="train-users-to-spot-threats-by-simulating-attacks-in-auditing-mode"></a>Denetim modunda saldırıların benzetimlerini yaparak kullanıcıları tehditleri tespit etmeye eğitin

Tehditleri tanımlamak ve şüpheli iletileri Office 365 için Defender Saldırı simülasyonu eğitimi bildirmek için kullanıcılarınızı doğru bilgiyle donatın.

- Savunmasız kullanıcıları tanımlamak için [gerçekçi tehditlerin benzetimini](attack-simulation-training.md) yapmak.
- Simülasyon sonuçlarına göre kullanıcılara [eğitim atayın](attack-simulation-training.md#assign-training).
- Simülasyonlar ve eğitim tamamlama aşamasında kuruluşunuzun [ilerleme durumunu izleyin](attack-simulation-training-insights.md).

  :::image type="content" source="../../media/mdo-trial-playbook-attack-simulation-training-results.png" alt-text="Microsoft 365 Defender portalındaki saldırı simülasyonu eğitim içgörüleri." lightbox="../../media/mdo-trial-playbook-attack-simulation-training-results.png":::

## <a name="additional-resources"></a>Ek kaynaklar

- **Etkileşimli kılavuz**: Office 365 için Defender aşina değil misiniz? Nasıl başlayabileceğinizi anlamak için [etkileşimli kılavuzu](https://mslearn.cloudguides.com/guides/Safeguard%20your%20organization%20with%20Microsoft%20Defender%20for%20Office%20365) gözden geçirin.
- **Hızlı İz Kullanmaya Başlama Kılavuzu**: [Office 365 için Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2197415)
- **Microsoft belgeleri**: Office 365 için Defender nasıl çalıştığı ve kuruluşunuz için bunu en iyi şekilde nasıl uygulayacakları hakkında ayrıntılı bilgi edinin. [Docs'u](overview.md) ziyaret edin.
- **Dahil olanlar**: Ürün katmanı tarafından listelenen Office 365 e-posta güvenlik özelliklerinin tam listesi için [Özellik Matrisi'ni](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability) görüntüleyin.
- **Neden Office 365 için Defender**: [Office 365 için Defender Veri Sayfası](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE4FCiy), müşterilerin Microsoft'u seçmesinin en önemli 10 nedenini gösterir.
