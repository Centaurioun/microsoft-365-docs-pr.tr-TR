---
title: Microsoft 365 OneDrive İş etkinlik raporları
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Kuruluşunuz için OneDrive kullanım raporunu alın ve her OneDrive kullanıcısının etkinliğini, paylaşılan dosya sayısını ve depolama kullanımını öğrenin.
ms.openlocfilehash: 840e7ea1aec87273940294aaf30c362f1a80dd83
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68196963"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Yönetim merkezinde Microsoft 365 Raporları - OneDrive İş etkinliği

Microsoft 365 Raporları panosu, kuruluşunuzdaki ürünler genelindeki etkinliğe genel bakışı gösterir. Bu pano sayesinde ürünlerin her birindeki etkinliklerle ilgili daha ayrıntılı bilgi edinmek için ürün düzeyinde raporları ayrıntılı olarak inceleyebilirsiniz. [Raporlara genel bakış konusuna](activity-reports.md) göz atın.
  
For example, you can understand the activity of every user licensed to use OneDrive by looking at their interaction with files on OneDrive. It also helps you to understand the level of collaboration going on by looking at the number of files shared.

## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>OneDrive Etkinlik raporuna nasıl ulaşabilirim?

1. Yönetim merkezinde, **Raporlar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Kullanımı</a> sayfasına gidin. 
2. Pano giriş sayfasından OneDrive kartındaki **Daha fazla görüntüle** düğmesine tıklayın.
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>OneDrive İş etkinlik raporunu yorumlama

**Etkinlik** sekmesini seçerek OneDrive raporundaki etkinlikleri görüntüleyebilirsiniz.<br/>![Microsoft 365 raporları - Microsoft OneDrive etkinlik raporu.](../../media/c89df0b0-2611-4acf-9ef7-17cedf7977be.png)

Rapora sütun eklemek veya rapordan sütun kaldırmak için Sütunları **seç'i** seçin.  <br/> ![OneDrive etkinlik raporu - sütunları seçin.](../../media/252f311f-ffde-4e5a-9158-2b822bf86964.png)

Dışarı **Aktar** bağlantısını seçerek rapor verilerini bir Excel .csv dosyasına da aktarabilirsiniz. Bu işlem tüm kullanıcıların verilerini dışarı aktarır ve daha fazla çözümleme yapmak için basit sıralama ve filtreleme işlemlerini kullanmanıza olanak tanır. 

**OneDrive İş aktivite** raporu, son 7 gün, 30 gün, 90 gün veya 180 günlük eğilimler için görüntülenebilir. Ancak raporda belirli bir gün seçerseniz, tablo geçerli tarihten itibaren (raporun oluşturulduğu tarihten değil) 28 güne kadar olan verileri gösterir.
  
|Öğe|Açıklama|
|:-----|:-----|
|**Metrik**|**Tanım**|
|Kullanıcı Adı  <br/> |OneDrive hesabının sahibinin kullanıcı adı.  <br/> |
|Son etkinlik tarihi (UTC)  <br/> |Seçilen tarih aralığı için OneDrive hesabında en son gündeki dosya etkinliği gerçekleşti. Belirli bir tarihte gerçekleştirilen etkinliği görmek için, grafikte doğrudan tarihi seçin.  <br/> |
|Görüntülenen veya düzenlenen dosyalar  <br/> |Kullanıcının karşıya yüklediği, indirdiği, değiştirdiği veya görüntülendiği dosya sayısı.   <br/> |
|Eşitlenen dosyalar  <br/> |Kullanıcının yerel cihazından OneDrive hesabına eşitlenen dosyaların sayısı. <br/> |
|Dahili olarak paylaşılan dosyalar  <br/> | Kuruluştaki kullanıcılarla veya gruplar içindeki kullanıcılarla (dış kullanıcıları içerebilecek) paylaşılan dosyaların sayısı.  <br/> |
|Harici olarak paylaşılan dosyalar  <br/> |Kuruluş dışındaki kullanıcılarla paylaşılan dosyaların sayısı. <br/>|
|Silindi  <br/> | Bu, kullanıcının lisansının kaldırıldığını gösterir.  <br/> NOT: Silinen bir kullanıcının etkinliği, seçilen zaman aralığında bir süre lisanslandığı sürece raporda görüntülenmeye devam eder. **Silindi** sütunu, kullanıcının artık etkin olamayacağını ama rapordaki verilere katkıda bulunduğunu belirlemenize yardımcı olur.  <br/> |
|Silinme tarihi  <br/> |Kullanıcının lisansının kaldırıldığı tarih. <br/>|
|Ürün atandı  <br/> |Kullanıcıya lisans verilen Microsoft 365 ürünleri.|
|||