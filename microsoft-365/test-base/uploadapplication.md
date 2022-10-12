---
title: Önceden oluşturulmuş zip paketini karşıya yükleme
description: Test Tabanı'nda önceden oluşturulmuş bir .zip dosyasını düzenleme, karşıya yükleme ve test etme
search.appverid: MET150
author: mansipatel-usl
ms.author: rshastri
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: tinachen
f1.keywords: NOCSH
ms.openlocfilehash: b2bb536df28f2b63114aa604241688458428760e
ms.sourcegitcommit: 893add1e40c3e26e5624663eaf272d12a72d0141
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68539993"
---
# <a name="uploading-a-pre-built-zip-package"></a>Önceden oluşturulmuş zip paketini karşıya yükleme

Bu bölüm, önceden oluşturulmuş bir .zip dosyanız olduğunda Test Temeli'ni düzenlemek, karşıya yüklemek ve test etmek için gereken tüm adımları sağlar.

**Ön istekler**

   - Test Temeli hesabı: **Test Temeli** hesabınız yoksa, [Test Temeli hesabı oluşturma](createAccount.md) bölümünde açıklandığı gibi devam etmeden önce bir hesap oluşturmanız gerekir.
   - Önceden oluşturulmuş .zip dosyası: Uygulama ikili dosyanızı ve test betiklerinizi içeren çevrimdışı oluşturulmuş bir .zip dosyası. Bkz[. Paket oluşturma | Test Temeli .zip](buildpackage.md) paketinizi masaüstünden hazırlamak için Microsoft Docs.

## <a name="upload-an-offline-built-package"></a>Çevrimdışı bir derlenmiş paketi karşıya yükleme

[Azure portal](https://portal.azure.com/), paketinizi oluşturup karşıya yükleyebileceğiniz **Test Temeli** hesabına gidin ve aşağıdaki adımları uygulayın.

Sol taraftaki menüde **Paket kataloğu** altında **Yeni paket'i** seçin. Ardından üçüncü " **Önceden oluşturulmuş paketi karşıya yükle"** kartını seçin.

> [!div class="mx-imgBorder"]
> [![Sol taraftaki menü](Media/uploadingzip01-new-package.png) ](Media/uploadingzip01-new-package.png#lightbox)

### <a name="step-1-define-content"></a>Adım 1. İçerik tanımlama

1. **Paket kaynağı bölümünde Paket kaynağı** türünde Önceden oluşturulmuş paket (.zip) öğesini seçin.

   > [!div class="mx-imgBorder"]
   > [![Yeni paket](Media/uploadingzip02-define-content.png) ](Media/uploadingzip02-define-content.png#lightbox)

2. 'Dosya seç' düğmesini seçerek önceden oluşturulmuş paket (zip) dosyanızı karşıya yükleyin.

3. Paketinizin adını ve sürümünü **Temel bilgiler** bölümüne yazın.

   > [!NOTE]
   > Paket adı ve sürümü birleşimi Test Temeli hesabınızda benzersiz olmalıdır.

   > [!div class="mx-imgBorder"]
   > ![Temel bilgiler](Media/uploadingzip03-basic-information.png)

4. İstenen tüm bilgiler belirtildikten sonra **sonraki: Yapılandırma testi** düğmesini seçin.

   > [!div class="mx-imgBorder"]
   > ![Sonraki: Yapılandırma testi](Media/uploadingzip04-next.png)

### <a name="step-2-configure-test"></a>Adım 2. Testi yapılandırma

1. Önceden oluşturulmuş paketinize göre **test türünü** seçin. Desteklenen iki test türü vardır:

   - Kullanıma **Açık (OOB) testi** paketinizi yükleme, başlatma, kapatma ve kaldırma işlemlerini gerçekleştirir. Yüklemeden sonra başlatma-kapatma yordamı, tek bir kaldırma çalıştırılmadan önce 30 kez yinelenir. OOB testi, Windows derlemeleriyle karşılaştırmak için paketinizde standart telemetri sağlar.
   - **İşlevsel test**, paketinizde karşıya yüklenen test betiklerinizi yürütür. Betikler belirttiğiniz sırada çalıştırılır ve belirli bir betikteki bir hata, izleyen betiklerin yürütülmesini durdurur.

   > [!NOTE]
   > Kullanıma Sunulan test artık isteğe bağlıdır.

   > [!div class="mx-imgBorder"]
   > [![kullanıma dışı test seçeneği](Media/uploadingzip05-configure-test.png) ](Media/uploadingzip05-configure-test.png#lightbox)

2. Gerekli tüm bilgiler doldurulduktan sonra İleri düğmesini seçin.

### <a name="step-3-edit-package"></a>Adım 3. Paketi düzenle

1. Paketi düzenle sekmesinde şunları yapabilirsiniz:
   - **Paket Önizlemesi'nde** paket klasörünüzü ve dosya yapınızı denetleyin.
   - **PowerShell kod düzenleyicisiyle** betiklerinizi çevrimiçi olarak düzenleyin.

   > [!NOTE]
   > Önceden oluşturulmuş paketiniz düzenlemek için ayıklanır. Betik etiketleri betik adına göre eklenir, lütfen bu betik etiketlerini gözden geçirin ve gerekirse ayarlayın. Betik etiketleri, test başlatıldığında kullanılacak doğru betik yollarını gösterir.

   > [!div class="mx-imgBorder"]
   > [![PowerShell kod düzenleyicisi](Media/uploadingzip06-edit-package.png) ](Media/uploadingzip06-edit-package.png#lightbox)

2. **Paket Önizlemesi'nde**, ihtiyacınıza göre şunları yapabilirsiniz:

   - yeni bir klasör oluşturun.
   - yeni bir betik oluşturun.
   - yeni bir dosya yükleyin.

3. **Betikler klasörünün** altında sizin için örnek betikler ve betik etiketleri oluşturulmuştur. Tüm betik etiketleri düzenlenebilir. Betik yollarınıza başvurmak için bunları yeniden atayabilirsiniz.

   - 2. adımda **İlk Çalıştırma testi** seçiliyse, betikler klasörünün altında **giden kutusu** klasörünü görebilirsiniz. Yükleme betiği için **'Yükledikten sonra yeniden başlat'** etiketi eklemeyi de seçebilirsiniz.

   > [!div class="mx-imgBorder"]
   > [![Örnek betikler ve betik etiketleri](Media/uploadingzip07-edit-script.png) ](Media/uploadingzip07-edit-script.png#lightbox)

   > [!NOTE]
   > OOB test türü için Yükleme, Başlatma ve Kapatma betik etiketleri zorunlu. Etiketlerin yeniden atanması, test başlatılırken doğru betik yolunun kullanılmasını sağlar.

   > [!div class="mx-imgBorder"]
   > [![Betikler eksik bildirimi](Media/uploadingzip08-required-prompt.png) ](Media/uploadingzip08-required-prompt.png#lightbox)

   - 2. adımda **İşlevsel test** seçilirse betikler klasörünün altında **işlev** klasörünü görebilirsiniz. **'İşlevsel test listesine ekle'** düğmesi kullanılarak daha işlevsel test betikleri eklenebilir. En az bir (1) betik gerekir ve en fazla sekiz (8) işlevsel test betiği ekleyebilirsiniz.

   > [!div class="mx-imgBorder"]
   > [![İşlevsel test listesine](Media/uploadingzip09-add-to-list.png) ekle ](Media/uploadingzip09-add-to-list.png#lightbox)

   > [!NOTE]
   > İşlevsel test türü için en az 1 işlevsel betik etiketi zorunludur.

   Eylem panelinden daha işlevsel betikler eklemek için **İşlevsel test listesine ekle'yi** seçin. Seçenekler şunlardır:

   - Sol üç nokta düğmeleriyle sürükleyerek betik yollarını yeniden sıralayabilirsiniz. İşlevsel betikler listelendikleri sırayla çalışır. Belirli bir betikteki bir hata, izleyen betiklerin yürütülmesini durdurur.
   - Birden çok betik için 'Yürütmeden sonra yeniden başlat' seçeneğini ayarlayın.
   - Belirli bir betik yolunda daha önce güncelleştirme uygulayın. Bu güncelleştirme, işlevsel test betiklerini yürütme sırasında Windows Update düzeltme ekinin ne zaman uygulanacağını belirtmek üzere işlevsel testler yapmak isteyen kullanıcılara yöneliktir.

   > [!div class="mx-imgBorder"]
   > [![İşlevsel test](Media/uploadingzip10-functional-test.png) ](Media/uploadingzip10-functional-test.png#lightbox)

4. Gerekli tüm bilgiler doldurulduktan sonra, alt kısımdaki İleri düğmesini seçerek 4. adıma geçebilirsiniz.

### <a name="step-4-set-test-matrix"></a>Adım 4. Test matrisini ayarlama

Test matrisi sekmesi, testinizin yürütülmesini isteyebileceğiniz belirli Windows güncelleştirme programını veya Windows ürününü belirtmenize yöneliktir.

   > [!div class="mx-imgBorder"]
   > ![Test matrisi yeni paketini ayarlama](Media/settestmatrix01-newpackage.png)

1. **İşletim sistemi güncelleştirme türünü** seçin
   - Test Tabanı, uygulamalarınızın performansının en son Windows güncelleştirmelerine göre bozulmamasını sağlamak için zamanlanmış test sağlar. 

   > [!div class="mx-imgBorder"]
   > ![Test matrisini ayarla osupdate'i seçin](Media/settestmatrix02-chooseosupdate.png)

   - Kullanılabilir 2 seçenek vardır:
   
     - **Güvenlik güncelleştirmeleri**, paketinizin Windows aylık güvenlik güncelleştirmelerinin artımlı değişim sıklığına karşı test edilmesine olanak tanır.
     - **Özellik güncelleştirmeleri**, paketinizin Windows Insider Programı'ndaki en son Windows Insider Preview Derlemelerindeki yeni özelliklere karşı test edilmesine olanak tanır.

2. **Güvenlik Güncelleştirmesini** Yapılandırma Güvenlik güncelleştirmelerini ayarlamak için, "Test etmek için işletim sistemi sürümleri" açılan listesinden test etmek istediğiniz Windows ürünlerini belirtmeniz gerekir.

   > [!div class="mx-imgBorder"]
   > ![Test matrisini ayarlama securityupdate'i yapılandırma](Media/settestmatrix03-configuresecurityupdate.png)

   - Seçiminiz, seçilen ürünler için Windows aylık kalite güncelleştirmelerinin B sürümüne karşı otomatik test çalıştırmaları için uygulamanızı kaydeder.
     - Test Temeli'ne Varsayılan Erişim müşterileri olan müşteriler için uygulamaları, Salı Düzeltme Eki'nden başlayarak B sürümü güvenlik güncelleştirmelerinin son sürümüne göre doğrulanır.
     - Test Temeli'ne Tam Erişim müşterileri olan müşteriler için, uygulamaları B yayın güvenlik güncelleştirmelerinin yayın öncesi sürümlerine göre doğrulanır ve Bu sürümLer, Düzeltme Eki Salı'dan 3 hafta öncesine kadar başlar. Bu, Tam Erişim müşterilerinin Yama Salı'daki son sürümden önce test sırasında bulunan sorunları çözmek için proaktif adımlar atmasına olanak tanır.  
       (Tam Erişim müşterisi nasıl olunur? Erişim [düzeyini değiştirme isteğine bakın | Microsoft Docs](accesslevel.md))

3. **Özellik Güncelleştirmesini** Yapılandırma
   - Özellik güncelleştirmelerini ayarlamak için hedef ürünü ve "Insider Kanalı" açılan listesinden önizleme kanalını belirtmeniz gerekir.

   > [!div class="mx-imgBorder"]
   > ![Test matrisini ayarlama featureupdate'i yapılandırma](Media/settestmatrix04-configurefeatureupdate.png)

   - Seçiminiz, uygulamanızı seçtiğiniz ürün kanalının en son özellik güncelleştirmelerine ve seçiminizin en son Windows Insider Preview Derlemelerinde gelecekteki tüm yeni güncelleştirmelere karşı otomatik test çalıştırmaları için kaydeder.

   - Geçerli işletim sisteminizi "İçgörüler için işletim sistemi temeli" bölümünde de ayarlayabilirsiniz. Olduğu gibi işletim sistemi ortamınızın ve en son hedef işletim sisteminizin regresyon analizini yaparak size daha fazla test içgörüleri sağlarız.

   > [!div class="mx-imgBorder"]
   > ![Test matrisi kümesi işletim sistemi ayarlama](Media/settestmatrix05-setos.png)  

### <a name="step-5-review--publish"></a>Adım 5. Gözden geçirme + yayımlama

1. Taslak paketinizin doğruluğu ve doğruluğu için tüm bilgileri gözden geçirin. Düzeltmeler yapmak için, ayarları gerektiği gibi belirttiğiniz erken adımlara geri dönebilirsiniz.

   > [!div class="mx-imgBorder"]
   > [![Gözden geçirme ve yayımlama](Media/uploadingzip12-review.png) ](Media/uploadingzip12-review.png#lightbox)

2. Doğrulama çalıştırması tamamlama bildirimi için paketinizin e-posta bildirimini almak için bildirim kutusunu da işaretleyebilirsiniz.

   > [!div class="mx-imgBorder"]
   > ![Bildirim](Media/uploadingzip13-notification.png)

3. Giriş verileri yapılandırmasını son haline getirme işlemini tamamladığınızda, paketinizi Test Temeli'ne yüklemek için **Yayımla'yı** seçin. Aşağıdaki bildirim, paket başarıyla yayımlandığında ve Doğrulama işlemine girdiğinde görüntülenir.

   > [!NOTE]
   > Paketin gelecekteki testler için kabul edilmeden önce doğrulanması gerekir. Paketi gerçek bir test ortamında çalıştırmayı içerdiğinden Doğrulama işlemi 24 saate kadar sürebilir.

   > [!div class="mx-imgBorder"]
   > ![Yayımlama başarılı bildirimi](Media/uploadingzip14-success.png)

4. Yeni karşıya yüklediğiniz paketin ilerleme durumunu denetlemek için **Paketleri Yönet** sayfasına yönlendirilirsiniz.

   > [!div class="mx-imgBorder"]
   > [![Paketleri](Media/uploadingzip15-package-list.png) Yönet ](Media/uploadingzip15-package-list.png#lightbox)

   > [!NOTE]
   > Doğrulama işlemi tamamlandığında Doğrulama durumu Kabul Edildi olarak değişir. Bu noktada başka eyleme gerek yoktur. Yapılandırılan işletim sistemlerinizde yeni güncelleştirmeler olduğunda paketiniz otomatik olarak yürütülecek şekilde alınır. Doğrulama işlemi başarısız olursa paketiniz test için hazır değildir. Lütfen günlükleri denetleyin ve herhangi bir hata oluşup oluşmadığını değerlendirin. Olası sorunlar için paket yapılandırma ayarlarınızı da denetlemeniz gerekebilir.


## <a name="continue-package-creation"></a>Paket oluşturmaya devam et

Daha önce taslak paketleriniz varsa, kaydedilen taslak paketlerinizin listesini **Yeni paket** sayfasında görüntüleyebilirsiniz. 'Düzenle' kalem simgesini seçerek düzenlemenize doğrudan geçen sefer duraklattığınız adımda devam edebilirsiniz.

> [!div class="mx-imgBorder"]
> [![Yeni paket sayfası](Media/uploadingzip16-draft-packages.png) ](Media/uploadingzip16-draft-packages.png#lightbox)

> [!NOTE]
> Panoda yalnızca devam eden çalışma paketi gösterilir. Yayımlanan paket için Paketleri Yönet sayfasını kontrol edebilirsiniz.
