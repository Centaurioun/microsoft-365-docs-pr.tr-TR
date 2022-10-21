---
title: Microsoft Syntex ile yerel bir SharePoint sitesinde model oluşturma
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.service: microsoft-syntex
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Microsoft Syntex ile yerel bir SharePoint sitesinde yerel model oluşturmayı öğrenin.
ms.openlocfilehash: dcd514b0d6656f7a4ce4d181aca348016e7ada53
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68660258"
---
# <a name="create-a-model-on-a-local-sharepoint-site-with-microsoft-syntex"></a>Microsoft Syntex ile yerel bir SharePoint sitesinde model oluşturma

<sup>**Şunlar için geçerlidir:**  &ensp; &#10003; Tüm özel modeller &ensp; | &ensp; &#10003; Tüm eğitilen modeller</sup>

Microsoft Syntex, modelleri kendi SharePoint sitenizde yerel olarak oluşturma ve eğitmek için bir seçenek sağlar. Bu modeller yalnızca oluşturuldukları sitede kullanılabilir. 

> [!NOTE]
> Modelinizi bulunabilir ve diğer kullanıcılar için kullanılabilir hale getirmek istiyorsanız bir *kurumsal model* oluşturmanız gerekir. Kurumsal model, [içerik merkezinde](create-a-content-center.md) oluşturulan ve eğitilen bir modeldir.  

SharePoint sitenizde belge sınıflandırma ve ayıklamayı etkinleştirerek Syntex, belge kitaplıklarındaki dosyaları sınıflandırmanıza, yeni dosyalardan bilgi ayıklamanıza ve ayıklanan bilgilere göre etkinlikleri otomatikleştirmenize olanak tanır.

Yerel model oluşturmayı etkinleştirdiğinizde, sitenize aşağıdaki listeler ve kitaplıklar eklenir:

- Modeller belge kitaplığı
- Eğitim dosyaları belge kitaplığı
- Açıklama şablonları listesi
- Model kullanım listesi

Model, yalnızca model sitedeki herhangi bir kitaplığa ilk kez uygulandığında otomatik olarak geçerli siteye yükseltilir. Bu, modeli kullanılabilir site modelleri listesinde bulunabilir ve sitedeki diğer tüm kitaplıklar için kullanılabilir hale getirir. Model sitedeki bir kitaplığa uygulanana kadar kullanılamaz. Benzer şekilde, bir model sitedeki tüm kitaplıklardan kaldırıldığında, kullanılabilir site modelleri listesinden de kaldırılır. 

Bu özellik tüm [model türlerinde](model-types-overview.md) kullanılabilir. 

## <a name="create-a-model-on-a-local-site"></a>Yerel sitede model oluşturma

1. SharePoint belge kitaplığından çözümlemek istediğiniz dosyaları seçin ve ardından **Sınıflandır ve ayıkla'yı** seçin.

    ![Sınıflandır ve ayıkla seçeneğinin vurgulandığı SharePoint belge kitaplığının ekran görüntüsü.](../media/content-understanding/local-model-classify-and-extract-option.png) 

2. Bu özelliği ilk kez kullandığınızda, sitenizde Syntex'i etkinleştirirsiniz. Aşağıdaki iletiyi görürsünüz.

    ![Belge sınıflandırma ve ayıklama bilgilerini etkinleştir sayfasının ekran görüntüsü.](../media/content-understanding/local-model-first-run-activate-message.png) 

    > [!NOTE]
    > Yönetim görevlerini gerçekleştirmek ve sitenin içeriğini yönetmek için Web Sitesini Yönet iznine sahip olmanız gerekir. Bu bir site sahibi olabilir. Özellik etkinleştirildikten sonra, Listeleri Yönet iznine sahip herkes model oluşturup yönetebilir.

3. Devam etmek için **Etkinleştir'i** seçin. Aşağıdaki iletiyi görürsünüz.

    ![Model oluştur seçeneğini içeren Belge sınıflandırma ve ayıklama etkin iletisinin ekran görüntüsü.](../media/content-understanding/local-model-activated-message.png) 

4. **Model oluştur'u** seçin.

5. **Model oluştur** panelinde modelin adını yazın, model türünü seçin ve ardından **Oluştur'u** seçin.

    ![Model oluştur panelinin ekran görüntüsü.](../media/content-understanding/local-model-create-a-model.png) 

6. [Özel modelinizi eğitmeye](apply-a-model.md) veya seçtiğiniz dosyaları kullanarak [eğitilen modelinizi yapılandırmaya](prebuilt-overview.md) devam edin.

7. İşiniz bittiğinde, **Kitaplığa ekle** paneli açılır.

    ![Sitenin ve kitaplıkların uygulandığını gösteren Kitaplığa ekle panelinin ekran görüntüsü.](../media/content-understanding/local-model-add-to-library-panel.png) 

8. **Kitaplığa ekle** panelinde, SharePoint sitenizin adını ve modelin uygulanacağı belge kitaplığını görürsünüz. Modeli farklı bir kitaplığa uygulamak istiyorsanız **Kitaplıklara geri dön'e** tıklayın ve kullanmak istediğiniz kitaplığı seçin. Ardından **Ekle'yi** seçin.

9. Model giriş sayfasındaki **Modelin bu sitede uygulandığı yer** bölümünde, modelin uygulandığı kitaplıkları görebilirsiniz. Modeli sitedeki diğer kitaplıklara uygulamak için **Modeli uygula'yı** seçin. 

    ![Modelin sitedeki uygulandığı yeri gösteren model giriş sayfasının ekran görüntüsü.](../media/content-understanding/local-model-home-page.png) 

> [!NOTE]
> Bir yerel model tek bir kitaplığa uygulandığında, uygulamanın aynı sitedeki diğer kitaplıklara bulunması için kullanılabilir hale gelir.