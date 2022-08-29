---
title: tarayıcı kullanım raporlarını Microsoft 365 yönetim merkezi
ms.author: waxiaoyu
author: sarahwxy
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
description: Microsoft 365 yönetim merkezi Microsoft 365 Raporları panosunu kullanarak Microsoft tarayıcı kullanım raporu almayı öğrenin.
ms.openlocfilehash: 2444a93a1a68cd994da19325a8a00af868b6ba16
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2022
ms.locfileid: "67386527"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-browser-usage"></a>Yönetim merkezinde Microsoft 365 Raporları - Microsoft tarayıcı kullanımı

Microsoft 365 Raporları panosu, kuruluşunuzdaki ürünler genelinde bir etkinliğe genel bakış sunar. Her bir üründeki etkinlikler hakkında daha ayrıntılı içgörüler elde etmek için tek tek ürün düzeyi raporlarında detaya gitmenizi sağlar. [Raporlara genel bakış konusuna](activity-reports.md) göz atın. 

Microsoft 365 Yönetici Merkezi'ndeki **Microsoft Tarayıcı Kullanımı raporu**, kullanıcıların Microsoft Edge aracılığıyla Microsoft 365 çevrimiçi hizmetler erişip erişmediğini görmenizi sağlar. Bu rapor içgörüleri, kuruluşunuzu Microsoft Edge'e geçirmenize yardımcı olabilir. Kullanım raporlaması, kuruluşunuzda Microsoft 365 hesaplarında oturum açıp Microsoft Edge tarayıcısını kullanarak Microsoft 365 hizmetlerine erişen toplam kullanıcı sayısını temel alır.

## <a name="how-to-get-to-the-microsoft-browser-usage-report"></a>Microsoft tarayıcı kullanım raporuna erişme

1. Yönetim merkezinde **Rapor** \> <b><a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Kullanımı</a></b> sayfasına gidin.

2. Pano giriş sayfasında, Microsoft tarayıcı kullanım kartındaki **Daha fazla görüntüle** düğmesine tıklayın.


## <a name="interpret-the-microsoft-browser-usage-report"></a>Microsoft tarayıcı kullanım raporunu yorumlama

:::image type="content" alt-text="Microsoft tarayıcı kullanım raporu." source="../../media/95557c88-24ee-417d-a828-96ba00b17aaf.png" lightbox="../../media/95557c88-24ee-417d-a828-96ba00b17aaf.png":::

**Microsoft tarayıcı kullanım** raporu son 7 gün, 30 gün, 90 gün veya 180 günlük eğilimler için görüntülenebilir. 

**Günlük etkin kullanıcılar** grafiği, Microsoft 365 hizmetlerine erişmek için kullanıldığında Microsoft Edge için günlük kullanıcı sayısını gösterir.

**Etkin Kullanıcılar** grafiği, seçilen zaman aralığında Microsoft Edge kullanırken Microsoft 365 hizmetlerine erişen toplam kullanıcı sayısını gösterir.

Rapor, Microsoft 365 Yönetici Merkezi'ndeki kullanım panosundaki etkinlik raporlarına mevcut erişimi olan BT yöneticileriyle sınırlı izinlerle kuruluşunuzun içinde yer alır.

> [!NOTE]
> Toplu Microsoft tarayıcı kullanımı ve kullanıcı düzeyi raporlama kullanılabilir. [Kuruluşunuzun ilkelerine göre kullanıcı düzeyi tanımlaması kaldırılabilir](activity-reports.md#show-user-details-in-the-reports) ve rapor erişimini ayarlamak için [rol tabanlı erişim denetimleri](../../admin/add-users/assign-admin-roles.md) kullanılabilir.


|Öğe|Açıklama|
|:-----|:-----|
|**Kullanıcı Adı** | Microsoft Edge kullanarak Microsoft 365 hizmetlerine bağlanan kullanıcının e-posta adresi.|
| **Kullanılan Microsoft Edge**| Microsoft 365 hizmetleri kullanıcısı Microsoft Edge ile bağlıysa bir onay işareti görüntüler.|

**Rapora sütun** eklemek veya rapordan sütun kaldırmak için Sütunları seç simgesini seçin.

Dışarı **Aktar** bağlantısını seçerek rapor verilerini bir Excel .csv dosyasına da aktarabilirsiniz. Bu, tüm kullanıcılar için verileri dışarı aktarır ve daha fazla analiz için basit toplama, sıralama ve filtreleme gerçekleştirmenize olanak tanır. 
