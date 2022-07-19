---
title: Test Tabanında İkili Dosyalar Oluşturma ve Test Etme
description: Test Tabanında ikili dosyalar oluşturma ve test etme
search.appverid: MET150
author: Tinacyt
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 04/08/2022
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: Tinacyt
f1.keywords: NOCSH
ms.openlocfilehash: 99e2a26294d8e67854387d3c4f3d41c469a97a50
ms.sourcegitcommit: aff1732dfa21e9283b173d8e5ca5bcbeeaaa26d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2022
ms.locfileid: "66861721"
---
# <a name="creating-and-testing-binary-files-on-test-base"></a>Test Tabanında İkili Dosyalar Oluşturma ve Test Etme

Bu bölüm, Test Temeli'ne yükleme ve test etme amacıyla ikili dosyaları içeren yeni bir paket oluşturmak için gereken tüm adımları sağlar. Önceden oluşturulmuş bir .zip dosyanız varsa, dosyanızı karşıya yüklemek için [Önceden oluşturulmuş Zip paketini](uploadApplication.md) karşıya yükleme seçeneğini görebilirsiniz.

> [!IMPORTANT]
> **Test Temeli** hesabınız yoksa, [Test Temeli hesabı oluşturma](createAccount.md) bölümünde açıklandığı gibi devam etmeden önce bir hesap oluşturmanız gerekir.

## <a name="create-a-new-package"></a>Yeni paket oluşturma

[Azure portal](https://portal.azure.com/), paketinizi oluşturup karşıya yükleyebileceğiniz **Test Temeli** hesabına gidin ve aşağıdaki adımları uygulayın. 

Sol taraftaki menüde **Paket kataloğu** altında **Yeni paket'i** seçin. Ardından paketinizi 5 adımda çevrimiçi olarak oluşturmak için ilk **'Yeni paketi çevrimiçi oluştur'** kartına tıklayın!

> [!div class="mx-imgBorder"]
> ![Yeni Paket oluşturma sihirbazı](Media/testapplication01.png)

### <a name="step-1-define-content"></a>Adım 1. İçerik tanımlama

1. **Paket kaynağı bölümünde, Paket kaynak** türünde İkili Dosyalar'ı (örneğin: .exe, .msi) seçin.

   > [!div class="mx-imgBorder"]
   > ![Paket kaynağınızı seçin](Media/testapplication02.png)

2. Ardından , 'Dosya seç' düğmesine tıklayarak veya dosyanız henüz hazır değilse Test Temeli örnek şablonunu başlangıç noktası olarak kullanmak için kutuyu işaretleyerek uygulama dosyanızı karşıya yükleyin.

   > [!div class="mx-imgBorder"]
   > ![Dosya seç](Media/testapplication03.png)

3. Paketinizin adını ve sürümünü **Temel bilgiler** bölümüne yazın.

   > [!NOTE]
   > Paket adı ve sürümü birleşimi Test Temeli hesabınızda benzersiz olmalıdır.

   > [!div class="mx-imgBorder"]
   > ![Temel bilgileri girin](Media/testapplication04.png)

4. İstenen tüm bilgiler belirtildikten sonra Sonraki **: Yapılandırma testi** düğmesine tıklayarak sonraki aşamaya geçebilirsiniz.

   > [!div class="mx-imgBorder"]
   > ![Sonraki adım](Media/testapplication05.png)

### <a name="step-2-configure-test"></a>Adım 2. Testi yapılandırma

1. **Test türünü** seçin. Desteklenen iki test türü vardır:
   - Kullanıma **Açık (OOB) testi** paketinizi yükleme, başlatma, kapatma ve kaldırma işlemlerini gerçekleştirir. Yüklemeden sonra başlatma-kapatma yordamı, tek bir kaldırma çalıştırılmadan önce 30 kez yinelenir. OOB testi, Windows derlemeleriyle karşılaştırmak için paketinizde standart telemetri sağlar.
   - **İşlevsel test**, paketinizde karşıya yüklenen test betiklerinizi yürütür. Betikler belirttiğiniz sırada çalıştırılır ve belirli bir betikteki bir hata, izleyen betiklerin yürütülmesini durdurur.

   > [!NOTE]
   > Kullanıma Sunulan test artık isteğe bağlıdır.

   > [!div class="mx-imgBorder"]
   > ![kullanıma sunulan test isteğe bağlıdır](Media/testapplication07.png)

2. Gerekli tüm bilgiler doldurulduktan sonra, en alttaki İleri düğmesine tıklayarak 3. adıma geçebilirsiniz. Test betikleri başarıyla oluşturulduğunda bir bildirim açılır.

   > [!div class="mx-imgBorder"]
   > ![Betik istemleri oluşturma](Media/testapplication08.png)

### <a name="step-3-edit-package"></a>Adım 3. Paketi düzenle

1. Paketi düzenle sekmesinde,
   - **Paket Önizlemesi'nde** paket klasörünüzü ve dosya yapınızı denetleyin.
   - **PowerShell kod düzenleyicisiyle** betiklerinizi çevrimiçi olarak düzenleyin.

   > [!NOTE]
   > Başvurunuz için bazı örnek betikler oluşturuldu. Her betiği dikkatle gözden geçirmeniz ve komut ve işlem adını kendinizle değiştirmeniz gerekir. 

   > [!div class="mx-imgBorder"]
   > ![betikleri çevrimiçi düzenleme](Media/testapplication09.png)

2. **Paket Önizlemesi'nde**, ihtiyacınıza göre
   - Yeni bir klasör oluşturun.
   - Yeni bir betik oluşturun.
   - Yeni bir dosya yükleyin.

   > [!div class="mx-imgBorder"]
   > ![Kaynak oluşturma](Media/testapplication10.png)

3. **Betikler klasörünün** altında sizin için örnek betikler ve betik etiketleri oluşturulmuştur. Tüm betik etiketleri düzenlenebilir, bunları betik yollarınıza başvurmak üzere yeniden atayabilirsiniz.
   - 2. adımda **İlk Çalıştırma testi** seçiliyse, betikler klasörünün altında **giden kutusu** klasörünü görebilirsiniz. Yükleme betiği için **'Yükledikten sonra yeniden başlat'** etiketi ekleme seçeneğiniz de vardır.

   > [!div class="mx-imgBorder"]
   > ![Başvuru betiği](Media/testapplication11.png)

   > [!NOTE]
   > OOB test türü için betik etiketlerini yükleme, başlatma ve kapatma zorunlu. Etiketlerin yeniden atanması, test başlatılırken doğru betik yolunun kullanılmasını sağlar.

   > [!div class="mx-imgBorder"]
   > ![Paket istemini düzenle](Media/testapplication11-2.png)

   - 2. adımda **İşlevsel test** seçilirse betikler klasörünün altında **işlev** klasörünü görebilirsiniz. **'İşlevsel test listesine ekle'** düğmesi kullanılarak daha işlevsel test betikleri eklenebilir. En az bir (1) betik gerekir ve en fazla sekiz (8) işlevsel test betiği ekleyebilirsiniz.

   > [!div class="mx-imgBorder"]
   > ![İşlevsel test listesine ekle](Media/testapplication12.png)

   > [!NOTE]
   > İşlevsel test türü için en az 1 işlevsel betik etiketi zorunludur.

   Daha fazla İşlevsel betik eklemek için **'İşlevsel test listesine ekle'ye** tıklayabilirsiniz. Ardından eylem paneli açılır ve şunları yapabilirsiniz:
   - Sol üç nokta düğmeleriyle sürükleyerek betik yollarını yeniden sıralayabilirsiniz. İşlevsel betikler listelendikleri sırayla çalışır. Belirli bir betikteki bir hata, izleyen betiklerin yürütülmesini durdurur.
   - Birden çok betik için 'Yürütmeden sonra yeniden başlat' seçeneğini ayarlayın.
   - Belirli bir betik yolunda daha önce güncelleştirme uygulayın. Bu, işlevsel test betiklerini yürütme sırasında Windows Update düzeltme ekinin ne zaman uygulanacağını belirtmek için işlevsel testler yapmak isteyen kullanıcılara yöneliktir.

   > [!div class="mx-imgBorder"]
   > ![işlevsel test](Media/testapplication13.png)

4. Gerekli tüm bilgiler doldurulduktan sonra, alttaki İleri düğmesine tıklayarak 4. adıma geçebilirsiniz.

### <a name="step-4-test-matrix"></a>Adım 4. Test matrisi

1. Test matrisi sekmesinde işletim **sistemi güncelleştirme türünü** seçin. Desteklenen iki işletim sistemi güncelleştirme türü vardır.
   - **Güvenlik güncelleştirmeleri**, paketinizin Windows yayın öncesi aylık güvenlik güncelleştirmelerinin artımlı değişim sıklığına karşı test edilmesine olanak tanır.
   - **Özellik güncelleştirmeleri**, paketinizin Windows Insider Programı windows yayın öncesi iki yıllık özellik güncelleştirmeleri derlemelerinde test edilmesine olanak tanır.

2. Güvenlik güncelleştirme testleri için işletim sistemi sürümlerini seçin.

   **İşletim sistemi güncelleştirme türünde Güvenlik güncelleştirmeleri** seçilirse paketinizin test edeceği Windows işletim sistemi sürümlerini seçmeniz gerekir.

   > [!NOTE]
   > Paketinizi hem Sunucu hem de İstemci işletim sistemiyle sınamayı seçerseniz, lütfen paketin uyumlu olduğundan ve her iki işletim sisteminde de çalıştırılabilir olduğundan emin olun.

3. Özellik güncelleştirme testleri seçeneklerini belirleyin.
   - **İşletim sistemi güncelleştirme türünde Özellik güncelleştirmeleri** seçiliyse, aşağıdaki seçenekleri tamamlamanız gerekir.
   - **Insider Channel** için paketlerinizin test edilmesi gereken derleme olarak Windows Insider Programı Kanalı'nı seçin. Şu anda **Insider Beta Kanalında** sunulan derlemeleri kullanıyoruz.
   - **insight işletim sistemi temeli için**, test sonuçlarınızı karşılaştırmak için temel olarak kullanılacak Windows işletim sistemi sürümünü seçin.

   > [!div class="mx-imgBorder"]
   > ![Windows işletim sistemi sürümünü seçin](Media/testapplication14.png)

4. Gerekli tüm bilgiler doldurulduktan sonra, en alttaki İleri düğmesine tıklayarak 5. adıma (son adım) geçebilirsiniz.

### <a name="step-5-review--publish"></a>Adım 5. Gözden geçirme + yayımlama

1. Taslak paketinizin doğruluğu ve doğruluğu için tüm bilgileri gözden geçirin. Düzeltmeler yapmak için, ayarları gerektiği gibi belirttiğiniz erken adımlara geri dönebilirsiniz.

   > [!div class="mx-imgBorder"]
   > ![Paketi gözden geçirme](Media/testapplication15.png)

2. Doğrulama çalıştırması tamamlama bildirimi için paketinizin e-posta bildirimini almak için bildirim kutusunu da işaretleyebilirsiniz.

   > [!div class="mx-imgBorder"]
   > ![Bildirim](Media/testapplication16.png)

3. Giriş verileri yapılandırmasını son haline getirme işlemini tamamladığınızda, paketinizi Test Temeli'ne yüklemek için **Yayımla'ya** tıklayın.  Aşağıdaki bildirim, paket başarıyla yayımlandığında ve Doğrulama işlemine girdiğinde görüntülenir.  

   > [!NOTE]
   > Paketin gelecekteki testler için kabul edilmeden önce doğrulanması gerekir. Paketi gerçek bir test ortamında çalıştırmayı içerdiğinden Doğrulama işlemi 24 saate kadar sürebilir. 

   > [!div class="mx-imgBorder"]
   > ![Paket yayımlama istemleri](Media/testapplication17.png)

4. Yeni karşıya yüklediğiniz paketin ilerleme durumunu denetlemek için **Paketleri Yönet** sayfasına yönlendirilirsiniz.

   > [!div class="mx-imgBorder"]
   > ![Paketleri yönetme](Media/testapplication18.png)

   > [!NOTE]
   > Doğrulama işlemi tamamlandığında Doğrulama durumu Kabul Edildi olarak değişir. Bu noktada başka eyleme gerek yoktur. Yapılandırılan işletim sistemlerinizde yeni güncelleştirmeler olduğunda paketiniz otomatik olarak yürütülecek şekilde alınır. Doğrulama işlemi başarısız olursa paketiniz test için hazır değildir. Lütfen günlükleri denetleyin ve herhangi bir hata oluşup oluşmadığını değerlendirin. Olası sorunlar için paket yapılandırma ayarlarınızı da denetlemeniz gerekebilir.

### <a name="resume-creation-of-a-saved-draft-package"></a>Kaydedilmiş taslak paketin oluşturulmasını sürdürme

Daha önce taslak paketleriniz varsa, kaydedilen taslak paketlerinizin listesini **Yeni paket** sayfasında görüntüleyebilirsiniz. **'Düzenle'** kalem simgesine tıklayarak, **Durum** sütununda açıklandığı gibi, seçtiğiniz paketi kaldığınız yerden düzenlemeye devam edebilirsiniz.

> [!div class="mx-imgBorder"]
> ![Yeni paket sayfası](Media/testapplication19.png)

> [!NOTE]
> Panoda yalnızca kaydedilen taslak paketler gösterilir. Yayımlanan paketleri görüntülemek için Paketleri Yönet sayfasına gitmeniz gerekir.

