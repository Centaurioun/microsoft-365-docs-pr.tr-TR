---
title: Microsoft Dynamics 365 müşteri ses etkinliği raporları
f1.keywords:
- NOCSH
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
- MST160
- MET150
- MOE150
description: Raporlar panosunu kullanarak Microsoft Dynamics 365 Customer Voice etkinlik raporu almayı ve lisanslı kullanıcıların nasıl işbirliği kullandığını öğrenin.
ms.openlocfilehash: 79214b6f07e3d7d881406ee22e965abfcc9087d7
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68724385"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>Yönetim merkezinde Microsoft 365 Raporları - Dynamics 365 Customer Voice etkinliği

Microsoft 365 Raporları panosu, kuruluşunuzdaki ürünler genelindeki etkinliğe genel bakışı gösterir. Bu pano sayesinde ürünlerin her birindeki etkinliklerle ilgili daha ayrıntılı bilgi edinmek için ürün düzeyinde raporları ayrıntılı olarak inceleyebilirsiniz. [Raporlara genel bakış konusuna](activity-reports.md) göz atın.
  
Örneğin, Microsoft Dynamics 365 Customer Voice kullanma lisansına sahip her kullanıcının etkinliğini anlamak için Dynamics 365 Customer Voice etkileşimlerine bakabilirsiniz. Ayrıca, oluşturulan Pro Anketlerinin sayısına ve kullanıcıların yanıt verdiği Pro Anketlerine bakarak devam eden işbirliği düzeyini anlamanıza yardımcı olur. 
  
## <a name="how-to-get-to-the-dynamics-365-customer-voice-activity-report"></a>Dynamics 365 Customer Voice etkinlik raporuna erişme

1. Yönetim merkezinde **Raporlar'a** gidin ve **Kullanım'ı** seçin. 
2. Pano giriş sayfasında, Dynamics 365 Customer Voice kartındaki **Daha fazla görüntüle** düğmesine tıklayın.
  
## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>Dynamics 365 Customer Voice etkinlik raporunu yorumlama

**Etkinlik** sekmesini seçerek Dynamics 365 Customer Voice raporundaki etkinlikleri görüntüleyebilirsiniz.

![Microsoft 365 raporları - Microsoft Dynamics 365 Customer Voice etkinlik raporu.](../../media/a7e57d18-1ac8-4d4b-bd70-83361505dc3e.png)

Rapora sütun eklemek veya rapordan sütun kaldırmak için Sütunları **seç'i** seçin.  <br/> ![etkinlik raporunu Dynamics 365 Customer Voice - sütunları seçin.](../../media/5ab66f4b-32eb-4c9b-9683-1157ae9e2c0a.png)

Dışarı **Aktar** bağlantısını seçerek rapor verilerini bir Excel .csv dosyasına da aktarabilirsiniz. Bu işlem tüm kullanıcıların verilerini dışarı aktarır ve daha fazla çözümleme yapmak için basit sıralama ve filtreleme işlemlerini kullanmanıza olanak tanır.

**Dynamics 365 Customer Voice etkinlik** raporu son 7 gün, 30 gün, 90 gün veya 180 günlük eğilimler için görüntülenebilir. Ancak raporda belirli bir gün seçerseniz, tablo geçerli tarihten itibaren (raporun oluşturulduğu tarihten değil) 28 güne kadar olan verileri gösterir.
  
|Öğe|Açıklama|
|:-----|:-----|
|Metrik|Tanım|
|Kullanıcı Adı  |Microsoft Forms etkinliği gerçekleştiren kullanıcının e-posta adresi. |
|Son etkinlik tarihi (UTC)  |Bir form etkinliğinin seçilen tarih aralığı için kullanıcı tarafından gerçekleştirildiği en son tarih. Belirli bir tarihte gerçekleştirilen etkinliği görmek için, grafikte doğrudan tarihi seçin.<br/>Bu, tabloyu yalnızca belirli bir günde etkinliği gerçekleştiren kullanıcılar için dosya etkinliği verilerini görüntüleyecek şekilde filtreler.  |
|Oluşturulan anket sayısı  |Kullanıcının oluşturduğu anket sayısı.   |
|Anket yanıtlarının sayısı  |Anketin dağıtıldığı yanıtlayıcıların yanıtlarının sayısı.|
