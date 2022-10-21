---
title: Microsoft Syntex'te modele duyarlılık etiketi uygulama
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
description: Microsoft Syntex'te modele duyarlılık etiketi uygulamayı öğrenin.
ms.openlocfilehash: b38cbdd23270a16a7f912fe78dff920c670cfe95
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68660895"
---
# <a name="apply-a-sensitivity-label-to-a-model-in-microsoft-syntex"></a>Microsoft Syntex'te modele duyarlılık etiketi uygulama

<sup>**Şunlar için geçerlidir:**  &ensp; Yapılandırılmamış belge işlemeyi &#10003;</sup>

Microsoft Syntex'teki yapılandırılmamış belge işleme modellerine [kolayca duyarlılık etiketi](../compliance/sensitivity-labels.md) uygulayabilirsiniz. 

> [!Note]
> Duyarlılık etiketleri henüz önceden oluşturulmuş modellerde veya serbest biçimli veya yapılandırılmış belge işleme modellerinde kullanılamaz.

Duyarlılık etiketleri, modellerinizin tanımladığınız belgelere şifreleme uygulamanıza olanak tanır. Örneğin, modelinizin yalnızca belge kitaplığınıza yüklenen banka hesap numaralarını veya kredi kartı numaralarını içeren finansal belgeleri tanımlamasını değil, aynı zamanda bu içeriğe kimlerin erişebileceğini ve nasıl kullanılabileceğini kısıtlamak için şifreleme ayarlarıyla yapılandırılmış bir duyarlılık etiketi uygulamasını istiyorsunuz. Syntex modelleri [etiket sırası](../compliance/apply-sensitivity-label-automatically.md#how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label) kurallarına uyar ve ayrıca kullanıcı tarafından dosyaya el ile uygulanan mevcut bir etiketin üzerine yazılamaz. 

Modelinizin giriş sayfasındaki model ayarlarınızdan modelinize önceden var olan bir duyarlılık etiketi uygulayabilirsiniz. Etiket, model ayarlarından seçilebilmek için zaten yayımlanmış olmalıdır. Etiketler Word (.docx), PowerPoint (.pptx) ve Excel (.xlsx) için Office dosyalarına uygulanır. 

> [!Important]
> Modellerinize uygulanabilecek duyarlılık etiketlerinin [Microsoft Purview uyumluluk portalı oluşturulması ve yayımlanması](../admin/security-and-compliance/set-up-compliance.md) gerekir.

## <a name="add-a-sensitivity-label-to-a-model"></a>Modele duyarlılık etiketi ekleme

1. Model giriş sayfasında **Model ayarları'nı** seçin.

   ![Model ayarları seçeneğinin vurgulandığı Modeller sayfasının ekran görüntüsü.](../media/content-understanding/sensitivity-model-settings.png)

2. **Model ayarları** bölmesindeki **Uyumluluk** bölümünde **Duyarlılık etiketi** menüsünü seçerek modele uygulayabileceğiniz duyarlılık etiketlerinin listesini görebilirsiniz.

   ![Duyarlılık etiketi menüsünü gösteren Model ayarları bölmesinin ekran görüntüsü.](../media/content-understanding/sensitivity-model-settings-pane.png) 

3. Modele uygulamak istediğiniz duyarlılık etiketini seçin ve ardından **Kaydet'i** seçin.

Duyarlılık etiketini modelinize uyguladıktan sonra aşağıdakilere uygulayabilirsiniz:

- Yeni belge kitaplığı
- Modelin zaten uygulandığı belge kitaplığı
 
### <a name="apply-the-sensitivity-label-to-a-document-library-to-which-the-model-is-already-applied"></a>Duyarlılık etiketini modelin zaten uygulandığı belge kitaplığına uygulama

Modeliniz bir belge kitaplığına zaten uygulanmışsa, duyarlılık etiketi güncelleştirmenizi eşitleyerek belge kitaplığına uygulamak için aşağıdakileri yapabilirsiniz:

1. Modelin giriş sayfasındaki **Bu modelle kitaplıklar** bölümünde duyarlılık etiketi güncelleştirmesini uygulamak istediğiniz belge kitaplığını seçin.

2. **Eşitle'yi** seçin.

   ![Eşitle seçeneğinin vurgulandığı bu model bölümüyle kitaplıkları gösteren ekran görüntüsü.](../media/content-understanding/sensitivity-libraries-sync.png)

Güncelleştirmeyi uyguladıktan ve modelinizle eşitledikten sonra, aşağıdaki adımları uygulayarak uygulandığını onaylayabilirsiniz:

1. İçerik merkezindeki **Bu modelle kitaplıklar** bölümünde, güncelleştirilmiş modelinizin uygulandığı kitaplığı seçin. 

2. Belge kitaplığı görünümünüzde, model özelliklerini denetlemek için bilgi simgesini seçin.

3. **Etkin modeller** listesinde güncelleştirilmiş modelinizi seçin.

4. **Duyarlılık etiketi** bölümünde, uygulanan duyarlılık etiketinin adını görürsünüz.

Belge kitaplığınızdaki modelinizin görünüm sayfasında yeni bir **Duyarlılık etiketi** sütunu görüntülenir. Modeliniz, içerik türüne ait olarak tanımladığı dosyaları sınıflandırır ve kitaplık görünümünde listelerken Duyarlılık **etiketi** sütunu, model aracılığıyla uygulanan duyarlılık etiketinin adını da görüntüler.

Örneğin, modelinizin tanımladığı tüm finansal belgelere de *Şifreleme* duyarlılığı etiketi uygulanır ve yetkisiz kişiler tarafından erişilmesini engeller. Yetkisiz bir kişi tarafından belge kitaplığından dosyaya erişmeye çalışılırsa, uygulanan duyarlılık etiketi nedeniyle dosyaya izin verilmediğini belirten bir hata görüntülenir.

## <a name="see-also"></a>Ayrıca bkz.

[Bekletme etiketi uygula](apply-a-retention-label-to-a-model.md)

