---
title: Microsoft Syntex'e genel bakış
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.custom: intro-overview
ms.service: microsoft-syntex
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Microsoft Syntex'teki özellikler ve özellikler hakkında bilgi edinin.
ms.openlocfilehash: b5c030231395284ece7342f8ed27349bce42f0df
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68664210"
---
# <a name="overview-of-microsoft-syntex"></a>Microsoft Syntex'e genel bakış

Microsoft Syntex, SharePoint kitaplıklarınızdaki belgeleri otomatik ve düşünceli bir şekilde bulmak, düzenlemek ve sınıflandırmak için akıllı belge işleme, içerik yapay zeka (AI) ve gelişmiş makine öğrenmesi kullanan bir içerik anlama, işleme ve uyumluluk hizmetidir.

:::row:::
   :::column span="":::      
      Syntex ile içerik tabanlı süreçlerinizi otomatikleştirebilir, iş belgelerinizdeki bilgileri yakalayabilir ve bu bilgileri kuruluşunuz için çalışan bilgilere dönüştürebilirsiniz.

      Syntex, yüzlerce veya binlerce dosyaya tıklayıp sıralamak yerine verileri sizin için ayıklar, analiz eder ve kategorilere ayırır.
   :::column-end:::
   :::column span="":::
      ![Syntex çalıştıran bilgisayarların görüntüsü.](../media/content-understanding/syntex-devices-image.png)
   :::column-end:::
:::row-end:::

İçeriğinizi gerçekten anlamak için daha derine inebilir ve bilgileri kuruluşunuzun bilinçli iş kararları almak için kullanabileceği anlamlı içgörülere dönüştürebilirsiniz.

## <a name="models"></a>Model

:::row:::
   :::column span="":::
      ![Genel model simgesinin resmi.](../media/content-understanding/model-generic-image.png) 
   :::column-end:::
   :::column span="3":::
      Syntex ile içeriğinizi anlamak modellerle başlar. Modeller, SharePoint belge kitaplıklarınıza yüklenen belgeleri tanımlamanıza ve sınıflandırmanıza ve ardından her dosyadan ihtiyacınız olan bilgileri ayıklamanıza olanak tanır.

      Syntex'te [özel modeller](model-types-overview.md) oluşturabilir veya [önceden oluşturulmuş modelleri](prebuilt-overview.md) kullanabilirsiniz. 
   :::column-end:::
:::row-end:::

Seçtiğiniz modelin türü, kullandığınız dosya türlerine, dosyaların biçimine ve yapısına, ayıklamak istediğiniz bilgilere ve modeli nereye uygulamak istediğinize bağlıdır.

### <a name="custom-models"></a>Özel modeller

Örnek belgelerden dosyalarınızın düzenini anlamak için özel modeller oluşturursunuz. Modeller, benzer belgelerden ayıklamak için ihtiyacınız olan verileri arama hakkında bilgi edinmektedir. Özel modeller şunlardır:

- [Yapılandırılmamış belge işleme](document-understanding-overview.md)
- [Serbest biçimli belge işleme](freeform-document-processing-overview.md)
- [Yapılandırılmış belge işleme](form-processing-overview.md)

| Yapılandırılmamış<br>belge işleme  | Freeform<br>belge işleme  | Yapılandırılmış<br>belge işleme  |
| ------------- | ------------- | ------------- |
|  ![Yapılandırılmamış belge işleme modeli simgesi.](../media/content-understanding/custom-classify-and-extract-by-text-pattern.png) | ![Serbest biçimli belge işleme modeli simgesi.](../media/content-understanding/custom-extract-by-text-pattern-and-layout.png) |  ![Yapılandırılmış belge işleme modeli simgesi.](../media/content-understanding/custom-extract-by-layout.png) |
| Belgeleri otomatik olarak sınıflandırmak ve onlardan bilgi ayıklamak için bu özel modeli kullanın. Modeli eğitmek için örnek belgelerde metnin desenlerini kullanın. Office dosyaları ve dosyaların otomatik sınıflandırması için en iyi yöntemdir. <br>[Daha fazla bilgi edinin](document-understanding-overview.md) | Yapılandırılmamış belgelerden otomatik olarak bilgi ayıklamak için bu özel modeli kullanın. Modeli eğitmek için örnek belgelerde metnin veya düzenin desenlerini kullanın. Hem metin hem de düzen gereksinimlerinin karışımı için en iyi yöntemdir. <br>[Daha fazla bilgi edinin](freeform-document-processing-overview.md) |  Formlar gibi yapılandırılmış veya yarı yapılandırılmış belgelerden alan ve tablo değerlerini otomatik olarak tanımlamak için bu özel modeli kullanın. Form düzenleri veya tablolar içeren çoğu dil ve dosya için idealdir. <br>[Daha fazla bilgi edinin](form-processing-overview.md) |

### <a name="prebuilt-models"></a>Önceden oluşturulmuş modeller

Özel bir model oluşturmanız gerekmiyorsa [önceden oluşturulmuş bir model](prebuilt-overview.md) kullanabilirsiniz. Bu model türü, ortak iş dosyalarından önceden tanımlanmış varlıkları ayıklamak için önceden eğitilir. Önceden oluşturulmuş modeller şunlardır:

- [Fatura işleme](prebuilt-model-invoice.md)
- [Makbuz işleme](prebuilt-model-receipt.md)

| Fatura işleme | Makbuz işleme | 
| ------------- | ------------- |
| ![Faturalar modeli simgesi.](../media/content-understanding/trained-invoices-model.png) | ![Makbuzlar modeli simgesi.](../media/content-understanding/trained-receipts-model.png) |
| Faturaları işlemek için zaman kazanmak için bu önceden oluşturulmuş modeli kullanın. Faturalara özgü önemli bilgileri otomatik olarak ayıklayın. <br>[Daha fazla bilgi edinin](prebuilt-model-invoice.md) | Makbuzları işlemek için zaman kazanmak için bu önceden oluşturulmuş modeli kullanın. Harcamalara özgü önemli bilgileri otomatik olarak ayıklayın. <br>[Daha fazla bilgi edinin](prebuilt-model-receipt.md) | 

Özel ve önceden oluşturulmuş modeller hakkında daha fazla bilgi için bkz. [Microsoft Syntex'te model türlerine genel bakış](model-types-overview.md).

## <a name="content-assembly"></a>İçerik derlemesi

:::row:::
   :::column span="":::
      ![Genel belge simgesinin resmi.](../media/content-understanding/document-assembly-image.png) 
   :::column-end:::
   :::column span="3":::
      Syntex ile en çok kullandığınız iş belgelerini temel alan *modern şablonlar* oluşturabilirsiniz.

      Daha sonra sharepoint listelerini veya kullanıcı girdilerini veri kaynağı olarak kullanarak otomatik olarak yeni belgeler oluşturmak için bu şablonları kullanabilirsiniz.
   :::column-end:::
:::row-end:::

 Bu işlem sözleşmeler, iş bildirimleri, hizmet sözleşmeleri, onay mektupları ve yazışmalar gibi standart yinelenen iş belgelerini otomatik olarak oluşturmanıza olanak tanır. Tüm bu görevleri daha hızlı, daha tutarlı ve Syntex'te daha az hatayla gerçekleştirebilirsiniz.

Daha fazla bilgi için bkz. [Microsoft Syntex'te içerik derlemesini kullanarak belge oluşturma](content-assembly.md).

## <a name="advanced-metadata-search"></a>Gelişmiş meta veri arama

:::row:::
   :::column span="3":::
      Syntex'teki gelişmiş meta veri arama özelliği, SharePoint belge kitaplıklarında belirli meta veri tabanlı sorgular gerçekleştirmenizi sağlar.

      Yalnızca anahtar sözcükleri aramak yerine belirli meta veri sütunu değerlerine göre daha hızlı ve daha hassas sorgular yapabilirsiniz.    
   :::column-end:::
   :::column span="":::
      ![Genel arama simgesinin resmi.](../media/content-understanding/search-generic-image.png)
   :::column-end:::
:::row-end:::

Bu özellik, belgenin en son ne zaman değiştirildiği, dosyayla ilişkilendirilmiş belirli bir kişi veya belirli bir dosya türü gibi aramak istediğiniz belirli bir bilgi parçasına sahip olduğunuzda kullanışlıdır.

Daha fazla bilgi için bkz [. Microsoft Syntex'te belge kitaplıklarında meta verileri arama](metadata-search.md).

--->

## <a name="content-compliance"></a>İçerik uyumluluğu

:::row:::
   :::column span="":::
      ![Genel uyumluluk simgesinin görüntüsü.](../media/content-understanding/compliance-image.png) 
   :::column-end:::
   :::column span="3":::
      İçeriğinizi anlamak daha iyi uyumluluk denetimi sağlar ve tüm verileriniz için yönetim ve idare seçeneklerini artırır. İçerik düzgün şekilde etiketlendiğinde ve etiketlendiğinde verileriniz üzerinde daha iyi denetim sahibi olursunuz ve düzenlemeleri daha kolay izleyebilirsiniz. Syntex, belgelerinizi yönetmek için bekletme etiketlerini ve duyarlılık etiketlerini kullanarak uyumluluğu sağlamanıza yardımcı olur.
   :::column-end:::
:::row-end:::

Daha fazla bilgi için bkz. [Microsoft Syntex'te bir modele bekletme etiketi uygulama](apply-a-retention-label-to-a-model.md) ve [Microsoft Syntex'te modele duyarlılık etiketi uygulama](apply-a-sensitivity-label-to-a-model.md).

## <a name="premium-taxonomy-services"></a>Premium taksonomi hizmetleri

:::row:::
   :::column span="3":::
      Kuruluşunuzda bir veya daha fazla Syntex lisansına sahip olmak, yöneticiler için aşağıdaki ek terim deposu özelliklerini etkinleştirir:<br><br>
       
      - [SKOS tabanlı bir biçim kullanarak bir terim kümesini](import-term-set-skos.md) içeri aktarmanızı sağlayan SKOS tabanlı terim kümesi içeri aktarma.      
   :::column-end:::
   :::column span="":::
      ![Genel taksonomi simgesinin resmi.](../media/content-understanding/taxonomy-image.png)
   :::column-end:::
:::row-end:::


- [Kurumsal içerik türlerini bir merkez sitesine](push-content-type-to-hub.md) gönderme, bunları ilişkili sitelere ve yeni oluşturulan listelere veya kitaplıklara da ekler.

- [Yayımlanmış terim](term-store-analytics.md) kümeleri ve bunların kuruluşunuzdaki kullanımı hakkında içgörüler sağlayan terim deposu raporları.

## <a name="scenarios-and-use-cases"></a>Senaryolar ve kullanım örnekleri

:::row:::
   :::column span="":::
      ![Genel senaryo simgesinin görüntüsü.](../media/content-understanding/scenarios-image.png) 
   :::column-end:::
   :::column span="3":::
      Syntex, kuruluşunuzun iş süreçlerini otomatikleştirmesine, arama doğruluğunu iyileştirmesine ve uyumluluk riskini yönetmesine yardımcı olabilir.

      İçerik yapay zekası hizmetleri ve özellikleriyle içerik anlama ve sınıflandırmayı doğrudan içerik yönetimi akışına oluşturabilirsiniz.
   :::column-end:::
:::row-end:::

Kuruluşunuzda Syntex'i nasıl kullanabileceğiniz hakkında fikir almak için bkz. [Microsoft Syntex için senaryolar ve kullanım örnekleri](adoption-scenarios.md).
<br><br>
> [!div class="nextstepaction"]
> [Microsoft Syntex'teki modeller hakkında daha fazla bilgi edinin](model-types-overview.md)
