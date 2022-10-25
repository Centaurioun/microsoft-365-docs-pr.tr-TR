---
title: Arama sorguları oluşturmak için KQL düzenleyicisini kullanma
description: İçerik arama, eBulma (Standart) ve eBulma (Premium) içinde eBulma arama sorgularını yapılandırmak için KQL düzenleyicisini kullanabilirsiniz.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier1
- purview-compliance
- ediscovery
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bfee0098300c6cb00bc456c5329f98f87e468461
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2022
ms.locfileid: "68686582"
---
# <a name="use-the-kql-editor-to-build-search-queries"></a>Arama sorguları oluşturmak için KQL düzenleyicisini kullanma

Microsoft Purview eKeşif araçları aramasında yeni Anahtar Sözcük Sorgu Dili (KQL) sorgu deneyimi, İçerik arama, Microsoft Purview eKeşif (Standart) ve eBulma (Premium) içinde arama sorguları oluştururken geri bildirim ve rehberlik sağlar. Düzenleyiciye sorgu girdiğinizde, desteklenen aranabilir özellikler ve koşullar için otomatik tamamlama sağlar ve standart özellikler ve koşullar için desteklenen değerlerin listesini sağlar. Örneğin, sorgunuzda e-posta özelliğini belirtirseniz `kind` düzenleyici, seçebileceğiniz desteklenen değerlerin listesini sunar. KQL düzenleyicisi, aramayı çalıştırmadan önce düzeltebileceğiniz olası sorgu hatalarını gerçek zamanlı olarak da görüntüler. En iyisi, standart koşul oluşturucusunda anahtar sözcükler ve koşullar kartlarını kullanarak sorguları el ile oluşturmak zorunda kalmadan karmaşık sorguları doğrudan düzenleyiciye yapıştırabilirsiniz.
  
KQL düzenleyicisini kullanmanın başlıca avantajları şunlardır:

- Rehberlik sağlar ve sıfırdan arama sorguları oluşturmanıza yardımcı olur.
- Uzun ve karmaşık sorguları doğrudan düzenleyiciye hızlı bir şekilde yapıştırmanızı sağlar. Örneğin, karşı danışmandan karmaşık bir sorgu alırsanız, bunu koşul oluşturucusunu kullanmak yerine KQL düzenleyicisine yapıştırabilirsiniz.
- Olası hataları hızla tanımlar ve sorunların nasıl çözüleceğini gösteren ipuçları görüntüler.

EBulma (Standart) ve eBulma (Premium) içinde sorgu tabanlı tutmalar oluşturduğunuzda da KQL düzenleyicisi kullanılabilir.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="displaying-the-kql-editor"></a>KQL düzenleyicisini görüntüleme

Bir eBulma araması oluşturduğunuzda veya düzenlediğinizde, KQL düzenleyicisini görüntüleme ve kullanma seçeneği arama veya koleksiyonlar sihirbazının **Koşullar** sayfasında bulunur.

### <a name="kql-editor-in-content-search-and-ediscovery-standard"></a>İçerik arama ve eBulma'da KQL düzenleyicisi (Standart)

![İçerik arama ve eBulma'da KQL düzenleyicisi (Standart)](../media/KQLEditorCore.png)

### <a name="kql-editor-in-ediscovery-premium"></a>eBulma'da KQL düzenleyicisi (Premium)

![eBulma'da KQL düzenleyicisi (Premium)](../media/KQLEditorAdvanced.png)

## <a name="using-the-kql-editor"></a>KQL düzenleyicisini kullanma

Aşağıdaki bölümlerde KQL düzenleyicisinin nasıl öneriler sağladığına ve olası hataları nasıl algılayabileceklerine ilişkin örnekler gösterilir.

### <a name="autocompletion-of-search-properties-and-operators"></a>Arama özelliklerini ve işleçlerini otomatik olarak tamamlama

KQL düzenleyicisine bir arama sorgusu girmeye başladığınızda düzenleyici, seçebileceğiniz desteklenen arama özelliklerinin ( *özellik kısıtlamaları* olarak da adlandırılır) önerilen otomatik tamamlamasını görüntüler. Bu iki karakterle başlayan desteklenen özelliklerin listesini görüntülemek için en az iki karakter yazmanız gerekir. Örneğin, aşağıdaki ekran görüntüsü ile `Se`başlayan önerilen arama özelliklerini gösterir.

![KQL düzenleyicisi desteklenen özellikler önerir](../media/KQLEditorAutoCompleteProperties.png)

Ayrıca düzenleyici, tam bir özellik adı yazdığınızda desteklenen işleçlerin (, ve `<>`gibi`:``=`) listesini de sağlar. Örneğin, aşağıdaki ekran görüntüsü özelliği için `Date` önerilen işleçleri gösterir.

![KQL düzenleyicisi işleçler önerir](../media/KQLEditorOperatorSuggestions.png)

Desteklenen arama özellikleri ve işleçleri hakkında daha fazla bilgi için bkz [. eBulma için anahtar sözcük sorguları ve arama koşulları](keyword-queries-and-search-conditions.md).

### <a name="property-value-suggestions"></a>Özellik değeri önerileri

KQL düzenleyicisi bazı özelliklerin olası değerleri için öneriler sağlar. Örneğin, aşağıdaki ekran görüntüsü özelliği için `Kind` önerilen değerleri gösterir.

![KQL düzenleyicisi bazı özellikler için değerler önerir](../media/KQLEditorValueSuggestions.png)

Düzenleyici ayrıca, , `To``Recipients` ve `Participants`gibi `From`e-posta alıcısı özelliklerini yazdığınızda kullanıcıların listesini (UPN biçiminde) önerir.

![KQL düzenleyicisi, alıcı e-posta özellikleri için kullanıcılar önerir](../media/KQLEditorRecipientSuggestions.png)

### <a name="detection-of-potential-errors"></a>Olası hataları algılama

KQL düzenleyicisi, arama sorgularındaki olası hataları algılar ve hatayı çözmenize yardımcı olmak için hataya neyin neden olduğuna ilişkin bir ipucu sağlar. Düzenleyici ayrıca bir özelliğin karşılık gelen bir işlemi veya değeri olmadığında olası bir hatayı gösterir. Sorgudaki olası hatalar kırmızı metinle vurgulanır ve **olası hatalar** açılan bölümünde hatanın açıklamaları ve olası düzeltmeleri görüntülenir. Örneğin, aşağıdaki sorguyu KQL düzenleyicisine yapıştırdıysanız dört olası hata algılanır.

![KQL düzenleyicisi hata algılama](../media/KQLEditorErrorDetection.png)

Bu durumda, olası hata ipuçlarını kullanarak sorgu sorunlarını giderebilir ve düzeltebilirsiniz.

## <a name="more-information"></a>Daha fazla bilgi

- Koşul oluşturucu ile KQL düzenleyicisi arasında geçiş yapabilirsiniz. Örneğin, Anahtar Sözcükler kutusunu ve birden çok koşul kartını kullanarak sorgu yapılandırmak için koşul oluşturucusunu kullanırsanız, sonuçta elde edilen sorguyu KQL düzenleyicisinde görüntüleyebilirsiniz. Ancak, KQL düzenleyicisinde karmaşık bir sorgu (anahtar sözcükler ve koşullarla) oluşturursanız, sonuçta elde edilen sorgu yalnızca koşul oluşturucusunda görüntülediğinizde Anahtar Sözcükler kutusunda görüntülenir.

- Karmaşık bir sorguyu KQL düzenleyicisine yapıştırırsanız düzenleyici olası hataları algılar ve hataları çözmek için olası çözümler önerir.
