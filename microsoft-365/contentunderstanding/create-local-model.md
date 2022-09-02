---
title: Microsoft SharePoint Syntex ile yerel sharepoint sitesinde model oluşturma
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.service: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: SharePoint Syntex ile yerel bir SharePoint sitesinde yerel model oluşturmayı öğrenin.
ms.openlocfilehash: 6a3d9098ef8f61d2ffe40c2871313ef1b2e2e0f7
ms.sourcegitcommit: 62368e5a48e569c8e475b07d194d7d8ff7d167ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67560515"
---
# <a name="create-a-model-on-a-local-sharepoint-site-with-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex ile yerel sharepoint sitesinde model oluşturma

SharePoint Syntex artık kendi SharePoint sitenizde modelleri yerel olarak oluşturma ve eğitmek için bir seçenek sunar. Bu modeller yalnızca oluşturuldukları sitede kullanılabilir. 

SharePoint sitenizde belge sınıflandırma ve ayıklamayı etkinleştirerek SharePoint Syntex belge kitaplıklarındaki dosyaları sınıflandırmanıza, yeni dosyalardan bilgi ayıklamanıza ve ayıklanan bilgilere göre etkinlikleri otomatikleştirmenize olanak tanır.

Yerel model oluşturmayı etkinleştirdiğinizde, sitenize aşağıdaki listeler ve kitaplıklar eklenir:

- Modeller belge kitaplığı
- Eğitim dosyaları belge kitaplığı
- Açıklama şablonları listesi
- Model kullanım listesi

Bu özellik yalnızca [belge anlama modelleri](apply-a-model.md) ve [önceden oluşturulmuş modeller](prebuilt-models.md) oluşturmak için kullanılabilir. 

## <a name="create-a-model-on-a-local-site"></a>Yerel sitede model oluşturma

1. SharePoint belge kitaplığından çözümlemek istediğiniz dosyaları seçin ve ardından **Sınıflandır ve ayıkla'yı** seçin.

    ![Sınıflandır ve ayıkla seçeneğinin vurgulandığı SharePoint belge kitaplığının ekran görüntüsü.](../media/content-understanding/local-model-classify-and-extract-option.png) 

2. Bu özelliği ilk kez kullandığınızda, sitenizde SharePoint Syntex etkinleştirirsiniz. Aşağıdaki iletiyi görürsünüz.

    ![Belge sınıflandırma ve ayıklama bilgilerini etkinleştir sayfasının ekran görüntüsü.](../media/content-understanding/local-model-first-run-activate-message.png) 

    > [!NOTE]
    > Yönetim görevlerini gerçekleştirmek ve sitenin içeriğini yönetmek için Web Sitesini Yönet iznine sahip olmanız gerekir. Bu bir site sahibi olabilir. Özellik etkinleştirildikten sonra, Listeleri Yönet iznine sahip herkes model oluşturup yönetebilir.

3. Devam etmek için **Etkinleştir'i** seçin. Aşağıdaki iletiyi görürsünüz.

    ![Model oluştur seçeneğini içeren Belge sınıflandırma ve ayıklama etkin iletisinin ekran görüntüsü.](../media/content-understanding/local-model-activated-message.png) 

4. **Model oluştur'u** seçin.

5. **Model oluştur** panelinde modelin adını yazın, model türünü seçin ve ardından **Oluştur'u** seçin.

    ![Model oluştur panelinin ekran görüntüsü.](../media/content-understanding/local-model-create-a-model.png) 

6. [Belgenizin modeli anlamasını eğitmeye](apply-a-model.md) veya seçtiğiniz dosyaları kullanarak [önceden oluşturulmuş modelinizi yapılandırmaya](prebuilt-models.md) devam edin.

7. İşiniz bittiğinde, **Kitaplığa ekle** paneli açılır.

    ![Sitenin ve kitaplıkların uygulandığını gösteren Kitaplığa ekle panelinin ekran görüntüsü.](../media/content-understanding/local-model-add-to-library-panel.png) 

8. **Kitaplığa ekle** panelinde, SharePoint sitenizin adını ve modelin uygulanacağı belge kitaplığını görürsünüz. Modeli farklı bir kitaplığa uygulamak istiyorsanız **Kitaplıklara geri dön'e** tıklayın ve kullanmak istediğiniz kitaplığı seçin. Ardından **Ekle'yi** seçin.

9. Model giriş sayfasındaki **Modelin bu sitede uygulandığı yer** bölümünde, modelin uygulandığı kitaplıkları görebilirsiniz. Modeli sitedeki diğer kitaplıklara uygulamak için **Modeli uygula'yı** seçin. 

    ![Modelin sitedeki uygulandığı yeri gösteren model giriş sayfasının ekran görüntüsü.](../media/content-understanding/local-model-home-page.png) 

