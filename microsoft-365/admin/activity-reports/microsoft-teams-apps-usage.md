---
title: Teams uygulama kullanım raporlarını Microsoft 365 yönetim merkezi
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Microsoft Teams uygulama kullanım raporunu almayı ve kuruluşunuzdaki Teams uygulaması etkinliğiyle ilgili içgörüler kazanmayı öğrenin.
ms.openlocfilehash: 4306ab0c0617bfbba9336991d93305f4b68798d6
ms.sourcegitcommit: 99b174a8d431092b3cf7d650593248671297fd91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68300775"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-apps-usage-reports"></a>Yönetim merkezinde Microsoft 365 Raporları - Microsoft Teams uygulamaları kullanım raporları

Microsoft 365 Raporları panosu, kuruluşunuzdaki ürünler genelindeki etkinliğe genel bakışı gösterir. Bu pano sayesinde her bir üründeki etkinliklerle ilgili daha ayrıntılı bilgi edinmek için ürün düzeyinde raporları ayrıntılı olarak inceleyebilirsiniz. [Raporlara genel bakış konusuna](activity-reports.md) göz atın. **Microsoft Teams uygulama kullanım raporunda**, kuruluşunuzdaki Teams uygulamaları etkinliği hakkında içgörüler elde edebilirsiniz. Bu makalede rapora erişme ve rapordaki çeşitli ölçümleri görüntüleme ve yorumlama işlemleri açıklanmaktadır. 

Uygulamaları yükleyen/kullananları anlamak için bu raporu kullanabilir ve uygulama başına ve kullanıcı başına düzeye ayrıntılı bir bakış sağlayabilirsiniz.

## <a name="whats-in-the-report"></a>Raporda neler var?

Teams uygulama kullanım raporu Microsoft 365 yönetim merkezi kullanılabilir ve veriler iki ayrı rapor aracılığıyla sağlanır:

**Uygulama kullanımı** - Bu rapor şunları yanıtlamanıza yardımcı olur:
- Ortamınızda kaç uygulama yüklü? 
- Ortamınızda en az bir etkin kullanıcı olan uygulama sayısını öğrenin. 
- Platform (Windows, Mac, Web veya mobil) tarafından kaç uygulama kullanılıyor? 
- Uygulamayı kaç etkin kullanıcı ve etkin ekip kullanıyor?

**Kullanıcı etkinliği** - Bu rapor şunları yanıtlamanıza yardımcı olur: 
- Ortamınızda en az bir uygulama yükleyen kullanıcı sayısı nedir? 
- Ortamınızda en az bir uygulama kullanan kullanıcı sayısı nedir? 
- Bir uygulamayı platformlar (Windows, Mac, Web vb.) genelinde kaç kullanıcı kullanıyor? 
- Her kullanıcı kaç uygulama kullandı?

## <a name="how-to-get-to-the-microsoft-teams-apps-usage-report"></a>Microsoft Teams uygulamaları kullanım raporuna erişme

1. Yönetim merkezinde, **Raporlar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Kullanımı</a> sayfasına gidin.
2. Pano giriş sayfasında Microsoft Teams uygulamaları etkinlik kartındaki **Daha fazlasını görüntüle** düğmesine tıklayın.

    :::image type="content" source="../../media/teams-apps-tile.png" alt-text="Microsoft Teams uygulaması.":::

## <a name="considerations"></a>Husus -lar

- Yeni yayımlanan bir uygulamanın kullanım/yükleme verilerinin raporda gösterilmesi yaklaşık beş gün sürebilir. Belirli bir güne ilişkin veriler 48 saat içinde gösterilir. Örneğin, 10 Ocak verileri 12 Ocak'a kadar raporda gösterilmelidir.  

- Tüm yükleme ölçümlerinin başlangıç tarihi Ekim 2021'dir. Yalnızca bu tarihten sonra yüklenen uygulamalar sayılır. 

- Bu rapordaki uygulama kimlikleri Dış (bildirim) Uygulama Kimlikleridir. Teams Yönetici Merkezi'ndeki Uygulamaları Yönetme deneyiminde bu kimliği bir uygulamaya bağlama hakkında daha fazla bilgi için bkz. [Microsoft Teams'de uygulama kurulum ilkelerini yönetme](/microsoftteams/teams-app-setup-policies#install-apps.md). 

- Dışarı Aktar bağlantısını seçerek rapor verilerini bir Excel .csv dosyasına aktarabilirsiniz. Bu, tüm kullanıcılar/uygulamalar için verileri dışarı aktarır ve daha fazla analiz için basit sıralama ve filtreleme yapmanıza olanak tanır. 


## <a name="exploring-the-report---app-usage-tab"></a>Raporu keşfetme - Uygulama kullanımı sekmesi

**Uygulama kullanımı** sekmesini seçerek Teams uygulama kullanımı raporunda **Uygulama kullanımını** görüntüleyebilirsiniz. <br/>

:::image type="content" source="../../media/teams-apps-usage-tab.png" alt-text="Teams kullanıcı etkinliği." lightbox="../../media/teams-apps-usage-tab.png":::

Raporun en üstünde, kuruluşunuz genelindeki uygulamalar arası eğilimleri açıklayan üç grafik göreceksiniz.

- Yüklü uygulamalar
- Kullanılan uygulamalar
- Ortam

Tüm grafikleri sağ üstteki zaman aralığı seçicisine göre filtreleyebilirsiniz. 

:::image type="content" source="../../media/teams-apps-usage-filter.png" alt-text="Microsoft Teams uygulamaları kullanım süresi filtresi.":::

### <a name="apps-installed"></a>Yüklü uygulamalar
Bu grafik, seçilen dönemdeki her bir tarihe kadar kuruluşunuz genelinde uygulama yüklemelerinin toplam sayısını gösterir. Örneğin, 28 Ocak 2022'yi seçerseniz grafikte Ekim 2021 ile 28 Ocak 2022 arasında toplam yükleme sayısı gösterilir. 

:::image type="content" source="../../media/apps-installed.png" alt-text="Microsoft Teams uygulamaları yüklü.":::

### <a name="apps-used"></a>Kullanılan uygulamalar
Bu grafik, seçilen dönemdeki her tarihte kuruluşunuz genelinde kullanılan uygulama sayısını gösterir. Örneğin, 28 Ocak'ı seçerseniz grafikte 28 Ocak'ta kullanılan toplam uygulama sayısı gösterilir.

:::image type="content" source="../../media/apps-used.png" alt-text="Kullanılan Microsoft Teams Uygulamaları.":::
  
### <a name="platform"></a>Ortam 
Bu grafikte, seçilen dönem için platforma göre kuruluşunuz genelinde kullanılan uygulama sayısı gösterilir. Kullanılabilir platformlar Windows, Mac, Mobile (iOS ve Android genelinde) ve Web'dir.

:::image type="content" source="../../media/platform.png" alt-text="Microsoft Teams platformu.":::

### <a name="apps-usage-details-table"></a>Uygulamalar kullanım ayrıntıları tablosu

Bu tabloda, her uygulama için aşağıdaki ölçümleri içeren uygulama başına görünüm gösterilir. Ölçüm sütunlarının bir alt kümesi varsayılan olarak eklenir ve sağ üst kısımdaki **Sütunları seç**"** seçeneğine tıklayarak sütun listesini seçebilir/düzenleyebilirsiniz.

:::image type="content" source="../../media/apps-usage-details.png" alt-text="Uygulama kullanım ayrıntıları." lightbox="../../media/apps-usage-details.png":::

|**Metrik**|**Tanım**|**Varsayılan olarak dahil mi?**|
|:-----|:-----|:-----|
|||
|Uygulama Kimliği   <br/> |Uygulama bildiriminde bulunan dış Uygulama tanımlayıcısı.     <br/> |Evet |
|Son kullanılan tarih    <br/> |Bu uygulamanın kuruluşunuzdaki herkes tarafından en son kullanıldığı tarih.   <br/> |Evet |
|Bu uygulamayı kullanan ekipler   <br/> |Bu uygulamayı kullanan en az bir kullanıcıya sahip olan ayrı Teams ekiplerinin sayısı.   <br/> |Evet |
|Bu uygulamayı kullanan kullanıcılar    <br/> |Kuruluşunuzda bu uygulamayı kullanan farklı kullanıcıların sayısı.   <br/> |Evet |
|Windows'ta kullanılır    <br/> | Bu, uygulamanın Kuruluşunuzdaki en az bir kullanıcı tarafından Windows'ta kullanılıp kullanılmadığını gösterir.  <br/> |Evet |
|Mobil cihazlarda kullanılır  <br/> |Bu, uygulamanın mobil cihazlarda kuruluşunuzdaki en az bir kullanıcı tarafından kullanılıp kullanılmadığını gösterir. <br/> |Evet |
|Web'de kullanılır   <br/> | Bu, uygulamanın kuruluşunuzdaki en az bir kullanıcı tarafından Web'de kullanılıp kullanılmadığını gösterir.  <br/> |Evet |
|Mac'te kullanılır <br/> |Kullanıcının belirtilen süre boyunca düzenlediği geçici toplantı sayısı. <br/>|Hayır |
|Uygulama adı  <br/> |Uygulama bildiriminde mevcut olan bu uygulamanın adı.   <br/>|Hayır |
|Publisher  <br/> |Uygulama bildiriminde olduğu gibi bu uygulamanın yayımcısı. Bu yalnızca genel Mağaza'da yayımlanan uygulamalar için kullanılabilir.  <br/>|Hayır |
|||

## <a name="exploring-the-report---teams-apps-usage-user-activity-tab"></a>Raporu keşfetme - Teams uygulamaları kullanım kullanıcı etkinliği sekmesi

**Kullanıcı etkinliği** sekmesini seçerek Teams uygulama kullanım raporunda **kullanıcı etkinliğini** görüntüleyebilirsiniz. <br/>

:::image type="content" source="../../media/teams-apps-user-activity.png" alt-text="Microsoft Teams kullanıcı etkinliği." lightbox="../../media/teams-apps-user-activity.png":::

Raporun en üstünde, kuruluşunuz genelindeki uygulamalar arası eğilimleri açıklayan üç grafik göreceksiniz.

- Uygulamaları yüklemiş olan kullanıcılar
- Uygulamaları kullanan kullanıcı
- Ortam

Tüm grafikleri sağ üstteki zaman aralığı seçicisine göre filtreleyebilirsiniz. 

:::image type="content" source="../../media/teams-apps-usage-filter.png" alt-text="Microsoft Teams kullanıcı etkinliği zaman filtresi.":::

### <a name="users-who-have-installed-apps"></a>Uygulamaları yüklemiş olan kullanıcılar
Bu grafik, seçilen dönemdeki her bir tarihe kadar bir uygulama yüklemiş olan benzersiz kullanıcıların toplam sayısını gösterir. Örneğin, 28 Ocak 2022'yi seçerseniz grafik, Ekim 2021 ile 28 Ocak 2022 arasında toplam kullanıcı sayısını gösterir.  

:::image type="content" source="../../media/users-who-installed-apps.png" alt-text="Microsoft Teams uygulamaları Uygulamalar grafiğini yükleyen kullanıcılar.":::

### <a name="user-who-have-used-apps"></a>Uygulamaları kullanan kullanıcı
Bu grafik, seçilen dönemdeki her tarihte herhangi bir uygulamayı kullanan benzersiz kullanıcıların sayısını gösterir. Örneğin, 28 Ocak'ı seçerseniz grafik size 28 Ocak'ta toplam kullanıcı sayısını gösterir.  

:::image type="content" source="../../media/users-who-used-apps.png" alt-text="Microsoft Teams uygulamaları Uygulamalar grafiğini kullanan kullanıcılar.":::

### <a name="platform"></a>Ortam 
Bu grafikte, seçilen dönem için platforma göre kuruluşunuz genelinde kullanılan uygulama sayısı gösterilir. Kullanılabilir platformlar Windows, Mac, Mobile (iOS ve Android genelinde) ve Web'dir.  

:::image type="content" source="../../media/user-activity-platform.png" alt-text="Microsoft Teams kullanım kullanıcı etkinliği platformu.":::
  
### <a name="user-activity-details-table"></a>Kullanıcı etkinliği ayrıntıları tablosu

Bu tablo, her uygulama için aşağıdaki ölçümleri içeren kullanıcı başına görünümü gösterir. Ölçüm sütunlarının bir alt kümesi varsayılan olarak eklenir ve sağ üst kısımdaki **Sütunları seç'e** tıklayarak sütun listesini seçebilir/düzenleyebilirsiniz. 

:::image type="content" source="../../media/user-activity-details.png" alt-text="Kullanıcı etkinliği ayrıntıları." lightbox="../../media/user-activity-details.png":::

|**Metrik**|**Tanım**|**Varsayılan olarak dahil mi?**|
|:-----|:-----|:-----|
||||
|Kullanıcı Adı    <br/> |Benzersiz bir kullanıcının Kullanıcı adı. Değer varsayılan olarak gizlidir.  <br/> |Evet |
|Yüklü uygulamalar     <br/> |Kullanıcının yüklediği benzersiz uygulamaların (Mağaza ve özel) sayısı.   <br/> |Evet |
|Kullanılan uygulamalar    <br/> |Kullanıcının açtığı ve/veya kullandığı benzersiz uygulamaların (Mağaza ve özel) sayısı.    <br/> |Evet |
|Ekipte kullanılan uygulamalar     <br/> |Kullanıcının teams ekibinde açtığı ve/veya kullandığı benzersiz uygulamaların (Mağaza ve özel) sayısı.   <br/> |Evet |
|Windows'ta kullanılır    <br/> | Bu, kullanıcının Windows üzerinde herhangi bir uygulama kullanıp kullanmadığını gösterir.  <br/> |Evet |
|Mobil cihazlarda kullanılır  <br/> |Bu, kullanıcının Mobil (iOS veya Android) üzerinde herhangi bir uygulama kullanıp kullanmadığını gösterir. <br/> |Evet |
|Web'de kullanılır   <br/> | Bu, kullanıcının Web'de herhangi bir uygulama kullanıp kullanmadığını gösterir.   <br/> |Evet |
|Mac'te kullanılır <br/> |Bu, kullanıcının Mac'te herhangi bir uygulama kullanıp kullanmadığını gösterir.  <br/>|Hayır |
|||

## <a name="managing-apps-in-the-teams-admin-center"></a>Teams Yönetici Merkezi'nde uygulamaları yönetme

Teams uygulamalarınızı yönetme hakkında daha fazla bilgi için lütfen [Microsoft Teams'deki uygulamalar hakkında](/microsoftteams/deploy-apps-microsoft-teams-landing-page.md) bölümüne bakın.

Bu rapordaki bir uygulamayı Teams Yönetici Center'daki Uygulamaları Yönet deneyimine bağlamak için aşağıdakileri kullanabilirsiniz:

- Uygulama Adı
- Dış Uygulama Kimliği

Dış Uygulama Kimlikleri, Mağaza uygulamalarının Uygulamaları yönet sayfasındaki kimlikle eşdeğerdir. Özel uygulamalar için Uygulamaları Yönet sayfasında Dış Uygulama Kimliği'ni görüntülemek için Microsoft [Teams'de uygulama kurulum ilkelerini yönetme](/microsoftteams/teams-app-setup-policies) bölümündeki yönergeleri izleyerek sütun ayarlarına sütunu ekleyin. Özel bir uygulamanın uygulama ayrıntıları sayfasında da görüntüleyebilirsiniz

 