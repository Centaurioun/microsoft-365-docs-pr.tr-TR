---
title: posta kutusu kullanım raporlarını Microsoft 365 yönetim merkezi
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: beffbe01-ce2d-4614-9ae5-7898868e2729
description: Kullanıcı posta kutusu olan kullanıcıların etkinlik düzeylerinin yanı sıra her birine ilişkin depolama ve kota bilgilerini öğrenmek için Posta Kutusu kullanım raporunu nasıl alacağınızı öğrenin.
ms.openlocfilehash: 55b5fba9328b43d107a8c34a40a4a5e55aa8a1aa
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68723945"
---
# <a name="microsoft-365-reports-in-the-admin-center---mailbox-usage"></a>Yönetim merkezinde Microsoft 365 Raporları - Posta kutusu kullanımı

**Posta kutusu kullanım raporu**, kullanıcı posta kutusu olan kullanıcılar hakkında bilgi ve e-posta gönderme, okuma, randevu oluşturma, toplantı gönderme, toplantıyı kabul etme, toplantıyı reddetme ve toplantı etkinliğini iptal etme işlemlerine göre her birinin etkinlik düzeyini sağlar. Ayrıca her kullanıcı posta kutusunun ne kadar depolama alanı kullandığı ve kaçının depolama kotalarına yaklaştığı hakkında bilgiler de sunar. Posta kutusu kullanım raporu, kullanıcılar arasında paylaşılan posta kutularıyla ilgili bilgiler de içerir ve paylaşılan posta kutularında depolama ve kota verileri sağlar.
 
## <a name="how-to-get-to-the-mailbox-usage-report"></a>Posta kutusu kullanım raporunu alma

1. Yönetim merkezinde, **Raporlar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Kullanımı</a> sayfasına gidin.
2. **etkinlik Email** altında **Daha Fazla Görüntüle'yi** seçin. 
3. **Email etkinlik** açılan listesinde **Exchange** \> **Posta Kutusu kullanımı'nı** seçin.

## <a name="interpret-the-mailbox-usage-report"></a>Posta kutusu kullanım raporunu yorumlama

**Posta Kutusu**, **Depolama** ve **Kota** grafiklerine bakarak kuruluşunuzun posta kutusu kullanımına ilişkin bir görünüm elde edebilirsiniz.

Paylaşılan posta kutusu bilgilerine erişmek için grafiklerin sağ üst kısmındaki açılan seçimi **Paylaşılan** olarak değiştirin.  Kiracınızda paylaşılan posta kutuları yoksa, paylaşılan posta kutusu bilgilerini görüntüleyemezsiniz.

> [!NOTE]
> Şu anda paylaşılan posta kutuları için özet grafik bilgilerini dışarı aktaramazsınız. Bu bilinen bir sorundur ve gelecekteki bir yinelemede düzeltilecektir.
  
:::image type="content" alt-text="Posta kutusu kullanım raporu." source="../../media/9f610e91-cbc1-4e59-b824-7b1ddd84b738.png" lightbox="../../media/9f610e91-cbc1-4e59-b824-7b1ddd84b738.png":::

**Posta Kutusu kullanımı** raporu, son 7 gün, 30 gün, 90 gün veya 180 günlük eğilimler için görüntülenebilir. Ancak raporda belirli bir gün seçerseniz, tablo geçerli tarihten itibaren (raporun oluşturulduğu tarihten değil) 28 güne kadar olan verileri gösterir. Her rapordaki veriler genellikle son 24-48 saati kapsar.

### <a name="the-mailbox-chart"></a>Posta Kutusu grafiği

**Posta Kutusu** grafiği, kuruluşunuzdaki toplam kullanıcı veya paylaşılan posta kutusu sayısını ve raporlama döneminin herhangi bir gününde etkin olan toplam kullanıcı posta kutusu sayısını gösterir. Bir kullanıcı posta kutusu, e-posta gönderme, okuma, randevu oluşturma, toplantı talebinde bulunma, toplantı kabul etme, reddetme ve toplantı etkinliğini iptal etme durumları varsa etkin kabul edilir.

> [!NOTE]
> Paylaşılan posta kutularının kullanıcı posta kutusundan bağımsız etkinliği yoktur, bu nedenle bu posta kutusu türü seçildiğinde yalnızca paylaşılan posta kutularının sayısı gösterilir.

Posta kutusu grafiğinde:
- Y ekseni, kullanıcı veya paylaşılan posta kutularının sayısıdır. 
- X ekseni, bu rapor için seçilen tarih aralığıdır.

### <a name="the-storage-chart"></a>Depolama grafiği

**Depolama** grafiği, kuruluşunuzda kullanılan depolama miktarını posta kutusu türüne göre gösterir. Depolama Grafiği arşiv posta kutularını içermez. Arşivlemenin otomatik olarak genişletilmesi hakkında daha fazla bilgi için bkz. [Microsoft 365'te otomatik genişletme arşivlemesine genel bakış](../../compliance/autoexpanding-archiving.md).

Depolama grafiğinde:
- Y ekseni, kuruluşunuzdaki kullanıcı veya paylaşılan posta kutuları tarafından kullanılan depolama alanı miktarıdır.
- X ekseni, bu rapor için seçilen tarih aralığıdır.

### <a name="the-quota-chart"></a>Kota grafiği

**Kota** grafiği, her kota kategorisindeki kullanıcı veya paylaşılan posta kutularının sayısını gösterir. Dört kota kategorisi vardır: 
- İyi: Depolama alanı "sorun uyarısı" kotasının altında olan kullanıcıların veya paylaşılan posta kutularının sayısı.
- Uyarı: Depolama alanı "sorun uyarısı" kotasının altında veya üzerinde olan ancak "göndermeyi yasakla" kotasının altında olan kullanıcı veya paylaşılan posta kutularının sayısı.
- Gönderemiyorum: Depolama alanı göndermeyi yasakla kotasının altında veya üzerinde olan, ancak gönderme/alma yasağı kotasının altında olan kullanıcı veya paylaşılan posta kutularının sayısı.
- Gönderme/alma işlemi yapılamıyor: Depolama alanı "gönderme/alma işlemini yasakla" kotasının üzerinde veya üzerinde olan kullanıcıların veya paylaşılan posta kutularının sayısı.

Kota grafiğinde:
- Y ekseni, her depolama kotasında kullanıcı veya paylaşılan posta kutularının sayısıdır.
- X ekseni kota kategorisidir.

Göstergede bir öğe seçerek gördüğünüz grafikleri filtreleyebilirsiniz.

## <a name="mailbox-usage-per-mailbox-table"></a>Posta kutusu tablosu başına posta kutusu kullanımı

Bu tabloda, posta kutusu düzeyinde posta kutusu kullanımının dökümü gösterilir. Tabloya başka sütunlar da ekleyebilirsiniz. 

|Öğe|Açıklama|
|:-----|:-----|
|Alıcı türü |Paylaşılan veya Kullanıcı. |
|Kullanıcı Adı |Kullanıcının e-posta adresi. |
|Görünen Ad  |Kullanıcının tam adı. |
|Silindi |Geçerli durumu silinmiş ancak raporun raporlama döneminin bir bölümünde etkin olan posta kutusu.|
|Silinme tarihi |Posta kutusunun silindiği tarih. |
|Tarih oluşturma | Posta kutusunun oluşturulduğu tarih.  |
|Son etkinlik tarihi | Posta kutusunun son e-posta gönderme veya okuma etkinliği tarihi.   |
|Öğe sayısı|Posta kutusunda bulunan öğelerin toplam sayısı. |
|Kullanılan depolama alanı (MB)|Kullanılan toplam depolama alanı. |
|Silinmiş Öğe Sayısı|Posta kutusunda silinen öğelerin toplam sayısı. |
|Silinmiş Öğe Boyutu (MB)|Posta kutusunda silinen tüm öğelerin toplam boyutu. |
|Sorun uyarı kotası (MB)|Posta kutusu sahibinin depolama kotasına isabet etmek üzere olduğuna dair bir uyarı alacağı depolama sınırı.  |
|Gönderme kotası (MB) yasakla|Posta kutusunun artık e-posta gönderemeyecek olduğu depolama sınırı. |
|Gönderme alma kotası (MB) yasakla|Posta kutusunun artık e-posta gönderip alamayacağı depolama sınırı. |
|Kurtarılabilir Öğe Kotası (MB)|Posta kutusu artık e-postaları silemediğinde posta kutusunda kurtarılabilir (silinmiş) öğeler için depolama sınırı. |
|Arşive Sahip|Posta kutusunun çevrimiçi arşivinin etkinleştirilip etkinleştirilmediğini gösterir. |


Kuruluşunuzun ilkeleri nedeniyle kişisel kullanıcı bilgilerinin bulunduğu raporları görüntüleyemiyorsanız bu raporların gizlilik ayarını değiştirebilirsiniz. [Microsoft 365 yönetim merkezi](activity-reports.md) **Etkinlik Raporları'nın Raporlar bölümünde Kullanıcı ayrıntılarını gizle** bölümüne göz atın.

Rapora sütun eklemek veya rapordan sütun kaldırmak için Sütunları **seç'i** seçin.  <br/> :::image type="content" alt-text="Posta kutusu kullanım raporu - sütunları seçin." source="../../media/ea3d0b18-6ac6-41b0-9bb9-4844f040ea75.png":::

Dışarı **Aktar bağlantısını** seçerek rapor verilerini bir Excel .csv dosyasına da aktarabilirsiniz. 
