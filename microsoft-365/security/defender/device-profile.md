---
title: Microsoft 365 güvenlik portalında cihaz profili
description: Kuruluşunuzdaki bir cihazın risk ve maruz kalma düzeylerini görüntüleyin. Geçmiş ve mevcut tehditleri analiz edin ve cihazı en son güncelleştirmelerle koruyun.
keywords: güvenlik, kötü amaçlı yazılım, Microsoft 365, M365, Microsoft 365 Defender, güvenlik merkezi, Uç Nokta için Microsoft Defender, Office 365 için Microsoft Defender, Kimlik için Microsoft Defender , cihaz sayfası, cihaz profili, makine sayfası, makine profili
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: dansimp
author: martyav
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
search.appverid: met150
ms.openlocfilehash: 269670d86676896a1a217f224c74776c73388fa9
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68631028"
---
# <a name="device-profile-page"></a>Cihaz profili sayfası

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft 365 güvenlik portalı size cihaz profili sayfaları sağlar, böylece ağınızdaki cihazların durumunu ve durumunu hızla değerlendirebilirsiniz.

> [!IMPORTANT]
> Cihazın Uç Nokta için Microsoft Defender, Kimlik için Microsoft Defender veya her ikisine de kaydedilip kaydedilmediğine bağlı olarak cihaz profili sayfası biraz farklı görünebilir.

Cihaz Uç Nokta için Microsoft Defender kayıtlıysa, bazı yaygın güvenlik görevlerini gerçekleştirmek için cihaz profili sayfasını da kullanabilirsiniz.

## <a name="navigating-the-device-profile-page"></a>Cihaz profili sayfasında gezinme

Profil sayfası birkaç geniş bölüme ayrılmıştır.

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-overall.png" alt-text="Microsoft 365 Defender portalındaki Cihaz profili sayfası" lightbox="../../media/mtp-device-profile/hybrid-device-overall.png":::

Kenar çubuğu (1) cihazla ilgili temel ayrıntıları listeler.

Ana içerik alanı (2), cihazla ilgili farklı türde bilgileri görüntülemek için geçiş yapabileceğiniz sekmeler içerir.

Cihaz Uç Nokta için Microsoft Defender kayıtlıysa, yanıt eylemlerinin listesini de görürsünüz (3). Yanıt eylemleri, güvenlikle ilgili yaygın görevleri gerçekleştirmenize olanak sağlar.

## <a name="sidebar"></a>Kenar çubuğu

Cihaz profili sayfasının ana içerik alanının yanında kenar çubuğu bulunur.

:::image type="content" source="../../media/mtp-device-profile/azure-atp-only-device-sidebar.png" alt-text="Microsoft 365 Defender portalında cihaz profili için Kenar Çubuğu sekmesi" lightbox="../../media/mtp-device-profile/azure-atp-only-device-sidebar.png":::

Kenar çubuğunda cihazın tam adı ve pozlama düzeyi listelenir. Ayrıca küçük alt bölümlerde açık veya kapalı olarak açılabilir veya kapatılabilir bazı önemli temel bilgiler sağlar, örneğin:

* **Etiketler** - Cihazla ilişkili tüm Uç Nokta için Microsoft Defender, Kimlik için Microsoft Defender veya özel etiketler. Kimlik için Microsoft Defender etiketleri düzenlenemez.
* **Güvenlik bilgileri** - Açık olaylar ve etkin uyarılar. Uç Nokta için Microsoft Defender kaydedilen cihazlar da maruz kalma düzeyini ve risk düzeyini görüntüler.

> [!TIP]
> Maruz kalma düzeyi, cihazın güvenlik önerilerine ne kadar uyduğuyla ilgilidir, risk düzeyi ise etkin uyarıların türleri ve önem derecesi dahil olmak üzere bir dizi faktöre göre hesaplanır.

* **Cihaz ayrıntıları** - Etki alanı, işletim sistemi, cihazın ilk görüldüğü zaman damgası, IP adresleri, kaynaklar. Uç Nokta için Microsoft Defender kaydedilen cihazlar da sistem durumunu görüntüler. Kimlik için Microsoft Defender kaydedilen cihazlarda SAM adı ve cihazın ilk oluşturulduğu zaman damgası görüntülenir.
* **Ağ etkinliği** - Cihazın ağda ilk ve son kez görüldüğü zaman damgaları.
* **Dizin verileri** (*yalnızca Kimlik için Microsoft Defender kayıtlı cihazlar için*) - [UAC](/windows/security/identity-protection/user-account-control/user-account-control-overview) bayrakları, [SPN'ler](/windows/win32/ad/service-principal-names) ve grup üyelikleri.

## <a name="response-actions"></a>Yanıt eylemleri

Yanıt eylemleri, tehditlere karşı savunma yapmak ve tehditleri analiz etmek için hızlı bir yol sunar.

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-long-action-bar.png" alt-text="Microsoft 365 Defender portalında cihaz profili için Eylem çubuğu" lightbox="../../media/mtp-device-profile/hybrid-device-long-action-bar.png":::

> [!IMPORTANT]
> * [Yanıt eylemleri](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) yalnızca cihaz Uç Nokta için Microsoft Defender kayıtlıysa kullanılabilir.
> * Uç Nokta için Microsoft Defender kaydedilen cihazlar, cihazın işletim sistemi ve sürüm numarasına göre farklı sayıda yanıt eylemi görüntüleyebilir.

Cihaz profili sayfasında kullanılabilen eylemler şunlardır:

* **Etiketleri yönetme** - bu cihaza uyguladığınız özel etiketleri Güncelleştirmeler.
* **Cihazı yalıtma** - Cihazı kuruluşunuzun ağından yalıtırken Uç Nokta için Microsoft Defender bağlı kalmasını sağlar. İletişim amacıyla cihaz yalıtılmış durumdayken Outlook, Teams ve Skype Kurumsal çalışmasına izin vermeyi seçebilirsiniz.
* **İşlem merkezi** - Gönderilen eylemlerin durumunu görüntüleyin. Yalnızca başka bir eylem seçilmişse kullanılabilir.
* **Uygulama yürütmeyi kısıtla** - Microsoft tarafından imzalanmayan uygulamaların çalışmasını engeller.
* **Virüsten koruma taraması çalıştırma** - Virüsten koruma tanımlarını Güncelleştirmeler Microsoft Defender ve hemen bir virüsten koruma taraması çalıştırır. Hızlı tarama veya Tam tarama arasında seçim yapın.
* **Araştırma paketi toplama** - Cihaz hakkında bilgi toplar. Araştırma tamamlandığında indirebilirsiniz.
* **Canlı Yanıt Oturumu Başlatma** - [Ayrıntılı güvenlik araştırmaları](/microsoft-365/security/defender-endpoint/live-response) için cihaza uzak bir kabuk yükler.
* **Otomatik araştırma başlatma** - [Tehditleri otomatik olarak araştırır ve düzelter](../office-365-security/office-365-air.md). Otomatik araştırmaların bu sayfadan çalıştırılmasını el ile tetikleyebilmenize rağmen, [bazı uyarı ilkeleri](../../compliance/alert-policies.md#default-alert-policies) otomatik araştırmaları kendi başlarına tetikler.
* **İşlem merkezi** - Çalışmakta olan tüm yanıt eylemleriyle ilgili bilgileri görüntüler.

## <a name="tabs-section"></a>Sekmeler bölümü

Cihaz profili sekmeleri, cihaz hakkındaki güvenlik ayrıntılarına ve uyarıların listesini içeren tablolara genel bakış arasında geçiş yapmanızı sağlar.

Uç Nokta için Microsoft Defender kaydedilen cihazlarda zaman çizelgesi, güvenlik önerileri listesi, yazılım envanteri, bulunan güvenlik açıklarının listesi ve eksik KB'ler (güvenlik güncelleştirmeleri) içeren sekmeler de görüntülenir.

### <a name="overview-tab"></a>Genel Bakış sekmesi

Varsayılan sekme **Genel Bakış'tır**. Cihazla ilgili en önemli güvenlik gerçeğine hızlı bir bakış sağlar.

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-tab-overview.png" alt-text="Microsoft 365 Defender portalında cihaz profili için Genel Bakış sekmesi" lightbox="../../media/mtp-device-profile/hybrid-device-tab-overview.png":::

Burada, cihazın etkin uyarılarına ve şu anda oturum açmış olan kullanıcılara hızlıca göz atabilirsiniz.

Cihaz Uç Nokta için Microsoft Defender kayıtlıysa, cihazın risk düzeyini ve güvenlik değerlendirmeleriyle ilgili kullanılabilir verileri de görürsünüz. Güvenlik değerlendirmeleri cihazın maruz kalma düzeyini açıklar, güvenlik önerileri sağlar ve etkilenen yazılımları ve bulunan güvenlik açıklarını listeler.

### <a name="alerts-tab"></a>Uyarılar sekmesi

**Uyarılar** sekmesi, hem Kimlik için Microsoft Defender hem de Uç Nokta için Microsoft Defender cihazda tetiklenen uyarıların listesini içerir.

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-tab-alerts.png" alt-text="Microsoft 365 Defender portalında cihaz profili için Uyarılar sekmesi" lightbox="../../media/mtp-device-profile/hybrid-device-tab-alerts.png":::

Görüntülenen öğe sayısını ve her öğe için hangi sütunların görüntüleneceğini özelleştirebilirsiniz. Varsayılan davranış, sayfa başına otuz öğeyi listelemektir.

Bu sekmedeki sütunlar uyarıyı tetikleyen tehdidin önem derecesine ilişkin bilgilerin yanı sıra durum, araştırma durumu ve uyarının atandığı kişiler hakkında bilgi içerir.

*Etkilenen varlıklar* sütunu, profilini görüntülemekte olduğunuz cihazı (varlık) ve ağınızdaki etkilenen diğer cihazları ifade eder.

Bu listeden bir öğe seçildiğinde, seçili uyarı hakkında daha fazla bilgi içeren bir açılır menü açılır.

Bu liste önem derecesine, duruma veya uyarının atandığı kişilere göre filtrelenebilir.

### <a name="timeline-tab"></a>Zaman Çizelgesi sekmesi

**Zaman Çizelgesi** sekmesi, cihazda tetiklenen tüm olayların etkileşimli, kronolojik bir grafiğini içerir. Grafiğin vurgulanan alanını sola veya sağa taşıyarak, farklı zaman dilimlerindeki olayları görüntüleyebilirsiniz. Ayrıca, etkileşimli grafik ile olay listesi arasındaki açılan menüden özel bir tarih aralığı seçebilirsiniz.

Grafiğin altında, seçilen tarih aralığına ait olayların listesi yer alır.

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-tab-timeline.png" alt-text="Microsoft 365 Defender portalında cihaz profili için Zaman Çizelgesi sekmesi" lightbox="../../media/mtp-device-profile/hybrid-device-tab-timeline.png":::

Görüntülenen öğe sayısı ve listedeki sütunlar özelleştirilebilir. Varsayılan sütunlar olay zamanını, etkin kullanıcıyı, eylem türünü, varlıkları (işlemleri) ve olayla ilgili ek bilgileri listeler.

Bu listeden bir öğe seçildiğinde, olaya dahil olan üst ve alt işlemleri gösteren olay varlıkları grafiğini gösteren bir açılır liste açılır.

Liste, belirli bir olay türüne göre filtrelenebilir; örneğin, Kayıt defteri olayları veya Akıllı Ekran Olayları.

Liste, indirilmek üzere bir CSV dosyasına da aktarılabilir. Dosya olay sayısıyla sınırlı olmasa da, dışarı aktarmayı seçebileceğiniz maksimum zaman aralığı yedi gündür.

### <a name="security-recommendations-tab"></a>Güvenlik önerileri sekmesi

**Güvenlik önerileri** sekmesi, cihazı korumak için gerçekleştirebileceğiniz eylemleri listeler. Bu listeden bir öğe seçildiğinde, önerinin nasıl uygulanacağı hakkında yönergeler alabileceğiniz bir açılır liste açılır.

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-tab-security-recs.png" alt-text="Microsoft 365 Defender portalında cihaz profili için Güvenlik önerileri sekmesi" lightbox="../../media/mtp-device-profile/hybrid-device-tab-security-recs.png":::

Önceki sekmelerde olduğu gibi, sayfa başına görüntülenen öğe sayısı ve hangi sütunların görünür olduğu özelleştirilebilir.

Varsayılan görünümde ele alınan güvenlik zayıflıklarını, ilişkili tehdidi, tehditten etkilenen ilgili bileşeni veya yazılımları ve daha fazlasını ayrıntılı olarak gösteren sütunlar bulunur. Öğeler önerinin durumuna göre filtrelenebilir.

### <a name="software-inventory"></a>Yazılım envanteri

**Yazılım envanteri** sekmesinde cihazda yüklü olan yazılımlar listelenir.

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png" alt-text="Microsoft 365 Defender portalında cihaz profili için Yazılım envanteri sekmesi" lightbox="../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png":::

Varsayılan görünümde yazılım satıcısı, yüklü sürüm numarası, bilinen yazılım zayıflıklarının sayısı, tehdit içgörüleri, ürün kodu ve etiketler görüntülenir. Görüntülenen öğe sayısı ve hangi sütunların görüntülendiği özelleştirilebilir.

Bu listeden bir öğe seçildiğinde, seçilen yazılım hakkında daha fazla ayrıntının yanı sıra yazılımın son bulunduğu zamana ait yol ve zaman damgasını içeren bir açılır liste açılır.

Bu liste ürün koduna göre filtrelenebilir.

### <a name="discovered-vulnerabilities-tab"></a>Bulunan güvenlik açıkları sekmesi

**Bulunan güvenlik açıkları** sekmesi, cihazı etkileyebilecek tüm Ortak Güvenlik Açıklarını ve Açıklardan Yararlanmaları (CVE) listeler.

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png" alt-text="Microsoft 365 Defender portalında cihaz profili için bulunan güvenlik açıkları sekmesi" lightbox="../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png":::

Varsayılan görünümde CVE'nin önem derecesi, Ortak Güvenlik Açığı Puanı (CVS), CVE ile ilgili yazılım, CVE yayımlandığı zaman, CVE'nin son güncelleştirme tarihi ve CVE ile ilişkili tehditler listelenir.

Önceki sekmelerde olduğu gibi, görüntülenen öğe sayısı ve hangi sütunların görünür olduğu özelleştirilebilir.

Bu listeden bir öğe seçildiğinde CVE'yi açıklayan bir açılır liste açılır.

### <a name="missing-kbs"></a>Eksik KB'ler

**Eksik KB'ler** sekmesi, cihaza henüz uygulanmamış microsoft Güncelleştirmeler listeler. Söz konusu "KB", bu güncelleştirmeleri açıklayan [Bilgi Bankası makaleleridir](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) ; örneğin [, KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG" alt-text="Microsoft 365 Defender portalında cihaz profili için Eksik KB sekmesi" lightbox="../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG":::

Varsayılan görünümde güncelleştirmeleri, işletim sistemi sürümünü, etkilenen ürünleri, ele alınan CV'leri, KB numarasını ve etiketleri içeren bülten listelenir.

Sayfa başına görüntülenen öğe sayısı ve hangi sütunların görüntülendiği özelleştirilebilir.

Bir öğe seçildiğinde güncelleştirmeye bağlanan bir açılır öğe açılır.

## <a name="related-topics"></a>İlgili konular

* [Microsoft 365 Defender genel bakış](microsoft-365-defender.md)
* [Microsoft 365 Defender’ı açın](m365d-enable.md)
* [Canlı yanıt kullanarak cihazlardaki varlıkları araştırma](../defender-endpoint/live-response.md)
* [Office 365'de otomatik araştırma ve yanıt (AIR)](../office-365-security/office-365-air.md)
