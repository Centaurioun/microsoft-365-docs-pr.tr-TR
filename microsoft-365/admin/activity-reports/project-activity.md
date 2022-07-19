---
title: 'proje etkinliğini Microsoft 365 yönetim merkezi '
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
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
description: Project etkinlik raporunu almayı ve kuruluşunuzdaki Project etkinliğiyle ilgili içgörüler kazanmayı öğrenin.
ms.openlocfilehash: 202f9e0655f2d96e6897f2803a43264741343381
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66861964"
---
# <a name="microsoft-365-reports-in-the-admin-center---project-activity"></a>Yönetim merkezinde Microsoft 365 Raporları - Proje etkinliği

Microsoft 365 Raporları panosu, kuruluşunuzdaki ürünler genelindeki etkinliğe genel bakışı gösterir. Bu pano sayesinde her bir üründeki etkinliklerle ilgili daha ayrıntılı bilgi edinmek için ürün düzeyinde raporları ayrıntılı olarak inceleyebilirsiniz. [Raporlara genel bakış konusuna](activity-reports.md) göz atın.

**Project etkinlik raporunda**, Project ile etkileşimlerine bakarak Microsoft Project'i kullanma lisansına sahip her kullanıcının etkinliğini anlayabilirsiniz. Ayrıca ziyaret edilen projelerin ve oluşturulan veya düzenlenen görevlerin sayısına bakarak devam eden işbirliği düzeyini anlamanıza da yardımcı olur.

## <a name="how-to-get-to-the-project-activity-report"></a>Project etkinlik raporuna nasıl ulaşabilirsiniz?

1. Yönetim merkezinde, **Raporlar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Kullanımı</a> sayfasına gidin.
2. Pano giriş sayfasında Proje kartındaki **Daha fazla görüntüle** düğmesine tıklayın.

## <a name="interpret-the-project-activity-report"></a>Proje etkinlik raporunu yorumlama

Ortamınızdaki Project etkinliğini ve kullanımını görmek için bu raporu kullanabilirsiniz. Bu raporda dört özet grafik görürsünüz:  <br/>![Microsoft 365 raporları - Proje etkinliği.](../../media/project-activity.png)

- **Etkin kullanıcılar** - Size her gün zaman içindeki günlük etkin kullanıcıları gösterir. Şu anda bu yalnızca Web için Project ve Project Online masaüstü istemcisini içerir.
- **Etkin kullanıcılar (istemciye göre)** - Zaman içinde her gün, istemciye göre ayrılmış günlük etkin kullanıcıları gösterir (Web için Project ve Project Online masaüstü istemcisi).
- **Proje Etkinliği** - Project'in her istemci için zaman içindeki günlük oturum sayısını gösterir (Web için Project ve Project Online masaüstü istemcisi).
- **Görev etkinliği** - Web için Project'te zaman içinde oluşturulan veya düzenlenen görevlerin günlük sayısını gösterir

Raporda ayrıca ortamınızdaki her proje kullanıcısı için etkinliği gösteren bir tablo vardır.

Tabloya sütun eklemek veya tablodan sütun kaldırmak için Sütunları **seç'i** seçin.

![Proje etkinliği raporu - sütunları seçin.](../../media/project-activity-columns.png)

Dışarı **Aktar** bağlantısını seçerek rapor verilerini bir Excel .csv dosyasına da aktarabilirsiniz. Bu işlem tüm kullanıcıların verilerini dışarı aktarır ve daha fazla çözümleme yapmak için basit sıralama ve filtreleme işlemlerini kullanmanıza olanak tanır.

**Proje etkinlik** raporu son 7 gün, 30 gün, 90 gün veya 180 günlük eğilimler için görüntülenebilir. Raporda belirli bir gün seçerseniz, kullanıcı başına veri tablosu o gün kullanıcıların kullanımını görüntüleyecek şekilde güncelleştirilir. Ancak bu özellik yalnızca en son 28 gün boyunca çalışır.

### <a name="privacy-settings-impact-on-the-dashboard"></a>Gizlilik ayarlarının pano üzerindeki etkisi

Kullanıcılar veya yöneticiler gizlilik ayarlarını **Hiçbiri** olarak ayarlarsa, Project Online masaüstü istemcisi için **Project etkinlik** grafiği için doğru ölçümlere sahip değilizdir. Gösterilen sayılar yetersiz sayılacaktır. Gizlilik ayarları hakkında daha fazla bilgi için bkz. [Kurumlar için Microsoft 365 Uygulamaları için gizlilik denetimlerini yönetmek için ilke ayarlarını kullanma](/deployoffice/privacy/manage-privacy-controls.md).

## <a name="user-activity-table"></a>Kullanıcı etkinliği tablosu

Aşağıda, kullanıcı etkinliği tablosundaki her ölçümün tanımları yer alır.

|Öğe|Açıklama|
|:-----|:-----|
|**Metrik**|**Tanım**|
|Kullanıcı adı|Kullanıcının asıl adı.|
|Görünen ad|Kullanıcının tam adı.|
|Son etkinlik tarihi|Özet raporlardaki etkinlikler de dahil olmak üzere, bu satırdaki kullanıcının Project'te etkinliği olduğu en son tarih.|
|Ziyaret edilen projeler (Masaüstü)|Sayfanın sağ üst kısmında seçilen zaman aralığı boyunca Project Online masaüstü istemcisinde kullanıcı tarafından açılan proje sayısı.|
|Ziyaret edilen projeler (Web)| Sayfanın sağ üst kısmında seçilen zaman aralığı boyunca Web için Project'te kullanıcı tarafından oluşturulan görev sayısı.|
|Oluşturulan görevler (Web)|Sayfanın sağ üst kısmında seçilen zaman aralığı boyunca Web için Project'te kullanıcı tarafından oluşturulan görev sayısı.|
|Düzenlenen görevler (Web)|Sayfanın sağ üst kısmında seçilen zaman aralığı boyunca Web için Project'te kullanıcı tarafından düzenlenen görev sayısı.|
|Diğer|Bu değer, kullanıcının sayfanın sağ üst kısmında seçilen zaman aralığında Project Online masaüstü istemcisinde veya Web için Project'te (diğer sütunlar tarafından kapsanmayan) bir etkinlik gerçekleştirmiş olması durumunda geçerlidir. Kullanıcı aksi takdirde, bu değer false olur.|
