---
title: SharePoint etkinlik raporlarını Microsoft 365 yönetim merkezi
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: SharePoint lisanslı kullanıcı dosyası etkileşimleri, paylaşılan dosya sayısı ve depolama kullanımı hakkında bilgi edinmek için SharePoint etkinlik kullanım raporunu alın.
ms.openlocfilehash: 97457e396a9a733183dadf7d10045321c7aed226
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68722648"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>Yönetim merkezinde Microsoft 365 Raporları - SharePoint etkinliği

Microsoft 365 yöneticisi olarak Raporlar panosu, kuruluşunuzdaki çeşitli ürünlerde etkinliğe genel bakış bilgilerini gösterir. Bu pano size, her ürüne özgü etkinlikler hakkında daha ayrıntılı bilgi edinmek için detaya gitme olanağı tanır. [Microsoft 365 yönetim merkezi etkinlik raporlarına](activity-reports.md) göz atın.
  
For example, you can understand the activity of every user licensed to use SharePoint by looking at their interaction with files. It also helps you to understand the level of collaboration going on by looking at the number of files shared.
  
## <a name="how-do-i-get-to-the-sharepoint-activity-report"></a>SharePoint etkinlik raporuna Nasıl yaparım? ulaşabilirsiniz?

1. Yönetim merkezinde, **Raporlar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Kullanımı</a> sayfasına gidin. 
2. Pano giriş sayfasında SharePoint kartındaki **Daha fazla görüntüle** düğmesine tıklayın.
  
## <a name="interpret-the-sharepoint-activity-report"></a>SharePoint etkinlik raporunu yorumlama

**Etkinlik** sekmesini seçerek SharePoint raporundaki etkinlikleri görüntüleyebilirsiniz.<br/>![Microsoft 365 raporları - Microsoft SharePoint etkinlik raporu.](../../media/5a0a96f-0e4f-4fb9-8baa-3262275b3d1f.png)

Rapora sütun eklemek veya rapordan sütun kaldırmak için Sütunları **seç'i** seçin. 

![SharePoint etkinlik raporu - sütunları seçin.](../../media/3c396cd1-9701-4712-8eaa-eb7bba702aa8.png)

Dışarı **Aktar** bağlantısını seçerek rapor verilerini bir Excel .csv dosyasına da aktarabilirsiniz. Bu işlem tüm kullanıcıların verilerini dışarı aktarır ve daha fazla çözümleme yapmak için basit sıralama ve filtreleme işlemlerini kullanmanıza olanak tanır.  

**SharePoint etkinlik** raporu son 7 gün, 30 gün, 90 gün veya 180 günlük eğilimler için görüntülenebilir. Ancak raporda belirli bir gün seçerseniz, tablo geçerli tarihten itibaren (raporun oluşturulduğu tarihten değil) 28 güne kadar olan verileri gösterir.
  
|Öğe|Açıklama|
|:-----|:-----|
|**Metrik**|**Tanım**|
|Kullanıcı Adı  <br/> |SharePoint Sitesinde etkinliği gerçekleştiren kullanıcının e-posta adresi.  <br/> |
|Son etkinlik tarihi (UTC)  <br/> |Seçilen tarih aralığı için bir dosya etkinliğinin gerçekleştirildiği veya bir sayfanın ziyaret edildiği en son tarih. Belirli bir tarihte gerçekleştirilen etkinliği görmek için, grafikte doğrudan tarihi seçin.  <br/> |
|Görüntülenen veya düzenlenen dosyalar  <br/> |Kullanıcının karşıya yüklediği, indirdiği, değiştirdiği veya görüntülendiği dosya sayısı.   <br/> |
|Eşitlenen dosyalar  <br/> |Kullanıcının yerel cihazından SharePoint sitesine eşitlenen dosyaların sayısı. <br/> |
|Dahili olarak paylaşılan dosyalar  <br/> | Kuruluştaki kullanıcılarla veya gruplar içindeki kullanıcılarla (dış kullanıcıları içerebilecek) paylaşılan dosyaların sayısı.  <br/> |
|Harici olarak paylaşılan dosyalar  <br/> |Kuruluş dışındaki kullanıcılarla paylaşılan dosyaların sayısı. <br/>|
|Ziyaret edilen sayfalar  <br/> |Kullanıcının benzersiz sayfalara yaptığı ziyaretler. <br/>|
|Silindi  <br/> | Bu, kullanıcının lisansının kaldırıldığını gösterir.  <br/>  **NOT:** Silinen bir kullanıcının etkinliği, seçilen zaman aralığında bir süre lisanslandığı sürece raporda görüntülenmeye devam eder. Silindi sütunu, kullanıcının artık etkin olamayacağını ama rapordaki verilere katkıda bulunduğunu belirlemenize yardımcı olur.  <br/> |
|Silinme tarihi  <br/> |Kullanıcının lisansının kaldırıldığı tarih. <br/>|
|Ürün atandı  <br/> |Kullanıcıya lisans verilen Microsoft 365 ürünleri.|
|||