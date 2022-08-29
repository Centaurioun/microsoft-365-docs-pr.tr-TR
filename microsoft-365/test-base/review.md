---
title: Gözden geçirin
description: Eklemeden sonra bölümü gözden geçirin.
search.appverid: MET150
author: mansipatel-usl
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: tinachen
f1.keywords: NOCSH
ms.openlocfilehash: f2c685af5c94260fce717db791eceee6a8a87060
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/11/2022
ms.locfileid: "67316566"
---
# <a name="step-6-review-your-selections-to-create-your-package"></a>6. Adım: Paketinizi oluşturmak için seçimlerinizi gözden geçirin.

1. Bu sekmede hizmet, test ayrıntılarınızı görüntüler ve hızlı bir tamlık denetimi çalıştırır.

    **Doğrulama başarılı** oldu veya **Doğrulama başarısız oldu** iletisi sonraki adımlara geçip geçemeyeceğinizi gösterir.

2. Test ayrıntılarınızı gözden geçirin ve memnunsanız **Oluştur** düğmesine tıklayın.

    :::image type="content" alt-text="Doğrulamayı görüntüleyin." source="Media/validation.png" lightbox="Media/validation.png":::

3. Bu işlem paketinizi Test Temeli ortamına ekler. Paketiniz başarıyla oluşturulursa, paketinizin Azure'da başarıyla yürütülip yürütülemeyeceğini doğrulayan otomatik bir test tetiklenir.

    ![Başarılı sonuç.](Media/successful.png)

    > [!NOTE]
    > Azure portal, paket doğrulamasının başarılı veya başarısız olduğunu bildiren bir bildirim alırsınız.
    >
    > İşlemin 24 saat kadar sürebileceğini, bu nedenle web sayfanızda etkin değilseniz zaman aşımına uğrar ve bu nedenle bildirim, bu isteğe bağlı çalıştırmanın tamamlandığını size bildirmez.

    - Böyle bir durumda paketinizin durumunu **Paketleri yönet** sekmesinde görüntüleyebilirsiniz.

      :::image type="content" alt-text="Paketleri yönetme resmi." source="Media/managepackages.png" lightbox="Media/managepackages.png":::

    - Başarılı testler için sonuçları Zamanlanmış aralıklarla **Test Özeti**, **Güvenlik Güncelleştirmeler Sonuçları** ve **Özellik Güncelleştirmeler Sonuçları** sayfaları üzerinden görülebilir ve bunlar genellikle karşıya yüklemenizden birkaç gün sonra başlar.
  
    - Başarısız testler sırasında yeni bir paket yüklemenizi gerektirir. 

      Daha fazla analiz için **test günlüklerini** **Güvenlik güncelleştirme sonuçları** ve **Özellik güncelleştirmeleri sonuçları** sayfalarından indirebilirsiniz.

    - Yinelenen test hatalarıyla karşılaşırsanız lütfen hatanızın ayrıntılarını içeren testbasepreview@microsoft.com ulaşın.

## <a name="next-steps"></a>Sonraki adımlar

aşağıdaki bağlantı aracılığıyla İçerik Yönergelerimizi keşfedin.

> [!div class="nextstepaction"]
> [Sonraki adım](contentguideline.md)
