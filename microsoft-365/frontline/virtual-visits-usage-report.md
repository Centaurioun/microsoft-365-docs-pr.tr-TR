---
title: Microsoft Teams Sanal Ziyaretleri kullanım raporu
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-frontline
ms.reviewer: ''
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
description: Kuruluşunuzdaki sanal randevu etkinliğine genel bir bakış elde etmek için Microsoft Teams yönetim merkezindeki Sanal Ziyaretler kullanım raporunu kullanmayı öğrenin.
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 66e55c0d09b6e38a98acd4716c14b48cdbdafea6
ms.sourcegitcommit: 0ad7edcfdcdd11d02fa8a14ffe4b36e120d92deb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2022
ms.locfileid: "68785055"
---
# <a name="microsoft-teams-virtual-visits-usage-report"></a>Microsoft Teams Sanal Ziyaretleri kullanım raporu

Microsoft Teams yönetim merkezindeki Sanal Ziyaretler kullanım raporu, kuruluşunuzdaki Teams sanal randevu etkinliğine genel bir bakış sağlar. [Bookings uygulaması](bookings-virtual-visits.md) ve [Microsoft Teams Elektronik Sistem Durumu Kaydı (EHR) bağlayıcısı](teams-in-hc.md#virtual-appointments-and-electronic-healthcare-record-ehr-integration) aracılığıyla zamanlanan sanal randevuların ayrıntılı etkinliğini görüntüleyebilirsiniz.

Raporu görüntülemek için genel yönetici veya Teams yöneticisi olmanız gerekir.

Rapor aşağıdaki sekmeleri içerir. Raporda göreceğiniz bilgiler Bookings uygulaması, Teams EHR bağlayıcısı veya her ikisi için bir lisansınız olup olmadığına bağlıdır.

|Sekme |Açıklama  |
|---------|---------|
|**[Sanal Ziyaretler](#virtual-visits)**     |Bookings uygulaması ve EHR sisteminizden gerçekleştirilen Teams EHR ile tümleşik toplantılar kullanılarak zamanlanan randevu sayısının dökümüyle birlikte toplam sanal randevu sayısını gösterir.         |
|**[Süre](#duration)**     |Randevuların ortalama süresini ve katılımcıların ortalama lobi bekleme süresini gösterir.         |
|**[Rezervasyon](#bookings)**     |Bookings uygulaması aracılığıyla zamanlanan randevu sayısını gösterir.         |
|**[EHR](#ehr)**     |EHR sisteminizden gerçekleştirilen Teams EHR ile tümleşik randevu sayısını gösterir.         |  

Kuruluşunuzdaki sanal randevu etkinliği ve eğilimleri hakkında içgörü elde etmek için bu raporu kullanın. Bilgiler, daha iyi iş sonuçları sunmak için sanal randevuları iyileştirmenize yardımcı olabilir.

## <a name="view-the-virtual-visits-usage-report"></a>Sanal Ziyaretler kullanım raporunu görüntüleme

1. Microsoft Teams yönetim merkezinin sol gezinti bölmesinde **Analiz & raporları** > **Kullanım raporları'nı** seçin. **Raporları görüntüle** sekmesindeki **Rapor'un** altında **Sanal Ziyaret kullanımı'nı** seçin.
2. **Tarih aralığı'nın** altında 7 gün, 30 gün veya 90 günlük bir tarih aralığı seçin. Ardından **Raporu çalıştır'ı** seçin.

> [!NOTE]
> Varsayılan olarak, Sanal Ziyaretler analizi açıktır ve rapor kullanılabilir. Bu raporu kullanarak Microsoft'a kuruluşunuzdaki sanal randevular hakkında veri toplama izni vermiş olursunuz. Veri saklama ilkelerimiz hakkında bilgi için bkz. [Microsoft 365'te veri saklama, silme ve yok etme](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).
>
>Kuruluşunuz için raporu kapatmak istiyorsanız, bunu sayfanın sağ üst köşesindeki **Ayarlar'da** yapabilirsiniz. Bu ayarın değiştirilmesi 0 (sıfır) ile 2 saat arasında sürebilir.

## <a name="interpret-the-report"></a>Raporu yorumlama

### <a name="virtual-visits"></a>Sanal Ziyaretler

Burada göreceğiniz grafikler Bookings uygulaması, Teams EHR bağlayıcısı veya her ikisi için bir lisansınız olup olmadığına bağlıdır. Daha fazla bilgi edinmek için bkz [. Bookings uygulamasını yönetme](/microsoftteams/bookings-app-admin?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json) ve [Cerner EHR ile Tümleştirme](ehr-admin-cerner.md) veya [Epic EHR ile Tümleştirme](ehr-admin-epic.md).

:::image type="content" source="media/virtual-visits-usage-report-virtual-visits.png" alt-text="Numaralandırılmış açıklama balonlarını gösteren Sanal Ziyaretler kullanım raporunun Sanal Ziyaretler sekmesinin ekran görüntüsü." lightbox="media/virtual-visits-usage-report-virtual-visits.png":::

|Bilgisi |Açıklama  |
|--------|-------------|
|**1**   |Her raporda, bu raporun oluşturulduğu tarih gösterilir. Raporlar genellikle etkinlik zamanından itibaren 24 ila 48 saatlik gecikme süresini yansıtır. |
|**2**   |X ekseni raporun seçili tarih aralığıdır. Y ekseni randevu sayısıdır.<br>Bu tarihteki randevu sayısını görmek için belirli bir tarihte noktanın üzerine gelin.|
|**3**   |Göstergede bir öğe seçerek grafikte gördüklerinizi filtreleyebilirsiniz. Örneğin, yalnızca her biriyle ilgili bilgileri görmek için **Toplam Rezervasyon Sanal Ziyaretleri** veya **Toplam EHR Sanal Ziyaretleri'ni** seçin. Bu seçimin değiştirilmesi tablodaki bilgileri değiştirmez. |
|**4**   |Tablo, seçilen tarih aralığında gerçekleşen her randevu hakkında ayrıntılı bilgi verir. <ul><li>**Başlangıç saati (UTC),** hem personel üyesinin hem de katılımcının toplantıda olduğu veya toplantıda ilk etkinliğin gerçekleştiği tarih ve saattir.  </li> <li>**Toplantı Kimliği** , toplantının benzersiz kimliğidir.</li> <li>**Lobi bekleme süresi** , bir katılımcının lobiye ilk katılmasıyla aynı katılımcının veya farklı bir katılımcının bir personel üyesi tarafından toplantıya kabul edilme zamanıdır.</li><li>**Süre** , başlangıç saati ile son kişinin toplantıdan ayrılması arasındaki zaman farkıdır. Hem personel üyesi hem de katılımcı toplantıya katılmadıysa süre 0 (sıfır) olarak gösterilir.</li> <li>**Durum** , toplantı durumunu gösterir. <ul><li>**Tamamlandı**: Toplantıya bir veya daha fazla personel üyesi ve katılımcı katılırsa ve toplantı sona erdiyse. Ya da bir veya daha fazla katılımcı toplantıya katılırsa ve toplantı sona erdiyse.</li> <li> **Gösteri yok**: Bir personel toplantıya katılıyorsa ancak başka hiç kişi katılmazsa ve toplantı sona erdiyse. </li></ul> </li> <li>**Toplantı türü** , sanal randevunun Bookings uygulaması veya Teams EHR bağlayıcısı aracılığıyla zamanlanıp zamanlandığını gösterir.</li> <li>**Katılımcılar** , toplantıdaki toplam personel üyesi ve katılımcı sayısıdır.</li> <li>**SMS gönderildi,** katılımcılara sms bildirimi gönderilip gönderilmediğini gösterir. </li> </li> </ul> |
|**5**   |**Ayarlar'ı** seçerek **Sanal Ziyaretler analiz** bölmesini açın. Buradan, kuruluşunuz için Sanal Ziyaretler raporlamasını kapatabilir veya etkinleştirebilir ve tabloya sütun ekleyebilir veya kaldırabilirsiniz. Tabloda olmasını istediğiniz bilgileri görmek için sütunları tabloya eklediğinizden emin olun.|
|**6**   |Raporu çevrimdışı analiz için csv dosyasına aktarabilirsiniz. Raporu hazır olduğunda indirmek **için Excel'e Aktar'ı** ve ardından **İndirmeler** sekmesinde **İndir'i** seçin.|

### <a name="duration"></a>Süre

:::image type="content" source="media/virtual-visits-usage-report-duration.png" alt-text="Numaralandırılmış belirtme çizgilerini gösteren Sanal Ziyaretler kullanım raporunun Süre sekmesinin ekran görüntüsü." lightbox="media/virtual-visits-usage-report-duration.png":::

|Bilgisi |Açıklama  |
|--------|-------------|
|**1**   |Her raporda, bu raporun oluşturulduğu tarih gösterilir. Raporlar genellikle etkinlik zamanından itibaren 24 ila 48 saatlik gecikme süresini yansıtır. |
|**2**   |X ekseni raporun seçili tarih aralığıdır. Y ekseni dakika sayısıdır.<br>Belirli bir tarih için ortalama randevu süresini veya ortalama lobi bekleme süresini görmek için belirli bir tarihteki noktanın üzerine gelin.  |
|**3**   |Göstergede bir öğe seçerek grafikte gördüklerinizi filtreleyebilirsiniz. Örneğin, yalnızca her biriyle ilgili bilgileri görmek için **Ortalama Sanal Ziyaret süresi** veya **Ortalama lobi bekleme süresi'ni** seçin. Bu seçimin değiştirilmesi tablodaki bilgileri değiştirmez. |
|**4**   |Tablo, seçilen tarih aralığında gerçekleşen her randevu hakkında ayrıntılı bilgi verir. <ul><li>**Başlangıç saati (UTC),** hem personel üyesinin hem de katılımcının toplantıda olduğu veya toplantıda ilk etkinliğin gerçekleştiği tarih ve saattir.  </li> <li>**Toplantı Kimliği** , toplantının benzersiz kimliğidir.</li> <li>**Lobi bekleme süresi** , bir katılımcının lobiye ilk katılmasıyla aynı katılımcının veya farklı bir katılımcının bir personel üyesi tarafından toplantıya kabul edilme zamanıdır.</li><li>**Süre** , başlangıç saati ile son kişinin toplantıdan ayrılması arasındaki zaman farkıdır. Hem personel üyesi hem de katılımcı toplantıya katılmadıysa süre 0 (sıfır) olarak gösterilir.</li> <li>**Durum** , toplantı durumunu gösterir. <ul><li>**Tamamlandı**: Toplantıya bir veya daha fazla personel üyesi ve katılımcı katılırsa ve toplantı sona erdiyse. Ya da bir veya daha fazla katılımcı toplantıya katılırsa ve toplantı sona erdiyse.</li> <li> **Gösteri yok**: Bir personel toplantıya katılıyorsa ancak başka hiç kişi katılmazsa ve toplantı sona erdiyse. </li></ul> </li> <li>**Toplantı türü** , sanal randevunun Bookings uygulaması veya Teams EHR bağlayıcısı aracılığıyla zamanlanıp zamanlandığını gösterir.</li> <li>**Katılımcılar** , toplantıdaki toplam personel üyesi ve katılımcı sayısıdır.</li> <li>**SMS gönderildi,** katılımcılara sms bildirimi gönderilip gönderilmediğini gösterir. </li> </li> </ul>|
|**5**   |**Ayarlar'ı** seçerek **Sanal Ziyaretler analiz** bölmesini açın. Buradan, kuruluşunuz için Sanal Ziyaretler raporlamasını kapatabilir veya etkinleştirebilir ve tabloya sütun ekleyebilir veya kaldırabilirsiniz. Tabloda olmasını istediğiniz bilgileri görmek için sütunları tabloya eklediğinizden emin olun.|
|**6**   |Raporu çevrimdışı analiz için csv dosyasına aktarabilirsiniz. Raporu hazır olduğunda indirmek **için Excel'e Aktar'ı** ve ardından **İndirmeler** sekmesinde **İndir'i** seçin.|
### <a name="bookings"></a>Rezervasyon

Bookings uygulamasını içeren bir lisansınız varsa bu sekmeyi görürsünüz. Daha fazla bilgi için bkz [. Bookings uygulamasını yönetme](/microsoftteams/bookings-app-admin?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json).

:::image type="content" source="media/virtual-visits-usage-report-bookings.png" alt-text="Numaralandırılmış açıklama balonlarını gösteren Sanal Ziyaretler kullanım raporunun Bookings sekmesinin ekran görüntüsü." lightbox="media/virtual-visits-usage-report-bookings.png":::

|Bilgisi |Açıklama  |
|--------|-------------|
|**1**   |Her raporda, bu raporun oluşturulduğu tarih gösterilir. Raporlar genellikle etkinlik zamanından itibaren 24 ila 48 saatlik gecikme süresini yansıtır. |
|**2**   |X ekseni raporun seçili tarih aralığıdır. Y ekseni Bookings randevularının sayısıdır.<br>Bu tarihte gerçekleşen Bookings randevularının sayısını görmek için belirli bir tarihte noktanın üzerine gelin.|
|**3**   |Tablo, seçilen tarih aralığında gerçekleşen her randevu hakkında ayrıntılı bilgi verir. <ul><li>**Başlangıç saati (UTC),** hem personel üyesinin hem de katılımcının toplantıda olduğu veya toplantıda ilk etkinliğin gerçekleştiği tarih ve saattir.  </li> <li>**Toplantı Kimliği** , toplantının benzersiz kimliğidir.</li> <li>**Lobi bekleme süresi** , bir katılımcının lobiye ilk katılmasıyla aynı katılımcının veya farklı bir katılımcının bir personel üyesi tarafından toplantıya kabul edilme zamanıdır.</li><li>**Süre** , başlangıç saati ile son kişinin toplantıdan ayrılması arasındaki zaman farkıdır. Hem personel üyesi hem de katılımcı toplantıya katılmadıysa süre 0 (sıfır) olarak gösterilir.</li> <li>**Durum** , toplantı durumunu gösterir. <ul><li>**Tamamlandı**: Toplantıya bir veya daha fazla personel üyesi ve katılımcı katılırsa ve toplantı sona erdiyse. Ya da bir veya daha fazla katılımcı toplantıya katılırsa ve toplantı sona erdiyse.</li> <li> **Gösteri yok**: Bir personel toplantıya katılıyorsa ancak başka hiç kişi katılmazsa ve toplantı sona erdiyse. </li></ul> </li> <li>**Toplantı türü** , sanal randevunun Bookings uygulaması veya Teams EHR bağlayıcısı aracılığıyla zamanlanıp zamanlandığını gösterir.</li> <li>**Katılımcılar** , toplantıdaki toplam personel üyesi ve katılımcı sayısıdır.</li> <li>**SMS gönderildi,** katılımcılara sms bildirimi gönderilip gönderilmediğini gösterir. </li> </li> </ul>|
|**4**   |**Ayarlar'ı** seçerek **Sanal Ziyaretler analiz** bölmesini açın. Buradan, kuruluşunuz için Sanal Ziyaretler raporlamasını kapatabilir veya etkinleştirebilir ve tabloya sütun ekleyebilir veya kaldırabilirsiniz. Tabloda olmasını istediğiniz bilgileri görmek için sütunları tabloya eklediğinizden emin olun.|
|**5**   |Raporu çevrimdışı analiz için csv dosyasına aktarabilirsiniz. Raporu hazır olduğunda indirmek **için Excel'e Aktar'ı** ve ardından **İndirmeler** sekmesinde **İndir'i** seçin.|
### <a name="ehr"></a>EHR

Teams EHR bağlayıcısını içeren bir lisansınız varsa bu sekmeyi görürsünüz. Daha fazla bilgi için bkz. [Cerner EHR ile Tümleştirme](ehr-admin-cerner.md) veya [Epic EHR ile Tümleştirme](ehr-admin-epic.md).

:::image type="content" source="media/virtual-visits-usage-report-ehr.png" alt-text="Numaralandırılmış açıklama balonlarını gösteren Sanal Ziyaretler kullanım raporunun EHR sekmesinin ekran görüntüsü." lightbox="media/virtual-visits-usage-report-ehr.png":::

|Bilgisi |Açıklama  |
|--------|-------------|
|**1**   |Her raporda, bu raporun oluşturulduğu tarih gösterilir. Raporlar genellikle etkinlik zamanından itibaren 24 ila 48 saatlik gecikme süresini yansıtır. |
|**2**   |X ekseni raporun seçili tarih aralığıdır. Y ekseni, EHR randevularının sayısıdır.<br>Bu tarihteki EHR randevularının sayısını görmek için belirli bir tarihte noktanın üzerine gelin.|
|**3**   |Tablo, seçilen tarih aralığında gerçekleşen her randevu hakkında ayrıntılı bilgi verir. <ul><li>**Başlangıç saati (UTC),** hem personel üyesinin hem de katılımcının toplantıda olduğu veya toplantıda ilk etkinliğin gerçekleştiği tarih ve saattir.  </li> <li>**Toplantı Kimliği** , toplantının benzersiz kimliğidir.</li> <li>**Lobi bekleme süresi** , bir katılımcının lobiye ilk katılmasıyla aynı katılımcının veya farklı bir katılımcının bir personel üyesi tarafından toplantıya kabul edilme zamanıdır.</li><li>**Süre** , başlangıç saati ile son kişinin toplantıdan ayrılması arasındaki zaman farkıdır. Hem personel üyesi hem de katılımcı toplantıya katılmadıysa süre 0 (sıfır) olarak gösterilir.</li> <li>**Durum** , toplantı durumunu gösterir. <ul><li>**Tamamlandı**: Toplantıya bir veya daha fazla personel üyesi ve katılımcı katılırsa ve toplantı sona erdiyse. Ya da bir veya daha fazla katılımcı toplantıya katılırsa ve toplantı sona erdiyse.</li> <li> **Gösteri yok**: Bir personel toplantıya katılıyorsa ancak başka hiç kişi katılmazsa ve toplantı sona erdiyse. </li></ul> </li> <li>**Toplantı türü** , sanal randevunun Bookings uygulaması veya Teams EHR bağlayıcısı aracılığıyla zamanlanıp zamanlandığını gösterir.</li> <li>**Katılımcılar** , toplantıdaki toplam personel üyesi ve katılımcı sayısıdır.</li> <li>**SMS gönderildi,** katılımcılara sms bildirimi gönderilip gönderilmediğini gösterir. </li> </li> </ul>|
|**4**   |**Ayarlar'ı** seçerek **Sanal Ziyaretler analiz** bölmesini açın. Buradan, kuruluşunuz için Sanal Ziyaretler raporlamasını kapatabilir veya etkinleştirebilir ve tabloya sütun ekleyebilir veya kaldırabilirsiniz. Tabloda olmasını istediğiniz bilgileri görmek için sütunları tabloya eklediğinizden emin olun.|
|**5**   |Raporu çevrimdışı analiz için csv dosyasına aktarabilirsiniz. Raporu hazır olduğunda indirmek **için Excel'e Aktar'ı** ve ardından **İndirmeler** sekmesinde **İndir'i** seçin.|

> [!NOTE]
> Kuruluşunuz, iş karar alıcıları gibi yönetici olmayan kullanıcıların bu rapora erişmesi ve bu raporu görüntülemesi için özel önizlemeye katılmak isterse [bize ulaşın](mailto:tapmwtanalytics@microsoft.com).

## <a name="related-articles"></a>İlgili makaleler

- [Teams ve Bookings uygulamasıyla sanal randevular](bookings-virtual-visits.md)
- [Teams ile sanal randevular - Epic EHR ile tümleştirme](ehr-admin-epic.md)
- [Teams ile sanal randevular - Cerner EHR ile tümleştirme](ehr-admin-cerner.md)
