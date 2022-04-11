---
title: Kişisel verilerin sızıntılarını izleme
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
ms.localizationpriority: high
search.appverid:
- MET150
description: Kişisel verilerin sızıntılarını izlemek için kullanabileceğiniz üç araç hakkında bilgi edinebilirsiniz.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4024640173d6cbbf6817d3fa2b1c24cb7264833c
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/25/2022
ms.locfileid: "64470867"
---
# <a name="monitor-for-leaks-of-personal-data"></a>Kişisel verilerin sızıntılarını izleme

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Kişisel verilerin kullanımını ve aktarımlarını izlemek için kullanılmaktadır. Bu konu başlığında, iyi çalışacak üç araç açıklanmıştır.

:::image type="content" source="../../media/Monitor-for-leaks-of-personal-data-image1.png" alt-text="Kişisel verilerin kullanımını ve aktarımlarını izleme araçları" lightbox="../../media/Monitor-for-leaks-of-personal-data-image1.png":::

Çizimde:

- SharePoint Online Microsoft 365 ta, e-postada ve e-postada kişisel verileri izlemek için veri OneDrive İş önleme raporlarıyla çalışmaya başlayabilirsiniz. Bu raporlar, kişisel verileri izlemek için en yüksek ayrıntı düzeyini sağlar. Ancak bu raporlar, raporlarda yer alan tüm hizmetleri Office 365.

- Ardından, hizmetler genelinde etkinliği izlemek için uyarı ilkelerini ve denetim günlüğünü kullanın. Devam eden izleme ayarlayın veya bir olayı araştırmak için denetim günlüğünde arama yapın. Denetim günlüğü; Sway, Power BI, eBulma, Dynamics 365, Power Automate, Microsoft Teams, Yönetici etkinliği, OneDrive İş, SharePoint Online, iletili posta ve diğer posta kutuları gibi hizmetler genelinde çalışır. Skype konuşmalar, posta kutularında kalan posta kutularına dahil edilir.

- Son olarak, Microsoft Defender for Cloud Apps SaaS sağlayıcılarında hassas verilerle dosyaları izlemek için bu bilgileri kullanın. Yakında, azure genelinde hassas bilgi türlerini ve birleşik etiketleri Information Protection ve Office uygulamalarıyla birlikte Bulut için Defender özelliği olacak. SaaS uygulamalarınızın veya belirli uygulamalarınız için geçerli olan ilkeler oluşturabilirsiniz (Box gibi). Bulut için Defender Uygulamaları e-postaya eklenmiş dosyalar dahil Exchange Online dosyaları bulmaz.

## <a name="data-loss-prevention-reports"></a>Veri kaybı önleme raporları

Veri kaybı önleme (DLP) ilkelerinizi oluşturdukktan sonra, bunların istediğiniz gibi çalıştığını doğrulamak ve uyumlu kalmanıza yardımcı olmak istiyor olursunuz. Office 365'daki DLP raporlarıyla, DLP ilkesi eşleşmelerinin, geçersiz kılmaların veya yanlış pozitiflerin sayısını hızla  görüntüleyebilirsiniz; zamanla yukarı mı yoksa aşağı mı eğilime olduğunu görebilir; raporu farklı şekillerde filtreleyebilirsiniz ve grafik üzerinde bir çizgi üzerinde bir nokta seçerek daha fazla ayrıntı görüntüleyebilirsiniz.

DLP raporlarını kullanarak şunları yapmak için kullanabilirsiniz:

- Belirli zaman dönemleri üzerinde odaklanın ve depolar ile eğilimlerin nedenlerini an edin.
- Kuruluş DLP ilkelerini ihlal eden iş işlemlerini keşfedin.
- DLP ilkelerinin ticari etkisini anlıyoruz.
- İlkeyi geçersiz karak veya hatalı pozitif bir sonuç bildirerek, kullanıcılar tarafından gönderilen gerekçeleri, ilke ipucu çözümleyene kadar görüntüleme.
- Belirli bir DLP ilkesine uyumluluğu doğrulamak için, o ilkeyle ilgili eşleşmeleri gösterin.
- Ayrıntılar bölmesinde DLP ilkelerinize eşleşen hassas veriler bulunduran dosyaların listesini görüntüleyin.

Buna ek olarak, DLP ilkelerini test modunda çalıştırarak ince ayar yapmak için DLP raporlarını kullanabilirsiniz.

DLP raporları aşağıdaki Microsoft 365 uyumluluk merkezi. DLP **ilkesi eşleşmelerini**\>, DLP olaylarını ve  **DLP** yanlış pozitiflerini ve raporları geçersiz kılmak için **Raporlar Kurumsal veri bölümüne** gidin. 

Daha fazla bilgi için bkz [. Veri kaybını önleme için raporları görüntüleme](../../compliance/view-the-dlp-reports.md).

:::image type="content" source="../../media/Monitor-for-leaks-of-personal-data-image2.png" alt-text="DLP ilkesi eşleşmelerini gösteren rapor" lightbox="../../media/Monitor-for-leaks-of-personal-data-image2.png":::

## <a name="audit-log-and-alert-policies"></a>Denetim günlüğü ve uyarı ilkeleri

Denetim günlüğü Exchange Online, SharePoint Online, OneDrive İş, Azure Active Directory, Microsoft Teams, Power BI, Sway ve diğer hizmetlerden olayları içerir.

Denetim Microsoft 365 Defender denetim günlüğü Microsoft 365 uyumluluk merkezi izlemek ve rapor etmek için iki yol sağlar:

- Uyarı ilkeleri ayarlama, uyarıları görüntüleme ve eğilimleri izleme—Uyarı ilkesi ve uyarı panosu araçlarını Microsoft 365 Defender portalda veya Microsoft 365 uyumluluk merkezi.
- Denetim günlüğünde doğrudan arama yapın: Belirli bir tarih içerisinde tüm olayları arama. Ya da sonuçları, eylemi, eylemi veya hedef nesneyi gerçekleştiren kullanıcı gibi belirli ölçütlere göre filtre de kullanabilirsiniz.

Bilgi uyumluluğu ve güvenlik ekipleri, hizmetler genelinde hem son kullanıcılar hem de yöneticiler tarafından gerçekleştirilen etkinlikleri önceden gözden geçirmek için bu araçları kullanabilir. Belirli site koleksiyonları üzerinde belirli etkinlikler gerçekleşirken, örneğin GDPR ile ilgili bilgiler içerdiği bilinen sitelerden içerik paylaşıldığında, otomatik uyarılar e-posta bildirimleri gönderecek şekilde ya da yapılandırılamaz. Bu, bu ekiplerin, kurumsal güvenlik ilkelerinin izlen olduğundan emin olmak veya ek eğitim sağlamak amacıyla kullanıcılarla izlemelerine olanak sağlar.

Bilgi güvenliği ekipleri ayrıca, şüpheli veri ihlallerini araştırmak ve ihlallerin hem temel nedenini hem de boyutunu belirlemek için denetim günlüğünde arama da bulundurabilirsiniz. Bu yerleşik özellik, belirli bir süre içinde GDPR denetim yetkilisine ve veri konularına bildirim verilmesini gerektiren GDPR'nin 33 ve 34. maddesine daha kolay uyumluluk sağlar. Denetim günlüğü girdileri hizmet içinde yalnızca 90 gün boyunca korunur. Bu girdilerin çoğunlukla kullanılması ve birçok kuruluşun bu günlüklerin daha uzun süre tutulması gerekir.

Çözümler, Microsoft Yönetim Etkinliği API'si aracılığıyla Birleşik Denetim Günlükleri'ne abone olarak kullanılabilir ve gerektiğinde günlük girdilerini depolar ve gelişmiş panolar ile uyarılar sağlar. Örneğin, [Microsoft Operations Management Suite (OMS)](/azure/operations-management-suite/oms-solution-office-365).

Uyarı ilkeleri ve denetim günlüğünde arama hakkında daha fazla bilgi:

- [E-postada uyarı Microsoft 365](../../compliance/alert-policies.md)
- [Denetim günlüğünde kullanıcı ve yönetici etkinliğini arama (Office 365](../../compliance/search-the-audit-log-in-security-and-compliance.md))
- [Denetim günlüğü aramalarını açma veya kapatma](../../compliance/turn-audit-log-search-on-or-off.md)
- [Denetim günlüğünde arama yapma](../../compliance/search-the-audit-log-in-security-and-compliance.md)
- [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) (cmdlet)
- [Denetim günlüğündeki ayrıntılı özellikler](../../compliance/detailed-properties-in-the-office-365-audit-log.md)

## <a name="microsoft-defender-for-cloud-apps"></a>Bulut Uygulamaları için Microsoft Defender

Microsoft Defender for Cloud Apps, ağlarda ve bu uygulamalardan gönderilen hassas veriler arasında diğer SaaS uygulamalarını keşfetmenize yardımcı olur.

Microsoft Defender for Cloud Apps kapsamlı görünürlük, ayrıntılı denetimler ve bulut uygulamalarınız için gelişmiş tehdit koruması sağlayan kapsamlı bir hizmettir. Ağ bağlantınıza tüm cihazlardan 15.000'den fazla bulut uygulaması tanımlar ve risk puanlama ile devam eden risk değerlendirmesi ve çözümlemeleri sağlar. Aracı gerekmez: Bulut kullanımı ve gölge IT'niz için tam görünürlük ve bağlam sağlayan güvenlik duvarlarınız ve aracılardan bilgiler toplanır.

Bulut ortamınızı daha iyi anlamak için, Bulut için Defender Uygulamaları araştırma özelliğiyle, ekli ve yönetilen uygulamalar için tüm etkinlikler, dosyalar ve hesaplar üzerinde derin bir görünürlük sağlar. Dosya düzeyinde ayrıntılı bilgi edinebilirsiniz ve bulut uygulamaları içinde verilerin nereye gittiğini keşfedebilirsiniz.

Örnek olarak, aşağıdaki çizimde GDPR Bulut için Defender yardımcı olacak iki farklı uygulama uygulaması uygulaması gösterilmiştir.

:::image type="content" source="../../media/Monitor-for-leaks-of-personal-data-image3.png" alt-text="Bulut için Defender Uygulamaları ilkeleri" lightbox="../../media/Monitor-for-leaks-of-personal-data-image3.png":::

Seçtiğiniz önceden tanımlanmış PII özniteliğine veya özel ifadeye sahip dosyalar, seçtiğiniz SaaS uygulamalarıyla kuruluşun dışında paylaşılırken ilk ilke uyarıları.

İkinci ilke, dosyaların indirilmelerini, yöneticisi olmayan tüm cihaza indirmelerini engeller. Dosyaların içindeki öznitelikleri, ilkenin uygulamak istediğiniz SaaS uygulamalarını seçersiniz.

Bu öznitelik türleri yakında Uygulamalarda Bulut için Defender geliyor:

- Hassas bilgi türleri
- Microsoft 365 Azure Information Protection'de birleştirilmiş etiketler

### <a name="defender-for-cloud-apps-dashboard"></a>Bulut için Defender Uygulamaları panosu

Bulut için Defender Uygulamalarını kullanmaya başlamadıysanız, başlangıç olarak bu uygulamaları kullanın. Bulut için Defender erişmek için: <https://portal.cloudappsecurity.com>.

> [!NOTE]
> Bulut için Defender Uygulamaları'na başlarken veya etiketler atamadan önce "Azure Information Protection sınıflandırma etiketleri için dosyaları otomatik olarak tara" (Genel ayarlar'da) ayarını etkinleştirmeyi öğrenin. Kurulumdan sonra, Bulut için Defender Uygulamalar değiştirilene kadar var olan dosyaları yeniden taramaz.

:::image type="content" source="../../media/Monitor-for-leaks-of-personal-data-image4.png" alt-text="Uyarılar hakkında bilgi gösteren pano" lightbox="../../media/Monitor-for-leaks-of-personal-data-image4.png":::

Daha fazla bilgi:

- [Uygulama Bulut için Defender dağıtma](/cloud-app-security/getting-started-with-cloud-app-security)
- [Daha fazla bilgi Microsoft Defender for Cloud Apps](https://www.microsoft.com/cloud-platform/cloud-app-security)
- [Microsoft Defender for Cloud Apps proxy'lerini kullanarak hassas bilgilerin indir Microsoft Defender for Cloud Apps engelleme](/cloud-app-security/use-case-proxy-block-session-aad)

## <a name="example-file-and-activity-policies-to-detect-sharing-of-personal-data"></a>Kişisel verilerin paylaşımını algılamak için örnek dosya ve etkinlik ilkeleri

### <a name="detect-sharing-of-files-containing-pii--credit-card-number"></a>PII içeren dosyaların paylaşımını algılama — Kredi kartı numarası

Onaylanmış bir bulut uygulamasından kredi kartı numarası içeren bir dosyanın paylaşılıyor olmasıyla ilgili uyarı.

|Denetim|Ayarlar|
|---|---|
|İlke türü|Dosya ilkesi|
|İlke şablonu|Şablon yok|
|İlke önem düzeyi|Yüksek|
|Kategori|DLP|
|Filtre ayarları|Erişim düzeyi = Genel (İnternet), Genel, Dış <p> Uygulama = \<select apps\> (belirli SaaS uygulamalarıyla izlemeyi sınırlamak için bu ayarı kullanın)|
|Uygula|Tüm dosyalar, tüm sahipler|
|İçerik incelemesi|Mevcut ifadeyle eşleşmeye sahip dosyaları içerir: Tüm ülkeler: Finans: Kredi kartı numarası <p> İlgili bağlam gerektirmeyen: işaretsiz (bu ayar anahtar sözcüklerle ve regex ile de eşler) <p> En az 1 eşleşmesi olan dosyaları içerir <p> İhlalin son 4 karakterine yer yok: işaretli|
|Uyarılar|Eşleşen her dosya için uyarı oluşturma: İşaretlendi <p> Günlük uyarı sınırı: 1000 <p> E-posta olarak uyarı seçme: işaretli <p> Bunu yapmak için: infosec@contoso.com|
|İdare|Microsoft OneDrive İş <p> Özel hale: Dış Kullanıcıları Kaldır'ı denetleme <p> Diğer tüm ayarlar: işaretsiz <p> Microsoft Office SharePoint Online <p> Özel hale: Dış Kullanıcıları Kaldır'ı denetleme <p> Diğer tüm ayarlar: işaretsiz|

Benzer ilkeler:

- PII içeren dosyaların paylaşımını algılama - E-posta Adresi
- PII - Pasaport Numarası içeren dosyaların paylaşımını algılama

### <a name="detect-customer-or-hr-data-in-box-or-onedrive-for-business"></a>Box veya OneDrive İş'de Müşteri veya İk Verilerini OneDrive İş

Posta Kutusuna Müşteri Verileri veya İk Verileri olarak etiketlenmiş bir dosyanın Karşıya OneDrive İş uyarı.

Notlar:

- Kutu izlemesi için API Bağlayıcı SDK'si kullanılarak bir bağlayıcı yapılandırıldığından emin olun.
- Bu ilke, şu anda özel önizlemede olan özellikler gerektirir.

|Denetim|Ayarlar|
|---|---|
|İlke türü|Etkinlik ilkesi|
|İlke şablonu|Şablon yok|
|İlke önem düzeyi|Yüksek|
|Kategori|Paylaşım Denetimi|
|Üzerinde eylemde davran|Tek etkinlik|
|Filtre ayarları|Etkinlik türü = Upload Dosyası <p> Uygulama = Microsoft OneDrive İş Box <p> Sınıflandırma Etiketi (şu anda özel önizlemede): Azure Information Protection = Müşteri Verileri, İnsan Kaynakları—Maaş Verileri, İnsan Kaynakları—Çalışan Verileri|
|Uyarılar|Uyarı oluşturma: işaretli <p> Günlük uyarı sınırı: 1000 <p> E-posta olarak uyarı seçme: işaretli <p> Bunu yapmak için: infosec@contoso.com|
|İdare|Tüm uygulamalar <p> Kullanıcı karantinaya alın: Denetleme <p> Diğer tüm ayarlar: işaretsiz <p> Office 365 <p> Kullanıcı karantinaya alın: Denetleme <p> Diğer tüm ayarlar: işaretsiz|

Benzer ilkeler:

- Müşteri verileri veya İk Verileri'nin büyük indirmelerini algılama-Kısa süre içinde müşteri verilerini veya İk verilerini içeren çok fazla sayıda dosyanın tek bir kullanıcı tarafından indirilirken algılandığında uyarı.
- Müşteri ve İk Verilerini Paylaşmayı Algıla—Müşteri veya İk Verilerini içeren dosyalar paylaşılırken uyarı.