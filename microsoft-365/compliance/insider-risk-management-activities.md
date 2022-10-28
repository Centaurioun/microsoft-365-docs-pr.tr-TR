---
title: Insider risk yönetimi etkinliklerini araştırma
description: Microsoft Purview'da insider risk yönetimi etkinliklerini araştırma hakkında bilgi edinin
keywords: Microsoft 365, Microsoft Purview, insider riski, risk yönetimi, uyumluluk
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- tier1
- purview-compliance
ms.custom: admindeeplinkCOMPLIANCE
ms.openlocfilehash: 540d7bd367f32399004b276ee9d7c92bc70b70a3
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2022
ms.locfileid: "68770315"
---
# <a name="investigate-insider-risk-management-activities"></a>Insider risk yönetimi etkinliklerini araştırma

>[!IMPORTANT]
>Microsoft Purview İçeriden Risk Yönetimi IP hırsızlığı, veri sızıntısı ve güvenlik ihlalleri gibi olası kötü amaçlı veya yanlışlıkla insider risklerini belirlemek için çeşitli sinyalleri ilişkilendirmektedir. Insider risk yönetimi, müşterilerin güvenlik ve uyumluluğu yönetmek için ilkeler oluşturmasına olanak tanır. Tasarım gereği gizlilikle oluşturulan kullanıcılar varsayılan olarak takma ad kullanır ve kullanıcı düzeyinde gizlilik sağlamaya yardımcı olmak için rol tabanlı erişim denetimleri ve denetim günlükleri kullanılır.

Riskli olabilecek kullanıcı etkinliklerini araştırmak, kuruluşunuz için iç riskleri en aza indirmenin önemli bir ilk adımıdır. Bu riskler, iç risk yönetimi ilkelerinden uyarı oluşturan etkinlikler olabilir. Bunlar, ilkeler tarafından algılanan uyumlulukla ilgili etkinliklerden kaynaklanan riskler de olabilir, ancak kullanıcılar için anında şirket içi risk yönetimi uyarıları oluşturmaz. **Kullanıcı etkinlik raporlarını (önizleme)** veya **Uyarı panosunu** kullanarak bu tür etkinlikleri araştırabilirsiniz.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="user-activity-reports"></a>Kullanıcı etkinliği raporları

Kullanıcı etkinliği raporları, bu etkinlikleri geçici veya açık bir şekilde bir iç risk yönetimi ilkesine atamak zorunda kalmadan riskli olabilecek etkinlikleri (belirli kullanıcılar ve tanımlı bir zaman aralığı için) incelemenize olanak tanır. Çoğu şirket içi risk yönetimi senaryosunda kullanıcılar ilkelerde açıkça tanımlanır ve ilke uyarıları (olayları tetiklemeye bağlı olarak) ve etkinliklerle ilişkili risk puanları olabilir. Ancak bazı senaryolarda, bir ilkede açıkça tanımlanmayan kullanıcıların etkinliklerini incelemek isteyebilirsiniz. Bu etkinlikler, kullanıcı ve riskli olabilecek etkinlikler hakkında bir ipucu aldığınız kullanıcılar veya genellikle bir iç risk yönetimi ilkesine atanma ihtiyacı olmayan kullanıcılara yönelik olabilir.

Insider risk yönetimi **Ayarları** sayfasında göstergeleri yapılandırdıktan sonra, seçilen göstergelerle ilişkili riskli olabilecek etkinlikler için kullanıcı etkinliği algılanır. Bu yapılandırma, kullanıcılar için algılanan tüm etkinliklerin bir tetikleyici olayı olup olmadığına veya uyarı oluştursa bile gözden geçirilebilir olduğu anlamına gelir. Raporlar kullanıcı başına oluşturulur ve özel 90 günlük bir süre için tüm etkinlikleri içerebilir. Aynı kullanıcı için birden çok rapor desteklenmez.

Olası riskli etkinlikleri inceledikten sonra, araştırmacılar tek tek kullanıcının etkinliklerini zararsız olarak kapatabilir. Ayrıca raporun bağlantısını diğer araştırmacılarla paylaşabilir veya e-postayla gönderebilir ya da kullanıcıları (geçici veya açık olarak) bir şirket içi risk yönetimi ilkesine atamayı seçebilirler. **Kullanıcı etkinlik raporları** sayfasını görüntülemek için kullanıcıların *Insider Risk Yönetimi Araştırmacıları* rol grubuna atanması gerekir.  

![Insider risk yönetimi kullanıcı etkinliği raporuna genel bakış.](../media/insider-risk-user-activity-report-overview.png)

Başlamak için, insider risk yönetimine **Genel Bakış** sayfasındaki **Kullanıcı etkinliğini araştır** bölümünde **Raporları yönet'i** seçin. 

Bir kullanıcının etkinliklerini görüntülemek için önce **Kullanıcı etkinliği raporu oluştur'u** seçin ve **Yeni kullanıcı etkinliği raporu** bölmesinde aşağıdaki alanları tamamlayın:

- **Kullanıcı**: Bir kullanıcıyı ada veya e-posta adresine göre arayın.
- **Başlangıç tarihi**: Kullanıcı etkinliklerinin başlangıç tarihini seçmek için takvim denetimini kullanın.
- **Bitiş tarihi**: Kullanıcı etkinliklerinin bitiş tarihini seçmek için takvim denetimini kullanın. Seçilen bitiş tarihi, seçilen başlangıç tarihinden sonra iki günden büyük ve seçili başlangıç tarihinden itibaren 90 günden uzun olmamalıdır.
 
Yeni raporların gözden geçirilmesi genellikle 10 saat kadar sürer. Rapor hazır olduğunda, Kullanıcı etkinliği raporu sayfasındaki **Durum** sütununda *Rapor hazır* ifadesini görürsünüz. Ayrıntılı raporu görüntülemek için kullanıcıyı seçin:

![Insider risk yönetimi kullanıcı etkinlik raporu](../media/insider-risk-user-activity-report.png)

Seçili kullanıcının **Kullanıcı etkinliği raporu** **Kullanıcı etkinliği**, **Etkinlik gezgini** ve **Adli kanıt (önizleme)** sekmelerini içerir:

- **Kullanıcı etkinliği**: Riskli olabilecek etkinlikleri araştırmak ve dizilerde gerçekleşen olası ilgili etkinlikleri görüntülemek için bu grafik görünümünü kullanın. Bu sekme, tüm etkinliklerin geçmiş zaman çizelgesi, etkinlik ayrıntıları, kullanıcı için geçerli risk puanı, risk olaylarının sırası ve araştırma çalışmalarına yardımcı olacak filtreleme denetimleri de dahil olmak üzere bir servis talebinin hızlı bir şekilde gözden geçirilmesini sağlayacak şekilde yapılandırılmıştır.
- **Etkinlik gezgini**: Bu sekme, risk araştırmacılarına etkinlikler hakkında ayrıntılı bilgi sağlayan kapsamlı bir analiz aracı sağlar. Etkinlik gezgini ile gözden geçirenler algılanan riskli etkinliğin zaman çizelgesini hızla gözden geçirebilir ve uyarılarla ilişkili tüm riskli etkinlikleri tanımlayıp filtreleyebilir. Etkinlik gezginini kullanma hakkında daha fazla bilgi edinmek için bu makalenin devamında yer alan *Etkinlik gezgini* bölümüne bakın.

## <a name="alert-dashboard"></a>Uyarı panosu

Insider risk yönetimi uyarıları, insider risk yönetimi ilkelerinde tanımlanan risk göstergeleri tarafından otomatik olarak oluşturulur. Bu uyarılar, uyumluluk analistlerine ve araştırmacılara geçerli risk durumunun tamamen görünümünü sağlar ve kuruluşunuzun bulunan olası riskleri önceliklendirmesine ve bunlara yönelik eylemler gerçekleştirmesine olanak sağlar. Varsayılan olarak, ilkeler belirli miktarda düşük, orta ve yüksek önem derecesinde uyarı oluşturur, ancak uyarı hacmini gereksinimlerinize uyacak şekilde [artırabilir veya azaltabilirsiniz](insider-risk-management-settings.md#alert-volume) . Ayrıca, ilke oluşturma aracıyla yeni bir ilke oluştururken [ilke göstergeleri için uyarı eşiğini](insider-risk-management-settings.md#indicator-level-settings-preview) yapılandırabilirsiniz.

Uyarıların riskli etkinlik için ayrıntıları, bağlamı ve ilgili içeriği nasıl sağladığına ve araştırma sürecinizi nasıl daha etkili hale getirebilirsiniz? genel bir bakış için [Insider Risk Yönetimi Uyarıları Önceliklendirme Deneyimi videosunu](https://www.youtube.com/watch?v=KgmpxBLJLPI) inceleyin.

Insider risk **Uyarısı panosu** , insider risk ilkeleri tarafından oluşturulan uyarıları görüntülemenize ve bunlar üzerinde işlem yapmanızı sağlar. Her rapor pencere öğesi son 30 güne ilişkin bilgileri görüntüler.

- **Gözden geçirilmesi gereken toplam uyarı** sayısı: Uyarı önem derecesine göre döküm de dahil olmak üzere gözden geçirme ve önceliklendirme gerektiren toplam uyarı sayısı listelenir.
- **Son 30 gün içindeki açık uyarılar**: İlke tarafından oluşturulan uyarıların toplam sayısı son 30 gün içinde eşleşir ve yüksek, orta ve düşük uyarı önem derecelerine göre sıralanır.
- **Uyarıları çözümlemek için ortalama süre**: Yararlı uyarı istatistiklerinin özeti:
  - Saat, gün veya ay cinsinden listelenen yüksek önem derecesi uyarılarını çözümlemek için ortalama süre.
  - Saat, gün veya ay cinsinden listelenen orta önem derecesi uyarılarını çözümlemek için ortalama süre.
  - Düşük önem derecesi uyarılarını çözümlemek için saat, gün veya ay cinsinden listelenen ortalama süre.

![Insider risk yönetimi uyarı panosu](../media/insider-risk-alerts-dashboard.png)

> [!NOTE]
> Insider risk yönetimi, risk araştırma ve gözden geçirme deneyiminizi korumaya ve iyileştirmeye yardımcı olmak için yerleşik uyarı azaltmayı kullanır. Bu azaltma, yanlış yapılandırılmış veri bağlayıcıları veya veri kaybı önleme ilkeleri gibi ilke uyarılarının aşırı yüklenmesine neden olabilecek sorunlara karşı koruma sağlar. Sonuç olarak, bir kullanıcı için yeni uyarıların görüntülenmesinde gecikme olabilir.

## <a name="alert-status-and-severity"></a>Uyarı durumu ve önem derecesi

Uyarıları aşağıdaki durumlardan birinde önceliklendirme yapabilirsiniz:

- **Onaylandı**: Bir uyarı onaylandı ve yeni veya mevcut bir servis talebine atandı.
- **Kapatıldı**: Önceliklendirme işleminde iyi huylu olarak kapatılan bir uyarı. Uyarının kapatılma nedenini sağlayabilir ve gelecekte başvurmak veya diğer gözden geçirenler için ek bağlam sağlamak üzere kullanıcının uyarı geçmişine notlar ekleyebilirsiniz. Nedenler beklenen etkinliklerden, etkili olmayan olaylara, yalnızca kullanıcı için uyarı etkinliklerinin sayısını azaltmaya veya uyarı notları ile ilgili bir nedene kadar değişebilir. Neden sınıflandırma seçenekleri *arasında Bu kullanıcı için Etkinlik bekleniyor*, *Etkinlik daha fazla araştırma yapmamı gerektirecek kadar etkili* ve *Bu kullanıcı için uyarılar çok fazla etkinlik içeriyor*.
- **Gözden geçirilmesi gerekiyor**: Önceliklendirme eylemlerinin henüz yapılmadığı yeni bir uyarı.
- **Çözüldü**: Kapatılan ve çözülen bir servis talebinin parçası olan bir uyarı.

Uyarı riski puanları, çeşitli risk etkinliği göstergelerinden otomatik olarak hesaplanır. Bu göstergeler risk etkinliğinin türünü, etkinlik oluşumunun sayısını ve sıklığını, kullanıcıların risk etkinliğinin geçmişini ve riskli olabilecek etkinliğin ciddiyetini artırabilecek etkinlik risklerinin eklenmesini içerir. Uyarı risk puanı, her uyarı için bir risk önem düzeyinin program aracılığıyla atanabilmesini sağlar ve özelleştirilemiyor. Uyarılar denenmemiş olarak kalırsa ve risk etkinlikleri uyarıya tahakkuk etmeye devam ederse, risk önem düzeyi artabilir. Risk analistleri ve araştırmacıları uyarı risk önem derecesini kullanarak uyarıları kuruluşunuzun risk ilkelerine ve standartlarına uygun olarak önceliklendirmeye yardımcı olabilir.

Uyarı riski önem düzeyleri şunlardır:

- **Yüksek önem derecesi**: Uyarı için riskli olabilecek etkinlikler ve göstergeler önemli bir risk oluşturur. İlgili risk etkinlikleri ciddidir, tekrar eder ve diğer önemli risk faktörleriyle güçlü bir şekilde çekirdeklenir.
- **Orta önem derecesi**: Uyarının riskli olabilecek etkinlikleri ve göstergeleri orta düzeyde bir risk oluşturur. İlişkili risk etkinlikleri ılımlı, sıktır ve diğer risk faktörleriyle bir bağıntıya sahiptir.
- **Düşük önem derecesi**: Uyarı için riskli olabilecek etkinlikler ve göstergeler küçük bir risk oluşturur. İlişkili risk etkinlikleri küçük, daha seyrek ve diğer önemli risk faktörleriyle bağlantılı değildir.

## <a name="filter-alerts-on-the-alert-dashboard"></a>Uyarı panosundaki uyarıları filtreleme

Kuruluşunuzdaki etkin insider risk yönetimi ilkelerinin sayısına ve türüne bağlı olarak, büyük bir uyarı kuyruğunun gözden geçirilmesi zor olabilir. Uyarı filtrelerini kullanmak analistlerin ve araştırmacıların uyarıları çeşitli özniteliklere göre sıralamalarına yardımcı olabilir. 

**Uyarılar panosundaki** uyarıları filtrelemek için **Filtre** denetimini seçin. Uyarıları bir veya daha fazla özniteliğe göre filtreleyebilirsiniz:

- **Durum**: Uyarı listesini filtrelemek için bir veya daha fazla durum değeri seçin. Seçenekler *Onaylandı*, *Kapatıldı*, *Gözden geçirilmesi gerekiyor* ve *Çözümlendi şeklindedir*.
- **Önem derecesi**: Uyarı listesini filtrelemek için bir veya daha fazla uyarı riski önem düzeyi seçin Seçenekler *Yüksek*, *Orta* ve *Düşük'tir*.
- **Algılanan zaman**: Uyarının oluşturulduğu zaman için başlangıç ve bitiş tarihlerini seçin. Bu filtre, başlangıç tarihinde UTC 00:00 ile bitiş tarihinde UTC 00:00 arasında uyarı arar. Belirli bir günün uyarılarını filtrelemek için **Başlangıç tarihi** alanına günün tarihini ve **Bitiş tarihi** alanına da sonraki günün tarihini girin.
- **İlke**: Seçili ilkeler tarafından oluşturulan uyarıları filtrelemek için bir veya daha fazla ilke seçin.
- **Risk faktörleri**: Uyarı listesini filtrelemek için daha fazla risk faktöründen birini seçin. Seçenekler *kümülatif sızdırma etkinlikleri*, *Etkinlikler öncelik içeriğini*, *Sıra etkinlikleri* ve *Etkinlikler izin verilmeyen etki alanlarını içerir*.

## <a name="search-alerts-on-the-alert-dashboard"></a>Uyarı panosunda uyarıları arama

Uyarı adında belirli bir sözcüğü aramak için **Ara** denetimini seçin ve aranacak sözcüğü yazın. Arama sonuçları, aramada tanımlanan sözcüğü içeren tüm ilke uyarılarını görüntüler.

## <a name="dismiss-multiple-alerts-preview"></a>Birden çok uyarıyı kapatma (önizleme)

Analistlerin ve araştırmacıların aynı anda birden çok uyarıyı hemen kapatması için önceliklendirme zamanından tasarruf etmeye yardımcı olabilir. **Uyarıları kapat** komut çubuğu seçeneği, panoda *Gözden geçirme gerekiyor* durumuna sahip bir veya daha fazla uyarı seçmenize ve bu uyarıları önceliklendirme işleminizde uygun şekilde zararsız şekilde hızla kapatmanıza olanak tanır. Aynı anda kapatmak için en fazla 400 uyarı seçebilirsiniz.

Insider risk uyarısını kapatmak için aşağıdaki adımları tamamlayın:

1. [Microsoft Purview uyumluluk portalı](https://compliance.microsoft.com) **Insider risk yönetimi'ne** gidin ve **Uyarılar** sekmesini seçin.
2. **Uyarılar panosunda**, kapatmak istediğiniz *Gözden geçirme gerekiyor* durumuna sahip uyarıyı (veya uyarıları) seçin.
3. Uyarılar komut çubuğunda Uyarıları **kapat'ı** seçin.
4. **Uyarıları kapat** ayrıntıları bölmesinde, seçili uyarılarla ilişkili kullanıcı ve ilke ayrıntılarını gözden geçirebilirsiniz.
5. Uyarıları zararsız olarak çözümlemek için Uyarıları **kapat'ı** seçin veya uyarıları kapatmadan ayrıntılar bölmesini kapatmak için **İptal'i** seçin.

## <a name="triage-alerts"></a>Uyarıları önceliklendirme

Insider risk uyarısını önceliklendirmek için aşağıdaki adımları tamamlayın:

1. [Microsoft Purview uyumluluk portalı](https://compliance.microsoft.com) **Insider risk yönetimi'ne** gidin ve **Uyarılar** sekmesini seçin.
2. **Uyarılar panosunda** önceliklendirmek istediğiniz uyarıyı seçin.
3. **Uyarı ayrıntıları** sayfasında uyarı hakkındaki bilgileri gözden geçirebilirsiniz. Uyarıyı onaylayabilir ve yeni bir servis talebi oluşturabilir, uyarıyı onaylayabilir ve mevcut bir servis talebine ekleyebilir veya uyarıyı kapatabilirsiniz. Bu sayfa ayrıca uyarının geçerli durumunu ve Uyarı riski önem düzeyinin Yüksek, Orta veya Düşük olarak listelendiğini de içerir. Uyarı önceliklendirilmezse önem düzeyi zaman içinde artabilir veya azalabilir.

Uyarı hakkında daha fazla bilgi için Uyarı ayrıntısı sayfasındaki aşağıdaki bölümleri ve sekmeleri kullanın:

### <a name="headersummary-section"></a>Üst Bilgi/Özet bölümü

Bu bölüm, kullanıcı ve uyarı hakkında genel bilgiler içerir. Bu bilgiler, kullanıcı için uyarıya dahil edilen algılanan risk yönetimi etkinliği hakkında ayrıntılı bilgiler gözden geçirilirken bağlam için kullanılabilir:

- **Bu uyarıyı oluşturan etkinlik**: Uyarının oluşturulmasına neden olan etkinlik değerlendirme döneminde riskli olabilecek en yüksek etkinlik ve ilke eşleşmesini görüntüler.
- **Tetikleyici olay**: İlkeden kullanıcının etkinliğine risk puanları atamaya başlamasını isteyen en son tetikleyici olayı görüntüler. *Riskli kullanıcılar tarafından yapılan Veri sızıntıları veya riskli kullanıcı* *ilkeleri tarafından güvenlik ilkesi ihlalleri* için [iletişim uyumluluğuyla tümleştirmeyi](/microsoft-365/compliance/communication-compliance-policies#integration-with-insider-risk-management-preview) yapılandırdıysanız, bu uyarılar için tetikleme olayının kapsamı iletişim uyumluluk etkinliği olarak belirlenmiştir.
- **Kullanıcı profili**: Uyarıya atanan kullanıcı hakkında genel bilgileri görüntüler. Anonimleştirme etkinse kullanıcı adı, e-posta adresi, diğer ad ve kuruluş alanları anonimleştirilir.
- **Kullanıcı uyarı geçmişi**: Son 30 güne ait kullanıcının uyarılarının listesini görüntüler. Kullanıcının uyarı geçmişinin tamamını görüntülemek için bir bağlantı içerir.

Yalnızca [öncelik içeriğini](/microsoft-365/compliance/insider-risk-management-policies#prioritize-content-in-policies) içeren etkinlikler kapsamındaki ilkelerden oluşturulan uyarılar, bu bölümdeki *bu uyarı bildirimi için Yalnızca öncelikli içeriğe sahip etkinlik puanlandı* öğesini içerir.

### <a name="all-risk-factors"></a>Tüm risk faktörleri

Bu sekme, kullanıcının uyarı etkinliği için risk faktörlerinin özetini açar. Risk faktörleri, gözden geçirme sırasında bu kullanıcının risk yönetimi etkinliğinin ne kadar riskli olduğunu belirlemenize yardımcı olabilir. Risk faktörleri şunlara ilişkin özetleri içerir:

- **En çok sızdırma etkinlikleri**: Uyarı için en yüksek sayıda veya olayla sızdırma etkinliklerini görüntüler.
- **Kümülatif sızdırma etkinlikleri**: Kümülatif sızdırma etkinlikleriyle ilişkili olayları görüntüler.
- **Etkinlik dizileri**: Risk dizileriyle ilişkili algılanan riskli etkinlikleri görüntüler.
- **Bu kullanıcı için olağan dışı etkinlik**: Kullanıcı için, olağan dışı ve tipik etkinliklerinden ayrıldıkları için riskli olduğu düşünülen belirli etkinlikleri görüntüler.
- **Öncelik içeriği: Öncelikli içerikle** ilişkili riskli olabilecek etkinlikleri görüntüler.
- **İzin verilmeyen etki alanları: İzin verilmeyen etki alanlarıyla** ilişkili olaylar için riskli olabilecek etkinlikleri görüntüler.
- **Sistem durumu kaydı erişimi: Sistem** durumu kayıtlarına erişimle ilişkili olaylar için riskli olabilecek etkinlikleri görüntüler.
- **Riskli tarayıcı kullanımı**: Uygunsuz olabilecek web sitelerine göz atmayla ilişkili olaylar için riskli olabilecek etkinlikleri görüntüler.

Bu filtrelerle, yalnızca yukarıdaki risk faktörlerine sahip uyarılar görürsünüz, ancak uyarı oluşturan etkinlik bu kategorilerden hiçbirine girmeyebilir. Örneğin, kullanıcı bir USB cihazına dosya kopyaladığından, sıra etkinliklerini içeren bir uyarı oluşturulmuş olabilir.

### <a name="content-detected"></a>İçerik algılandı

**Tüm risk faktörleri** sekmesindeki bölüm, uyarının risk etkinlikleriyle ilişkili içeriği içerir ve etkinlik olaylarını önemli alanlara göre özetler. Etkinlik bağlantısı seçildiğinde Etkinlik gezgini açılır ve etkinlik hakkında daha fazla ayrıntı görüntülenir.

### <a name="activity-explorer"></a>Etkinlik gezgini

Bu sekme Etkinlik gezginini açar. Daha fazla bilgi için bu makaledeki Etkinlik gezgini bölümüne bakın.

### <a name="user-activity"></a>Kullanıcı etkinliği

**Kullanıcı etkinlik** grafiği, iç risk analizi ve iç risk yönetimi çözümündeki uyarılar ve durumlar için araştırma için en güçlü araçlardan biridir. Bu sekme, bir kullanıcının tüm uyarıların geçmiş zaman çizelgesi, uyarı ayrıntıları, kullanıcı için geçerli risk puanı ve risk olaylarının sırası dahil olmak üzere tüm etkinliklerin hızlı bir şekilde gözden geçirilmesini sağlayacak şekilde yapılandırılmıştır.

![Insider risk yönetimi kullanıcı etkinliği](../media/insider-risk-user-activities.png)

1. **Zaman filtreleri**: Varsayılan olarak, riskli olabilecek etkinliklerin son üç ayı Kullanıcı etkinlik grafiğinde görüntülenir. Kabarcık grafiğinde *6 Ay*, *3 Ay* veya *1 Ay* sekmelerini seçerek grafik görünümünü kolayca filtreleyebilirsiniz.
2. **Risk uyarısı etkinliği ve ayrıntıları**: Riskli olabilecek etkinlikler, Kullanıcı etkinlik grafiğinde görsel olarak renkli kabarcıklar olarak görüntülenir. Kabarcıklar farklı risk kategorileri ve için oluşturulur. Riskli olabilecek her etkinliğin ayrıntılarını görüntülemek için bir kabarcık seçin. Ayrıntılar şunlardır:
    - Risk etkinliğinin **tarihi**.
    - **Risk etkinliği kategorisi**. Örneğin, Email ve *sharepoint online'dan indirilen* *dosya veya kuruluş dışına gönderilen ekleri* içerir.
    - Uyarı için **risk puanı**. Bu puan, uyarı riski önem düzeyi için sayısal puandır.
    - Uyarıyla ilişkili olay sayısı. Risk etkinliğiyle ilişkili her dosyaya veya e-postaya bağlantılar da sağlanır.
3. **Filtreler ve sıralama (önizleme)**:
    - **Risk kategorisi**: Etkinlikleri aşağıdaki risk kategorilerine göre filtreleyin: *Risk puanı 15 > olan etkinlikler (sıralı olmadığı sürece)* ve *Sıralı etkinlikler*.
    - **Etkinlik Türü**: Etkinlikleri şu türlere göre filtreleyin: *Erişim*, *Silme*, *Toplama*, *Sızdırma*, *Sızma*, *Gizleme* ve *Güvenlik*.
    - **Sıralama ölçütü**: Riskli olabilecek etkinliklerin zaman çizelgesini *Gerçekleşen Tarihe* veya *Risk puanına* göre listeleyin.
4. **Risk sırası**: Riskli olabilecek etkinliklerin kronolojik sırası, risk araştırmasının önemli bir yönüdür ve bu ilgili etkinliklerin tanımlanması, kuruluşunuz için genel riski değerlendirmenin önemli bir parçasıdır. İlgili uyarı etkinlikleri, bu etkinliklerin daha büyük bir risk alanıyla ilişkilendirildiğini vurgulamak için bağlantı çizgileri ile görüntülenir. Diziler, bu görünümde sıranın risk puanına göre sıra etkinliklerinin üzerine yerleştirilmiş bir simgeyle de tanımlanır. Bu diziyle ilişkili riskli etkinliğin tarihini ve saatini görmek için simgenin üzerine gelin. Etkinliklerin bu görünümü, araştırmacıların yalıtılmış veya tek seferlik olaylar olarak görülebilecek risk etkinlikleri için kelimenin tam anlamıyla "noktaları birbirine bağlamalarına" yardımcı olabilir. İlişkili tüm risk etkinliklerinin ayrıntılarını görüntülemek için dizideki simgeyi veya herhangi bir baloncuğu seçin. Ayrıntılar şunlardır:

    - **Sıranın adı** .
    - Sıranın **Tarih** veya **Tarih aralığı**.
    - Sıra için **risk puanı**. Bu puan, dizideki ilgili her etkinlik için birleştirilmiş uyarı riski önem derecesi düzeylerinin dizisinin sayısal puanıdır.
    - **Dizideki her uyarıyla ilişkili olay sayısı**. Riskli olabilecek her etkinlikle ilişkili her dosyaya veya e-postaya bağlantılar da sağlanır.
    - **Etkinlikleri sırayla gösterin**. Sırayı kabarcık grafiğinde vurgu çizgisi olarak görüntüler ve uyarı ayrıntılarını genişleterek tüm ilgili uyarıları dizide görüntüler.

5. **Risk etkinliği göstergesi**: Kullanıcı etkinlik grafiğinin alt kısmında, renk kodlu gösterge her uyarı için risk kategorisini hızla belirlemenize yardımcı olur.
6. **Risk etkinliği kronolojisi**: Servis talebiyle ilişkili tüm risk uyarılarının tam kronolojisi, ilgili uyarı baloncuğunda sağlanan tüm ayrıntılar da dahil olmak üzere listelenir.
7. **Büyük/küçük harf eylemleri**: Servis talebini çözümleme seçenekleri, servis talebi eylem araç çubuğundadır. Bir servis talebini görüntülerken bir olayı çözebilir, kullanıcıya e-posta bildirimi gönderebilir veya bir veri ya da kullanıcı araştırması için olayı yükseltebilirsiniz.

## <a name="activity-explorer"></a>Etkinlik gezgini

> [!NOTE]
> Etkinlik gezgini, kuruluşunuzda bu özellik kullanıma sunulduktan sonra olayları tetikleyen kullanıcılar için uyarı yönetimi alanında kullanılabilir.

Etkinlik gezgini, risk araştırmacılarına ve analistlerine uyarılar hakkında ayrıntılı bilgi sağlayan kapsamlı bir analiz aracı sağlar. Etkinlik gezgini ile gözden geçirenler, riskli olabilecek etkinliklerin zaman çizelgesini hızla gözden geçirebilir ve uyarılarla ilişkili tüm risk etkinliklerini tanımlayıp filtreleyebilir. 

Sütun bilgileri için Etkinlik gezginindeki uyarıları filtrelemek için Filtre denetimini seçin. Uyarıları, uyarının ayrıntılar bölmesinde listelenen bir veya daha fazla özniteliğe göre filtreleyebilirsiniz. Etkinlik gezgini, araştırmacıların ve analistlerin panoyu kendileri için en önemli bilgilere odaklamalarına yardımcı olmak için özelleştirilebilir sütunları da destekler.

Aşağıdaki alanlara yönelik etkinlikleri ve içgörüleri görüntülemek ve sıralamak için *Etkinlik kapsamı* ve *Risk içgörü* filtrelerini kullanın.

- **Etkinlik kapsamı filtreleri**: Kullanıcı için puanlanan tüm etkinlikleri filtreler.
  - Bu kullanıcı için tüm puanlanan etkinlikler
  - Bu uyarıda yalnızca puanlanan etkinlik

- **Risk faktörü filtreleri: Risk** puanı atayan tüm ilkeler için geçerli olan risk faktörü etkinliği filtreleri Kapsam içi kullanıcılar için tüm ilkeler için tüm etkinlikleri içerir.
  - Olağan dışı etkinlik
  - Öncelikli içeriğe sahip olayları içerir
  - İzin verilmeyen etki alanına sahip olayları içerir
  - Sıra etkinlikleri
  - Kümülatif sızdırma etkinlikleri
  - Sistem durumu kaydı erişim etkinlikleri
  - Riskli tarayıcı kullanımı

![Insider risk yönetimi etkinlik gezginine genel bakış](../media/insider-risk-activity-explorer.png)

**Etkinlik gezginini** kullanmak için aşağıdaki adımları tamamlayın:

1. [Microsoft Purview uyumluluk portalı](https://compliance.microsoft.com) **Insider risk yönetimi'ne** gidin ve **Uyarılar** sekmesini seçin.
2. **Uyarılar panosunda** önceliklendirmek istediğiniz uyarıyı seçin.
3. **Uyarılar ayrıntı bölmesinde** **Genişletilmiş görünümü aç'ı** seçin.
4. Seçili uyarının sayfasında **Etkinlik gezgini** sekmesini seçin.

Etkinlik gezginindeki etkinlikleri gözden geçirirken araştırmacılar ve analistler belirli bir etkinliği seçip etkinlik ayrıntıları bölmesini açabilir. Bölmede araştırmacıların ve analistlerin uyarı önceliklendirme işlemi sırasında kullanabilecekleri etkinlik hakkında ayrıntılı bilgiler görüntülenir. Ayrıntılı bilgiler uyarı için bağlam sağlayabilir ve uyarıyı tetikleyen risk etkinliğinin tam kapsamını belirlemeye yardımcı olabilir.

Etkinlik zaman çizelgesinden bir etkinliğin olaylarını seçerken, gezginde görüntülenen etkinliklerin sayısı zaman çizelgesinde listelenen etkinlik olaylarının sayısıyla eşleşmeyebilir. Bu farkın neden ortaya çıkabileceğinin örnekleri:

- **Kümülatif sızdırma algılama**: Kümülatif sızdırma algılama olay günlüklerini analiz eder, ancak işlem kümülatif sızdırma riskine benzer etkinliklerin yinelenenleri kaldırmayı içeren bir model uygular. Ayrıca, mevcut ilkenizde veya ayarlarınızda değişiklik yaptıysanız Etkinlik gezgininde görüntülenen riskli olabilecek etkinliklerin sayısında da bir fark olabilir. Örneğin, izin verilen/izin verilmeyen etki alanlarını değiştirirseniz veya bir ilke oluşturulduktan ve riskli olabilecek etkinlik eşleşmeleri oluştuktan sonra yeni dosya türü dışlamaları eklerseniz, ilke veya ayarlar değişmeden önce toplu sızdırma algılama etkinlikleri sonuçlardan farklı olur. Kümülatif sızdırma algılama etkinliği toplamları hesaplama sırasında ilke ve ayarlar yapılandırmasını temel alır ve ilke ve ayarlar değişikliklerinden önceki etkinlikleri içermez
- **Dış alıcılara gönderilen e-postalar: Dış alıcılara** gönderilen e-postalar için riskli olabilecek etkinliklere, gönderilen e-postaların sayısına göre bir risk puanı atanır ve bu da etkinlik olay günlükleriyle eşleşmeyebilir.

![Insider risk yönetimi etkinlik gezgini ayrıntıları.](../media/insider-risk-activity-explorer-details.png)

## <a name="create-a-case-for-an-alert"></a>Uyarı için servis talebi oluşturma

Uyarı gözden geçirilip önceliklendirildikçe riskli olabilecek etkinliği daha fazla araştırmak için yeni bir olay oluşturabilirsiniz. Uyarı için servis talebi oluşturmak için şu adımları izleyin:

1. [Microsoft Purview uyumluluk portalı](https://compliance.microsoft.com) **Insider risk yönetimi'ne** gidin ve **Uyarılar** sekmesini seçin.
2. **Uyarılar panosunda**, onaylamak istediğiniz uyarıyı seçin ve yeni bir servis talebi oluşturun.
3. **Uyarılar ayrıntıları bölmesinde** **Eylemler** > **Uyarıları onayla & olay oluştur'u** seçin.
4. **Uyarıyı onayla ve içeriden risk olayı oluştur** iletişim kutusunda servis talebi için bir ad girin, katkıda bulunan olarak eklenecek kullanıcıları seçin ve uygun şekilde açıklamalar ekleyin. Açıklamalar servis talebine servis talebi notu olarak otomatik olarak eklenir.
5. Yeni bir **servis talebi oluşturmak için Büyük/küçük harf oluştur'u** seçin veya servis talebi oluşturmadan iletişim kutusunu kapatmak için **İptal'i** seçin.

Olay oluşturulduktan sonra, araştırmacılar ve analistler olayı yönetebilir ve üzerinde işlem yapabilir. Daha fazla bilgi için [Insider risk yönetimi olayı](insider-risk-management-cases.md) makalesine bakın.

## <a name="retention-and-item-limits"></a>Bekletme ve öğe sınırları

Insider risk yönetimi uyarıları yaş ilerledikçe, riskli olabilecek etkinlikleri en aza indirmeye yönelik değerleri çoğu kuruluş için azalır. Buna karşılık, etkin servis talepleri ve ilişkili yapıtlar (uyarılar, içgörüler, etkinlikler) kuruluşlar için her zaman değerlidir ve otomatik son kullanma tarihine sahip olmamalıdır. Bu, etkin bir servis talebiyle ilişkilendirilmiş tüm kullanıcılar için etkin durumdaki tüm gelecek uyarıları ve yapıtları içerir.

Sınırlı geçerli değer sağlayan eski öğelerin sayısını en aza indirmeye yardımcı olmak için, insider risk yönetimi uyarıları, durumları ve kullanıcı raporları için aşağıdaki saklama ve sınırlar geçerlidir:

|**Öğe**|**Bekletme/Sınır**|
|:-------|:------------------|
|Gözden geçirme durumu gerekiyor olan uyarılar|Uyarı oluşturma işleminden 120 gün sonra otomatik olarak silindi|
|Etkin durumlar (ve ilişkili yapıtlar)|Süresiz saklama, süresi asla dolmaz|
|Çözümlenen servis talepleri (ve ilişkili yapıtlar)|Servis talebi çözümünden 120 gün sonra otomatik olarak silindi|
|Etkin servis talebi sayısı üst sınırı|100|
|Kullanıcı etkinlikleri raporları|Etkinlik algılamadan 120 gün sonra otomatik olarak silindi|

## <a name="get-help-managing-your-insider-risk-alert-queue"></a>Insider risk uyarı kuyruğunuzu yönetme konusunda yardım alın

Riskli olabilecek insider uyarılarını gözden geçirmek, araştırmak ve üzerinde hareket etmek, kuruluşunuzdaki insider risklerini en aza indirmenin önemli parçalarıdır. Bu risklerin etkisini en aza indirmek için hızla harekete geçmek, kuruluşunuz için zaman, para ve yasal sonuçlardan veya yasal sonuçlardan tasarruf edebilir. Bu düzeltme sürecinde, uyarıları gözden geçirmenin ilk adımı birçok analist ve araştırmacı için en zor görev gibi görünebilir. Koşullarınıza bağlı olarak, riskli olabilecek insider uyarılarına göre hareket ederken bazı küçük engellerle karşılaşabilirsiniz. Aşağıdaki önerileri gözden geçirin ve uyarı gözden geçirme işlemini iyileştirmeyi öğrenin.

### <a name="too-many-alerts-to-review"></a>Gözden geçiremeyecek kadar çok uyarı var

Insider risk yönetimi ilkeleriniz tarafından oluşturulan uyarı sayısından bunalmış olmak sinir bozucu olabilir. Aldığınız uyarı birimi türlerine bağlı olarak, uyarı sayısı basit adımlarla hızlı bir şekilde giderilebilir. Çok fazla geçerli uyarı alıyor olabilirsiniz veya çok fazla eski düşük riskli uyarınız olabilir. Aşağıdaki eylemleri gerçekleştirmeyi göz önünde bulundurun:

- **Insider risk ilkelerinizi ayarlayın: Doğru insider** risk ilkesini seçmek ve yapılandırmak, uyarıların türünü ve hacmini ele almak için en temel yöntemdir. Uygun [ilke şablonuyla](insider-risk-management-policies.md#policy-templates) başlayarak, göreceğiniz risk etkinliklerinin ve uyarıların türlerine odaklanmanıza yardımcı olur. Uyarı hacmini etkileyebilecek diğer faktörler kapsam içi kullanıcı ve grupların boyutu ile [önceliklendirilen içerik ve kanallardır](insider-risk-management-policies.md#prioritize-content-in-policies). Bu alanları kuruluşunuz için en önemli olan alanlara daraltmak için ilkeleri ayarlamayı göz önünde bulundurun.
- **Insider risk ayarlarınızı değiştirme**: Insider risk ayarları, alacağınız birim ve uyarı türlerini etkileyebilecek çok çeşitli yapılandırma seçenekleri içerir. Bunlar [ilke göstergeleri](insider-risk-management-settings.md#indicators), [gösterge eşikleri](insider-risk-management-settings.md#indicator-level-settings-preview) ve [ilke zaman çerçeveleri](insider-risk-management-settings.md#policy-timeframes) için ayarları içerir. Belirli dosya türlerini ve hassas bilgi türlerini dışlamak, ilkeleriniz tarafından etkinlik uyarıları raporlanmadan önce minimum eşikleri tanımlamak ve uyarı birimi yapılandırmasını daha düşük bir ayara değiştirmek için [akıllı algılama](insider-risk-management-settings.md#intelligent-detections) seçeneklerini yapılandırmayı göz önünde bulundurun.
- **Satır içi uyarı özelleştirmesini etkinleştirme (önizleme)**: [Satır içi uyarı özelleştirmesini](/microsoft-365/compliance/insider-risk-management-settings#inline-alert-customization-preview) etkinleştirmek analistlerin ve araştırmacıların uyarıları gözden geçirirken ilkeleri hızla düzenlemesine olanak tanır. Microsoft önerileriyle etkinlik algılama için eşikleri güncelleştirebilir, özel eşikleri yapılandırabilir veya uyarıyı oluşturan etkinlik türünü yoksaymayı seçebilirler. Bu etkin değilse, yalnızca *Insider Risk Yönetimi* rol grubuna atanan kullanıcılar satır içi uyarı özelleştirmesini kullanabilir.
- **Uygun olduğunda uyarıları toplu silme**: Analistlerinizin ve araştırmacılarınızın [aynı anda birden fazla uyarıyı hemen kapatması](insider-risk-management-activities.md#dismiss-multiple-alerts-preview) için önceliklendirme süresinden tasarruf etmeye yardımcı olabilir. Aynı anda kapatmak için en fazla 400 uyarı seçebilirsiniz.

### <a name="not-familiar-with-the-alert-triage-process"></a>Uyarı önceliklendirme işlemi hakkında bilgi sahibi değilim

Insider risk yönetiminde uyarıları araştırmak ve bu uyarılar üzerinde işlem yapmak kolaydır:

1. **Uyarılar için [Uyarı panosunu](insider-risk-management-activities.md#alert-dashboard) gözden geçirin ve durumu Gözden geçirme gerekiyor olarak belirleyin**. Bu tür uyarıların bulunmasına yardımcı olmak için gerekirse uyarı *Durumuna* göre [filtreleyin](insider-risk-management-activities.md#filter-alerts-on-the-alert-dashboard).
2. **En yüksek önem derecesine sahip uyarılarla başlayın**. Bu tür uyarıların bulunmasına yardımcı olmak için gerekirse uyarı *Önem Derecesi'ne* göre [filtreleyin](insider-risk-management-activities.md#filter-alerts-on-the-alert-dashboard).
3. **Daha fazla bilgi bulmak ve uyarı ayrıntılarını gözden geçirmek için bir uyarı seçin**. Gerekirse, [etkinlik gezginini](insider-risk-management-activities.md#activity-explorer) kullanarak ilişkili olası riskli davranışın zaman çizelgesini gözden geçirin ve uyarının tüm risk etkinliklerini belirleyin.
4. **Uyarıya göre hareket edin**. Uyarıyı onaylayabilir ve uyarı için [bir servis talebi oluşturabilir](insider-risk-management-activities.md#create-a-case-for-an-alert) veya uyarıyı kapatıp çözümleyebilirsiniz.

### <a name="resource-constraints-in-my-organization"></a>Kuruluşumdaki kaynak kısıtlamaları

Modern çalışma alanı kullanıcıları genellikle zamanlarında çok çeşitli sorumluluklara ve taleplere sahiptir. Kaynak kısıtlamalarını gidermeye yardımcı olmak için gerçekleştirebileceğiniz çeşitli eylemler vardır:

- **Analist ve araştırmacı çalışmalarını öncelikle en yüksek risk uyarılarına odakla**. İlkelerinize bağlı olarak, kullanıcı etkinliklerini yakalayıyor ve risk azaltma çabalarınızı farklı derecede etkileyebilecek uyarılar oluşturuyor olabilirsiniz. Uyarıları önem derecesine göre [filtreleyin](insider-risk-management-activities.md#filter-alerts-on-the-alert-dashboard) ve *Yüksek önem derecesi* uyarılarının önceliklerini belirleyin.
- **Kullanıcıları analist ve araştırmacı olarak atayın**. Doğru kullanıcıya uygun roller atanmak, insider risk uyarısı gözden geçirme sürecinin önemli bir parçasıdır. *Insider Risk Yönetimi Analistleri ve Insider Risk Yönetimi Araştırmacıları* rol gruplarına uygun kullanıcıları *atadığınızdan* emin olun.  
- **En yüksek risk etkinliklerini keşfetmeye yardımcı olmak için otomatik insider risk özelliklerini kullanın**. Insider risk yönetimi [dizisi algılama](insider-risk-management-policies.md#sequence-detection-preview) ve [kümülatif sızdırma algılama](insider-risk-management-policies.md#cumulative-exfiltration-detection-preview) özellikleri, kuruluşunuzdaki riskleri bulmanın daha zor olduğunu hızla keşfetmenize yardımcı olabilir. [Risk puanı artırıcılarınızı](insider-risk-management-settings.md#indicators), [dosya etkinliği algılamanızı](insider-risk-management-settings.md#file-activity-detection), [etki alanlarınızı](insider-risk-management-settings.md#domains) ve ilkeleriniz için minimum [gösterge eşiği ayarlarını](insider-risk-management-settings.md#indicator-level-settings-preview) ince ayarlamayı göz önünde bulundurun.
