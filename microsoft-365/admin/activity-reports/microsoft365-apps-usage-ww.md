---
title: Uygulama kullanım raporlarını Microsoft 365 yönetim merkezi
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
description: Uygulamalar genelinde lisanslı kullanıcı etkinliğini ve uygulamaların platformlar arasında nasıl kullanıldığını görmek için Microsoft 365 Uygulamaları kullanım raporu almayı öğrenin.
ms.openlocfilehash: 0a3545c71627c666249b91f2080603ea32ae30f0
ms.sourcegitcommit: 5014666778b2d48912c68c2e06992cdb43cfaee3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/07/2022
ms.locfileid: "66662734"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-apps-usage"></a>Yönetim merkezinde Microsoft 365 Raporları - Microsoft 365 Uygulamaları kullanımı

Microsoft 365 Raporları panosu, kuruluşunuzdaki ürünler genelindeki etkinliğe genel bakışı gösterir. Bu pano sayesinde her bir üründeki etkinliklerle ilgili daha ayrıntılı bilgi edinmek için ürün düzeyinde raporları ayrıntılı olarak inceleyebilirsiniz. [Raporlara genel bakış konusuna](activity-reports.md) göz atın.

Örneğin, Microsoft 365 Uygulamaları uygulamalarını kullanma lisansına sahip her kullanıcının etkinliğini, uygulamalar genelindeki etkinliklerine ve platformlar arasında nasıl kullanıldıklarına bakarak anlayabilirsiniz.

> [!NOTE]
> Paylaşılan bilgisayar etkinleştirmeleri bu rapora dahil değildir.

## <a name="how-to-get-to-the-microsoft-365-apps-usage-report"></a>Microsoft 365 Uygulamaları kullanım raporuna nasıl ulaşabilirsiniz?

1. Yönetim merkezinde, **Raporlar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Kullanımı</a> sayfasına gidin. 
2. Pano giriş sayfasında, Etkin kullanıcılar - Microsoft 365 Uygulamaları kartındaki **Daha fazla görüntüle** düğmesine tıklayın.

## <a name="interpret-the-microsoft-365-apps-usage-report"></a>Microsoft 365 Uygulamaları kullanım raporunu yorumlama

**Kullanıcılar** ve **Platform** grafiklerine bakarak kullanıcınızın Microsoft 365 Uygulamaları etkinliğine ilişkin bir görünüm elde edebilirsiniz.

> [!div class="mx-imgBorder"]
> ![kullanım raporunu Microsoft 365 Uygulamaları.](../../media/0bcf67e6-a6e4-4109-a215-369f9f20ad84.png)

**Microsoft 365 Uygulamaları kullanım** raporu son 7 gün, 30 gün, 90 gün veya 180 günlük eğilimler için görüntülenebilir. Ancak raporda belirli bir gün seçerseniz, tablo geçerli tarihten itibaren (raporun oluşturulduğu tarihten değil) 28 güne kadar olan verileri gösterir.

Her rapordaki veriler genellikle son iki güne kadar kapsar. Altı günde bir, veri kalitesini sağlamak için raporu küçük güncelleştirmelerle yenileyeceğiz.

**Kullanıcılar** görünümü, outlook, Word, Excel, PowerPoint, OneNote ve Teams gibi her uygulama için etkin kullanıcı sayısındaki eğilimi gösterir. "Etkin kullanıcılar", bu uygulamalar içinde herhangi bir kasıtlı eylem gerçekleştiren kullanıcılardır.

**Platformlar** görünümü, windows, Mac, Web ve Mobil gibi her platform için tüm uygulamalarda etkin kullanıcıların eğilimini gösterir.

Kullanıcılar grafiğinde Y ekseni, ilgili uygulamanın benzersiz etkin kullanıcı sayısıdır. Platformlar grafiğinde Y ekseni, ilgili platform için benzersiz kullanıcı sayısıdır. Her iki grafikteki X ekseni, belirli bir platformda bir uygulamanın kullanıldığı tarihtir.

Göstergede bir öğe seçerek grafikte gördüğünüz seriyi filtreleyebilirsiniz. Örneğin, Kullanıcılar grafiğinde, yalnızca her biriyle ilgili bilgileri görmek için Outlook, Word, Excel, PowerPoint, OneDrive veya Teams'i seçin. Bu seçimin değiştirilmesi, altındaki kılavuz tablosundaki bilgileri değiştirmez.

Tablo, kullanıcı başına verilerin dökümünü gösterir. Tablodaki sütunları ekleyebilir veya kaldırabilirsiniz.


|Öğe|Açıklama|
|---|---|
|Kullanıcı Adı|Microsoft Apps etkinliği gerçekleştiren kullanıcının e-posta adresi.|
|Son etkinleştirme tarihi (UTC)|Kullanıcının bir makinede Microsoft 365 Uygulamaları aboneliğini etkinleştirdiği veya paylaşılan bilgisayarda oturum açtığı ve uygulamayı kendi hesabıyla başlattığı en son tarih.|
|Son etkinlik tarihi (UTC)|Kullanıcı tarafından kasıtlı bir etkinliğin gerçekleştirildiği en son tarih. Belirli bir tarihte gerçekleştirilen etkinliği görmek için, grafikte doğrudan tarihi seçin.|


Diğer sütunlar, kullanıcının seçilen dönemde o uygulama için (Microsoft 365 Uygulamaları içinde) o platformda etkin olup olmadığını belirler.

**Rapora sütun** eklemek veya rapordan sütun kaldırmak için Sütunları seç simgesini seçin.

Dışarı **Aktar** bağlantısını seçerek rapor verilerini bir Excel .csv dosyasına da aktarabilirsiniz. Bu, tüm kullanıcılar için verileri dışarı aktarır ve daha fazla analiz için basit toplama, sıralama ve filtreleme gerçekleştirmenize olanak tanır. 