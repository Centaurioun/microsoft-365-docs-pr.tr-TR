---
title: Microsoft Syntex'te yapılandırılmış belge işleme modelini eğitin
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
description: Microsoft Syntex'te yapılandırılmış bir belge işleme modelini eğitmeyi öğrenin.
ms.openlocfilehash: 12bc46578d6cd26b4847baeb77856ff37b7d246c
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68660357"
---
# <a name="train-a-structured-document-processing-model-in-microsoft-syntex"></a>Microsoft Syntex'te yapılandırılmış belge işleme modelini eğitin

<!---
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhN]  

</br>


Using [AI Builder](/ai-builder/overview)—a feature in Microsoft Power Apps—Syntex users can create a [structured document processing](form-processing-overview.md) model directly from a SharePoint document library. 
--->

İçerik merkezinde yapılandırılmış bir belge işleme modeli oluşturmak için [Syntex'te model oluşturma](create-syntex-model.md) başlığı altındaki yönergeleri izleyin. Veya [modeli yerel bir sitede oluşturmak için Yerel SharePoint sitesinde model](create-local-model.md) oluşturma başlığı altında yer alan yönergeleri izleyin. Ardından modelinizi eğitmek için bu makaleyi kullanın.

![AI Builder modelini eğitmek için iş akışının diyagramı.](../media/content-understanding/train-aib-model.png)

Yapılandırılmış bir belge işleme modelini eğitmek için şu adımları izleyin:

 - [1. Adım: Belgeleri ekleme ve analiz etme](#step-1-add-and-analyze-documents)
 - [2. Adım: Alanları ve tabloları etiketleme](#step-2-tag-fields-and-tables)
 - [3. Adım: Modelinizi eğitin ve yayımlayın](#step-3-train-and-publish-your-model)
 - [4. Adım: Modelinizi kullanma](#step-4-use-your-model)

## <a name="step-1-add-and-analyze-documents"></a>1. Adım: Belgeleri ekleme ve analiz etme

Yapılandırılmış belge işleme modelinizi oluşturduktan sonra **Ayıklamak için bilgi seçin** sayfası açılır. Burada, AI modelinin belgelerinizden ayıklamasını istediğiniz *Ad*, *Adres* veya *Tutar* gibi tüm bilgi parçalarını listeleyebilirsiniz. 

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

    ![Belge kitaplığı modeli uygulandı.](../media/content-understanding/doc-lib-view.png)

2. **Belgeler'in** yanındaki bilgi bağlantısının bu belge kitaplığına form işleme modelinin uygulandığına dikkat edin.
<!---
    ![Info button.](../media/content-understanding/info-button.png)  
--->
3. Dosyaları belge kitaplığınıza yükleyin. Modelin içerik türü olarak tanımlamış olduğu tüm dosyalar, görünümünüzdeki dosyaları listeler ve ayıklanan verileri sütunlarda görüntüler.

    ![Ayıklanan verileri gösteren ekran görüntüsü.](../media/content-understanding/doc-lib-done.png) 

> [!NOTE]
> Aynı kitaplığa yapılandırılmış veya serbest biçimli bir belge işleme modeli ve yapılandırılmamış bir belge işleme modeli uygulanırsa, dosya yapılandırılmamış belge işleme modeli ve bu model için eğitilmiş ayıklayıcılar kullanılarak sınıflandırılır. Belge işleme modeliyle eşleşen boş sütunlar varsa, bu ayıklanan değerler kullanılarak sütunlar doldurulur.

### <a name="classification-date-field"></a>Sınıflandırma Tarihi alanı

Belge kitaplığına herhangi bir özel model uygulandığında, **Sınıflandırma Tarihi** alanı kitaplık şemasına eklenir. Varsayılan olarak, bu alan boş olur. Ancak, belgeler bir model tarafından işlendiğinde ve sınıflandırıldığında, bu alan tamamlanma tarih-saat damgasıyla güncelleştirilir. 

Model **Sınıflandırma Tarihi** ile damgalandığında, **Syntex bir dosya akışını işledikten sonra e-posta gönder'i** kullanarak kullanıcılara SharePoint belge kitaplığındaki bir model tarafından yeni bir dosyanın işlendiğini ve sınıflandırıldığını bildirebilirsiniz.

Akışı çalıştırmak için:

1. Bir dosya seçin ve ardından **Power Automate'i tümleştir** >  >  **Akış oluştur'u** seçin.

2. **Akış oluştur** panelinde **Syntex bir dosyayı işledikten sonra E-posta gönder'i** seçin.

    ![Akış oluştur panelini ve akış seçeneğinin vurgulandığı ekran görüntüsü.](../media/content-understanding/integrate-create-flow.png) 

### <a name="use-flows-to-extract-information"></a>Bilgileri ayıklamak için akışları kullanma

> [!IMPORTANT]
> Bu bölümdeki bilgiler Syntex'in en son sürümü için geçerli değildir. Yalnızca önceki sürümlerde oluşturulan form işleme modelleri için başvuru olarak bırakılır. En son sürümde, akışları artık mevcut dosyaları işecek şekilde yapılandırmanız gerekmez.

Yapılandırılmış belge işleme modelinin uygulandığı kitaplıkta seçili bir dosyayı veya dosya toplu işlemini işlemek için iki akış kullanılabilir.

- **Belge işleme modeliyle bir görüntüden veya PDF dosyasından bilgi ayıklama — Belge işleme modeli** çalıştırarak seçili görüntüden veya PDF dosyasından metin ayıklamak için kullanın. Tek seferde tek bir seçili dosyayı destekler ve yalnızca PDF dosyalarını ve görüntü dosyalarını (.png, .jpg ve .jpeg) destekler. Akışı çalıştırmak için bir dosya seçin ve ardından **Bilgileri ayıklamayı** **otomatikleştir'i** >  seçin.

    ![Bilgileri ayıkla seçeneğinin vurgulandığı Otomatikleştir menüsünü gösteren ekran görüntüsü.](../media/content-understanding/automate-extract-info.png)  

- **Belge işleme modeline sahip dosyalardan bilgi ayıklama** — Bir grup dosyadan bilgi okumak ve ayıklamak için belge işleme modelleriyle kullanın. Aynı anda en fazla 5.000 SharePoint dosyasını işler. Bu akışı çalıştırdığınızda ayarlayabileceğiniz bazı parametreler vardır. Şunları yapabilirsiniz:

    - Önceden işlenen dosyaların dahil edilip edilmeyeceğini seçin (varsayılan ayar, önceden işlenen dosyaları dahil etmek değildir).
    - İşlenmek üzere dosya sayısını seçin (varsayılan değer 100 dosyadır).
    - Dosyaların işlenme sırasını belirtin (seçenekler dosya kimliğine, dosya adına, dosya oluşturma zamanına veya son değiştirme zamanına göredir).
    - Düzenin nasıl sıralanmasını istediğinizi belirtin (artan veya azalan düzen).

    ![Parametre seçeneklerinin vurgulandığı Akışı çalıştır panelini gösteren ekran görüntüsü.](../media/content-understanding/run-flow-panel.png)  
    
> [!NOTE]
> **Belge işleme modeli akışına sahip bir görüntüden veya PDF dosyasından bilgi ayıkla** akışı, belge işleme modeliyle ilişkilendirilmiş bir kitaplık için otomatik olarak kullanılabilir. **Belge işleme modeline sahip dosyalardan bilgi ayıkla** akışı, gerekirse kitaplığa eklenmesi gereken bir şablondur.

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Syntex'te model oluşturma](create-syntex-model.md)

[Power Automate belgeleri](/power-automate/)

[Eğitim: AI Builder ile iş performansını geliştirme](/training/paths/improve-business-performance-ai-builder/?source=learn)
