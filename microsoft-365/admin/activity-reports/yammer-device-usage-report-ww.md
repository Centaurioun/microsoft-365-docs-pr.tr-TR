---
title: Yammer cihaz kullanım raporlarını Microsoft 365 yönetim merkezi
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
description: Kullanıcılarınızın Yammer'ı hangi cihazlarda kullandığı, cihaz türüne göre günlük kullanıcı sayısı ve kullanıcı başına ayrıntılar hakkında daha fazla bilgi edinmek için Yammer cihaz kullanım raporunu alın.
ms.openlocfilehash: e2ca63fb67b08c96a6b4c5528092b14f55739540
ms.sourcegitcommit: 5014666778b2d48912c68c2e06992cdb43cfaee3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/07/2022
ms.locfileid: "66663074"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>Yönetim merkezinde Microsoft 365 Raporları - Yammer cihaz kullanım raporu

Microsoft 365 Raporları panosu, kuruluşunuzdaki ürünler genelindeki etkinliğe genel bakışı gösterir. Bu pano sayesinde her bir üründeki etkinliklerle ilgili daha ayrıntılı bilgi edinmek için ürün düzeyinde raporları ayrıntılı olarak inceleyebilirsiniz. [Raporlara genel bakış konusuna](activity-reports.md) göz atın.
  
Yammer cihaz kullanım raporları kullanıcılarınızın Yammer'ı hangi cihazlar üzerinde kullandığı hakkında bilgi verir. Cihaz türüne göre günlük kullanıcı sayısını ve cihaz türüne göre kullanıcı sayısını görüntüleyebilirsiniz. Bu bilgilerin ikisi de seçili bir zaman aralığında görüntülenebilir. Dilerseniz, kullanıcı başına ayrıntıları da görüntüleyebilirsiniz.
 
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>Yammer cihaz kullanım raporuna nasıl ulaşabilirim?

1. Yönetim merkezinde **Raporlar'a** gidin ve **Kullanım'ı** seçin. 
2. Pano giriş sayfasında Yammer kartındaki **Daha fazla görüntüle** düğmesine tıklayın.
  
## <a name="interpret-the-yammer-device-usage-report"></a>Yammer cihaz kullanım raporunu yorumlama

**Cihaz kullanımı** sekmesini seçerek OneDrive raporunda kullanımı görüntüleyebilirsiniz.

![Microsoft 365 raporları - Microsoft Yammer cihaz kullanım raporu.](../../media/e21af4c0-0ad2-4485-8ab1-2f82d7dfa90e.png)

Rapora sütun eklemek veya rapordan sütun kaldırmak için Sütunları **seç'i** seçin.  

![Yammer cihaz kullanım raporu - sütunları seçin.](../../media/fc1fc8db-e197-4878-85c7-7ba0d67b9379.png)

Dışarı **Aktar** bağlantısını seçerek rapor verilerini bir Excel .csv dosyasına da aktarabilirsiniz. Bu işlem tüm kullanıcıların verilerini dışarı aktarır ve daha fazla çözümleme yapmak için basit sıralama ve filtreleme işlemlerini kullanmanıza olanak tanır. 

**Yammer cihaz kullanım** raporu son 7 gün, 30 gün, 90 gün veya 180 günlük eğilimler için görüntülenebilir. Ancak raporda belirli bir gün seçerseniz, tablo geçerli tarihten itibaren (raporun oluşturulduğu tarihten değil) 28 güne kadar olan verileri gösterir.
  
|Öğe|Açıklama|
|:-----|:-----|
|**Metrik**|**Tanım**|
|Kullanıcı Adı  <br/> |Kullanıcının e-posta adresi. Asıl e-posta adresini görüntüleyebilir veya bu alanın anonim olmasını sağlayabilirsiniz. Bu kılavuzda, Microsoft 365 hesabını kullanarak Yammer'da oturum açan veya çoklu oturum açma kullanarak ağda oturum açan kullanıcılar gösterilir. <br/> |
|Görünen ad  <br/> |Kullanıcının tam adı. Asıl e-posta adresini görüntüleyebilir veya bu alanın anonim olmasını sağlayabilirsiniz.  <br/> |
|Kullanıcı durumu  <br/> |Üç değerden biri: Etkin, Silinmiş veya Askıya Alındı. Bu raporlarda etkin, askıya alınan ve silinen kullanıcıların verileri gösterilir. Bunlar bekleyen kullanıcıları yansıtmaz, çünkü bekleyen kullanıcılar iletileri gönderemez, okuyamaz veya beğenemez.   <br/> |
|Durum değiştirme tarihi (UTC)  <br/> |Yammer'da kullanıcının durumunun değiştirildiği tarih.  <br/> |
|Son etkinlik tarihi (UTC)  <br/> |Kullanıcının bir Yammer etkinliğine katıldığı son tarih (UTC).  <br/> |
|Web  <br/> |Kullanıcının Web üzerinde Yammer kullanıp kullanmadığını gösterir.  <br/> |
|Windows phone  <br/> | Kullanıcının Windows telefonunda Yammer kullanıp kullanmadığını gösterir.  <br/> |
|Android telefon  <br/> |Kullanıcının Android telefonda Yammer kullanıp kullanmadığını gösterir. <br/>|
|Iphone <br/> | Kullanıcının iPhone'da Yammer kullanıp kullanmadığını gösterir.  <br/> |
|Ipad  <br/> |Kullanıcının iPad'de Yammer kullanıp kullanmadığını gösterir. <br/>|
|Diğer  <br/> |Kullanıcının yammer'ı daha önce listelenmeyen başka bir cihazda kullanıp kullanmadığını gösterir. <br/>|
|||