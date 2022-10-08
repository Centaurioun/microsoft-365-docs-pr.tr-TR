---
title: E-posta güvenliği için derinlemesine savunma yapılandırmasıyla çalışmaya başlama
description: Üçüncü taraf e-posta filtrelemeniz olduğunda Office 365 için Microsoft Defender'dan güvenlik değeri alma konusunda adım adım yapılandırma kılavuzu.
search.product: ''
ms.service: microsoft-365-security
ms.subservice: mdo
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: benharri
author: MSFTBen
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-guidance-templates
- m365-security
- tier3
ms.topic: how-to
search.appverid: met150
ms.openlocfilehash: 99d767aca4d5e619372569f621c07cbca96d403b
ms.sourcegitcommit: 2ff545246fec060ea7829da5afbc1cdc698d51ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68363090"
---
# <a name="getting-the-best-security-value-from-microsoft-defender-for-office-365-when-you-have-third-party-email-filtering"></a>Üçüncü taraf e-posta filtrelemeniz olduğunda Office 365 için Microsoft Defender en iyi güvenlik değerini alma

Bu kılavuz şu durumda size yöneliktir:

- Office 365 için Microsoft Defender lisansınız var ve posta kutularınızı Office 365
- Ayrıca e-posta güvenliğiniz için bir üçüncü taraf kullanıyorsunuz

Aşağıdaki bilgiler, kolayca izlenecek adımlara ayrılmış şekilde yatırımlarınızdan nasıl en iyi şekilde nasıl kurtulacağınız hakkında ayrıntılı bilgi sağlar.

## <a name="what-you-will-need"></a>İhtiyacınız olan şey
- Office 365'de barındırılan posta kutuları
- Bir veya daha fazla:
  - Koruma özellikleri için Plan 1'i Office 365 için Microsoft Defender
  - Diğer özelliklerin çoğu için plan 2'yi Office 365 için Microsoft Defender (E5 planlarında bulunur)
  - Office 365 için Microsoft Defender Deneme Sürümü (aka.ms/tryMDO tüm müşteriler tarafından kullanılabilir)
- Aşağıda açıklanan özellikleri yapılandırmak için yeterli izinler

## <a name="step-1--understand-the-value-you-already-have"></a>1. Adım : Zaten sahip olduğunuz değeri anlama

### <a name="protection-features"></a>Koruma özellikleri

- Yerleşik koruma temel düzeyde göze çarpmayan koruma sunar ve e-postada (iç e-posta dahil), SharePoint Online, OneDrive ve Teams'de kötü amaçlı yazılım, sıfır gün (Güvenli Ekler) ve URL koruması (Güvenli Bağlantılar) içerir. Bu durumda sağlanan URL korumasının yalnızca API çağrısı aracılığıyla olduğunu unutmayın. URL'leri sarmalamaz veya yeniden yazmaz, ancak desteklenen bir Outlook istemcisi gerektirir. Korumanızı genişletmek için kendi özel ilkelerinizi oluşturabilirsiniz.

**Daha fazla bilgi edinin & Burada Güvenli Bağlantılar'ın genel bakış videosunu izleyin:** [Güvenli Bağlantıları Tamamlamaya genel bakış](../safe-links.md)

**Güvenli Ekler hakkında daha fazla bilgiyi burada bulabilirsiniz:**  [Güvenli Ekler](../safe-attachments.md) 

### <a name="detection-investigation-response-and-hunting-features"></a>Algılama, araştırma, yanıt ve avcılık özellikleri

- Uyarılar Office 365 için Microsoft Defender tetiklendiğinde, güvenlik personelindeki uyarı yorgunluğunu azaltmaya yardımcı olmak için otomatik olarak ilişkilendirilip Olaylar olarak birleştirilir. Otomatik Araştırma ve Yanıt (AIR), tehditleri düzeltmeye ve kapsamaya yardımcı olmak için araştırma tetikler.

**Daha fazla bilgi edinin, genel bakış videosunu izleyin ve buradan başlayın:** [Microsoft 365 Defender ile olay yanıtı](/microsoft-365/security/defender/incidents-overview)

- Threat Analytics, uzman Microsoft güvenlik araştırmacılarının ürün içi ayrıntılı tehdit bilgileri çözümümüz, en son tehdit gruplarında size hız vermek için tasarlanmış ayrıntılı raporlar, saldırı teknikleri, Risk Göstergeleri (IOC) ile kuruluşunuzu koruma ve çok daha fazlası.

**Daha fazla bilgi edinin, genel bakış videosunu izleyin ve buradan başlayın:** [Microsoft 365 Defender'de tehdit analizi](../../defender/threat-analytics.md)

- Explorer tehditleri avlamak, posta akışı desenlerini görselleştirmek, eğilimleri belirlemek ve Office 365 için Defender ayarlama sırasında yaptığınız değişikliklerin etkisini belirlemek için kullanılabilir. Ayrıca birkaç basit tıklamayla kuruluşunuzdan gelen iletileri hızla silebilirsiniz.

**Daha fazla bilgi edinin ve buradan başlayın:** [Tehdit Gezgini ve Gerçek zamanlı algılamalar](../threat-explorer.md)

## <a name="step-2--enhance-the-value-further-with-these-simple-steps"></a>2. Adım – Bu basit adımlarla değeri daha da geliştirin

### <a name="protection-features"></a>Koruma özellikleri

- Yerleşik Koruma'nın ötesinde ilkeleri etkinleştirmeyi göz önünde bulundurun. Örneğin, üçüncü taraf korumanızda eksik olan ek katmanlar veya boşlukları doldurmak için tıklama zamanı korumasını veya kimliğe bürünme korumasını etkinleştirme. Kararları geçersiz kılan bir aktarım kuralınız veya bağlantı filtreniz varsa (bu SCL-1 olarak da bilinir) diğer koruma özelliklerini açmadan önce bu sorunu gidermeniz gerektiğini unutmayın.

**Burada daha fazla bilgi edinin:** [Kimlik avı önleme ilkeleri](../set-up-anti-phishing-policies.md)

- Geçerli güvenlik sağlayıcınız iletileri *herhangi bir şekilde* değiştirecek şekilde yapılandırılmışsa, kimlik doğrulama sinyallerinin Office için Defender'ın sizi sahtekarlık gibi saldırılara karşı koruma becerisini etkileyebileceğini unutmayın. Üçüncü tarafınız Kimliği Doğrulanmış Alınan Zinciri (ARC) destekliyorsa, bunun etkinleştirilmesi gelişmiş çift filtreleme yolculuğunuzda kesinlikle önerilen bir adımdır. herhangi bir ileti değişikliği yapılandırmasını Office 365 için Defender'a taşımak da alternatif bir seçenektir.

**Burada daha fazla bilgi edinin:** [Gönderen ve alıcı arasındaki geçerli cihazlar ve hizmetler için Güvenilen ARC gönderenlerini kullanma](../use-arc-exceptions-to-mark-trusted-arc-senders.md)

- Bağlayıcılar için gelişmiş Filtreleme, IP adresi ve gönderen bilgilerinin üçüncü taraf aracılığıyla korunmasına olanak tanır. Bu, filtreleme (koruma) yığını, ihlal sonrası özellikleri & kimlik doğrulama geliştirmeleri için doğruluğu artırır.

**Burada daha fazla bilgi edinin:** [Exchange Online'da bağlayıcılar için gelişmiş filtreleme](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- Öncelik hesabı koruması, gelişmiş bir savunma ayrıntılı yapılandırma durumundayken ek korumanın yanı sıra araçlardaki hesaplar için gelişmiş görünürlük sunar.

**Burada daha fazla bilgi edinin:** [Öncelik hesabı koruması](protect-your-c-suite-with-priority-account-protection.md)

- Gelişmiş Teslim, üçüncü taraf kimlik avı simülasyonlarını doğru şekilde teslim edecek şekilde yapılandırılmalıdır ve Güvenlik İşlemleri posta kutunuz varsa, tehditler nedeniyle e-postaların posta kutusundan *kaldırılmadığından* emin olmak için bunu SecOps posta kutusu olarak tanımlamayı göz önünde bulundurun.

**Daha fazla bilgi için buraya bakın:** [Gelişmiş teslim](../configure-advanced-delivery.md)

- Kullanıcı tarafından bildirilen e-posta ayarları, kullanıcıların iletileri doğrudan Microsoft'a veya özel posta kutunuza (geçerli güvenlik iş akışlarıyla tümleştirmek için) veya her ikisini birden raporlamasına olanak tanıyacak şekilde yapılandırılabilir. Gönderim portalına hatalı pozitif ve hatalı negatifleri önceliklendirmek için de erişilebilir.

**Burada daha fazla bilgi edinin:** [Rapor iletisi eklentisini kullanıcılara dağıtma ve yapılandırma](deploy-and-configure-the-report-message-add-in.md)

### <a name="detection-investigation-response-and-hunting-features"></a>Algılama, araştırma, yanıt ve tehdit avcılığı özellikleri

- Gelişmiş avcılık, kullanmaya başlamanıza yardımcı olmak için topluluktan paylaşılan sorguları kullanarak kuruluşunuzdaki tehditleri proaktif olarak avlamak için kullanılabilir. Kişiselleştirilmiş ölçütler karşılandığında uyarıları ayarlamak için özel algılamaları da kullanabilirsiniz.

**Daha fazla bilgi edinin, genel bakış videosunu izleyin ve buradan başlayın:** [Genel Bakış - Gelişmiş avcılık](../../defender/advanced-hunting-overview.md)

### <a name="education-features"></a>Eğitim özellikleri

- Saldırı simülasyonu eğitimi, kuruluşunuzda gerçekçi ama zararsız siber saldırı senaryoları çalıştırmanıza olanak tanır. Birincil e-posta güvenlik sağlayıcınızdan kimlik avı simülasyonu özelliklerine sahip değilseniz, Microsoft'un sanal saldırıları savunmasız kullanıcıları, ilkeleri ve uygulamaları belirlemenize ve bulmanıza yardımcı olabilir. Bu, gerçek bir saldırı kuruluşunuzu *etkilemeden önce* sahip olmanız ve düzeltmeniz gereken önemli bir bilgidir. Kullanıcıları kaçırdıkları tehditler hakkında eğitmek ve sonuç olarak kuruluşunuzun risk profilini azaltmak için ürün veya özel eğitimde atadığımız simülasyon sonrası. Saldırı simülasyonu eğitimi ile iletileri doğrudan gelen kutusuna teslim ederiz, böylece kullanıcı deneyimi zengin olur. Bu, simülasyonların doğru teslim edilmesi için geçersiz kılmalar gibi hiçbir güvenlik değişikliği gerekmediğini de gösterir.

**Buradan başlayın:** [Saldırı benzetimi kullanmaya başlama](../attack-simulation-training-get-started.md)

**Burada doğrudan bir simülasyon sunmaya atlayın:** [Saldırı simülasyonu eğitimi içinde otomatik saldırıları ve eğitimi ayarlama](how-to-setup-attack-simulation-training-for-automated-attacks-and-training.md)

## <a name="step-3-and-beyond-becoming-a-dual-use-hero"></a>3. adım ve sonrası, çift kullanımlı bir kahraman haline geliyor

- Yukarıda açıklanan algılama, araştırma, yanıt ve tehdit avcılığı etkinliklerinin çoğu güvenlik ekipleriniz tarafından tekrarlanmalıdır. Bu kılavuzda görevlerin, temponun ve ekip atamalarının ayrıntılı bir açıklaması önerilir.

**Daha Fazla Bilgi:** [Office 365 için Defender için Güvenlik İşlemleri Kılavuzu](../mdo-sec-ops-guide.md)

- Birden çok karantinaya erişim gibi kullanıcı deneyimlerini veya hatalı pozitiflerin ve yanlış negatiflerin gönderilmesini / rapor edilmesini göz önünde bulundurun. Üçüncü taraf hizmeti tarafından algılanan iletileri özel bir *X* üst bilgisi ile işaretleyerek, örneğin, Office 365 için Defender aktarım kuralları aracılığıyla bunları algılayıp karantinaya almalarına izin verebilirsiniz. Bu da kullanıcılara karantinaya alınan postalara erişmek için tek bir yer sağlar.

**Daha Fazla Bilgi:** [Karantina izinlerini ve ilkelerini yapılandırma](how-to-configure-quarantine-permissions-with-quarantine-policies.md)

- Geçiş kılavuzu, ortamınızı geçişe hazır olacak şekilde hazırlama ve ayarlama konusunda birçok yararlı kılavuz içerir. Ancak adımların çoğu çift kullanımlı bir senaryo için *de* geçerlidir. Son adımlarda MX anahtarı kılavuzunu yoksaymanız yeterlidir. 

**Buradan okuyun:** [Üçüncü taraf koruma hizmetinden Office 365 için Microsoft Defender geçiş - Office 365 | Microsoft Docs](../migrate-to-defender-for-office-365.md)

## <a name="more-information"></a>Daha fazla bilgi

[Üçüncü taraf koruma hizmetinden Office 365 için Microsoft Defender geçiş](../migrate-to-defender-for-office-365.md)

[Office 365 için Defender için Güvenlik İşlemleri Kılavuzu](../mdo-sec-ops-guide.md)

[Microsoft 365 Defender ile Office 365 için Microsoft Defender'den daha fazla yararlanın](https://www.youtube.com/watch?v=Tdz6KfruDGo)
