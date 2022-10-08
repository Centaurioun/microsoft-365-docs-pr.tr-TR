---
title: Office 365 için Microsoft Defender deneme kullanım kılavuzu
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.collection: m365-security
ms.localizationpriority: high
ms.service: microsoft-365-security
search.appverid:
- MOE150
- MET150
description: Office 365 için Microsoft Defender çözümleri deneme kullanım kılavuzu.
ms.subservice: mdo
ms.custom: trial-playbook
ms.openlocfilehash: 145ebc155b2ae10bfdd2b6cdb05e35746969ad2f
ms.sourcegitcommit: 7828a1e78c3e6bd8d10289f1ad6c8b6769da0966
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/07/2022
ms.locfileid: "68495176"
---
# <a name="trial-user-guide-microsoft-defender-for-office-365"></a>Deneme kullanım kılavuzu: Office 365 için Microsoft Defender

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Şunlar için geçerlidir:**
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Office 365 için Microsoft Defender deneme kullanım kılavuzuna hoş geldiniz! Bu kullanıcı kılavuzu, kuruluşunuzu e-posta iletileri, bağlantılar (URL' ler) ve işbirliği araçları tarafından ortaya konan kötü amaçlı tehditlere karşı nasıl koruyacağınızı öğreterek ücretsiz denemenizden en iyi şekilde yararlanın.

## <a name="what-is-defender-for-office-365"></a>Office 365 için Defender nedir?

Office 365 için Defender, kuruluşların tehdit koruma ilkeleri, raporlar, tehdit araştırma ve yanıt özellikleri ile otomatik araştırma ve yanıt özellikleri gibi kapsamlı özellikler sunarak kuruluşlarının güvenliğini sağlamalarına yardımcı olur.

:::image type="content" source="../../media/microsoft-defender-for-office-365.png" alt-text="kavramsal diyagramı Office 365 için Microsoft Defender." lightbox="../../media/microsoft-defender-for-office-365.png":::

Gelişmiş tehditleri algılamaya ek olarak, aşağıdaki videoda Office 365 için Defender SecOps özelliklerinin ekibinizin tehditlere yanıt vermesine nasıl yardımcı olabileceği gösterilmektedir:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMmIe]

### <a name="audit-mode-vs-blocking-mode-for-defender-for-office-365"></a>Denetim modu ile Office 365 için Defender için engelleme modu karşılaştırması

Office 365 için Defender deneyiminizin etkin mi yoksa pasif mi olmasını istiyorsunuz? Şunlar arasından seçim yapabileceğiniz iki mod vardır:

- **Denetim modu**: Kimlik avı önleme (kimliğe bürünme koruması, Güvenli Ekler ve Güvenli Bağlantılar dahil) için özel *değerlendirme ilkeleri* oluşturulur. Bu değerlendirme ilkeleri yalnızca tehditleri *algılamak* için yapılandırılır. Office 365 için Defender, raporlama için zararlı iletileri algılar, ancak iletiler üzerinde işlem gerçekleştirilmiyor (örneğin, algılanan iletiler karantinaya alınmıyor). Bu değerlendirme ilkelerinin ayarları, bu makalenin devamında [denetim modunda ilkeler](try-microsoft-defender-for-office-365.md#policies-in-audit-mode) bölümünde açıklanmaktadır.

  Denetim modu, konumundaki **Değerlendirme modu** sayfasında <https://security.microsoft.com/atpEvaluation>Office 365 için Defender tarafından algılanan tehditler için özelleştirilmiş raporlara erişim sağlar.

- **Engelleme modu**: [Önceden ayarlanmış güvenlik ilkeleri](preset-security-policies.md) için Standart şablon açılır ve deneme sürümü için kullanılır ve deneme sürümüne dahil etmek için belirttiğiniz kullanıcılar Standart önceden ayarlanmış güvenlik ilkesine eklenir. Office 365 için Defender zararlı iletileri *algılar* ve *üzerinde işlem uygular* (örneğin, algılanan iletiler karantinaya alınır).

  Varsayılan ve önerilen seçim, bu Office 365 için Defender ilkelerini kuruluştaki tüm kullanıcılara kapsamaktır. Ancak denemenizin kurulumu sırasında veya sonrasında, ilke atamasını Microsoft 365 Defender portalında veya Office 365 için Defender [denemeleriyle ilişkili İlke ayarları'nda](try-microsoft-defender-for-office-365.md#policy-settings-associated-with-defender-for-office-365-trials) belirli kullanıcılara, gruplara veya e-posta etki alanlarına değiştirebilirsiniz

  Engelleme modu, Office 365 için Defender tarafından algılanan tehditler için özelleştirilmiş raporlar sağlamaz. Bunun yerine, bilgiler Office 365 için Defender Plan 2'nin normal raporlarında ve araştırma özelliklerinde kullanılabilir.

E-postanın Microsoft 365 kuruluşunuza nasıl teslim edilmesi denetim modunda ve engelleme modunda önemli bir faktördür:

- İnternet'ten gelen postalar doğrudan Microsoft 365'e akar, ancak geçerli aboneliğinizde yalnızca [Exchange Online Protection (EOP)](exchange-online-protection-overview.md) veya [Plan 1 Office 365 için Defender](overview.md#microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet) vardır.

  ![EOP ve/veya Office 365 için Defender Plan 1'e karşı koruma ile posta İnternet'ten Microsoft 365'e akar.](../../media/mdo-trial-mail-flow.png)

  Bu ortamlarda **denetim modunu** veya **engelleme modunu** seçebilirsiniz.

- Şu anda Microsoft 365 posta kutularınızın e-posta koruması için üçüncü taraf bir hizmet veya cihaz kullanıyorsunuz. İnternet'ten gelen postalar, Microsoft 365 kuruluşunuza teslim etmeden önce koruma hizmeti aracılığıyla akar. Microsoft 365 koruması mümkün olduğunca düşüktür (hiçbir zaman tamamen kapalı değildir; örneğin, kötü amaçlı yazılım koruması her zaman uygulanır).

  ![Microsoft 365'e teslim etmeden önce İnternet'ten üçüncü taraf koruma hizmeti veya cihazı aracılığıyla posta akışları.](../../media/mdo-migration-before.png)

  Bu ortamlarda yalnızca **denetim modunu** seçebilirsiniz. Posta akışınızı (MX kayıtları) değiştirmeniz gerekmez.

Başlayalım!

## <a name="blocking-mode"></a>Engelleme modu

### <a name="step-1-getting-started-in-blocking-mode"></a>1. Adım: Engelleme modunda çalışmaya başlama

#### <a name="start-your-microsoft-defender-for-office-365-trial"></a>Office 365 için Microsoft Defender denemenizi başlatın

Deneme sürümünü başlattıktan ve [kurulum işlemini](try-microsoft-defender-for-office-365.md#set-up-an-evaluation-or-trial-in-blocking-mode) tamamladıktan sonra değişikliklerin geçerli olması 2 saate kadar sürebilir.

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

- Araştırma kullanıcı kılavuzları hakkında [daha fazla bilgi edinin](automated-investigation-response-office.md).
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

[Kurulum işlemini](try-microsoft-defender-for-office-365.md#set-up-an-evaluation-or-trial-in-audit-mode) tamamladıktan sonra değişikliklerin etkili olması 2 saat kadar sürebilir. Ortamınızda Önceden Belirlenmiş Değerlendirme ilkelerini otomatik olarak yapılandırdık.

Değerlendirme ilkeleri, Office 365 için Defender tarafından algılanan e-postalarda hiçbir işlem yapılmamasını sağlar.

#### <a name="enable-users-to-report-suspicious-content-in-auditing-mode"></a>Kullanıcıların denetim modunda şüpheli içeriği bildirmesini sağlama

Office 365 için Defender, kullanıcıların güvenlik ekiplerine ileti bildirmesine olanak tanır ve yöneticilerin analiz için Microsoft'a ileti göndermesine olanak tanır.

- [Rapor İletisi eklentisini veya Rapor Kimlik Avı eklentisini dağıtın](enable-the-report-message-add-in.md).
- [Hatalı pozitifleri ve hatalı negatifleri raporlamak](report-false-positives-and-false-negatives.md) için bir iş akışı oluşturun.
- [Gönderimler portalını](admin-submission.md) kullanın.

Daha fazla bilgi edinmek için bu videoyu izleyin: [Analiz için ileti göndermek için Gönderimler portalını kullanmayı öğrenin - YouTube](https://www.youtube.com/watch?v=ta5S09Yz6Ks&ab_channel=MicrosoftSecurit).

#### <a name="review-reports-to-understand-the-threat-landscape-in-auditing-mode"></a>Denetim modundaki tehdit ortamını anlamak için raporları gözden geçirin

Ortamınız hakkında daha fazla bilgi edinmek için Office 365 için Defender'deki raporlama özelliklerini kullanın.

- [Değerlendirme panosu](try-microsoft-defender-for-office-365.md#reports-for-audit-mode), değerlendirme sırasında Office 365 için Defender tarafından algılanan tehditlerin kolay bir görünümünü sağlar.
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
- **Office 365 için Microsoft Defender belgeleri**: Office 365 için Defender nasıl çalıştığı ve kuruluşunuz için bunu en iyi şekilde nasıl uygulayacakları hakkında ayrıntılı bilgi edinin. [Office 365 için Microsoft Defender belgelerini ziyaret edin](defender-for-office-365.md).
- **Dahil olanlar**: Ürün katmanı tarafından listelenen Office 365 e-posta güvenlik özelliklerinin tam listesi için [Özellik Matrisi'ni](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability) görüntüleyin.
- **Neden Office 365 için Defender**: [Office 365 için Defender Veri Sayfası](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE4FCiy), müşterilerin Microsoft'u seçmesinin en önemli 10 nedenini gösterir.
