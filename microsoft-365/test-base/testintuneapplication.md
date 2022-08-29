---
title: Test Tabanında Intune uygulamanızı test edin
description: Intune uygulamanızı test etme
search.appverid: MET150
author: Tinacyt
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 04/11/2022
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: Tinacyt
f1.keywords: NOCSH
ms.openlocfilehash: 2fbe3a21762f6bf048d5f35485a359389df93ce2
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/11/2022
ms.locfileid: "67315996"
---
# <a name="test-your-intune-application-on-test-base"></a>Test Tabanında Intune uygulamanızı test edin 
  > [!Note] 
  > Bu kılavuz, intunewin biçim paketinizi Test Temeli'ne yüklemeniz için size yol gösterir. Genel Test Temeli paketi karşıya yükleme yönergesi için lütfen bu [belgeyi inceleyin](https://microsoft.sharepoint.com/:w:/t/AzureSUVPCoreTeam/EeHQIT3qA0FKqBDWI5TzmzgBiH2Syz39o5VbY2kdugMn4A?e=Rk1KD9).

## <a name="intunewin-upload-flow"></a>Intunewin Karşıya Yükleme Akışı
Ticari kullanımı daha da etkinleştirmeye yönelik bir çaba olarak Test Base, standart ekleme paketi biçimi olarak Intune içinde uygulamaları için uygulamaları yöneten BT Uzmanları için intunewin biçimini desteklemeye başladı. intunewin karşıya yükleme akışı, BT Uzmanlarının uygulamalarını ve test yapılandırmalarını Test Temeli'ne hızlı bir şekilde eklemek için MEM/Intune aracılığıyla son cihazlarına dağıttığı uygulamaları içeren intunewin biçim paketlerini yeniden kullanma deneyimi sağlar. 

**Önkoşullar**
  - Şu anda Intune hesabı ile Test Temeli hesabı arasında aynı abonelik aracılığıyla eşitlenen Test Temeli desteği (intunewin paketinizi karşıya yüklemek için bir Intune hesabınız olması gerekmez, ancak intunewin dosyasının ilgili uygulamaları için Intune yapılandırmasını Intune eşitlemek istiyorsanız, Intune  hesabı, Test Temel hesabınızla aynı abonelik altında oluşturulur).
  - Karşıya yüklenecek Intunewin paketleri. 

**Intunwin dosyası Karşıya Yükleme Akışı (Intune hesabıyla eşitlenir)** <br/>
zaten Intune portalına eklenmiş olan bir Intune paketine sahip Intune müşterisi olarak. Müşteri intunewin paketini (Intune'de yönetilen önceden yükleme uygulamalarının bağımlılıkları olan/olmayan bir uygulamayı içeren) Test Temel hizmetine ekleyebilir. (Intune uygulama bilgilerini eşitlemek için uygun izne sahip Intune hesabı aracılığıyla).

**Hazırlık Adımı**
1. Test Temeli hesabınızla oturum açın.
2. intunewin paketinizi hazırlayın.
3. Aşağıdaki gibi "Intune Uygulaması ile paket oluştur" bağlantısına tıklayarak karşıya yüklemeye başlayın.
    
    > [!div class="mx-imgBorder"] 
    > ![Intune uygulamasıyla paket oluşturmaya başlama](Media/testintuneapplication01.png) 


**1. Adım: İçerik Tanımlama**
1. Seçtiğiniz intunewin paketini karşıya yükleyin.
2. Aşağıdaki "Belirteç ver ve uygulamayı seç" bağlantısına tıklayarak belirteç verin.
3. Intune hesabınızla otomatik eşitleme yaptıktan sonra, Intune hesabınızın altında uygulamalarınızla birlikte listelenirsiniz. Karşıya yüklediğiniz intunewin paketine karşılık gelen uygulamayı seçin ve ardından "Seç"e tıklayın.
    
    > [!div class="mx-imgBorder"] 
    > ![Intune paketini karşıya yükleme](Media/testintuneapplication02.png) 


5. 1. Adım sayfasında Bağımlılık bölümünde listelenen bağımlılıkları görürsünüz; bağımlılığın yükleme dosyasını karşıya yüklemeyi veya bu adımdan kaldırmayı seçebilirsiniz (3. Adımda bağımlılığı kendiniz yönetmeyi planlıyorsanız ilgili ikili dosyaları kendiniz sağlarsınız). Bu bölümdeki seçili bağımlılıklar, Intune aracılığıyla yükleneceği şekilde önceden yüklenir.
    
    > [!div class="mx-imgBorder"] 
    > ![Bağımlılık paketini karşıya yükleme](Media/testintuneapplication03.png) 


**2. Adım: Testi Yapılandırma**
1. PowerShell'i seçin.
2. İlk Çalıştırma'ya tıklayın.


**3. Adım: Paketi Düzenle**
1. Otomatik olarak oluşturulan betiklerin doğru etiketlenmiş olup olmadığını denetleyin.
2. yapılandırmayı Intune başarıyla eşitlediyseniz, yükleme/kaldırma betiklerine test uygulamasının yükleme/kaldırma komutlarının eklendiğini görebilmeniz gerekir; **karşıya yüklenen bağımlılığın** komutları da gözden geçirilmek üzere paket gezgini ağacına eklenmelidir.
3. Test uygulaması ikili dosyalarının **bin** klasörü altına taşınıp taşınmadığını denetleyin.
4. **Guid** klasörünün altına **yüklenen** bağımlılık ikili dosyalarını denetleyin.
5. Betikleri gerektiği gibi düzenleyebilir ve kaydedebilirsiniz.
    > [!Note] 
    > Bağımlılık paketi karşıya yüklenmediyse, Test Temeli bunun için yükleme/kaldırma komutları oluşturmaz.


**4. Adım: Test Matrisi**
1. İlgili test türleri için işletim sistemi listesinde bulunan varsayılan seçimleri denetleyin.
    - Test tabanı **, Windows 10 2004 dışında Windows 10 1909'dan** birden çok Windows toplu güncelleştirmesi seçmeyi destekler, ancak Intune Win **uygulamasına Windows 10 1607'ye** eşit veya daha yüksek sürümlerden bir sürüm atanabilir.
    - İşletim sistemi listesi, Intune Win uygulaması için belirtilen en düşük işletim sisteminden daha yüksek olan Test tabanı tarafından desteklenen tüm işletim sistemini içerecek şekilde varsayılan olarak kullanılır.
2. Kullanıcıların işletim sistemi seçimini gerektiği gibi değiştirmesine izin verilir.


**5. Adım: Gözden Geçirme + Yayımlama** <br/>
Paketin yayımlanabileceği yapılandırmayı gözden geçirin.<br/><br/>


**Intunwin dosyası Karşıya Yükleme Akışı (Intune hesabıyla eşitlenemiyor)** <br/>
Tek başına intunewin paketi olan bir Test Temeli müşterisi olarak. Müşteri, ekleme işlemini tamamlamak için Intune hesabına izin verilmesine gerek kalmadan intunewin paketini (Intune yönetilen önceden yükleme uygulamalarının bağımlılıkları olan/olmayan bir uygulama içeren) ekleyebilir.

**Hazırlık Adımı**
1. Test Temeli hesabınızla oturum açın.
2. intunewin paketinizi hazırlayın.
3. Aşağıdaki gibi "Intune Uygulaması ile paket oluştur" bağlantısına tıklayarak karşıya yüklemeye başlayın.
    
    > [!div class="mx-imgBorder"] 
    > ![Intune Uygulaması ile paket oluşturma](Media/testintuneapplication04.png) 


**1. Adım: İçerik Tanımlama**
1. intunewin paketini karşıya yükleyin.
2. Tüm bilgileri tercihinize göre belirtin.


**2. Adım: Testi Yapılandırma**
1. PowerShell'i seçin.
2. İlk Çalıştırma'ya tıklayın.


**3. Adım: Paketi Düzenle**
1. Betiklerin doğru etiketlenmiş olup olmadığını denetleyin.
2. Karşılık gelen Intune hesabından hiçbir yükleme/kaldırma komutu eşitlenmediği için tüm betikleri (yükleme/kaldırma/başlatma/kapatma) kendiniz sağlamanız gerekir.
3. Test uygulaması ikili dosyalarının bin klasörü altına taşınıp taşınmadığını denetleyin.
4. Betikleri gerektiği gibi düzenleyebilir ve kaydedebilirsiniz.


**4. Adım: Test Matrisi**
1. Varsayılan işletim sistemi sürümü önceden seçilmez.
2. Kullanıcıların zamanlanacak işletim sistemi üzerinde kendi seçimlerini yapmalarına izin verilir.


**5. Adım: Gözden Geçirme + Yayımlama** <br/>
Paketin yayımlanabileceği yapılandırmayı gözden geçirin.




