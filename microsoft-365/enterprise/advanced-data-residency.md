---
title: Microsoft 365'te gelişmiş veri yerleşimi
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.reviewer: dmwmsft
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: Microsoft 365'teki gelişmiş veri yerleşimi seçenekleri hakkında bilgi edinin.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3f770faaf96de604fa9d190f538006f67242b227
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806141"
---
# <a name="advanced-data-residency-in-microsoft-365"></a>Microsoft 365'te gelişmiş Data Residency

## <a name="overview-of-advanced-data-residency"></a>Gelişmiş Data Residency Genel Bakış

Microsoft 365 Gelişmiş Data Residency eklentisi ("ADR"), uygun müşterilere Microsoft 365 iş yüklerinin ve Müşteri Verilerinin genişletilmiş kapsamı, yerel ülke veri merkezi bölgeleri için taahhüt edilen veri yerleşimi ve öncelikli kiracı geçiş hizmetleri sağlar.  Gelişmiş Data Residency ile kurumsal müşteriler veri yerleşimi uyumluluğu ve kiracı konumu gereksinimlerini en iyi şekilde karşılayabilir.

Aşağıdaki iş yükleri ADR'ye dahil edilir. Daha fazla bilgi için bkz.:

- [Exchange Online](m365-dr-workload-exo.md)
- [SharePoint Online ve OneDrive İş](m365-dr-workload-spo.md)
- [Microsoft Teams](m365-dr-workload-teams.md)
- [Office P1 ve Exchange Online Protection için Microsoft Defender](m365-dr-workload-mdo-p1.md)
- [Web için Office](m365-dr-workload-office-for-web.md)
- [Viva Connections](m365-dr-workload-viva-connections.md)
- [Viva Topics](m365-dr-workload-viva-topics.md)
- [Microsoft Purview](m365-dr-workload-purview.md)
  - [Denetim (Standart)](m365-dr-workload-purview.md#purview-audit-standard)
  - [Denetim (Premium)](m365-dr-workload-purview.md#purview-audit-premium)
  - [Veri Saklama](m365-dr-workload-purview.md#data-lifecycle-management---data-retention)
  - [Microsoft Purview Kayıt Yönetimi](m365-dr-workload-purview.md#data-lifecycle-management---records-management)
  - [Duyarlılık Etiketleri](m365-dr-workload-purview.md#information-protection---sensitivity-labels)
  - [Veri Kaybı Önleme](m365-dr-workload-purview.md#information-protection---data-loss-prevention-dlp)
  - [Office İleti Şifrelemesi](m365-dr-workload-purview.md#information-protection---office-message-encryption)
  - [Bilgi Engelleri](m365-dr-workload-purview.md#insider-risk-management---information-barriers)

## <a name="licensing-and-purchase"></a>Lisanslama ve Satın Alma

### <a name="licensing-requirements"></a>Lisanslama Gereksinimleri

- Microsoft 365 F1, F3, E3 veya E5
- Office 365 F3, E1, E3 veya E5
- Exchange Online Plan 1 veya Plan 2
- OneDrive İş Plan 1 veya Plan 2
- SharePoint Online Plan 1 veya Plan 2

### <a name="eligibility"></a>Uygunluk

Gelişmiş Data Residency ("ADR") eklentisi, kapsamlı veri yerleşimi gereksinimleri olan Microsoft 365'in kurumsal müşterilerine yöneliktir.  ADR satın almaya uygun olmak için müşterilerin iki önkoşulu karşılaması gerekir:

- _Kiracıdaki_ abonelikler Microsoft Kurumsal Anlaşma ("EA") veya Web Direct kanalı üzerinden satın alınır.
- _Kiracı_ _Varsayılan Coğrafyası__, Yerel Bölge Coğrafyası'na_ dahil edilen ülkelerden biri olmalıdır
  
Coğrafi ve kanal kullanılabilirliği kullanılabilir olarak güncelleştirilir.

Müşterilerin, ADR iş yükleri için veri yerleşimi alabilmesi için kiracının ADR eklenti lisansıyla yukarıdaki ücretli kullanıcıların %100'ünün kapsanması gerekir.

### <a name="mixedhybrid-tenants"></a>Karma/Karma Kiracılar:

Müşteri, aboneliğinde hem Ticari/Kamu Sektörü (örneğin, E3, E5) **hem** de Eğitim (örneğin, A1, A3 vb.) lisansları dahil olmak üzere birden çok lisans türüne sahipse "karma" veya "karma" olarak tanımlanır.

Karma/Karma müşteriler, Microsoft 365 SKU'larının yalnızca ücretli kısmı için tam ADR eklentisi satın alma haklarına sahiptir ve ücretsiz abonelik türlerini kapsamak zorunda değildir. Ancak ücretli eğitim koltuklarını ADR (Microsoft 365 A3/A5, Office 365 A3/A5) ile karşılamaları gerekir.

## <a name="data-migration-management"></a>Veri Geçişi Yönetimi

Bir müşterinin Gelişmiş Data Residency özelliği kapsamındaki tüm kiracı verileri uygun _Yerel Bölge Coğrafyası'nda_ bekleyen konumda depolanmadıysa _Yerel Bölge Coğrafyası'na_ veri geçişi gerekir.  Bir müşterinin Gelişmiş Data Residency özelliği kapsamındaki tüm kiracı verileri uygun _Yerel Bölge Coğrafyası'nda_ bekleyen konumda depolanıyorsa _, Yerel Bölge Coğrafyası'na_ veri geçişi gerekmez.

### <a name="starting-data-migration"></a>Veri Geçişi Başlatılıyor

Müşteri Gelişmiş Data Residency lisanslarını aldıktan sonra, gerekirse müşterinin veri geçişinin başlaması için hazır olduğunu belirtmesi gerekir. Müşteri yöneticisi, kiracınızın veri geçişi için hazır olduğunu haber vermek için Ayarlar -> Kuruluş Ayarları -> Kuruluş Profili alanındaki Microsoft 365 Yönetici Konsolu'nun Veri Konumu bölümünü ziyaret eder. Müşteri yöneticisi burada bekleyen verilerinin geçerli konumunu ve müşteri verilerinin geçirileceği _Yerel Bölge Coğrafyasını_ görebilir. Lütfen Unutmayın: Müşteri yöneticisi bu görevi yürütene kadar veri geçişi başlamaz. Ayrıca, bu belgenin başka bir yerinde açıklanan geçiş beklentisi, bu görev müşteri yöneticisi tarafından yürütülene kadar izlenmemeye başlar.

Müşteri sinyali alındıktan sonra, kabul tarihi ve hedef tamamlanma tarihi sağlanır.

Tamamlandıktan sonra İleti Merkezi'ne gönderilen bildirime ek olarak, veri geçişi gerektiren her iş yükü tamamlandıktan sonra Microsoft 365 Yönetici Konsolu'ndaki Veri Konumu bölümü de güncelleştirilir.

### <a name="migration-expectations"></a>Geçiş Beklentileri

Microsoft, gelişmiş Data Residency eklenti müşteri geçişini, müşteri yöneticisinin geçiş için hazır olduğunu belirten on iki (12) ay içinde tamamlamayı denemek için makul çabayı gösterecektir. Ancak Microsoft, tüm müşteriler için bu zaman çerçevesi içinde geçişi tamamlayamayabilir. Örneğin, daha büyük veya daha karmaşık müşteriler veya Microsoft'un denetimi dışındaki durumlar, geçişi tamamlamak için ek süre gerektirebilir. Gelişmiş Data Residency eklenti müşterileri, kiracıları için eski Taşıma Programı geçiş seçeneğine göre öncelikli geçiş hizmetleri de alır. Bu geçiş beklentileri tüm ADR EDU müşterileri için de geçerlidir. Gelişmiş Data Residency özelliğine sahip olmayan bir veri geçişi için eski Taşıma Programı'nı kullanan müşteriler bunun yerine [Eski Taşıma Programı Geçiş Beklentileri'ni](m365-dr-legacy-move-program.md#migration-expectations) izler.

Veri taşıma, son kullanıcılar üzerinde en az etkiye sahip bir arka uç hizmeti işlemidir. Kullanılabilirlik için [Microsoft Online Services Hizmet Düzeyi Sözleşmesi'ne (SLA)](https://go.microsoft.com/fwlink/p/?LinkId=523897) bağlıyız, dolayısıyla taşıma sırasında müşterilerin hazırlaması veya izlemesi gereken hiçbir şey yoktur. Gerekirse herhangi bir hizmet bakımı bildirimi yapılır.

Geçiş işlemi sırasında Microsoft, adres defteri verilerinizi geçici olarak şifrelenmiş ve yalnızca iş sürekliliği ve olağanüstü durum kurtarma işlemlerini (BCDR) desteklemek için kullanılan Microsoft genel kaynaklarına kopyalar. Microsoft posta kutusu verilerinin taşınmasını tamamladıktan sonra, Microsoft bu geçici verileri genel kaynaklardan siler. Microsoft düzenli olarak küresel ve bölgesel kaynaklara yatırım yapmaya devam ediyor. Microsoft, 2023 takvim yılında, geçiş işlemi sırasında BCDR amacıyla bölgesel kaynakları kullanmayı planlıyor.

### <a name="during-and-after-your-migration"></a>Geçişiniz Sırasında ve Sonrasında

Veri taşıma, son kullanıcılar üzerinde herhangi bir etki olması durumunda en düşük düzeyde olan bir arka uç işlemidir. Microsoft kiracınız için her hizmeti ve ilişkili müşteri verilerini ilgili coğrafyaya taşırken hiçbir eylem gerekmez.

> [!NOTE]
> Taşımalar her hizmet için farklı zamanlarda gerçekleşir. Sonuç olarak, her hizmetin farklı zamanlarda gerçekleşen azaltılmış işlevselliği hakkında aşağıda açıklananları görürsünüz.

Her iş yükü hizmeti için taşıma tamamlandığında onay için Microsoft 365 İleti Merkezi'ni izleyin.

### <a name="impact-on-end-users-and-workloads"></a>Son Kullanıcılar ve İş Yükleri Üzerindeki Etkisi

Veri taşıma, son kullanıcılar üzerinde en az etkiye sahip bir arka uç hizmeti işlemidir. Etkilenebilen özellikler, Verilerinizi taşıma sırasında ve sonrasında sayfasında listelenir. Kullanılabilirlik için [Microsoft Online Services Hizmet Düzeyi Sözleşmesi'ne (SLA)](https://go.microsoft.com/fwlink/p/?LinkId=523897) bağlıyız, dolayısıyla taşıma sırasında müşterilerin hazırlaması veya izlemesi gereken hiçbir şey yoktur. Gerekirse herhangi bir hizmet bakımı bildirimi yapılır.

### <a name="features-impacted"></a>Etkilenen Özellikler

Müşterilerin tipik bir E3 veya E5 lisansına kaydolup kullandığı birçok iş yükünde kullanılabilen yüzlerce hizmetin karmaşık yapısı nedeniyle, müşteri verilerinin bir veri merkezinden diğerine geçirilmesi, müşterilerin kullandığı bazı hizmetlerin küçük kesintilere ve/veya geçici olarak kullanılamamasına neden olabilir. Daha fazla bilgi için [İş Yükü Data Residency Özellikleri bölümündeki](m365-dr-workload-exo.md) her iş yükünün geçiş bölümlerine bakın.

### <a name="status-notification"></a>Durum Bildirimi

Veri geçişi gerektiren müşteriler, her iş yükü veri geçişini tamamladıkça güncelleştirmelerin sağlanması için İleti Merkezi'ni izleyebilir. Microsoft 365 Yönetici Konsolu'ndaki Veri Konumu bölümüne, bir iş yükünün geçişini tamamlamış olup olmadığını görmek için de başvurulabilir.
Geçişlerin çalışma şekli gereği, geçişin tamamlanmasına ne kadar yakın olabileceğini belirtmek için ayrıntılı bir durum sağlanmış değildir.

### <a name="faq"></a>SSS

#### <a name="how-do-enterprise-customers-purchase-the-microsoft-365-advanced-data-residency-add-on"></a>Kurumsal müşteriler Microsoft 365 Gelişmiş Data Residency eklentisini nasıl satın alır?
<details><summary>Genişletmek için tıklayın</summary>

Uygun kurumsal müşteriler, Gelişmiş Data Residency eklentisi satın almayı kolaylaştırmak için Microsoft hesabı ekibine veya Kurumsal Anlaşma lisanslama iş ortağına başvurmalıdır. Web Direct müşterileri çevrimiçi hesapları aracılığıyla satın almalıdır.
</details>

#### <a name="what-does-the-launch-of-adr-mean-for-the-move-program"></a>Taşıma Programı için ADR'nin başlatılması ne anlama gelir?
<details><summary>Genişletmek için tıklayın</summary>

Gelişmiş Data Residency ve Taşıma Programı çalışmaları sınırlı bir süre boyunca aynı anda mevcut olacak ve farklı müşteri taahhütlerine sahip olacaktır. Taşıma Programı Exchange Online, SharePoint Online, OneDrive İş ve Microsoft Teams ile sınırlıdır. ADR, bunları ve daha fazla iş yükünü içerir.  Move programı Katar yerel veri merkezinin kullanıma sunulmasıyla sonlandırıldı ve gelecekteki yerel veri merkezlerinde kullanılamayacak.  Gelişmiş Data Residency müşterileri, Taşıma Programı müşterilerine göre öncelikli geçiş hizmetleri alır. Daha fazla ayrıntı için Geçiş Beklentisi bölümüne bakın.
</details>

#### <a name="how-can-i-move-my-data-to-my-country-with-advanced-data-residency-what-does-the-process-look-like"></a>Gelişmiş Data Residency ile verilerimi ülkeme nasıl taşıyabilirim? İşlem nasıl görünüyor?
<details><summary>Genişletmek için tıklayın</summary>

İlk adım, ADR SKU'su satın almaktır ve [ADR Uygunluğu](advanced-data-residency.md#eligibility) konusuna bakın.  ADR'yi satın aldıktan sonra, satın alma onayının ana hatlarını içeren İleti Merkezi (kiracı yönetim merkezinde) aracılığıyla bir bildirim alırsınız.  Geçişlere başlamaya hazır olduğunuzu onayladıktan sonra, yukarıda listelenen iş yükleriyle ilgili olarak tüm müşteri bekleyen verilerinizi geçirmeye yönelik 12 aylık beklenti başlar. Buradan müşteri verilerinin geçişi yapılan tüm iş yükleri, kiracı yöneticisine İleti Merkezi aracılığıyla bildirim sağlar (biri geçiş işleminin başında ve sonunda olmak üzere iki ileti).
</details>

## <a name="related-articles"></a>İlgili makaleler

[Eski Taşıma Programı](m365-dr-legacy-move-program.md)
  
[Microsoft Dynamics CRM Online için yeni veri merkezi coğrafi bölgeleri](/power-platform/admin/new-datacenter-regions?branch=main)
  
[Bölgeye göre Azure hizmetleri](https://azure.microsoft.com/regions/)

[Microsoft 365 Multi-Geo özellikli kiracıda Teams deneyimi](/microsoftteams/teams-experience-o365odb-spo-multi-geo?branch=main)
