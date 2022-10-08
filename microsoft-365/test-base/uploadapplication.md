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
ms.openlocfilehash: 7cec39a88c5b589959a8cd5b9fd3103f465ca60c
ms.sourcegitcommit: fa570d90b00ed1bb40e1ca27b11c66a84c4204e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2022
ms.locfileid: "68481839"
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

### <a name="step-4-test-matrix"></a>Adım 4. Test matrisi

1. Test matrisi sekmesinde işletim **sistemi güncelleştirme türünü** seçin. Desteklenen iki işletim sistemi güncelleştirme türü vardır.

   - **Güvenlik güncelleştirmeleri**, paketinizin Windows yayın öncesi aylık güvenlik güncelleştirmelerinin artımlı değişim sıklığına karşı test edilmesine olanak tanır.
   - **Özellik güncelleştirmeleri**, paketinizin Windows Insider Programı'ndan windows yayın öncesi iki yıllık özellik güncelleştirmeleri derlemelerine karşı test edilmesine olanak tanır.

2. Güvenlik güncelleştirme testleri için işletim sistemi sürümlerini seçin.

   **İşletim sistemi güncelleştirme türünde Güvenlik güncelleştirmeleri** seçilirse paketinizin test edeceği Windows işletim sistemi sürümlerini seçmeniz gerekir.

   > [!NOTE]
   > Paketinizi hem Sunucu hem de İstemci işletim sistemiyle sınamayı seçerseniz, lütfen paketin uyumlu olduğundan ve her iki işletim sisteminde de çalıştırılabilir olduğundan emin olun.

3. Özellik güncelleştirme testleri seçeneklerini belirleyin.

   - **İşletim sistemi güncelleştirme türünde Özellik güncelleştirmeleri** seçiliyse, aşağıdaki seçenekleri tamamlamanız gerekir.
   - **Insider Kanalı** için, paketlerinizin test edilmesi gereken derleme olarak Windows Insider Program Kanalı'nı seçin. Şu anda **Insider Beta Kanalında** sunulan derlemeleri kullanıyoruz.
   - **insight işletim sistemi temeli için**, test sonuçlarınızı karşılaştırmak için temel olarak kullanılacak Windows işletim sistemi sürümünü seçin.

   > [!div class="mx-imgBorder"]
   > [![Test matrisi](Media/uploadingzip11-test-matrix.png) ](Media/uploadingzip11-test-matrix.png#lightbox)

4. Gerekli tüm bilgiler doldurulduktan sonra, alt kısımdaki İleri düğmesini seçerek 5. adıma (son adım) geçebilirsiniz.

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