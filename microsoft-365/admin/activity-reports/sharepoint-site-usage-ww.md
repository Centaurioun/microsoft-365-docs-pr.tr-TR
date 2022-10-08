---
title: SharePoint site kullanım raporlarını Microsoft 365 yönetim merkezi
f1.keywords:
- NOCSH
ms.author: camillepack
author: camillepack
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Kullanıcıların SharePoint sitelerinde kaç dosya depolayıp kaç tane etkin olarak kullanıldığını ve kullanılan toplam depolama alanını öğrenmek için SharePoint site kullanım raporunu alın.
ms.openlocfilehash: e0d61ce924c09f8ee782a314629089978e42348f
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68172125"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Yönetim merkezinde Microsoft 365 Raporları - SharePoint site kullanımı

Microsoft 365 yöneticisi olarak Raporlar panosu, kuruluşunuzdaki çeşitli ürünlerde etkinliğe genel bakış bilgilerini gösterir. Bu pano size, her ürüne özgü etkinlikler hakkında daha ayrıntılı bilgi edinmek için detaya gitme olanağı tanır. Örneğin, kullanıcıların SharePoint sitelerinde depoladığınız toplam dosya sayısı, etkin olarak kullanılan dosya sayısı ve tüm bu sitelerde kullanılan depolama alanı açısından SharePoint'ten elde ettiğiniz değerin üst düzey bir görünümünü elde edebilirsiniz. Daha sonra, tüm siteler için eğilimleri ve site düzeyinde ayrıntıları anlamak için SharePoint site kullanım raporunda detaya gidebilirsiniz. 

## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>SharePoint sitesi kullanım raporunu alma

1. Yönetim merkezinde, **Raporlar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Kullanımı</a> sayfasına gidin. 
2. Pano giriş sayfasında SharePoint kartındaki **Daha fazla görüntüle** düğmesine tıklayın.

## <a name="show-user-details-in-the-reports"></a>Raporlarda kullanıcı ayrıntılarını gösterme

Raporlar, kuruluşunuzun kullanım verileri hakkında bilgi sağlar. Varsayılan olarak, raporlar kullanıcılar, gruplar ve siteler için tanımlanabilir adlarla bilgileri görüntüler. 1 Eylül 2021'den itibaren, şirketlerin yerel gizlilik yasalarını desteklemesine yardımcı olmak için devam eden taahhüdümüzün bir parçası olarak tüm raporlar için kullanıcı bilgilerini varsayılan olarak gizleyeceğiz.
  
Kullanıcı listeniz şöyle görünür:
  
![Raporlar - anonimleştirilmiş kullanıcı listesi.](../../media/2ed99bce-4978-4ee3-9ea2-4a8db26eef02.png)
  
Genel yöneticiler, kiracıları için bu değişikliği geri alabilir ve kuruluşlarının gizlilik uygulamaları izin verirse tanımlanabilir kullanıcı bilgilerini gösterebilir. Bu, aşağıdaki adımları izleyerek Microsoft 365 yönetim merkezi elde edilebilir:
  
1. Yönetim merkezinde **Ayarlar** \> **Kuruluş Ayarları** \> **Hizmetleri** sayfasına gidin.

2. **Raporlar**'ı seçin. 
  
3. Deyimin işaretini kaldırın **Tüm raporlarda, kullanıcılar, gruplar ve siteler için kimliği kaldırılmış adları görüntüleyin ve** değişikliklerinizi kaydedin. 
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>SharePoint site kullanım raporunu yorumlama

Site kullanımı sekmesini seçerek SharePoint raporunda **site kullanımını** görüntüleyebilirsiniz.

:::image type="content" alt-text="Microsoft 365 raporları - Microsoft SharePoint site kullanım raporu." source="../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png" lightbox="../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png":::

Rapora sütun eklemek veya rapordan sütun kaldırmak için Sütunları **seç'i** seçin.

:::image type="content" alt-text="SharePoint site kullanım raporu - sütunları seçin." source="../../media/71ac3195-c494-40c1-9346-a858125ef6df.png":::

Dışarı **Aktar** bağlantısını seçerek rapor verilerini bir Excel .csv dosyasına da aktarabilirsiniz. Bu işlem tüm kullanıcıların verilerini dışarı aktarır ve daha fazla çözümleme yapmak için basit sıralama ve filtreleme işlemlerini kullanmanıza olanak tanır. 

**SharePoint site kullanım** raporu son 7 gün, 30 gün, 90 gün veya 180 günlük eğilimler için görüntülenebilir. Ancak raporda belirli bir gün seçerseniz, tablo geçerli tarihten itibaren (raporun oluşturulduğu tarihten değil) 28 güne kadar olan verileri gösterir.
  
|Metrik|Açıklama|
|:-----|:-----|
|Site URL'si  |Sitenin tam URL'si. |
|Silindi  |Sitenin silme durumu. Sitelerin silinmiş olarak işaretlenmesi en az 7 gün sürer.  |
|Site sahibi  |Sitenin birincil sahibinin kullanıcı adı.   |
|Site sahibi asıl adı  |Site sahibinin e-posta adresi. |
|Son etkinlik tarihi (UTC)  | Dosya etkinliğinin algılandığı veya sitede bir sayfanın görüntülendiği son tarih.  |
|Site duyarlılık etiketi kimliği  | Sitedeki duyarlılık etiketi.  |
|Dış paylaşım  | Site için dış paylaşım ayarının değeri. Bu değer, site duyarlılık etiketleri tarafından yapılan etkin ayarda yapılan değişiklikleri yansıtmaz. Duyarlılık etiketleri kullanıyorsanız, doğru değerleri almak için [veri erişimi idare raporlarını](/sharepoint/data-access-governance-reports) kullanın.|
|Yönetilmeyen cihaz ilkesi  | Yönetilmeyen cihazlar için site erişim ilkesi.  |
|Coğrafi konum  | Sitenin Coğrafi konumu.  |
|Dosyalar  |Sitedeki dosya sayısı. |
|Etkin dosyalar  | Sitedeki etkin dosyaların sayısı. Belirtilen süre içinde kaydedilmiş, eşitlenmiş, değiştirilmiş veya paylaşılmış bir dosya etkin olarak kabul edilir.<br/> NOT: Rapor için belirtilen süre boyunca dosyalar kaldırıldıysa, raporda gösterilen etkin dosyaların sayısı sitedeki geçerli dosya sayısından daha fazla olabilir.  |
|Kullanılan depolama alanı (MB)  |Sitede kullanılmakta olan depolama alanı miktarı.  |
|Ayrılan depolama alanı (MB)  |Site için ayrılan maksimum depolama alanı miktarı.  |
|Sayfa görünümleri  |Sayfaların sitede görüntülenme sayısı.  |
|Ziyaret edilen sayfalar  |Sitede ziyaret edilen benzersiz sayfaların sayısı.  |
|Anonim bağlantı sayısı  |Sitedeki "Bağlantıya sahip herkes" kullanılarak belgelerin veya klasörlerin paylaşılma sayısı.  |
|Şirket bağlantı sayısı  |Sitedeki "bağlantıyı içeren kuruluşta Kişiler" kullanılarak belge veya klasörlerin paylaşılma sayısı.  |
|Konuk sayısı için güvenli bağlantı  |Sitedeki "belirli kişiler" kullanılarak belge veya klasörlerin paylaşılma sayısı.  |
|Üye sayısı için güvenli bağlantı  |Sitedeki "belirli kişiler" kullanılarak belge veya klasörlerin paylaşılma sayısı.  |
|Kök Web Şablonu  |Siteyi oluşturmak için kullanılan şablon.  <br/> NOT: Verileri farklı site türlerine göre filtrelemek istiyorsanız, verileri dışarı aktarın ve Kök Web Şablonu sütununu kullanın. |

