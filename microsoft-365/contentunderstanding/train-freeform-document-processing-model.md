---
title: Microsoft Syntex'te serbest biçimli belge işleme modelini eğitin
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
ms.custom: admindeeplinkSPO
ms.localizationpriority: medium
description: Microsoft Syntex'te serbest biçimli belge işleme modelini eğitmeyi öğrenin.
ms.openlocfilehash: b8e306c725680be1bf36ba8922e52c9d1978242e
ms.sourcegitcommit: fa5a1699c8c863a1e61e427e522b3c40855a4f7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68667808"
---
# <a name="train-a-freeform-document-processing-model-in-microsoft-syntex"></a>Microsoft Syntex'te serbest biçimli belge işleme modelini eğitin

İçerik merkezinde serbest [biçimli bir belge işleme modeli oluşturmak için Syntex'te model oluşturma](create-syntex-model.md) başlığı altındaki yönergeleri izleyin. Veya [modeli yerel bir sitede oluşturmak için Yerel SharePoint sitesinde model](create-local-model.md) oluşturma başlığı altında yer alan yönergeleri izleyin. Ardından modelinizi eğitmek için bu makaleyi kullanın.

Serbest biçimli bir belge işleme modelini eğitmek için şu adımları izleyin:

 - [1. Adım: Belgeleri ekleme ve analiz etme](#step-1-add-and-analyze-documents)
 - [2. Adım: Alanları ve tabloları etiketleme](#step-2-tag-fields-and-tables)
 - [3. Adım: Modelinizi eğitin ve yayımlayın](#step-3-train-and-publish-your-model)
 - [4. Adım: Modelinizi kullanma](#step-4-use-your-model)

## <a name="step-1-add-and-analyze-documents"></a>1. Adım: Belgeleri ekleme ve analiz etme

Yapılandırılmış belge işleme modelinizi oluşturduktan sonra **Ayıklamak için bilgi seçin** sayfası açılır. Burada, AI modelinin belgelerinizden ayıklamasını istediğiniz Ad, Adres veya Tutar gibi tüm bilgi parçalarını listeleyebilirsiniz.  

> [!NOTE]
> Kullanılacak örnek dosyaları aradığınızda [, belge işleme modeli giriş belgesi gereksinimlerine ve iyileştirme ipuçlarına](/ai-builder/form-processing-model-requirements) bakın. 
 
1. İlk olarak modelinize ayıklamayı öğretmek istediğiniz alanları ve tabloları **Ayıklamak için bilgi seçin sayfasında tanımlarsınız** . Ayrıntılı adımlar için bkz. [Ayıklanması gereken alanları ve tabloları tanımlama](/ai-builder/create-form-processing-model#define-fields-and-tables-to-extract). 

2.  Modelinizin işlemesini istediğiniz kadar belge düzeni koleksiyonu oluşturabilirsiniz. Ayrıntılı adımlar için bkz. [Belgeleri koleksiyonlara göre gruplandırma](/ai-builder/create-form-processing-model#group-documents-by-collections). 

3. Koleksiyonlarınızı oluşturduktan ve her birine en az beş örnek dosya ekledikten sonra Syntex üzerinde AI Builder, alanları ve tabloları algılamak için karşıya yüklenen belgeleri inceler. Bu işlem genellikle birkaç saniye sürer. Analiz tamamlandığında, belgeleri etiketlemeye devam edebilirsiniz.

## <a name="step-2-tag-fields-and-tables"></a>2. Adım: Alanları ve tabloları etiketleme

Modele ayıklamak istediğiniz alanları ve tablo verilerini anlamasını öğretmek için belgeleri etiketlemeniz gerekir. Ayrıntılı adımlar için bkz. [Belgeleri etiketleme](/ai-builder/create-form-processing-model#tag-documents).

## <a name="step-3-train-and-publish-your-model"></a>3. Adım: Modelinizi eğitin ve yayımlayın

1. Modelinizi oluşturup eğittikkten sonra yayımlamaya ve SharePoint'te kullanmaya hazır olursunuz. Modeli yayımlamak için **Yayımla'yı** seçin. Ayrıntılı adımlar için bkz. [Belge işleme modelinizi eğitin ve yayımlayın](/ai-builder/form-processing-train). 

    ![Model giriş sayfasındaki model ayrıntılarını gösteren ekran görüntüsü.](../media/content-understanding/ai-builder-create-a-flow-1.png)

2. Model yayımlandıktan sonra modelin giriş sayfasına gidersiniz. Ardından modeli belge kitaplığına uygulama seçeneğiniz olur.

    ![Modelin kitaplığını uygulamak için model giriş sayfasının ekran görüntüsü.](../media/content-understanding/ai-builder-apply-model.png)

## <a name="step-4-use-your-model"></a>4. Adım: Modelinizi kullanma

1. Belge kitaplığı modeli görünümünde, seçtiğiniz alanların artık sütun olarak görüntülendiğine dikkat edin.

    ![Belge kitaplığı modelinin uygulandığını gösteren ekran görüntüsü.](../media/content-understanding/doc-lib-view.png)

2. **Belgeler'in** yanındaki bilgi bağlantısının bu belge kitaplığına form işleme modelinin uygulandığına dikkat edin.

3. Dosyaları belge kitaplığınıza yükleyin. Modelin içerik türü olarak tanımlamış olduğu tüm dosyalar, görünümünüzdeki dosyaları listeler ve ayıklanan verileri sütunlarda görüntüler.

    ![İşlemin tamamlendiğini gösteren ekran görüntüsü.](../media/content-understanding/doc-lib-done.png) 

> [!NOTE]
> Aynı kitaplığa serbest biçimli veya yapılandırılmış bir belge işleme modeli ve yapılandırılmamış bir belge işleme modeli uygulanırsa, dosya yapılandırılmamış belge işleme modeli ve bu model için eğitilmiş ayıklayıcılar kullanılarak sınıflandırılır. Serbest biçimli veya yapılandırılmış belge işleme modeliyle eşleşen boş sütunlar varsa, sütunlar ayıklanan değerler kullanılarak doldurulur.

### <a name="classification-date-field"></a>Sınıflandırma Tarihi alanı

Belge kitaplığına Syntex özel modeli uygulandığında, **Sınıflandırma Tarihi** alanı kitaplık şemasına eklenir. Varsayılan olarak, bu alan boş olur. Ancak, belgeler bir model tarafından işlendiğinde ve sınıflandırıldığında, bu alan tamamlanma tarih-saat damgasıyla güncelleştirilir. 

Model **Sınıflandırma Tarihi** ile damgalandığında, **Syntex bir dosya akışını işledikten sonra e-posta gönder'i** kullanarak kullanıcılara SharePoint belge kitaplığındaki bir model tarafından yeni bir dosyanın işlendiğini ve sınıflandırıldığını bildirebilirsiniz.

Akışı çalıştırmak için:

1. Bir dosya seçin ve ardından **Power Automate'i tümleştir** >  >  **Akış oluştur'u** seçin.

2. **Akış oluştur** panelinde **Syntex bir dosyayı işledikten sonra E-posta gönder'i** seçin.

    ![Akış oluştur panelini ve akış seçeneğinin vurgulandığı ekran görüntüsü.](../media/content-understanding/integrate-create-flow.png) 

## <a name="see-also"></a>Ayrıca bkz.
  
[Microsoft Syntex'te model oluşturma](create-syntex-model.md)

[Power Automate belgeleri](/power-automate/)

[Eğitim: AI Builder ile iş performansını geliştirme](/learn/paths/improve-business-performance-ai-builder/?source=learn)
