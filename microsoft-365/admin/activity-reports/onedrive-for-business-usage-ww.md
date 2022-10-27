---
title: Microsoft 365 OneDrive İş kullanım raporları
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
- Tier2
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
description: Kuruluşunuzda kullanılan toplam dosya ve depolama alanı sayısı hakkında daha fazla bilgi edinmek için OneDrive İş Kullanım Raporu'na bakın.
ms.openlocfilehash: ff25945543a7a0bbe7f6fb9c0faf1807edd87522
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68722846"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Yönetim merkezinde Microsoft 365 Raporları - OneDrive İş kullanımı

Microsoft 365 Raporları panosu, kuruluşunuzdaki ürünler genelindeki etkinliğe genel bakışı gösterir. Bu pano sayesinde her bir üründeki etkinliklerle ilgili daha ayrıntılı bilgi edinmek için ürün düzeyinde raporları ayrıntılı olarak inceleyebilirsiniz. [Raporlara genel bakış konusuna](activity-reports.md) göz atın.
  
For example, the OneDrive card on the dashboard gives you a high-level view of the value you are getting from OneDrive for Business in terms of the total number of files and storage used across your organization. You can then drill into it to understand the trends of active OneDrive accounts, how many files are users interacting with as well as the storage used. It also gives you details for each user's OneDrive.

## <a name="how-do-i-get-to-the-onedrive-usage-report"></a>OneDrive kullanım raporuna Nasıl yaparım? ulaşabilirsiniz?

1. Yönetim merkezinde **Raporlar'a** gidin ve **Kullanım'ı** seçin. 
2. Pano giriş sayfasından OneDrive kartındaki **Daha fazla görüntüle** düğmesine tıklayın.
  
## <a name="interpret-the-onedrive-usage-report"></a>OneDrive raporunu yorumlama

Kullanım sekmesini seçerek OneDrive raporunda **kullanımı** görüntüleyebilirsiniz.

![Microsoft 365 raporları - Microsoft OneDrive kullanım raporu.](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

Rapora sütun eklemek veya rapordan sütun kaldırmak için Sütunları **seç'i** seçin.  

![OneDrive kullanım raporu - sütunları seçin.](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

Dışarı **Aktar** bağlantısını seçerek rapor verilerini bir Excel .csv dosyasına da aktarabilirsiniz. Bu işlem tüm kullanıcıların verilerini dışarı aktarır ve daha fazla çözümleme yapmak için basit sıralama ve filtreleme işlemlerini kullanmanıza olanak tanır. 

**OneDrive İş kullanım** raporu son 7 gün, 30 gün, 90 gün veya 180 günlük eğilimler için görüntülenebilir. Ancak raporda belirli bir gün seçerseniz, tablo geçerli tarihten itibaren (raporun oluşturulduğu tarihten değil) 28 güne kadar olan verileri gösterir.
  
|Öğe|Açıklama|
|:-----|:-----|
|**Metrik**|**Tanım**|
|Url  <br/> |Kullanıcının OneDrive web adresi. <br/> |
|Silindi  <br/> |OneDrive'ın silme durumu. Hesapların silinmiş olarak işaretlenmesi en az 7 gün sürer.  <br/> |
|Sahibi  <br/> |OneDrive'ın birincil yöneticisinin kullanıcı adı.   <br/> |
|Sahip asıl adı  <br/> |OneDrive sahibinin e-posta adresi. <br/> |
|Son etkinlik tarihi (UTC)  <br/> | OneDrive'da bir dosya etkinliğinin en son gerçekleştirildiği tarih. OneDrive değerinde hiç dosya etkinliği yoksa değer boş olur.  <br/> |
|Dosyalar  <br/> |OneDrive'daki dosya sayısı. <br/>|
|Etkin dosyalar  <br/> | Zaman aralığındaki etkin dosyaların sayısı.<br/> NOT: Rapor için belirtilen süre boyunca dosyalar kaldırıldıysa, raporda gösterilen etkin dosyaların sayısı OneDrive'daki geçerli dosya sayısından daha fazla olabilir. >  Silinmiş kullanıcılar 180 gün süreyle raporlarda gösterilmeye devam eder.  <br/> |
|Kullanılan depolama alanı (MB)  <br/> |OneDrive'ın MB cinsinden kullandığı depolama alanı miktarı. |
|||
   
> [!NOTE]
> Rapor yalnızca geçerli bir OneDrive İş lisansına sahip kullanıcıları içerir.
