---
title: Microsoft Syntex'teki makbuzlardan bilgi ayıklamak için önceden oluşturulmuş bir model kullanma
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
description: Microsoft Syntex'te önceden oluşturulmuş makbuz modelini kullanmayı öğrenin.
ms.openlocfilehash: c9ac1c5d657e03ff9ac418b36a89275fd7264d5f
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68664281"
---
# <a name="use-a-prebuilt-model-to-extract-information-from-receipts-in-microsoft-syntex"></a>Microsoft Syntex'teki makbuzlardan bilgi ayıklamak için önceden oluşturulmuş bir model kullanma

Microsoft Syntex'teki önceden oluşturulmuş *makbuzlar modeli, satış makbuzlarındaki* önemli bilgileri analiz eder ve ayıklar. API basılı ve el yazısı makbuzları tanır ve satıcı adı, satıcı telefon numarası, işlem tarihi, vergi ve işlem toplamı gibi [önemli makbuz bilgilerini ayıklar](/azure/applied-ai-services/form-recognizer/concept-receipt#field-extraction). Makbuzlar, basılı ve el yazısı makbuzlar da dahil olmak üzere çeşitli biçimlerde ve kalitede olabilir.

Makbuz modelini kullanmak için şu adımları izleyin:

- [1. Adım: Makbuz modeli oluşturma](#step-1-create-a-receipts-model)
- [2. Adım: Analiz etmek için örnek bir dosyayı karşıya yükleme](#step-2-upload-an-example-file-to-analyze)
- [3. Adım: Modeliniz için ayıklayıcıları seçme](#step-3-select-extractors-for-your-model)
- [4. Adım: Modeli uygulama](#step-4-apply-the-model)

## <a name="step-1-create-a-receipts-model"></a>1. Adım: Makbuz modeli oluşturma

Önceden oluşturulmuş [makbuz modeli oluşturmak için Syntex'te model oluşturma başlığındaki](create-syntex-model.md) yönergeleri izleyin. Ardından modelinizi tamamlamak için aşağıdaki adımlarla devam edin.

## <a name="step-2-upload-an-example-file-to-analyze"></a>2. Adım: Analiz etmek için örnek bir dosyayı karşıya yükleme

1. **Modeller** sayfasındaki **Analiz için dosya ekle** bölümünde **Dosya ekle'yi** seçin.

    ![Analiz etmek için dosya ekle bölümünü gösteren yeni modeller sayfasının ekran görüntüsü.](../media/content-understanding/prebuilt-add-file-to-analyze.png) 

2. **Modeli analiz etmek için dosyalar** sayfasında, kullanmak istediğiniz dosyayı bulmak için **Ekle'yi** seçin.

    ![Model analiz etmek için Dosyalar sayfasının Ekle düğmesini gösteren ekran görüntüsü.](../media/content-understanding/prebuilt-add-file-button.png) 

3. **Eğitim dosyaları kitaplığından dosya ekle** sayfasında dosyayı seçin ve ardından **Ekle'yi** seçin.

    ![Eğitim dosyaları kitaplığından dosya ekle sayfasının ekran görüntüsü.](../media/content-understanding/prebuilt-add-file-from-training-library.png) 

4. **Modeli analiz etmek için dosyalar** sayfasında **İleri'yi** seçin.

## <a name="step-3-select-extractors-for-your-model"></a>3. Adım: Modeliniz için ayıklayıcıları seçme

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

## <a name="step-4-apply-the-model"></a>4. Adım: Modeli uygulama

- Değişiklikleri kaydetmek ve model giriş sayfasına dönmek için **Ayıklayıcılar** panelinde **Kaydet ve çık'ı** seçin.

- Modeli kitaplığa uygulamaya hazırsanız belge alanında **İleri'yi** seçin. **Kitaplığa ekle** panelinde, modeli eklemek istediğiniz kitaplığı seçin ve ardından **Ekle'yi** seçin.

## <a name="change-the-view-in-a-document-library"></a>Belge kitaplığındaki görünümü değiştirme

Varsayılan görünümü ayarlama ve belge kitaplığı görünümünü değiştirme hakkında bilgi için bkz. [Belge kitaplığında görünümü seçme](choose-library-view.md).


