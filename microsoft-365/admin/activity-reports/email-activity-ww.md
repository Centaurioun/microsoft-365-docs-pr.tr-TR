---
title: E-posta etkinlik raporlarını Microsoft 365 yönetim merkezi
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44
description: Microsoft 365 yönetim merkezi Microsoft 365 Raporları panosunu kullanarak e-posta etkinlik raporu almayı ve kullanıcı e-posta eğilimlerini anlama hakkında bilgi edinin.
ms.openlocfilehash: 2cbea5265976f46be41379843981afb5a5a057de
ms.sourcegitcommit: 5014666778b2d48912c68c2e06992cdb43cfaee3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/07/2022
ms.locfileid: "66662131"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-activity"></a>Yönetim merkezinde Microsoft 365 Raporları - E-posta etkinliği

Microsoft 365 Raporları panosu, kuruluşunuzdaki ürünler genelindeki etkinliğe genel bakışı gösterir. Bu pano sayesinde her bir üründeki etkinliklerle ilgili daha ayrıntılı bilgi edinmek için ürün düzeyinde raporları ayrıntılı olarak inceleyebilirsiniz. [Raporlara genel bakış konusuna](activity-reports.md) göz atın.
  
Örneğin, Raporlar sayfasında kuruluşunuzun içindeki e-posta trafiğinin üst düzey bir görünümünü elde edebilir ve ardından, kuruluşunuzdaki e-posta etkinliğinin eğilimlerini ve tek tek kullanıcılar düzeyindeki ayrıntılarını anlamak için E-posta etkinliği widget'inde detaya gidebilirsiniz.

## <a name="how-to-get-to-the-email-activity-report"></a>E-posta etkinlik raporuna ulaşma

1. Yönetim merkezinde, **Raporlar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Kullanımı</a> sayfasına gidin.
2. **E-posta etkinliği** altında **Daha Fazla Görüntüle'yi** seçin. 
3. **E-posta etkinliği** açılan listesinde **Exchange** \> **E-posta etkinliği'ni** seçin.
  
## <a name="interpret-the-email-activity-report"></a>E-posta etkinlik raporunu yorumlama

Kullanıcınızın e-posta etkinliğini görmek için, **Etkinlik** ve **Kullanıcılar** grafiklerine bakabilirsiniz. 
  
![E-posta etkinlik raporu.](../../media/5eb1d9e9-8106-4843-acb7-c0238c0da816.png)

**E-posta etkinlik** raporu son 7 gün, 30 gün, 90 gün veya 180 günlük eğilimler için görüntülenebilir. Ancak raporda belirli bir gün seçerseniz, tablo geçerli tarihten itibaren (raporun oluşturulduğu tarihten değil) 28 güne kadar olan verileri gösterir. Her rapordaki veriler genellikle son 24-48 saati kapsar.

**Etkinlik** grafiği, kuruluşunuzda devam eden e-posta etkinliğinin miktarına ilişkin eğilimi anlamasına olanak tanır. E-posta gönderme, e-posta okuma, alınan e-posta, toplantı oluşturma veya toplantı etkileşim etkinliklerinin bölünmesini anlayabilirsiniz. 

**Kullanıcı** grafiği, e-posta etkinliklerini oluşturan benzersiz kullanıcı sayısının eğilimini anlamanıza olanak tanır. E-posta gönderme, e-posta okuma, e-posta alma, toplantı oluşturma veya toplantı etkileşim etkinlikleri gerçekleştiren kullanıcıların eğilimine bakabilirsiniz. 

Etkinlik grafiğinde, Y ekseni gönderilen, alınan e-posta, okunan e-posta, oluşturulan toplantı ve etkileşimde bulunan toplantı türündeki etkinlik sayısıdır. 

Kullanıcılar etkinlik grafiğinde, Y ekseni, kullanıcının gönderilen, alınan e-posta, e-posta okuma, toplantı oluşturma veya etkileşimde bulunan toplantı türündeki etkinliğidir. 

Her iki grafikte bulunan X ekseni, söz konusu rapora ait seçilen tarih aralığıdır. 

Göstergede bir öğe seçerek grafikte gördüğünüz seriyi filtreleyebilirsiniz.

 Tabloda, kullanıcı düzeyine göre e-posta etkinliklerinin dökümü gösterilir. Bu, kendisine Exchange ürünü atanmış olan kullanıcıları ve onların e-posta etkinliklerini gösterir.

  
|Öğe|Açıklama|
|:-----|:-----|
|Kullanıcı Adı  |Kullanıcının e-posta adresi. |
|Görünen ad |Kullanıcının tam adı. |
|Silindi |Geçerli durumu silinmiş olan ancak raporun raporlama döneminin bir bölümünde etkin olan kullanıcıyı ifade eder. |
|Silinme tarihi |Kullanıcının silindiği tarih. |
|Son etkinlik tarihi  | Kullanıcının son kez bir e-posta okuma veya gönderme etkinliği gerçekleştirmesi. |
|Eylemleri gönderme |Kullanıcı için e-posta gönderme eyleminin kaç kez kaydedildiğini gösterir.  |
|Eylemleri alma  |Kullanıcı için bir e-posta eyleminin kaç kez kaydedildiğini gösterir. |
|Okuma eylemleri |Kullanıcı için e-posta okuma eyleminin kaydedilme sayısı. |
|Toplantı oluşturma eylemleri  |Bir toplantı isteği gönderme eyleminin kullanıcı için kaç kez kaydedildiğini gösterir. |
|Toplantıyla etkileşime alınan eylemler |Bir toplantı isteğinin kullanıcı için kabul etme, kesin olmayan, reddetme veya iptal etme eyleminin kaç kez kaydedildiğini gösterir. |
|Ürün atandı  |Bu kullanıcıya atanan ürünler.  |


Kuruluşunuzun ilkeleri nedeniyle kişisel kullanıcı bilgilerinin bulunduğu raporları görüntüleyemiyorsanız bu raporların gizlilik ayarını değiştirebilirsiniz. Microsoft 365 yönetim merkezi Etkinlik Raporları'nın **kullanıcı düzeyi ayrıntılarını Nasıl yaparım?** [gizlensin mi](activity-reports.md)? bölümüne göz atın.

Rapora sütun eklemek veya rapordan sütun kaldırmak için Sütunları **seç'i** seçin.  

![E-posta etkinliği raporu - sütunları seçin.](../../media/80ffa0ad-61c5-4a6f-8a1d-5f6730ff7da9.png)

Dışarı **Aktar bağlantısını** seçerek rapor verilerini bir Excel .csv dosyasına da aktarabilirsiniz. Bu işlem tüm kullanıcıların verilerini dışarı aktarır ve daha fazla çözümleme yapmak için basit sıralama ve filtreleme işlemlerini kullanmanıza olanak tanır. 
   
> [!NOTE]
> E-posta etkinlik raporu yalnızca lisansları olan kullanıcılarla ilişkilendirilmiş posta kutuları için kullanılabilir.
