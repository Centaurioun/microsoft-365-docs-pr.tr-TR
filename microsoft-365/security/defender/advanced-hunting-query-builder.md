---
title: Microsoft 365 Defender gelişmiş avcılıkta kılavuzlu modu kullanarak sorgular oluşturma
description: Farklı kullanılabilir filtreleri ve koşulları birleştirerek kılavuzlu modda sorgu oluşturmayı öğrenin.
keywords: destekli mod, gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, özel algılamalar, şema, Kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.openlocfilehash: b054bd3518d9cdc1bdbb4a11f59dfff70832b701
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68080183"
---
# <a name="build-hunting-queries-using-guided-mode-in-microsoft-365-defender"></a>Microsoft 365 Defender'da kılavuzlu modu kullanarak tehdit avcılığı sorguları oluşturma

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

Kılavuzlu modda sorgu oluşturucu, analistlerin *Kusto Sorgu Dili (KQL) veya veri şemasını bilmeden* anlamlı avcılık sorguları oluşturmasına olanak tanır. Her deneyim katmanındaki analistler sorgu oluşturucusunu kullanarak son 30 güne ait verileri filtreleyerek tehditleri arayabilir, olay araştırmalarını genişletebilir, tehdit verileri üzerinde veri analizi yapabilir veya belirli tehdit alanlarına odaklanabilir.

Analist, hangi veri kümesinin bakılıp hangi filtrelerin ve koşulların kullanılacağını seçerek verileri ihtiyaç duydukları değere daraltabilir. 


## <a name="open-query-in-builder"></a>Sorguyu oluşturucuda açma
**Gelişmiş tehdit avcılığı** sayfasında **Yeni oluştur'u** seçerek yeni bir sorgu sekmesi açın ve **Oluşturucuda sorgula'yı** seçin. 

![Kılavuzlu mod sorgu oluşturucusunun ekran görüntüsü](../../media/guided-hunting/query-in-builder-page.png)

Böylece, açılan menüleri kullanarak farklı bileşenler seçerek sorgunuzu oluşturabilirsiniz.

## <a name="specify-the-data-domain-to-hunt-in"></a>Avlanılacak veri etki alanını belirtin
Sorgunun hangi etki alanını kapsadığını seçerek avın kapsamını denetleyebilirsiniz:

![Kılavuzlu mod sorgu oluşturucu etki alanları açılan listesinin ekran görüntüsü](../../media/guided-hunting/query-builder-view-in.png)


**Tümü** seçildiğinde şu anda erişiminiz olan tüm etki alanlarındaki veriler bulunur. Belirli bir etki alanıyla daraltmak, yalnızca bu etki alanıyla ilgili filtrelere izin verir. 

Şu seçimlerden birini yapabilirsiniz:
- Tüm etki alanları - sorgunuzdaki tüm kullanılabilir verilere göz atmak için
- Uç noktalar - Uç Nokta için Microsoft Defender tarafından sağlanan uç nokta verilerine göz atmak için
- Uygulamalar ve kimlikler - Microsoft Defender for Cloud Apps ve Kimlik için Microsoft Defender tarafından sağlanan uygulama ve kimlik verilerine göz atmak için[; Etkinlik günlüğü](/defender-cloud-apps/activity-filters) hakkında bilgi sahibi olan kullanıcılar aynı verileri burada bulabilir
- Email ve işbirliği - SharePoint, OneDrive ve diğerleri gibi e-posta ve işbirliği uygulamaları verilerine bakmak için[; Tehdit Gezgini'ni](/office-365-security/threat-explorer) bilen kullanıcılar aynı verileri burada bulabilir

## <a name="use-basic-filters"></a>Temel filtreleri kullanma

Varsayılan olarak, kılavuzlu avcılık hızlı bir şekilde başlamanızı sağlamak için birkaç temel filtre içerir. 

![Kılavuzlu mod sorgu oluşturucusu temel filtre kümesinin ekran görüntüsü](../../media/guided-hunting/query-builder-basic-filters.png)



Örneğin **Uç Noktalar** gibi bir veri kaynağı seçtiğinizde sorgu oluşturucusu yalnızca geçerli filtre gruplarını görüntüler. Daha sonra daraltmayla ilgilendiğiniz bir filtreyi, örneğin **EventType** filtresini seçerek ve tercih ettiğiniz filtreyi seçerek seçebilirsiniz.

![Kılavuzlu mod sorgu oluşturucusu uç noktası temel filtre kümesinin ekran görüntüsü](../../media/guided-hunting/query-builder-query-basic-filter.png)



Sorgu hazır olduktan sonra mavi **Sorguyu çalıştır** düğmesini seçin. Düğme gri görünüyorsa, sorgunun doldurulması veya daha fazla düzenlenmesi gerektiği anlamına gelir. 

>[!NOTE]
> Temel filtre görünümü yalnızca **AND** işlecini kullanır, yani sorgu çalıştırıldığında tüm ayarlanan filtrelerin doğru olduğu sonuçlar oluşturulur. 


## <a name="load-sample-queries"></a>Örnek sorguları yükleme

Kılavuzlu avcılık hakkında bilgi edinmenin bir diğer hızlı yolu da Örnek sorguları yükle açılan menüsünü kullanarak **örnek sorguları** yüklemektir. 
![Kılavuzlu mod sorgu oluşturucusu yük örnek sorgular listesinin ekran görüntüsü](../../media/guided-hunting/load-sample-queries.png)

>[!NOTE] 
> Örnek sorgu seçildiğinde mevcut sorgu geçersiz kılınıyor. 

Örnek sorgu yüklendikten sonra **Sorguyu çalıştır'ı** seçin.

![Destekli mod sorgu oluşturucusu yüklenen sorgunun ekran görüntüsü](../../media/guided-hunting/load-sample-queries-1.png)

Daha önce bir etki alanı seçtiyseniz, kullanılabilir örnek sorguların listesi buna göre değişir.

![Kılavuzlu mod sorgu oluşturucusu kısıtlı listesinin ekran görüntüsü](../../media/guided-hunting/load-sample-queries-2.png)

Örnek sorguların tam listesini geri yüklemek için **Tüm etki alanları'nı** seçin ve **Örnek sorguları yükle'yi** yeniden açın.

Yüklenen örnek sorgu temel filtre kümesinin dışındaki filtreleri kullanıyorsa iki durumlu düğme gri görünür. Temel filtre kümesine dönmek için **Tümünü temizle'yi** seçip **Tüm filtreler'i** değiştirin. 


## <a name="use-more-filters"></a>Daha fazla filtre kullanma

Daha fazla filtre grubunu ve koşulu görüntülemek **için, daha fazla filtre ve koşul görmek için Geçiş'i** seçin.

![Kılavuzlu mod sorgu oluşturucusu diğer filtreler iki durumlu düğmesinin ekran görüntüsü](../../media/guided-hunting/query-builder-view-in-endpoints.png)

**Tüm filtreler** iki durumlu düğmesi etkin olduğunda, artık kılavuzlu modda tam filtre ve koşul aralığını kullanabilirsiniz.

![Tüm filtrelerin etkin olduğu kılavuzlu mod sorgu oluşturucusunun ekran görüntüsü](../../media/guided-hunting/query-builder-all-filters.png)




### <a name="create-conditions"></a>Koşul oluşturma

Sorguda kullanılacak bir veri kümesini belirtmek için **Filtre seçin'i** seçin. Kullanabileceğiniz öğeleri bulmak için farklı filtre bölümlerini keşfedin.
 
![Kullanabileceğiniz farklı filtreleri gösteren ekran görüntüsü](../../media/guided-hunting/query-builder-filters.png)

Filtreyi bulmak için listenin en üstündeki arama kutusuna bölümün başlıklarını yazın. *Bilgilerle* biten bölümler, bakabileceğiniz farklı bileşenler hakkında bilgi sağlayan filtreler ve varlıkların durumları için filtreler içerir. *Olaylarla* biten bölümler, varlıkta izlenen herhangi bir olayı aramanıza olanak sağlayan filtreler içerir. Örneğin, belirli cihazlarla ilgili etkinlikleri avlamak için **Cihaz olayları** bölümündeki filtreleri kullanabilirsiniz.

>[!NOTE]
> Temel filtreler listesinde olmayan bir filtre seçildiğinde, temel filtreler görünümüne dönmek için iki durumlu düğme devre dışı bırakılır veya gri görünür. Sorguyu sıfırlamak veya geçerli sorgudaki mevcut filtreleri kaldırmak için **Tümünü temizle'yi** seçin. Bu, temel filtreler listesini de yeniden etkinleştirir.


Ardından, ikinci açılan menüden seçerek ve gerekirse üçüncü açılan menüde girdiler sağlayarak verileri daha fazla filtrelemek için uygun koşulu ayarlayın:

![Kullanabileceğiniz farklı koşulları gösteren ekran görüntüsü](../../media/guided-hunting/query-builder-operators-equals.png)

**VE** ve **OR** koşullarını kullanarak sorgunuza daha fazla koşul ekleyebilirsiniz. AND, sorgudaki tüm koşulları yerine getiren sonuçlar döndürürken OR, sorgudaki koşulların herhangi birini karşılayan sonuçlar döndürür.  

![VE VEYA işleçlerini gösteren ekran görüntüsü](../../media/guided-hunting/query-builder-operators.png)

Sorgunuzu iyileştirmeniz, belirli tehdit avcılığı ihtiyacınıza yönelik bir sonuç listesi oluşturmak için hacimli kayıtları otomatik olarak gözden geçirmenizi sağlar.

Hangi veri türlerinin desteklendiği ve sorgunuzda ince ayar yapmanızı sağlayacak diğer destekli mod özelliklerini öğrenmek için Bkz. [Sorgunuzu kılavuzlu modda iyileştirme](advanced-hunting-query-builder-details.md).

## <a name="try-sample-query-walk-throughs"></a>Örnek sorgu adım adım kılavuzlarını deneyin

Destekli avcılık hakkında bilgi edinmenin bir diğer yolu da kılavuzlu modda önceden oluşturulmuş örnek sorguları yüklemektir. 

Tehdit avcılığı sayfasının **Başlarken** bölümünde yükleyebileceğiniz üç destekli sorgu örneği sağladık. Sorgu örnekleri, genellikle avcılığınızda ihtiyacınız olan en yaygın filtrelerden ve girişlerden bazılarını içerir. Üç örnek sorgudan herhangi birinin yüklenmesi, destekli modu kullanarak girişi nasıl oluşturabileceğinize ilişkin kılavuzlu bir tur açar.

![Kılavuzlu mod sorgu oluşturucusu kullanmaya başlama sorgu kılavuzunun ekran görüntüsü](../../media/guided-hunting/load-examples.png)

Sorgunuzu oluşturmak için mavi öğretim kabarcıklarındaki yönergeleri izleyin. **Sorguyu çalıştır'ı** seçin.

## <a name="try-some-queries"></a>Bazı sorguları deneyin

### <a name="hunt-for-successful-connections-to-specific-ip"></a>Belirli IP'ye başarılı bağlantılar ara
Belirli bir IP adresiyle başarılı ağ iletişimlerini aramak için önerilen filtreleri almak için "ip" yazmaya başlayın:

![Belirli bir IP ilk filtresine başarılı bağlantılar için kılavuzlu mod sorgu oluşturucu avı ekran görüntüsü](../../media/guided-hunting/query-builder-hunt-ip.png)

IP'nin iletişimin hedefi olduğu belirli bir IP adresini içeren olayları aramak için, IP Adresi Olayları bölümünün altında öğesini seçin `DestinationIPAddress` . Ardından **equals** işlecini seçin. Üçüncü açılan menüye IP yazın ve **Enter tuşuna** basın:

![Belirli IP'ye başarılı bağlantılar için kılavuzlu mod sorgu oluşturucu avı ekran görüntüsü](../../media/guided-hunting/query-builder-hunt-ip-2.png)

Ardından, başarılı ağ iletişim olaylarını arayan ikinci bir koşul eklemek için belirli bir olay türünün filtresini arayın:

![Belirli IP'ye başarılı bağlantılar için kılavuzlu mod sorgu oluşturucu avının ekran görüntüsü, ikinci koşul](../../media/guided-hunting/query-builder-hunt-ip-3.png)

**EventType** filtresi, günlüğe kaydedilen farklı olay türlerini arar. Gelişmiş avcılık tablolarının çoğunda bulunan **ActionType** sütununa eşdeğerdir. Filtre uygulamak üzere bir veya daha fazla olay türü seçmek için bunu seçin. Başarılı ağ iletişim olaylarını aramak için **DeviceNetworkEvents** bölümünü genişletin ve ardından öğesini seçin `ConnectionSuccess`:

![Belirli bir IP üçüncü koşuluna başarılı bağlantılar için kılavuzlu mod sorgu oluşturucu avı ekran görüntüsü](../../media/guided-hunting/query-builder-hunt-ip-4.png)

Son olarak, 52.168.117.170 IP adresine yapılan tüm başarılı ağ iletişimlerini aramak için **Sorguyu çalıştır'ı** seçin:

![Belirli IP sonuçları görünümüne başarılı bağlantılar için kılavuzlu mod sorgu oluşturucu avı ekran görüntüsü](../../media/guided-hunting/query-builder-hunt-ip-5.png)

### <a name="hunt-for-high-confidence-phish-or-spam-emails-delivered-to-inbox"></a>Gelen kutusuna teslim edilen yüksek güvenilirlikli kimlik avı veya istenmeyen posta e-postaları arayın 

Teslim sırasında gelen kutusu klasörüne teslim edilen tüm yüksek güvenilirlikli kimlik avı ve istenmeyen posta e-postalarını aramak için önce olaylar Email altında **ConfidenceLevel** öğesini seçin, **eşittir'i** seçin ve çoklu seçimi destekleyen önerilen kapalı listeden Hem **Kimlik Avı** hem de **İstenmeyen Posta** altında **Yüksek'i** seçin:

![Kılavuzlu mod sorgu oluşturucusu, gelen kutusuna ilk koşula teslim edilen yüksek güvenilirlikli kimlik avı veya istenmeyen posta e-postalarını avlar ekran görüntüsü](../../media/guided-hunting/hunt-phishing-1.png)

Ardından, bu kez klasörü veya **DeliveryLocation, Gelen Kutusu/klasörü** belirterek başka bir koşul ekleyin. 

![Kılavuzlu mod sorgu oluşturucusu, gelen kutusuna teslim edilen yüksek güvenilirlikli kimlik avı veya istenmeyen posta e-postalarının ekran görüntüsü, ikinci koşul](../../media/guided-hunting/hunt-phishing-2.png)




## <a name="see-also"></a>Ayrıca bkz.

- [Sorgunuzu kılavuzlu modda daraltma](advanced-hunting-query-builder-details.md)
- [Sorgu sonuçlarıyla kılavuzlu modda çalışma](advanced-hunting-query-builder-results.md)
 - [Şemayı anlayın](advanced-hunting-schema-tables.md)
