---
title: Microsoft Syntex'te kurumsal model oluşturma
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
description: Microsoft Syntex ile özel veya önceden oluşturulmuş bir model oluşturmayı öğrenin.
ms.openlocfilehash: bd2275c40c491626e42f666d2a75dd809c04e584
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68664484"
---
# <a name="create-an-enterprise-model-in-microsoft-syntex"></a>Microsoft Syntex'te kurumsal model oluşturma

<sup>**Şunlar için geçerlidir:**  &ensp; &#10003; Tüm özel modeller &ensp; | &ensp; &#10003; Tüm önceden oluşturulmuş modeller</sup>

[İçerik merkezinde](create-a-content-center.md) bir kurumsal model oluşturulur ve eğitilir ve kullanmak üzere başkaları tarafından bulunabilir. İster özel model oluşturmak ister önceden oluşturulmuş bir model kullanmak istiyorsanız, bunu Microsoft Syntex'teki şu yerlerden herhangi birinden yapabilirsiniz:

- **Modeller** kitaplığından
- [İçerik merkezi](create-a-content-center.md) giriş sayfasından
- Syntex'in etkinleştirildiği sitedeki herhangi bir belge kitaplığından

Bu makale için **Modeller** kitaplığından başlayacağız. Farklı model türleri hakkında bilgi için bkz. [Syntex'te model türlerine genel bakış](model-types-overview.md).

Yerel bir model oluşturmak istiyorsanız bkz. [Yerel SharePoint sitesinde model oluşturma](create-local-model.md).

## <a name="create-a-model"></a>Model oluşturma

**Modeller** kitaplığından **Model oluştur'u** seçin.

![Model oluştur düğmesini gösteren Modeller kitaplığının ekran görüntüsü.](../media/content-understanding/create-a-model-from-the-models-page.png) 

**Model oluşturma seçenekleri** sayfasında iki bölüm vardır:

- [**Özel model eğit**](#train-a-custom-model)
    
- [**Önceden oluşturulmuş bir model ayarlama**](#set-up-a-prebuilt-model)

![Özel modelleri ve önceden oluşturulmuş modelleri gösteren Model oluşturma seçenekleri sayfasının ekran görüntüsü.](../media/content-understanding/options-for-model-creation.png) 

> [!NOTE]
> Tüm model seçenekleri kullanılamayabilir. Bu seçenekler Microsoft 365 yöneticiniz tarafından yapılandırılır.

## <a name="train-a-custom-model"></a>Özel model eğit

**Özel model eğit** bölümünde oluşturabileceğiniz özel model türleri gösterilir.

![Model oluşturma seçenekleri sayfasındaki Özel model oluşturma bölümünün ekran görüntüsü.](../media/content-understanding/build-a-custom-model-section.png) 

- **Öğretme yöntemi** – [Yapılandırılmamış bir belge işleme modeli](document-understanding-overview.md) oluşturur.

- **Serbest biçimli seçim yöntemi** – [Serbest biçimli bir belge işleme modeli](freeform-document-processing-overview.md) oluşturur.

- **Düzen yöntemi** – Yapılandırılmış bir [belge işleme modeli](form-processing-overview.md) oluşturur.

Kullanmak istediğiniz özel modele devam etmek için aşağıdaki sekmelerden birini seçin.

# <a name="teaching-method"></a>[Öğretim yöntemi](#tab/teaching-method)

[Yapılandırılmamış bir belge işleme modeli](document-understanding-overview.md) oluşturmak için **Öğretim yöntemini** kullanın.

1. **Öğretim yöntemi'ne** tıklayın.

2. **Öğretim yöntemi: Ayrıntılar** sayfasında model hakkında daha fazla bilgi bulabilirsiniz. Modeli oluşturmaya devam etmek istiyorsanız **İleri'yi** seçin.

3. **Öğretim yöntemiyle model oluşturma** sayfasının sağ panelinde aşağıdaki bilgileri girin.

    - **Model adı** – Modelin adını girin, örneğin *Hizmet sözleşmeleri*.

    - **Açıklama** – Bu modelin nasıl kullanılacağı hakkında bilgi girin.

        ![Öğretim yöntemiyle model oluşturma sayfasının sağ panelinin ekran görüntüsü.](../media/content-understanding/create-a-model-panel.png) 
    
4. **Gelişmiş ayarlar'ın** altında:

    - **İçerik türü** bölümünde yeni bir içerik türü oluşturmayı veya var olan bir içerik türünü kullanmayı seçin.

    - **Uyumluluk** bölümünde, **Bekletme etiketleri'nin** altında, eklemek istediğiniz bekletme etiketini seçin. **Duyarlılık etiketleri'nin** altında, eklemek istediğiniz duyarlılık etiketini seçin. Dosyanın depolandığı kitaplığa zaten bir uyumluluk etiketi uygulanmışsa, bu etiket gösterilir.

5. Modeli oluşturmaya hazır olduğunuzda **Oluştur'u** seçin.

6. Artık [modeli eğitmeye](create-a-classifier.md) hazırsınız.

# <a name="freeform-selection-method"></a>[Serbest biçimli seçim yöntemi](#tab/freeform-selection-method)

[Serbest biçimli bir belge işleme modeli](freeform-document-processing-overview.md) oluşturmak için **Serbest Biçimli seçim yöntemini** kullanın.

1. **Serbest biçimli seçim yöntemi'ne tıklayın**.

2. **Serbest Biçimli seçim yöntemi: Ayrıntılar** sayfasında model hakkında daha fazla bilgi bulabilirsiniz. Modeli oluşturmaya devam etmek istiyorsanız **İleri'yi** seçin.

3. **Serbest biçimli seçim yöntemiyle model oluştur** sayfasının sağ paneline aşağıdaki bilgileri girin.

    - **Model adı** – Modelin adını girin, örneğin *Hizmet sözleşmeleri*.

    - **Açıklama** – Bu modelin nasıl kullanılacağı hakkında bilgi girin.

        ![Serbest Biçimli seçim yöntemiyle model oluştur sayfasının sağ panelinin ekran görüntüsü.](../media/content-understanding/create-a-model-panel.png) 
    
4. **Gelişmiş ayarlar'ın** altında:

    - **İçerik türü** bölümünde yeni bir içerik türü oluşturmayı veya var olan bir içerik türünü kullanmayı seçin.

    - **Uyumluluk** bölümünde, **Bekletme etiketleri'nin** altında, eklemek istediğiniz bekletme etiketini seçin. Dosyanın depolandığı kitaplığa zaten bir uyumluluk etiketi uygulanmışsa, bu etiket gösterilir.

    > [!NOTE]
    > Duyarlılık etiketleri şu anda **Serbest Biçimli seçim yönteminde** (serbest biçimli belge işleme modelleri) kullanılamaz.

5. Modeli oluşturmaya hazır olduğunuzda **Oluştur'u** seçin.

6. Artık [modeli eğitmeye](train-freeform-document-processing-model.md) hazırsınız.

    > [!NOTE]
    > Yayımlandığında, bu model türü modelin sahibi olmayan diğer kişiler tarafından yeniden kullanılabilir. Şu anda bu model yalnızca model sahibi tarafından düzenlenmekte ve paylaşılabiliyor.

# <a name="layout-method"></a>[Layout yöntemi](#tab/layout-method)

[Yapılandırılmış bir belge işleme modeli](form-processing-overview.md) oluşturmak için **Layout yöntemini** kullanın.

1. **Düzen yöntemi'ni** seçin.

2. **Düzen yöntemi: Ayrıntılar** sayfasında model hakkında daha fazla bilgi bulabilirsiniz. Modeli oluşturmaya devam etmek istiyorsanız **İleri'yi** seçin.

3. **Düzen yöntemiyle model oluşturma** sayfasının sağ panelinde aşağıdaki bilgileri girin.

    - **Model adı** – Modelin adını girin, örneğin *Hizmet sözleşmeleri*.

    - **Açıklama** – Bu modelin nasıl kullanılacağı hakkında bilgi girin.

        ![Düzen yöntemiyle model oluştur sayfasının sağ panelinin ekran görüntüsü.](../media/content-understanding/create-a-model-panel.png) 
    
4. **Gelişmiş ayarlar'ın** altında:

    - **İçerik türü** bölümünde yeni bir içerik türü oluşturmayı veya var olan bir içerik türünü kullanmayı seçin.

    - **Uyumluluk** bölümünde, **Bekletme etiketleri'nin** altında, eklemek istediğiniz bekletme etiketini seçin. Dosyanın depolandığı kitaplığa zaten bir uyumluluk etiketi uygulanmışsa, bu etiket gösterilir.

    > [!NOTE]
    > Duyarlılık etiketleri şu anda **Düzen yönteminde** (yapılandırılmış belge işleme modelleri) kullanılamaz.

5. Modeli oluşturmaya hazır olduğunuzda **Oluştur'u** seçin.

6. Artık [modeli eğitmeye](create-a-form-processing-model.md) hazırsınız.

    > [!NOTE]
    > Yayımlandığında, bu model türü modelin sahibi olmayan diğer kişiler tarafından yeniden kullanılabilir. Şu anda bu model yalnızca model sahibi tarafından düzenlenmekte ve paylaşılabiliyor.

---

## <a name="set-up-a-prebuilt-model"></a>Önceden oluşturulmuş bir model ayarlama

**Önceden oluşturulmuş model ayarlama** bölümünde, kullanabileceğiniz önceden oluşturulmuş model türleri gösterilir. 

![Önceden oluşturulmuş model ayarlama sayfasındaki Önceden oluşturulmuş model kullanma bölümünün ekran görüntüsü.](../media/content-understanding/use-a-trained-model-section.png) 

- **Fatura işleme**

- **Makbuz işleme**

Kullanmak istediğiniz önceden oluşturulmuş modelle devam etmek için aşağıdaki sekmelerden birini seçin.

# <a name="invoice-processing"></a>[Fatura işleme](#tab/invoice-processing)

1. **Fatura işleme'yi** seçin.

2. **Fatura işleme: Ayrıntılar** sayfasında model hakkında daha fazla bilgi bulabilirsiniz. Modeli kullanmaya devam etmek istiyorsanız **İleri'yi** seçin.

3. **Fatura işleme modeli oluştur** sayfasının sağ panelinde aşağıdaki bilgileri girin.

    - **Model adı** – Modelin adını girin, örneğin *Office giderleri*.

    - **Açıklama** – Bu modelin nasıl kullanılacağı hakkında bilgi girin.

        ![Fatura işleme modeli oluştur sayfasının sağ panelinin ekran görüntüsü.](../media/content-understanding/create-a-model-panel.png) 
    
4. **Gelişmiş ayarlar'ın** altında:

    - **İçerik türü** bölümünde yeni bir içerik türü oluşturmayı veya var olan bir içerik türünü kullanmayı seçin.

    - **Uyumluluk** bölümünde, **Bekletme etiketleri'nin** altında, eklemek istediğiniz bekletme etiketini seçin. Dosyanın depolandığı kitaplığa zaten bir bekletme etiketi uygulanmışsa, bu etiket seçilir. 

    > [!NOTE]
    > Duyarlılık etiketleri şu anda önceden oluşturulmuş modeller için kullanılamaz.

5. Modeli oluşturmaya hazır olduğunuzda **Oluştur'u** seçin.

6. Artık [modeli ayarlamayı tamamlamaya](prebuilt-model-invoice.md) hazırsınız.

# <a name="receipt-processing"></a>[Makbuz işleme](#tab/receipt-processing)


1. **Makbuz işleme'yi** seçin.

2. **Makbuz işleme: Ayrıntılar** sayfasında model hakkında daha fazla bilgi bulabilirsiniz. Modeli kullanmaya devam etmek istiyorsanız **İleri'yi** seçin.

2. **Makbuz işleme modeli oluştur** sayfasının sağ panelinde aşağıdaki bilgileri girin.

    - **Model adı** – Modelin adını girin, örneğin *Office giderleri*.

    - **Açıklama** – Bu modelin nasıl kullanılacağı hakkında bilgi girin.

        ![Makbuzları işlemek için model oluştur sayfasının sağ panelinin ekran görüntüsü.](../media/content-understanding/create-a-model-panel.png) 
    
3. **Gelişmiş ayarlar'ın** altında:

    - **İçerik türü** bölümünde yeni bir içerik türü oluşturmayı veya var olan bir içerik türünü kullanmayı seçin.

    - **Uyumluluk** bölümünde, **Bekletme etiketleri'nin** altında, eklemek istediğiniz bekletme etiketini seçin. Dosyanın depolandığı kitaplığa zaten bir bekletme etiketi uygulanmışsa, bu etiket seçilir. 

    > [!NOTE]
    > Duyarlılık etiketleri şu anda önceden oluşturulmuş modeller için kullanılamaz.

4. Modeli oluşturmaya hazır olduğunuzda **Oluştur'u** seçin.

5. Artık [modeli ayarlamayı tamamlamaya](prebuilt-model-receipt.md) hazırsınız.

---



<!---
### Teaching method

Use the **Teaching method** to create an [unstructured document processing model](document-understanding-overview.md).

1. Select **Teaching method**.

2. On the **Teaching method: Details** page, you'll find more information about the model. If you want to proceed with creating the model, select **Next**.

3. On the right panel of the **Create a model with the teaching method** page, enter the following information.

    - **Model name** – Enter the name of the model, for example *Service agreements*.

    - **Description** – Enter information about how this model will be used.

        ![Screenshot of the right panel of the Create a model with the teaching method  page.](../media/content-understanding/create-a-model-panel.png) 
    
4. Under **Advanced settings**:

    - In the **Content type** section, choose whether to create a new content type or to use an existing one.

    - In the **Compliance** section, under **Retention labels**, select the retention label you want to add. Under **Sensitivity labels**, select the sensitivity label you want to add. If a compliance label has been already applied to the library where the file is stored, it will be shown.

5. When you are ready to create the model, select **Create**.

6. You are now ready to [train the model](create-a-classifier).

### Freeform selection method

Use the **Freeform selection method** to create a [freeform document processing model](freeform-document-processing-overview.md).

1. Select **Freeform selection method**.

2. On the **Freeform selection method: Details** page, you'll find more information about the model. If you want to proceed with creating the model, select **Next**.

3. On the right panel of the **Create a model with the freeform selection method** page, enter the following information.

    - **Model name** – Enter the name of the model, for example *Service agreements*.

    - **Description** – Enter information about how this model will be used.

        ![Screenshot of the right panel of the Create a model with the Freeform selection method page.](../media/content-understanding/create-a-model-panel.png) 
    
4. Under **Advanced settings**:

    - In the **Content type** section, choose whether to create a new content type or to use an existing one.

    - In the **Compliance** section, under **Retention labels**, select the retention label you want to add. If a compliance label has been already applied to the library where the file is stored, it will be shown.

    > [!NOTE]
    > Sensitivity labels are not available for **Freeform selection method** (freeform document processing models) at this time.

5. When you are ready to create the model, select **Create**.

6. You are now ready to [train the model](train-freeform-document-processing-model.md).

    > [!NOTE]
    > When published, this model type is available for reuse by others who do not own the model. Currently, this model can be edited and shared for editing only by the model owner.

### Layout method

Use the **Layout method** to create a [structured document processing model](form-processing-overview.md).

1. Select **Layout method**.

2. On the **Layout method: Details** page, you'll find more information about the model. If you want to proceed with creating the model, select **Next**.

3. On the right panel of the **Create a model with the layout method** page, enter the following information.

    - **Model name** – Enter the name of the model, for example *Service agreements*.

    - **Description** – Enter information about how this model will be used.

        ![Screenshot of the right panel of the Create a model with the layout method page.](../media/content-understanding/create-a-model-panel.png) 
    
4. Under **Advanced settings**:

    - In the **Content type** section, choose whether to create a new content type or to use an existing one.

    - In the **Compliance** section, under **Retention labels**, select the retention label you want to add. If a compliance label has been already applied to the library where the file is stored, it will be shown.

    > [!NOTE]
    > Sensitivity labels are not available for **Layout method** (structured document processing models) at this time.

5. When you are ready to create the model, select **Create**.

6. You are now ready to [train the model](create-a-form-processing-model.md).

    > [!NOTE]
    > When published, this model type is available for reuse by others who do not own the model. Currently, this model can be edited and shared for editing only by the model owner.

## Set up a prebuilt model

1. In the **Set up a prebuilt model** section, view the types of prebuilt models you can use. Select the type of prebuilt model you want to learn more about or to start using. 

    ![Screenshot of the Use a prebuilt model section on the Set up a prebuilt model page.](../media/content-understanding/use-a-trained-model-section.png) 

    - [**Invoice processing**](#invoice-processing)

    - [**Receipt processing**](#receipt-processing)

2. When you select a prebuilt model, the next page will show you more information about the model. If you want to continue to create the model, select **Next**.

### Invoice processing

1. Select **Invoice processing**.

2. On the **Invoice processing: Details** page, you'll find more information about the model. If you want to proceed with using the model, select **Next**.

3. On the right panel of the **Create an invoice processing model** page, enter the following information.

    - **Model name** – Enter the name of the model, for example *Office expenses*.

    - **Description** – Enter information about how this model will be used.

        ![Screenshot of the right panel of the Create an invoice processing model page.](../media/content-understanding/create-a-model-panel.png) 
    
4. Under **Advanced settings**:

    - In the **Content type** section, choose whether to create a new content type or to use an existing one.

    - In the **Compliance** section, under **Retention labels**, select the retention label you want to add. If a retention label has been already applied to the library where the file is stored, it will be selected. 

    > [!NOTE]
    > Sensitivity labels are not available for prebuilt models at this time.

5. When you are ready to create the model, select **Create**.

6. You are now ready to [complete setting up the model](prebuilt-model-invoice.md).

### Receipt processing

1. Select **Receipt processing**.

2. On the **Receipt processing: Details** page, you'll find more information about the model. If you want to proceed with using the model, select **Next**.

2. On the right panel of the **Create a receipt processing model** page, enter the following information.

    - **Model name** – Enter the name of the model, for example *Office expenses*.

    - **Description** – Enter information about how this model will be used.

        ![Screenshot of the right panel of the Create a model to process receipts page.](../media/content-understanding/create-a-model-panel.png) 
    
3. Under **Advanced settings**:

    - In the **Content type** section, choose whether to create a new content type or to use an existing one.

    - In the **Compliance** section, under **Retention labels**, select the retention label you want to add. If a retention label has been already applied to the library where the file is stored, it will be selected. 

    > [!NOTE]
    > Sensitivity labels are not available for prebuilt models at this time.

4. When you are ready to create the model, select **Create**.

5. You are now ready to [complete setting up the model](prebuilt-model-receipt.md).
--->