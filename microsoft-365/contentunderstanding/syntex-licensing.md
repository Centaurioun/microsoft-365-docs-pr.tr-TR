---
title: SharePoint Syntex lisansı
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
ms.localizationpriority: high
description: SharePoint Syntex için lisanslama hakkında bilgi edinin
ms.openlocfilehash: 86776af3184e44cb88f17e0164859f0ba0e2f334
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66822279"
---
# <a name="licensing-for-sharepoint-syntex"></a>SharePoint Syntex lisansı

SharePoint Syntex kullanmak için her Syntex kullanıcısına bir lisans gerekir. SharePoint Syntex lisanslarınızı gelecekteki bir tarihte iptal ederseniz (veya deneme süreniz dolarsa), kullanıcılar artık belge anlama veya form işleme modelleri oluşturamaz, yayımlayamaz veya çalıştıramaz. Ayrıca terim deposu raporları, SKOS taksonomisi içeri aktarma ve içerik türü gönderimi artık kullanılamaz. Hiçbir model, içerik veya meta veri silinmez ve site izinleri değiştirilmez.
 
> [!NOTE] 
> SharePoint Syntex bir eklenti lisansıdır ve kullanıcıların da Microsoft 365 lisansına sahip olmasını gerektirir.
 
## <a name="tasks-requiring-a-license"></a>Lisans gerektiren görevler
 
Aşağıdaki görevler, bunları gerçekleştiren kullanıcı için [SharePoint Syntex lisansı](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex) gerektirir:
 
- Kitaplığa belge anlama modeli uygulama. (Lisanssız kullanıcılara içerik merkezine erişim verilebilir ve burada belge anlama modelleri oluşturabilir ancak bunları belge kitaplığına uygulayamaz.)
- Kitaplıktaki giriş noktası aracılığıyla form işleme modeli oluşturma
- Belge anlama veya form işleme modelinin uygulandığı kitaplığa içerik yükleme
- İsteğe bağlı olarak belge anlama modeli çalıştırma
- Premium taksonomi hizmetlerini kullanın. (Premium taksonomi hizmetleri SKOS tabanlı terim kümesi içeri aktarmayı, kurumsal içerik türlerini hub ile ilişkili sitelere göndermeyi ve terim deposu raporlarını içerir.)

Lisanssız kullanıcılara içerik merkezine erişim izni verilebilir ve burada belge anlama modelleri oluşturabilir ancak bunları belge kitaplığına uygulayamaz.
 
## <a name="cost-of-training-and-running-models"></a>Eğitim ve çalıştırma modellerinin maliyeti
 
Belge anlama modellerini eğitip çalıştırmanın maliyeti, SharePoint Syntex lisansının maliyetine dahildir. Ancak form işleme modelleri hem eğitim hem de çalışma zamanı işleme için AI Builder kapasitesini kullanır. Kapasite, AI Builder'ı kullanacağınız Power Apps ortamına ayrılmalıdır.

Her SharePoint Syntex lisansı için lisans başına aylık 3.500 AI Builder kredisi ayrılır ve kiracı düzeyinde havuza alınır ve ayda en fazla 1 milyon kredi ayrılır. Bu ayırma, her etkin SharePoint Syntex lisansı için her ay yenilenir. (Kullanılmayan krediler aydan aya yuvarlanmıyor.) 

AI Builder hesaplayıcısı ile size en uygun [AI Builder](https://powerapps.microsoft.com/ai-builder-calculator) kapasitesini tahmin edebilirsiniz.

Özel bir Power Platform ortamı kullanmayı planlıyorsanız, [bu ortama kredi ayırmanız](/power-platform/admin/capacity-add-on) gerekir.

Kredilerinizi ve kullanımınızı denetlemek için [Power Platform yönetim merkezine](https://admin.powerplatform.microsoft.com/resources/capacity) gidin.
  
## <a name="additional-term-store-features"></a>Ek terim deposu özellikleri

Kuruluşunuzda bir veya daha fazla SharePoint Syntex lisansına sahip olmak, SharePoint yöneticileri için aşağıdaki ek terim deposu özelliklerini etkinleştirir:
 
- SKOS tabanlı terim kümesi içeri aktarma
- Kurumsal içerik türlerini bir merkez sitesine gönderme, bunları ilişkili sitelere ve yeni oluşturulan listelere veya kitaplıklara da ekler
- Yayımlanan terim kümeleri ve bunların kiracınız genelinde kullanımı hakkında içgörüler sağlayan terim deposu raporları


## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Power Platform için lisanslamaya genel bakış](/power-platform/admin/pricing-billing-skus)

[Power Apps ve Power Automate lisanslama hakkında SSS](/power-platform/admin/powerapps-flow-licensing-faq)
