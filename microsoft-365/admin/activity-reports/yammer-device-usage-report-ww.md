---
title: Yammer cihaz kullanım raporlarını Microsoft 365 yönetim merkezi
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
description: Kullanıcılarınızın Yammer'ı hangi cihazlarda kullandığı, cihaz türüne göre günlük kullanıcı sayısı ve kullanıcı başına ayrıntılar hakkında daha fazla bilgi edinmek için Yammer cihaz kullanım raporunu alın.
ms.openlocfilehash: 5be41a946f110c809cc45a8fa9b0cdb21c0a9f35
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68722499"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>Yönetim merkezinde Microsoft 365 Raporları - Yammer cihaz kullanım raporu

Microsoft 365 Raporları panosu, kuruluşunuzdaki ürünler genelindeki etkinliğe genel bakışı gösterir. Bu pano sayesinde her bir üründeki etkinliklerle ilgili daha ayrıntılı bilgi edinmek için ürün düzeyinde raporları ayrıntılı olarak inceleyebilirsiniz. [Raporlara genel bakış konusuna göz atın](activity-reports.md).
  
The Yammer device usage reports give you information about which devices your users are using Yammer on. You can view the number of daily users by device type, and number of users by device type. You can view both over a selected time period. You can also view details per user.
 
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>Yammer cihaz kullanım raporuna nasıl ulaşabilirim?

1. Yönetim merkezinde **Raporlar'a** gidin ve **Kullanım'ı** seçin. 
2. Pano giriş sayfasında Yammer kartında **Daha fazlasını görüntüle'yi** seçin.
  
## <a name="interpret-the-yammer-device-usage-report"></a>Yammer cihaz kullanım raporunu yorumlama

**OneDrive raporunda kullanımı görüntülemek için Cihaz kullanımı** sekmesini seçin.

:::image type="content" source="../../media/e21af4c0-0ad2-4485-8ab1-2f82d7dfa90e.png" alt-text="Microsoft 365 raporları - Microsoft Yammer cihaz kullanım raporu.":::

Rapora sütun eklemek veya rapordan sütun kaldırmak için Sütunları **seç'i** seçin.  

:::image type="content" source="../../media/fc1fc8db-e197-4878-85c7-7ba0d67b9379.png" alt-text="Yammer cihaz kullanım raporu - sütunları seçin.":::

Dışarı Aktar bağlantısını seçerek rapor verilerini bir Excel .csv dosyasına da aktarabilirsiniz. Bu bağlantı tüm kullanıcıların verilerini dışarı aktarır ve daha fazla analiz için basit sıralama ve filtreleme yapmanıza olanak tanır.

**Yammer cihaz kullanım** raporu son 7 gün, 30 gün, 90 gün veya 180 günlük eğilimler için görüntülenebilir. Ancak raporda belirli bir gün seçerseniz, tablo geçerli tarihten itibaren (raporun oluşturulduğu tarihten değil) 28 güne kadar olan verileri gösterir.
  
|Metrik|Tanım|
|:-----|:-----|
|Kullanıcı Adı  |Kullanıcının e-posta adresi. Asıl e-posta adresini görüntüleyebilir veya bu alanın anonim olmasını sağlayabilirsiniz. Bu kılavuzda, Microsoft 365 hesabını kullanarak Yammer'da oturum açan veya çoklu oturum açma kullanarak ağda oturum açan kullanıcılar gösterilir.  |
|Görünen ad |Kullanıcının tam adı. Asıl e-posta adresini görüntüleyebilir veya bu alanın anonim olmasını sağlayabilirsiniz. |
|Kullanıcı durumu |Üç değerden biri: Etkin, Silinmiş veya Askıya Alındı. Bu raporlarda etkin, askıya alınan ve silinen kullanıcıların verileri gösterilir. Bekleyen kullanıcılar ileti gönderemediği, okuyamadığı veya beğenemediği için bekleyen kullanıcıları yansıtmaz.   |
|Durum değiştirme tarihi (UTC)  |Yammer'da kullanıcının durumunun değiştirildiği tarih.  |
|Son etkinlik tarihi (UTC) |Kullanıcının bir Yammer etkinliğine katıldığı son tarih (UTC). |
|Web  |Kullanıcının Web üzerinde Yammer kullanıp kullanmadığını gösterir.   |
|Windows phone   | Kullanıcının Windows telefonunda Yammer kullanıp kullanmadığını gösterir.  |
|Android telefon  |Kullanıcının Android telefonda Yammer kullanıp kullanmadığını gösterir. |
|Iphone  | Kullanıcının iPhone'da Yammer kullanıp kullanmadığını gösterir.  |
|Ipad   |Kullanıcının iPad'de Yammer kullanıp kullanmadığını gösterir. |
|Diğer  |Kullanıcının yammer'ı daha önce listelenmeyen başka bir istemcide kullanıp kullanmadığını gösterir. Buna Yammer Ekleme, SharePoint Web Bölümü, Viva Engage ve Outlook e-postalarını seçme dahildir.  |
