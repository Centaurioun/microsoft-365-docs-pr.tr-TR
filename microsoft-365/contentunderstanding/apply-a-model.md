---
title: Microsoft Syntex'te belge kitaplığına model uygulama
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
description: Microsoft Syntex'te yayımlanmış bir modeli SharePoint belge kitaplığına nasıl uygulayacağınızı öğrenin.
ms.openlocfilehash: b0aed07a5a530b06b04fe78775d49373daae290f
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68659247"
---
# <a name="apply-a-model-to-a-document-library-in-microsoft-syntex"></a>Microsoft Syntex'te belge kitaplığına model uygulama

<sup>**Şunlar için geçerlidir:**  &ensp; &#10003; Tüm özel modeller &ensp; | &ensp; &#10003; Tüm önceden oluşturulmuş modeller</sup>

<!---
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>
--->

Yapılandırılmamış bir belge işleme modelini eğittik, serbest biçimli veya yapılandırılmış bir belge işleme modeli eğitip yayımladıktan veya önceden oluşturulmuş bir model oluşturduktan sonra, bunu Microsoft 365 kiracınızdaki bir veya daha fazla SharePoint belge kitaplığına uygulayabilirsiniz.

Bu makale hem *kurumsal modeller* hem de *yerel modeller* için geçerlidir. [İçerik merkezinde](create-a-content-center.md) bir kurumsal model oluşturulur ve eğitilir ve kullanmak üzere başkaları tarafından bulunabilir. [Yerel bir model](create-local-model.md) oluşturulur ve kendi SharePoint sitenizde yerel olarak eğitilir.  

> [!NOTE]
> Modeli yalnızca erişiminiz olan belge kitaplıklarına uygulayabilirsiniz.

## <a name="apply-your-model-to-a-document-library"></a>Modelinizi belge kitaplığına uygulama

Modeli giriş sayfası veya kullanılabilir modeller listesinden dahil olmak üzere farklı yerlere uygulayabilirsiniz. Modelinizi bir SharePoint belge kitaplığına uygulamak için:

1. Model giriş sayfasındaki **Modeli kitaplıklara uygula** kutucuğunda **Modeli uygula'yı** seçin. Öte yandan **Modelin uygulandığı yer** bölümünde **Kitaplık ekle'yi** de seçebilirsiniz.

    ![Kitaplık ekle seçeneğinin vurgulandığı Modelin uygulandığı yer bölümünün ekran görüntüsü.](../media/content-understanding/apply-to-library.png)

2. Ardından modeli uygulamak istediğiniz belge kitaplığını içeren SharePoint sitesini seçebilirsiniz. Site listede gösterilmiyorsa, bulmak için arama kutusunu kullanın.

    ![Bir site seçin.](../media/content-understanding/site-search.png)

    > [!NOTE]
    > Modeli uyguladığınız belge kitaplığında *Listeyi Yönet* izinlerine veya *Düzenleme* haklarına sahip olmanız gerekir.

3. Siteyi seçtikten sonra, modeli uygulamak istediğiniz belge kitaplığını seçin. Örnekte Contoso *Servis Talebi İzleme* sitesinden *Belgeler* belge kitaplığını seçin.

    ![Bir belge kitaplığı seçin.](../media/content-understanding/select-doc-library.png)

4. Model bir içerik türüyle ilişkilendirildiğinden, kitaplığa uyguladığınızda içerik türünü ekler ve ayıkladığınız etiketler sütun olarak gösterilen varsayılan görünümü güncelleştirir. Ancak, isteğe bağlı olarak geçerli kitaplık görünümünü korumayı veya model bilgileri ve dosya küçük resimleriyle yeni bir görünüm kullanmayı seçmek için **Gelişmiş ayarlar'ı** seçebilirsiniz. Geçerli kitaplık görünümünü korumayı seçerseniz, model bilgilerine sahip yeni görünümler kitaplığın görünüm menüsünde yine kullanılabilir.

    ![Kitaplık görünümlerini gösteren Gelişmiş ayarların ekran görüntüsü.](../media/content-understanding/library-view.png)

    Daha fazla bilgi için bkz. [Belge kitaplığında görünümü seçme](choose-library-view.md).

5. Modeli kitaplığa uygulamak için **Ekle'yi** seçin.

6. Modelin giriş sayfasındaki **Modelin uygulandığı yer** bölümünde SharePoint sitesinin adını listelenmiş olarak görmeniz gerekir.

7. Belge kitaplığınıza gidin ve modelin belge kitaplığı görünümünde olduğunuzdan emin olun. **Modelleri görüntülemeyi** **otomatikleştir'i** >  seçin.

8. **Modelleri gözden geçir ve yenilerini uygula** sayfasında, belge kitaplığına uygulanan modelleri görmek için **Uygulanan** sekmesini seçin.

    ![Uygulanan sekmesinin seçili olduğunu ve uygulanan modelleri gösteren ekran görüntüsü.](../media/content-understanding/applied-models.png) 

9. Modelin açıklaması, modeli yayımlayan kişi ve modelin sınıflandırdığı dosyalara bekletme veya duyarlılık etiketleri uygulayıp uygulamadığı gibi model hakkındaki bilgileri görmek için Model **ayrıntılarını görüntüle'yi** seçin.

Modeli belge kitaplığına uyguladıktan sonra, belgeleri siteye yüklemeye başlayabilir ve sonuçları görebilirsiniz.

Model, modelin ilişkili içerik türüne sahip tüm dosya ve klasörleri tanımlar ve bunları görünümünüzde listeler. Modelinizde ayıklayıcı varsa, görünümde her dosya veya klasörden ayıkladığınız verilerin sütunları görüntülenir.

> [!NOTE]
> Aynı kitaplığa iki veya daha fazla yapılandırılmamış belge işleme modeli uygulanırsa, karşıya yüklenen dosya en yüksek ortalama güvenilirlik puanına sahip model kullanılarak sınıflandırılır. Ayıklanan varlıklar yalnızca uygulanan modelden olacaktır. <br><br>Aynı kitaplığa serbest biçimli veya yapılandırılmış bir belge işleme modeli ve yapılandırılmamış bir belge işleme modeli uygulanırsa, dosya yapılandırılmamış belge işleme modeli ve bu model için eğitilmiş ayıklayıcılar kullanılarak sınıflandırılır. Serbest biçimli veya yapılandırılmış belge işleme modeliyle eşleşen boş sütunlar varsa, sütunlar ayıklanan değerler kullanılarak doldurulur.

## <a name="sync-changes-to-one-or-more-document-libraries"></a>Değişiklikleri bir veya daha fazla belge kitaplığına eşitleme

Bir modeli birden çok belge kitaplığına yayımladığınızda ve ardından bir ayıklayıcı ekleme veya kaldırma gibi modeli güncelleştirdiğinizde, güncelleştirmeyi modelin uygulandığı tüm kitaplıklara göndermeniz gerekir.

Değişiklikleri tüm uygulanan kitaplıklara eşitlemek için:

1. Model giriş sayfasındaki **Modelin uygulandığı yer** bölümünde **Tümünü eşitle'yi** seçin.

    ![Modelin uygulandığı yer bölümünü ve Tümünü eşitle düğmesinin vurgulandığı ekran görüntüsü.](../media/content-understanding/sync-all-button.png) 

Değişiklikleri bir veya yalnızca seçili kitaplıklara eşitlemek için:

1. Model giriş sayfasındaki **Modelin uygulandığı yer** bölümünde, değişiklikleri uygulamak istediğiniz kitaplığı veya kitaplıkları seçin.

2. **Eşitle'yi** seçin.

    ![Modelin uygulandığı yer bölümünü ve Eşitle düğmesinin vurgulandığı ekran görüntüsü.](../media/content-understanding/sync-button.png) 

## <a name="apply-the-model-to-files-and-folder-content-already-in-the-document-library"></a>Modeli belge kitaplığında zaten bulunan dosyalara ve klasör içeriğine uygulama

Uygulanan model, belge kitaplığına yüklenen tüm dosyaları ve klasör içeriğini uygulandıktan sonra işler. Modeli uygulamadan önce belge kitaplığında zaten var olan dosya ve klasör içeriğinde çalıştırmak için aşağıdaki adımları da gerçekleştirebilirsiniz:

1. Belge kitaplığınızda, modeliniz tarafından işlenmesini istediğiniz dosya ve klasörleri seçin.

2. Dosya ve klasörlerinizi seçtikten sonra, belge kitaplığı şeridinde **Sınıflandır ve ayıkla** görüntülenir. **Sınıflandır ve ayıkla'yı** seçin.

      ![Sınıflandır ve ayıkla seçeneğini gösteren ekran görüntüsü.](../media/content-understanding/extract-classify.png) 

3. Seçtiğiniz dosya ve klasörler işlenecek kuyruğa eklenir.

    > [!NOTE]
    > Bir veya daha fazla klasör seçtiyseniz veya büyük bir dosya kümesini geçiriyorsanız sınıflandırma 24 saate kadar sürebilir.

### <a name="classification-date-field"></a>Sınıflandırma Tarihi alanı

Belge kitaplığına özel bir uygulama uygulandığında **, Sınıflandırma Tarihi** alanı kitaplık şemasına eklenir. Varsayılan olarak, bu alan boş olur. Ancak, belgeler bir model tarafından işlendiğinde ve sınıflandırıldığında, bu alan tamamlanma tarih-saat damgasıyla güncelleştirilir. 

   ![Sınıflandırma Tarihi sütununu gösteren belge kitaplığının ekran görüntüsü.](../media/content-understanding/class-date-column.png) 

**Sınıflandırma Tarihi** alanı, bir model dosya veya klasörün içeriğini işlemeyi bitirdikten ve **Sınıflandırma Tarihi** alanını güncelleştirdikten sonra Power Automate akışını çalıştırmak için bir dosya [**içerik anlama modeli tetikleyicisi tarafından sınıflandırıldığında**](/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model) tarafından kullanılır.

   ![Akış tetikleyicisi.](../media/content-understanding/trigger.png)

Bir **dosya bir içerik anlama modeli tarafından sınıflandırıldığında** tetikleyicisi, dosya veya klasörden ayıklanan bilgileri kullanarak akış başlatmak için kullanılabilir.

Örneğin, bir model **Sınıflandırma Tarihi** ile damgalandığında, **Syntex dosya akışını işledikten sonra kullanıcılara** SharePoint belge kitaplığındaki bir model tarafından yeni bir dosyanın işlendiğini ve sınıflandırıldığını bildirmek için E-posta gönder'i kullanabilirsiniz.

Akışı çalıştırmak için:

1. Bir dosya seçin ve ardından **Power Automate'i tümleştir** >  >  **Akış oluştur'u** seçin.

2. **Akış oluştur** panelinde **Syntex bir dosyayı işledikten sonra E-posta gönder'i** seçin.

    ![Akış oluştur panelini ve akış seçeneğinin vurgulandığı ekran görüntüsü.](../media/content-understanding/integrate-create-flow.png) 

## <a name="see-also"></a>Ayrıca bkz.

[Kurumsal modeli paylaşma](model-discovery.md)

[Diğer eğitilmiş modelleri keşfedin](discover-other-trained-models.md)

[Belge kitaplığında görünümü seçme](choose-library-view.md)

