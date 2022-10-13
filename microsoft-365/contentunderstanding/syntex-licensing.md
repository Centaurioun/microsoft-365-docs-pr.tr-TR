---
title: Microsoft Syntex için lisanslama
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
ms.localizationpriority: high
description: Microsoft Syntex için lisanslama hakkında bilgi edinin.
ms.openlocfilehash: c3c78d407aacb260d6b9d6edb9597d9fc3a4c38c
ms.sourcegitcommit: 04e517c7e00323b5c33d8ea937115725cf2cfd4d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2022
ms.locfileid: "68565058"
---
# <a name="licensing-for-microsoft-syntex"></a>Microsoft Syntex için lisanslama

SharePoint Syntex kullanmak için her Syntex kullanıcısı için bir lisansınız olmalıdır. Kiracınızdaki tüm SharePoint Syntex lisanslarını gelecekteki bir tarihte kaldırırsanız (veya deneme süreniz dolarsa), kullanıcılar artık belge anlama veya form işleme modelleri oluşturamaz, yayımlayamaz veya çalıştıramaz. Ayrıca terim deposu raporları, SKOS taksonomisi içeri aktarma ve İçerik türü gönderimi artık kullanılamaz. Hiçbir model, içerik veya meta veri silinmez ve site izinleri değiştirilmez.
 
> [!NOTE] 
> Syntex bir eklenti lisansıdır ve kullanıcıların da Microsoft 365 lisansına sahip olmasını gerektirir.
 
## <a name="tasks-requiring-a-license"></a>Lisans gerektiren görevler
 
Aşağıdaki görevler, bunları gerçekleştiren kullanıcı için [bir Syntex lisansı](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex) gerektirir:
 
- Kitaplığa belge anlama modeli uygulama. (Lisanssız kullanıcılara içerik merkezine erişim verilebilir ve burada belge anlama modelleri oluşturabilir ancak bunları belge kitaplığına uygulayamaz.)
- Kitaplıktaki giriş noktası aracılığıyla form işleme modeli oluşturma
- Belge anlama veya form işleme modelinin uygulandığı kitaplığa içerik yükleme
- İsteğe bağlı olarak belge anlama modeli çalıştırma
- İçerik derlemesi ile modern bir şablon oluşturma
- Modern bir şablondan belge oluşturma
- Gelişmiş meta veri arama kullanımı
- Premium taksonomi hizmetlerinin kullanımı. (Premium taksonomi hizmetleri SKOS tabanlı terim kümesi içeri aktarmayı, kurumsal içerik türlerini hub ile ilişkili sitelere göndermeyi ve terim deposu raporlarını içerir.)

Lisanssız kullanıcılara içerik merkezine erişim izni verilebilir ve burada belge anlama modelleri oluşturabilir ancak bunları belge kitaplığına uygulayamaz.
 
## <a name="cost-of-training-and-running-models"></a>Eğitim ve çalıştırma modellerinin maliyeti
 
Belge anlama modellerini eğitip çalıştırmanın maliyeti Syntex lisansının maliyetine dahildir. Ancak form işleme modelleri hem eğitim hem de çalışma zamanı işleme için AI Builder kapasitesini kullanır. Kapasite, AI Builder'ı kullanacağınız Power Apps ortamına ayrılmalıdır.

Her Syntex lisansı için lisans başına aylık 3.500 AI Builder kredisi ayrılır ve kiracı düzeyinde havuza alınır ve ayda en fazla 1 milyon kredi ayrılır. Bu ayırma her etkin Syntex lisansı için her ay yenilenir. (Kullanılmayan krediler aydan aya yuvarlanmıyor.) 

AI Builder hesaplayıcısı ile size en uygun [AI Builder](https://powerapps.microsoft.com/ai-builder-calculator) kapasitesini tahmin edebilirsiniz.

Özel bir Power Platform ortamı kullanmayı planlıyorsanız, [bu ortama kredi ayırmanız](/power-platform/admin/capacity-add-on) gerekir.

Kredilerinizi ve kullanımınızı denetlemek için [Power Platform yönetim merkezine](https://admin.powerplatform.microsoft.com/resources/capacity) gidin.
  
## <a name="additional-term-store-features"></a>Ek terim deposu özellikleri

Kuruluşunuzda bir veya daha fazla Syntex lisansına sahip olmak, SharePoint yöneticileri için aşağıdaki ek terim deposu özelliklerini etkinleştirir:
 
- SKOS tabanlı terim kümesi içeri aktarma
- Kurumsal içerik türlerini bir merkez sitesine gönderme, bunları ilişkili sitelere ve yeni oluşturulan listelere veya kitaplıklara da ekler
- Yayımlanan terim kümeleri ve bunların kiracınız genelinde kullanımı hakkında içgörüler sağlayan terim deposu raporları


## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Power Platform için lisanslamaya genel bakış](/power-platform/admin/pricing-billing-skus)

[Power Apps ve Power Automate lisanslama hakkında SSS](/power-platform/admin/powerapps-flow-licensing-faq)
