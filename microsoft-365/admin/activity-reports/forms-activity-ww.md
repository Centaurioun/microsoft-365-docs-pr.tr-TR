---
title: form etkinlik raporlarını Microsoft 365 yönetim merkezi
f1.keywords:
- NOCSH
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
- MST160
- MET150
- MOE150
description: Microsoft 365 Raporları panosunu kullanarak Microsoft Forms etkinlik raporu almayı ve lisanslı kullanıcıların formlarla nasıl etkileşime geçtiğini öğrenin.
ms.openlocfilehash: 106baca93a3cd7078c97d3ca3f5430efc540d4af
ms.sourcegitcommit: 5014666778b2d48912c68c2e06992cdb43cfaee3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/07/2022
ms.locfileid: "66662140"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-activity"></a>Yönetim merkezinde Microsoft 365 Raporları - Forms etkinliği

Microsoft 365 Raporları panosu, kuruluşunuzdaki ürünler genelindeki etkinliğe genel bakışı gösterir. Bu pano sayesinde ürünlerin her birindeki etkinliklerle ilgili daha ayrıntılı bilgi edinmek için ürün düzeyinde raporları ayrıntılı olarak inceleyebilirsiniz. [Raporlara genel bakış konusuna](activity-reports.md) göz atın.
  
Örneğin, formlarla etkileşimlerine bakarak Microsoft Forms kullanma lisansına sahip her kullanıcının etkinliğini anlayabilirsiniz. Ayrıca, kullanıcının yanıt verdiği form ve form sayısına bakarak devam eden işbirliği düzeyini anlamanıza da yardımcı olur.
  
## <a name="how-to-get-to-the-forms-activity-report"></a>Forms etkinlik raporuna erişme

1. Yönetim merkezinde **Raporlar'a** gidin ve **Kullanım'ı** seçin. 
2. Pano giriş sayfasında, Formlar kartındaki **Daha fazla görüntüle** düğmesine tıklayın.
  
## <a name="interpret-the-forms-activity-report"></a>Forms etkinlik raporunu yorumlama

**Etkinlik** sekmesini seçerek Etkinlikleri Formlar raporunda görüntüleyebilirsiniz.

![Microsoft 365 raporları - etkinlik raporu Microsoft Forms.](../../media/275fb0a1-b9d9-4233-8aaf-e7df73cc705f.png)

Rapora sütun eklemek veya rapordan sütun kaldırmak için Sütunları **seç'i** seçin. 

![Formlar etkinlik raporu - sütunları seçin.](../../media/0c9b0b69-5dc7-43ea-8e2c-54407b6ce2ab.png)

Dışarı **Aktar** bağlantısını seçerek rapor verilerini bir Excel .csv dosyasına da aktarabilirsiniz. Bu işlem tüm kullanıcıların verilerini dışarı aktarır ve daha fazla çözümleme yapmak için basit sıralama ve filtreleme işlemlerini kullanmanıza olanak tanır. 

**Formlar etkinlik** raporu son 7 gün, 30 gün, 90 gün veya 180 günlük eğilimler için görüntülenebilir. Ancak raporda belirli bir gün seçerseniz, tablo geçerli tarihten itibaren (raporun oluşturulduğu tarihten değil) 28 güne kadar olan verileri gösterir.
  
|Öğe|Açıklama|
|:-----|:-----|
|Metrik|Tanım|
|Kullanıcı Adı   |Microsoft Forms etkinliği gerçekleştiren kullanıcının e-posta adresi.   |
|Son etkinlik tarihi (UTC)   |Bir form etkinliğinin seçilen tarih aralığı için kullanıcı tarafından gerçekleştirildiği en son tarih. Belirli bir tarihte gerçekleştirilen etkinliği görmek için, grafikte doğrudan tarihi seçin.<br/><br/>Bu, tabloyu yalnızca belirli bir günde etkinliği gerçekleştiren kullanıcılar için dosya etkinliği verilerini görüntüleyecek şekilde filtreler.   |
|Oluşturulan form sayısı   |Kullanıcının oluşturduğu form sayısı.    |
|Yanıtlanan form sayısı  |Kullanıcının yanıt gönderdiği form sayısı.|

