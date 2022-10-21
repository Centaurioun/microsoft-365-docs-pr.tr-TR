---
title: Microsoft Syntex'te modele bekletme etiketi uygulama
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
description: Microsoft Syntex'te bir modele bekletme etiketi uygulamayı öğrenin.
ms.openlocfilehash: 7fb57fa2e33bde1a3534ffbb6c4541587072b730
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68661643"
---
# <a name="apply-a-retention-label-to-a-model-in-microsoft-syntex"></a>Microsoft Syntex'te modele bekletme etiketi uygulama

<sup>**Şunlar için geçerlidir:**  &ensp; &#10003; Yapılandırılmamış belge işleme &ensp; | &ensp; &#10003; Yapılandırılmış belge işleme &ensp;| &ensp; &#10003; Tüm önceden oluşturulmuş modeller</sup>

<!---
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>
--->

Microsoft Syntex'te bir modele [kolayca bekletme etiketi](../compliance/retention.md) uygulayabilirsiniz.

> [!Note]
> Serbest Biçimli belge işleme modellerinde bekletme etiketleri henüz kullanılamıyor.

Bekletme etiketleri, modellerinizin tanımladığınız belgelere bekletme ayarları uygulamanıza olanak tanır.  Örneğin, modelinizin yalnızca belge kitaplığınıza yüklenen *Sigorta bildirimi* belgelerini tanımlamasını değil, aynı zamanda bu belgelerin belirtilen süre boyunca belge kitaplığından silinememesi için (örneğin, sonraki beş ay) onlara bir *İş* saklama etiketi uygulamasını istiyorsunuz.

Modelinizin giriş sayfasındaki model ayarlarınızdan modelinize önceden var olan bir bekletme etiketi uygulayabilirsiniz. 

## <a name="add-a-retention-label-to-an-unstructured-document-processing-model-or-a-prebuilt-model"></a>Yapılandırılmamış belge işleme modeline veya önceden oluşturulmuş bir modele bekletme etiketi ekleme

> [!Important]
> Bekletme etiketlerinin yapılandırılmamış belge işleme veya önceden oluşturulmuş modellerinize uygulanabilmek için Microsoft Purview uyumluluk portalı [oluşturulması](../compliance/file-plan-manager.md#create-retention-labels) ve [yayımlanması](../compliance/create-apply-retention-labels.md#how-to-publish-retention-labels) gerekir.

1. Model giriş sayfasında **Model ayarları'nı** seçin.

2. **Model ayarları'ndaki** **Güvenlik ve uyumluluk** bölümünde **, modele** uygulayabileceğiniz bekletme etiketlerinin listesini görmek için Bekletme etiketi menüsünü seçin.

 ![Bekletme etiketi menüsü.](../media/content-understanding/retention-labels-menu.png)

3. Modele uygulamak istediğiniz bekletme etiketini seçin ve ardından **Kaydet'i** seçin.

Bekletme etiketini modelinize uyguladıktan sonra şunun için uygulayabilirsiniz:

- Yeni belge kitaplığı
- Modelin zaten uygulandığı belge kitaplığı
 
### <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>Bekletme etiketini modelin zaten uygulandığı belge kitaplığına uygulama

Yapılandırılmamış belge işleme modeliniz veya önceden oluşturulmuş modeliniz bir belge kitaplığına zaten uygulanmışsa, belge kitaplığına uygulamak üzere bekletme etiketi güncelleştirmenizi eşitlemek için aşağıdakileri yapabilirsiniz:

1. Modelinizin giriş sayfasındaki **Bu modelle kitaplıklar** bölümünde, bekletme etiketi güncelleştirmesini uygulamak istediğiniz belge kitaplığını seçin.

2. **Eşitle'yi** seçin.

   ![Eşitleme modeli.](../media/content-understanding/sync-model.png)</br> 

Güncelleştirmeyi uyguladıktan ve modelinizle eşitledikten sonra, aşağıdaki adımları uygulayarak uygulandığını onaylayabilirsiniz:

1. İçerik merkezindeki **Bu modelle kitaplıklar** bölümünde, güncelleştirilmiş modelinizin uygulandığı kitaplığı seçin.

2. Belge kitaplığı görünümünüzde, model özelliklerini denetlemek için bilgi simgesini seçin.

3. **Etkin modeller** listesinde güncelleştirilmiş modelinizi seçin.

4. **Bekletme etiketi** bölümünde, uygulanan bekletme etiketinin adını görürsünüz.

Belge kitaplığınızdaki modelinizin görünüm sayfasında yeni bir **Bekletme etiketi** sütunu görüntülenir.  Modeliniz, içerik türüne ait olarak tanımladığı dosyaları sınıflandırır ve kitaplık görünümünde listelerken, **Bekletme etiketi** sütunu model aracılığıyla bu dosyaya uygulanmış olan bekletme etiketinin adını da görüntüler.

Örneğin, modelinizin belirlediği tüm *Sigorta bildirimi* belgelerinde de *İş* saklama etiketi uygulanır ve bu da belge kitaplığından beş ay boyunca silinmesini önler. Dosyayı belge kitaplığından silme girişiminde bulunulduysa, uygulanan bekletme etiketi nedeniyle buna izin verilmediğini belirten bir hata görüntülenir.

## <a name="add-a-retention-label-to-a-structured-document-processing-model"></a>Yapılandırılmış belge işleme modeline bekletme etiketi ekleme

> [!Important]
> Bekletme etiketlerinin yapılandırılmış belge işleme modellerinize uygulanabilmek için Microsoft Purview uyumluluk portalı [oluşturulması](../compliance/file-plan-manager.md#create-retention-labels) ve [yayımlanması](../compliance/create-apply-retention-labels.md#how-to-publish-retention-labels) gerekir.

Model oluştururken yapılandırılmış belge işleme modeline bekletme etiketi uygulayabilir veya bunu mevcut bir modele uygulayabilirsiniz.

### <a name="to-add-a-retention-label-when-you-create-a-structured-document-processing-model"></a>Yapılandırılmış belge işleme modeli oluşturduğunuzda bekletme etiketi eklemek için

1. [Yeni bir yapılandırılmış belge işleme modeli oluştururken](./create-a-form-processing-model.md) **Gelişmiş ayarlar'ı** seçin.

2. **Gelişmiş ayarlar'daki** **Bekletme etiketi** bölümünde menüyü ve ardından modele uygulamak istediğiniz bekletme etiketini seçin.
 
     ![Yeni bir yapılandırılmış belge işleme modeline ekleyin.](../media/content-understanding/retention-label-forms.png)

3.  Kalan model ayarlarınızı tamamladıktan sonra modelinizi oluşturmak için **Oluştur'u** seçin.

### <a name="to-add-a-retention-label-to-an-existing-structured-document-processing-model"></a>Mevcut yapılandırılmış belge işleme modeline bekletme etiketi eklemek için

Mevcut yapılandırılmış belge işleme modeline farklı yollarla bekletme etiketi ekleyebilirsiniz:

- Belge kitaplığındaki **Otomatikleştir** menüsü aracılığıyla
- Belge kitaplığındaki **Etkin model** ayarları aracılığıyla 

#### <a name="to-add-a-retention-label-to-an-existing-structured-document-processing-model-through-the-automate-menu"></a>Otomatikleştir menüsü aracılığıyla mevcut yapılandırılmış belge işleme modeline bekletme etiketi eklemek için

Sahip olduğunuz yapılandırılmış belge işleme modeline, modelin uygulandığı belge kitaplığındaki **Otomatikleştir** menüsü aracılığıyla bekletme etiketi ekleyebilirsiniz.

1. Modelin uygulandığı belge kitaplığınızda **Automate** > **AI Builder** > **View model ayrıntılarını** seçin.

    ![Otomatikleştir menüsü.](../media/content-understanding/automate-menu.png)

2. Model ayrıntılarındaki **Bekletme etiketi** bölümünde, uygulamak istediğiniz bekletme etiketini seçin ve ardından **Kaydet'i** seçin.

    ![Var olan bir yapılandırılmış belge işleme modeline ekleyin.](../media/content-understanding/retention-label-model-details.png)</br> 

#### <a name="to-add-a-retention-label-to-an-existing-structured-document-processing-model-in-the-active-model-settings"></a>Etkin model ayarlarında mevcut yapılandırılmış belge işleme modeline bekletme etiketi eklemek için

Sahip olduğunuz yapılandırılmış belge işleme modeline, modelin uygulandığı belge kitaplığındaki Etkin model ayarları aracılığıyla bekletme etiketi ekleyebilirsiniz.

1. Modelin uygulandığı SharePoint belge kitaplığında **Etkin modelleri görüntüle** simgesini ve ardından **Etkin modelleri görüntüle'yi** seçin.

    ![Etkin modelleri görüntüleme.](../media/content-understanding/info-du.png)

2. **Etkin modeller'de** bekletme etiketini uygulamak istediğiniz modeli seçin.

    ![Model ayrıntıları.](../media/content-understanding/retention-label-model-details.png)</br> 

3. Model ayrıntılarındaki **Bekletme etiketi** bölümünde, uygulamak istediğiniz bekletme etiketini seçin ve ardından **Kaydet'i** seçin.

> [!NOTE]
> Model ayarları bölmesinin düzenlenebilir olması için model sahibi olmanız gerekir. 

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Syntex'te modele duyarlılık etiketi uygulama](create-a-classifier.md)



