---
title: Bir XDR çözümü olan Microsoft 365 Defender değerlendirme ve pilot uygulama
description: XDR güvenliği nedir? Microsoft 365 Defender'da Bir Microsoft XDR'sini nasıl değerlendirebilirsiniz? Cihazları, kimlikleri, verileri ve uygulamaları korumak için tasarlanmış bir güvenlik çözümünü test etmek ve pilot olarak kullanmak üzere Microsoft 365 Defender deneme laboratuvarınızı veya pilot ortamınızı planlamak için bu blog serisini kullanın. XDR siber güvenlik yolculuğunuza buradan başlayın ve bu testi üretime alın.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 06/25/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
- zerotrust-solution
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 5256a578abb515f7d8d2d6e73b5a01fe71404dd0
ms.sourcegitcommit: 61b22df76e0f81e5ef11c587b129287886151c79
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2022
ms.locfileid: "66750088"
---
# <a name="evaluate-and-pilot-microsoft-365-defender"></a>Microsoft 365 Defender'ı değerlendirme ve pilot

**Şunlar için geçerlidir:**

- Microsoft 365 Defender

## <a name="how-this-article-series-works"></a>Bu makale serisi nasıl çalışır?

Bu makale serisi, deneme XDR ortamını *uçtan uca* ayarlama sürecinde size adım adım yol gösterir; böylece Microsoft 365 Defender özelliklerini ve özelliklerini değerlendirebilir ve hatta hazır olduğunuzda ve hazır olduğunuzda değerlendirme ortamını doğrudan üretim ortamına yükseltebilirsiniz.

XDR'yi düşünmeye yeni başlarsanız, çözümün ne kadar kapsamlı olduğuna dair fikir edinmek için bu bağlantılı 7 makaleyi tarayabilirsiniz.

- [Ortamı oluşturma](eval-create-eval-environment.md)
- Bu Microsoft XDR'nin her teknolojisini ayarlama veya öğrenme
  - [Kimlik için Microsoft Defender](eval-defender-identity-overview.md)
  - [Office için Microsoft Defender](eval-defender-office-365-overview.md)
  - [Uç Nokta için Microsoft Defender](eval-defender-endpoint-overview.md)
  - [Bulut Uygulamaları için Microsoft Defender](eval-defender-mcas-overview.md)
- [Bu XDR'yi kullanarak araştırma ve yanıtlama](eval-defender-investigate-respond.md)
- [Deneme ortamını üretime yükseltme](eval-defender-promote-to-production.md)

## <a name="microsoft-365-defender-is-a-microsoft-xdr-cyber-security-solution"></a>Microsoft 365 Defender bir Microsoft XDR siber güvenlik çözümüdür

Microsoft 365 Defender, *Uç nokta, e-posta, uygulamalar ve kimlikler* dahil olmak üzere Microsoft 365 *ortamınızdaki sinyal*, tehdit ve uyarı verilerini otomatik olarak toplayan, ilişkilendiren ve analiz eden bir **eXtended algılama ve yanıt (XDR) çözümüdür**. Saldırıları *otomatik olarak* durdurmak ve etkilenen varlıkları güvenli bir duruma getirmek için yapay zeka (AI) ve otomasyondan yararlanıyor.

XDR'yi güvenlik, uç noktayı birleştirme (uç nokta algılama ve yanıt veya EDR), e-posta, uygulama ve kimlik güvenliğinde bir sonraki adım olarak düşünün.

## <a name="microsoft-recommendations-for-evaluating-microsoft-365-defender"></a>Microsoft 365 Defender değerlendirmeye yönelik Microsoft önerileri

Microsoft, değerlendirmenizi mevcut bir Office 365 üretim aboneliğinde oluşturmanızı önerir. Bu şekilde hemen gerçek dünya içgörüleri elde eder ve ayarları ortamınızdaki mevcut tehditlere karşı çalışacak şekilde ayarlayabilirsiniz. Deneyim kazandıktan ve platformdan memnun olduktan sonra, her bileşeni birer birer üretime yükseltmeniz yeterlidir.

## <a name="the-anatomy-of-a-cyber-security-attack"></a>Siber güvenlik saldırısının anatomisi

Microsoft 365 Defender Bulut tabanlı, birleşik, ihlal öncesi ve sonrası kurumsal savunma paketidir. Uç noktalar, kimlikler, uygulamalar, e-posta, işbirliğine dayalı uygulamalar ve bunların tüm verileri arasında *önleme*, *algılama*, *araştırma* ve *yanıtı* koordine eder.

Bu çizimde bir saldırı sürüyor. Kimlik avı e-postası, kuruluşunuzdaki bir çalışanın Gelen Kutusu'na ulaşır ve e-posta ekini bilmeden açar. Bu, hassas verilerin çalınmasıyla sona erebilecek bir olay zincirine yol açan kötü amaçlı yazılımları yükler. Ancak bu durumda, Office 365 için Defender çalışır durumdadır.

:::image type="content" source="../../media/defender/m365-defender-eval-threat-chain.png" alt-text="Çeşitli saldırı girişimleri" lightbox="../../media/defender/m365-defender-eval-threat-chain.png":::

Çizimde:

- **Office 365 için Microsoft Defender** parçası olan Exchange Online Protection, kimlik avı e-postasını algılayabilir ve gelen kutusuna hiç ulaşmadığından emin olmak için posta akışı kurallarını kullanabilir.
- **Office 365 için Defender** güvenli ekler eki test eder ve zararlı olduğunu belirler, bu nedenle gelen posta kullanıcı tarafından eyleme dönüştürülemez veya ilkeler postanın gelmesini engeller.
- **Uç Nokta için Defender** , şirket ağına bağlanan ve aksi takdirde kötüye kullanılabilecek cihaz ve ağ güvenlik açıklarını algılayan cihazları yönetir.
- **Kimlik için Defender** , ayrıcalık yükseltme veya yüksek riskli yanal hareket gibi ani hesap değişikliklerini not alır. Ayrıca güvenlik ekibi tarafından düzeltilmesi için kısıtlanmamış Kerberos temsilcisi gibi kolayca yararlanılan kimlik sorunlarını bildirir.
- **Microsoft Defender for Cloud Apps** imkansız seyahat, kimlik bilgisi erişimi ve olağan dışı indirme, dosya paylaşımı veya posta iletme etkinliği gibi anormal davranışlar fark eder ve bunları güvenlik ekibine bildirir.

### <a name="microsoft-365-defender-components-secure-devices-identity-data-and-applications"></a>Microsoft 365 Defender bileşenleri cihazların, kimliklerin, verilerin ve uygulamaların güvenliğini sağlar

Microsoft 365 Defender, birlikte çalışan bu güvenlik teknolojilerinden oluşur. XDR ve Microsoft 365 Defender özelliklerinden yararlanmak için bu bileşenlerin tümüne ihtiyacınız yoktur. Bir veya iki tane kullanarak da kazançlar ve verimlilikler elde edebilirsiniz.

|Bileşen|Açıklama|Başvuru malzemesi|
|---|---|---|
|Kimlik için Microsoft Defender|Kimlik için Microsoft Defender gelişmiş tehditleri, güvenliği aşılmış kimlikleri ve kuruluşunuza yönelik kötü amaçlı insider eylemlerini tanımlamak, algılamak ve araştırmak için Active Directory sinyallerini kullanır.|[Kimlik için Microsoft Defender nedir?](/defender-for-identity/what-is)|
|Exchange Online Protection|Exchange Online Protection, kuruluşunuzu istenmeyen postalara ve kötü amaçlı yazılımlara karşı korumaya yardımcı olan yerel bulut tabanlı SMTP geçişi ve filtreleme hizmetidir.|[Exchange Online Protection (EOP) genel bakış - Office 365](../office-365-security/overview.md)|
|Office 365 için Microsoft Defender|Office 365 için Microsoft Defender, kuruluşunuzu e-posta iletileri, bağlantılar (URL'ler) ve işbirliği araçları tarafından ortaya konan kötü amaçlı tehditlere karşı korur.|[Office 365 için Microsoft Defender - Office 365](../office-365-security/overview.md)|
|Uç Nokta için Microsoft Defender|Uç Nokta için Microsoft Defender cihaz koruması, ihlal sonrası algılama, otomatik araştırma ve önerilen yanıt için birleşik bir platformdur.|[Uç Nokta için Microsoft Defender - Windows güvenliği](../defender-endpoint/microsoft-defender-endpoint.md)|
|Bulut Uygulamaları için Microsoft Defender|Microsoft Defender for Cloud Apps, bulut uygulamalarınıza derin görünürlük, güçlü veri denetimleri ve gelişmiş tehdit koruması getiren kapsamlı bir SaaS çözümüdür.|[Cloud Apps için Defender nedir?](/cloud-app-security/what-is-cloud-app-security)|
|Azure AD Kimlik Koruması|Azure AD Kimlik Koruması milyarlarca oturum açma girişiminden kaynaklanan risk verilerini değerlendirir ve ortamınızda her oturum açma riskini değerlendirmek için bu verileri kullanır. Bu veriler, Koşullu Erişim ilkelerinin nasıl yapılandırıldığına bağlı olarak hesap erişimine izin vermek veya erişimi engellemek için Azure AD tarafından kullanılır. Azure AD Kimlik Koruması, Microsoft 365 Defender ayrı olarak lisanslanır. Azure Active Directory Premium P2'a dahildir.|[Kimlik Koruması nedir?](/azure/active-directory/identity-protection/overview-identity-protection)|
||||

## <a name="microsoft-365-defender-architecture"></a>Microsoft 365 Defender mimarisi

Aşağıdaki diyagramda önemli Microsoft 365 Defender bileşenleri ve tümleştirmeleri için üst düzey mimari gösterilmektedir. Her Defender bileşeni ve kullanım örneği senaryoları için *ayrıntılı* mimari, bu makale serisi boyunca verilmiştir.

:::image type="content" source="../../media/defender/m365-defender-eval-architecture.png" alt-text="Microsoft 365 Defender portalının üst düzey mimarisi" lightbox="../../media/defender/m365-defender-eval-architecture.png":::

Bu çizimde:

- Microsoft 365 Defender, etki alanları arasında genişletilmiş algılama ve yanıt (XDR) sağlamak için tüm Defender bileşenlerinden gelen sinyalleri birleştirir. Buna birleşik bir olay kuyruğu, saldırıları durdurmak için otomatik yanıt, kendi kendini iyileştirme (güvenliği aşılmış cihazlar, kullanıcı kimlikleri ve posta kutuları için), çapraz tehdit avcılığı ve tehdit analizi dahildir.
- Office 365 için Microsoft Defender, kuruluşunuzu e-posta iletileri, bağlantılar (URL'ler) ve işbirliği araçları tarafından ortaya konan kötü amaçlı tehditlere karşı korur. Bu etkinliklerden kaynaklanan sinyalleri Microsoft 365 Defender ile paylaşır. Exchange Online Protection (EOP), gelen e-postalar ve ekler için uçtan uca koruma sağlamak üzere tümleşiktir.
- Kimlik için Microsoft Defender, Active Directory Federasyon Hizmetleri (AD FS) ve şirket içi Active Directory Etki Alanı Hizmetleri (AD DS) çalıştıran sunuculardan sinyaller toplar. Bu sinyalleri hibrit kimlik ortamınızı korumak için kullanır. Bu sinyaller, şirket içi ortamdaki iş istasyonları arasında yaya olarak hareket etmek için güvenliği aşılmış hesapları kullanan korsanlara karşı koruma da dahil olmak üzere.
- Uç Nokta için Microsoft Defender, kuruluşunuz tarafından kullanılan cihazlardan sinyal toplar ve bu cihazları korur.
- Microsoft Defender for Cloud Apps, kuruluşunuzun bulut uygulamalarını kullanmasından gelen sinyalleri toplar ve hem tasdikli hem de tasdiksiz bulut uygulamaları dahil olmak üzere ortamınızla bu uygulamalar arasında akan verileri korur.
- Azure AD Kimlik Koruması milyarlarca oturum açma girişiminden kaynaklanan risk verilerini değerlendirir ve ortamınızda her oturum açma riskini değerlendirmek için bu verileri kullanır. Bu veriler, Koşullu Erişim ilkelerinin nasıl yapılandırıldığına bağlı olarak hesap erişimine izin vermek veya erişimi engellemek için Azure AD tarafından kullanılır. Azure AD Kimlik Koruması, Microsoft 365 Defender ayrı olarak lisanslanır. Azure Active Directory Premium P2'a dahildir.

## <a name="microsoft-siem-and-soar-can-use-data-from-microsoft-365-defender"></a>Microsoft SIEM ve SOAR, Microsoft 365 Defender verilerini kullanabilir

Bu çizimde bulunmayan ek isteğe bağlı mimari bileşenleri:

- **Tüm Microsoft 365 Defender bileşenlerinden gelen ayrıntılı sinyal verileri Microsoft Sentinel ile tümleştirilebilir** ve tam SIEM ve SOAR özellikleri ve içgörüleri sunmak için diğer günlük kaynaklarıyla birleştirilebilir.
- Azure **SIEM olan Microsoft Sentinel'i XDR olarak Microsoft 365 Defender kullanma hakkında daha fazla bilgi** için bu [Genel Bakış makalesine](/azure/sentinel/microsoft-365-defender-sentinel-integration) ve Microsoft Sentinel ile Microsoft 365 Defender [tümleştirme adımlarına](/azure/sentinel/connect-microsoft-365-defender?tabs=MDE) göz atın.
- Microsoft Sentinel'de SOAR hakkında daha fazla bilgi için (Microsoft Sentinel GitHub Deposu'ndaki playbook'lara bağlantılar dahil), lütfen [bu makaleyi](/azure/sentinel/automate-responses-with-playbooks) okuyun.

## <a name="the-evaluation-process-for-microsoft-365-defender-cyber-security"></a>Microsoft 365 Defender siber güvenlik değerlendirme süreci

Microsoft, Microsoft 365 bileşenlerinin gösterildiği sırayla etkinleştirilmesini önerir:

:::image type="content" source="../../media/defender/m365-defender-eval-process.png" alt-text="Microsoft 365 Defender portalında üst düzey değerlendirme süreci" lightbox="../../media/defender/m365-defender-eval-process.png":::

Aşağıdaki tabloda bu çizim açıklanmaktadır.

|  Seri Numarası   |Adım  |Açıklama  |
|------|---------|---------|
|1     | [Değerlendirme ortamını oluşturun](eval-create-eval-environment.md)       |Bu adım, Microsoft 365 Defender için deneme lisansına sahip olduğunuzdan emin olun.         |
|2     | [Kimlik için Defender'ın etkinleştirilmesi](eval-defender-identity-overview.md)        | Mimari gereksinimlerini gözden geçirin, değerlendirmeyi etkinleştirin ve farklı saldırı türlerini tanımlamaya ve düzeltmeye yönelik öğreticileri gözden geçirin.   |
|3     | [Office 365 için Defender etkinleştirme ](eval-defender-office-365-overview.md)       | Mimari gereksinimlerini karşıladığınızdan emin olun, değerlendirmeyi etkinleştirin ve ardından pilot ortamı oluşturun. Bu bileşen Exchange Online Protection içerir ve bu nedenle *her ikisini de* burada değerlendirebilirsiniz.      |
|4     | [Uç Nokta için Defender'ın etkinleştirilmesi ](eval-defender-endpoint-overview.md)       | Mimari gereksinimlerini karşıladığınızdan emin olun, değerlendirmeyi etkinleştirin ve ardından pilot ortamı oluşturun.         |
|5     | [Microsoft Defender for Cloud Apps etkinleştirme](eval-defender-mcas-overview.md)        |  Mimari gereksinimlerini karşıladığınızdan emin olun, değerlendirmeyi etkinleştirin ve ardından pilot ortamı oluşturun.        |
|6     | [Tehditleri araştırın ve karşı yanıt verin](eval-defender-investigate-respond.md)        |   Bir saldırının benzetimini yapıp olay yanıtı özelliklerini kullanmaya başlayın.      |
|7     | [Deneme sürümünü üretime yükseltin](eval-defender-promote-to-production.md)        | Microsoft 365 bileşenlerini tek tek üretime yükseltin.        |

Bu, genellikle özellikleri dağıtmak ve yapılandırmak için gereken çabaya bağlı olarak özelliklerin değerinden hızlı bir şekilde yararlanmak için tasarlanmış yaygın olarak önerilen bir sipariştir. Örneğin Office 365 için Defender, cihazları Uç Nokta için Defender'a kaydetmek için gerekenden daha kısa sürede yapılandırılabilir. Elbette, iş gereksinimlerinizi karşılamak için bileşenleri önceliklendirmeniz gerekir ve bunları farklı bir sırayla etkinleştirebilirsiniz.

## <a name="go-to-the-next-step"></a>Sonraki Adıma Gitme

[Microsoft 365 Defender Değerlendirme Ortamı hakkında bilgi edinin ve/veya oluşturma](eval-create-eval-environment.md)
