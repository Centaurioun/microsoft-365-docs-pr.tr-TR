---
title: Microsoft Syntex'te faturalardan bilgi ayıklamak için önceden oluşturulmuş bir model kullanma
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
description: Microsoft Syntex'te önceden oluşturulmuş bir fatura modelini kullanmayı öğrenin.
ms.openlocfilehash: f2f23a164231089e803c4626c09ffa76f908123c
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68664464"
---
# <a name="use-a-prebuilt-model-to-extract-information-from-invoices-in-microsoft-syntex"></a>Microsoft Syntex'te faturalardan bilgi ayıklamak için önceden oluşturulmuş bir model kullanma

Önceden oluşturulmuş *faturalar modeli, satış faturalarından* önemli bilgileri analiz eder ve ayıklar. API çeşitli biçimlerdeki faturaları tanır ve müşteri adı, fatura adresi, son tarih ve son ödeme tutarı gibi [önemli fatura bilgilerini ayıklar](/azure/applied-ai-services/form-recognizer/concept-invoice#field-extraction).

Fatura modeli kullanmak için şu adımları izleyin:

- 1. Adım: [Fatura modeli oluşturma](#create-an-invoices-model)
- 2. Adım: [Analiz etmek için örnek bir dosyayı karşıya yükleme](#upload-an-example-file-to-analyze)
- 3. Adım: [Modeliniz için ayıklayıcıları seçme](#select-extractors-for-your-model)
- 4. Adım: [Modeli uygulama](#apply-the-model)

## <a name="create-an-invoices-model"></a>Fatura modeli oluşturma

Önceden oluşturulmuş bir fatura modeli oluşturmak için [Syntex'te model oluşturma başlığındaki](create-syntex-model.md) yönergeleri izleyin. Ardından modelinizi tamamlamak için aşağıdaki adımlarla devam edin.


<!---
## Create an invoices model

Follow these steps to create a trained invoices model.

1. From the **Models** page, select **Create a model**.

    ![Screenshot of the Models page showing the Create a model button.](../media/content-understanding/create-a-model-from-the-models-page.png) 


2. On the **View options for classification and extraction** page, in the **Use a trained model** section, select **Invoices**.

    ![Screenshot of the View options for classification and extraction page showing the custom models and trained models.](../media/content-understanding/view-options-for-classification-and-extraction-page.png) 

3. To continue, follow these [instructions to continue to create an invoices model](create-syntex-model.md#invoices).

    > [!NOTE]
    > Sensitivity labels are not available for trained models at this time.
--->

## <a name="upload-an-example-file-to-analyze"></a>Analiz etmek için örnek bir dosyayı karşıya yükleme

1. **Modeller** sayfasındaki **Analiz için dosya ekle** bölümünde **Dosya ekle'yi** seçin.

    ![Analiz etmek için dosya ekle bölümünü gösteren yeni modeller sayfasının ekran görüntüsü.](../media/content-understanding/prebuilt-add-file-to-analyze.png) 

2. **Modeli analiz etmek için dosyalar** sayfasında, kullanmak istediğiniz dosyayı bulmak için **Ekle'yi** seçin.

    ![Model analiz etmek için Dosyalar sayfasının Ekle düğmesini gösteren ekran görüntüsü.](../media/content-understanding/prebuilt-add-file-button.png) 

3. **Eğitim dosyaları kitaplığından dosya ekle** sayfasında dosyayı seçin ve ardından **Ekle'yi** seçin.

    ![Eğitim dosyaları kitaplığından dosya ekle sayfasının ekran görüntüsü.](../media/content-understanding/prebuilt-add-file-from-training-library.png) 

4. **Modeli analiz etmek için dosyalar** sayfasında **İleri'yi** seçin.

## <a name="select-extractors-for-your-model"></a>Modeliniz için ayıklayıcıları seçme

Ayıklayıcı ayrıntıları sayfasında, sağ tarafta belge alanını ve sol tarafta **Ayıklayıcılar** panelini görürsünüz. **Ayıklayıcılar** paneli, belgede tanımlanan ayıklayıcıların listesini gösterir.

   ![Ayıklayıcı ayrıntıları sayfasının ve Ayıklayıcı panelinin ekran görüntüsü.](../media/content-understanding/prebuilt-extractor-details-page.png) 

Belge alanında yeşil renkle vurgulanan varlık alanları, dosyayı analiz ederken model tarafından algılanan öğelerdir. Ayıklamak için bir varlık seçtiğinizde, vurgulanan alan maviye dönüşür. Daha sonra varlığı eklememeye karar verirseniz, vurgulanan alan griye dönüşür. Vurgular, seçtiğiniz ayıklayıcıların geçerli durumunu görmeyi kolaylaştırır.

> [!TIP]
> Varlık alanlarını okumak için gerektiğinde yakınlaştırmak veya uzaklaştırmak için farenizdeki kaydırma tekerleğini veya belge alanının altındaki denetimleri kullanabilirsiniz.

### <a name="select-an-extractor-entity"></a>Ayıklayıcı varlığı seçme

Tercihinize bağlı olarak, belge alanından veya **Ayıklayıcılar** panelinden bir ayıklayıcı seçebilirsiniz.
 
- Belge alanından bir ayıklayıcı seçmek için varlık alanını seçin.

    ![Varlık alanının nasıl seçiliyor olduğunu gösteren belge alanının ekran görüntüsü.](../media/content-understanding/prebuilt-document-area-select-field.png) 

- **Ayıklayıcılar** panelinden bir ayıklayıcı seçmek için varlık adının sağındaki onay kutusunu seçin.

    ![Varlık alanı seçmeyi gösteren Ayıklayıcılar panelinin ekran görüntüsü.](../media/content-understanding/prebuilt-extractors-panel-select-field.png) 

Bir ayıklayıcı seçtiğinizde, belge alanında **Ayıklayıcı seç?** kutusu görüntülenir. Kutu, ayıklayıcı adını, özgün değeri ve ayıklayıcı olarak seçme seçeneğini gösterir. Sayılar veya tarihler gibi belirli veri türleri için ayıklanan bir değer de gösterilir.

   ![Ayıklayıcı ayrıntıları sayfasındaki Ayıklayıcı seç kutusunun ekran görüntüsü.](../media/content-understanding/prebuilt-select-distractor-box.png) 

Özgün değer, belgedeki değerdir. Ayıklanan değer, SharePoint'teki sütuna yazılacak değerdir. Model bir kitaplığa uygulandığında, belgede nasıl görünmesini istediğinizi belirtmek için sütun biçimlendirmesini kullanabilirsiniz.

Kullanmak istediğiniz ek ayıklayıcıları seçmeye devam edin. Bu model yapılandırması için analiz etmek üzere başka dosyalar da ekleyebilirsiniz.

### <a name="rename-an-extractor"></a>Ayıklayıcıyı yeniden adlandır

Ayıklayıcıyı model giriş sayfasından veya **Ayıklayıcılar** panelinden yeniden adlandırabilirsiniz. Model kitaplığa uygulandığında bu adlar sütun adları olarak kullanılacağından, seçili ayıklayıcıları yeniden adlandırmayı düşünebilirsiniz.

Model giriş sayfasından ayıklayıcıyı yeniden adlandırmak için:

1. **Ayıklayıcılar** bölümünde, yeniden adlandırmak istediğiniz ayıklayıcıyı ve ardından **Yeniden Adlandır'ı** seçin.

    ![Yeniden Adlandır seçeneğinin vurgulandığı Ayıklayıcılar bölümünün ekran görüntüsü.](../media/content-understanding/prebuilt-model-page-rename-extractor.png) 

2. **Varlığı ayıklayıcıyı yeniden adlandır** panelinde ayıklayıcının yeni adını girin ve Yeniden **Adlandır'ı** seçin.

**Ayıklayıcılar** panelinden ayıklayıcıyı yeniden adlandırmak için:

1. Yeniden adlandırmak istediğiniz ayıklayıcıyı ve ardından **Yeniden Adlandır'ı** seçin.

    ![Ayıklayıcıyı yeniden adlandırmayı gösteren Ayıklayıcılar panelinin ekran görüntüsü.](../media/content-understanding/prebuilt-extractors-panel-rename-field.png) 

2. **Ayıklayıcıyı yeniden adlandır** kutusuna ayıklayıcının yeni adını girin ve yeniden **adlandır'ı** seçin.

## <a name="apply-the-model"></a>Modeli uygulama

- Değişiklikleri kaydetmek ve model giriş sayfasına dönmek için **Ayıklayıcılar** panelinde **Kaydet ve çık'ı** seçin.

- Modeli kitaplığa uygulamaya hazırsanız belge alanında **İleri'yi** seçin. **Kitaplığa ekle** panelinde, modeli eklemek istediğiniz kitaplığı seçin ve ardından **Ekle'yi** seçin.

## <a name="change-the-view-in-a-document-library"></a>Belge kitaplığındaki görünümü değiştirme

Varsayılan görünümü ayarlama ve belge kitaplığı görünümünü değiştirme hakkında bilgi için bkz. [Belge kitaplığında görünümü seçme](choose-library-view.md).

<!---
[!INCLUDE [Change the view in a document library](../includes/change-library-view.md)]
--->
