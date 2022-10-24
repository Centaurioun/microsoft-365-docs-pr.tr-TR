---
title: Uygulamanızı en son Microsoft 365 uygulamalarıyla test edin
description: Uygulamanızı en son Microsoft 365 uygulamalarıyla test etme
search.appverid: MET150
author: Tinacyt
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 10/21/2022
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: Tinacyt
f1.keywords: NOCSH
ms.openlocfilehash: 8fa106208f537ea67202eaa6a60b700c2854614a
ms.sourcegitcommit: 0ca3ab2abe07810e9b2cc2d806e3c6b9f35b146c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2022
ms.locfileid: "68685402"
---
# <a name="test-your-application-with-latest-microsoft-365-apps"></a>Uygulamanızı en son Microsoft 365 uygulamalarıyla test edin


Bu bölümde, uygulamanızı en son Microsoft 365 uygulamalarıyla test etme yönergeleri sağlanır.

> [!IMPORTANT]
> Şu anda yalnızca aylık önizleme kanalından Office 365 ön sürümü kullanılabilir.


### <a name="choose-the-microsoft-365-application"></a>Microsoft 365 uygulamasını seçme 

Yeni bir paket eklerken test adımını **yapılandır'da** **Microsoft uygulamalarını önceden yükle iki durumlu** düğmesi, kullanıcının test için yüklenecek en son güncelleştirmeye sahip Microsoft 365 uygulamalarının yayın öncesi sürümünü seçmesine olanak tanır.

 > [!div class="mx-imgBorder"]  
 > ![Paket yapılandırma testlerini gösteren ekran görüntüsü](Media/testwithm365app01.png)  
 > [!NOTE] 
 > Office önizleme kanalı, aylık tempolu sürüm öncesi Office güncelleştirmeleri sağladığından, iki durumlu düğme açıldıktan sonra paket için yalnızca **güvenlik güncelleştirme** türü etkinleştirilir. Test matrisinde seçilebilen Windows işletim sistemi sürümleri, seçilen Office ürününün kullanılabilir olduğu Windows ürünleriyle de sınırlı olacaktır. Belirtilen ön koşul nedeniyle, mevcut paketler için Office güncelleştirme testi özelliğini açmak isterseniz, desteklenmeyen güncelleştirme türü ve Windows işletim sistemi ürünleri varsayılan olarak devre dışı bırakılır.

&nbsp;  
### <a name="define-the-install-sequence-for-the-chosen-microsoft-365-application"></a>Seçilen Microsoft 365 uygulaması için yükleme sırasını tanımlama 

**İşlevsel testi** kullanarak, en son güncelleştirmeyle birlikte yayın öncesi Office yükleme sırasını tanımlayabilirsiniz. Kendi betiğinizi oluşturduktan ve İşlevsel test listesine ekledikten sonra aşağıdaki **İşlevsel test panelini aç** simgesine tıklayın.

 > [!div class="mx-imgBorder"]  
 > ![Paket düzenleme paketini gösteren ekran görüntüsü](Media/testwithm365app02.png)

öğeleri doğru adıma yukarı ve aşağı sürükleyerek işlevsel liste panelindeki betikleri yeniden sıralayabilirsiniz. Office yüklemesinin yayın öncesi sürümünün gerçekleşmesini istediğiniz betiği seçerek Office yüklemesinin yürütüleceği adımı seçin.  

Aşağıdaki örnekte, önce Windows update, ardından office yükleme öncesi betiği yüklenir, ardından kullanıcının uygulaması için yükleme betiğinden önce Office ön sürümü yüklenir ve ardından çalıştırma testi betiği yürütülür.

 > [!div class="mx-imgBorder"]  
 > ![İşlevsel testi gösteren ekran görüntüsü](Media/testwithm365app03.png)  
 > [!NOTE]
 > İlk çalıştırma testi türü için, Office yüklemesi varsayılan olarak Windows update yüklemesinin ardından ve yükleme betiği yürütülmeden önce yürütülür.

&nbsp;  
### <a name="view-the-test-result-with-microsoft-365-application"></a>Microsoft 365 uygulamasıyla test sonucunu görüntüleme  

Paket doğrulamayı geçtikten sonra bir test çalıştırması yürütülür. Aylık olarak, en son Windows güvenlik güncelleştirmesi yayımlandığında Salı günü her düzeltme ekinde otomatik çalıştırma zamanlanır. Paket, uygulamanızın hem en son Windows hem de Office güncelleştirmelerine göre test edilmesine izin vermek için ilgili yürütme tarihi itibarıyla aylık önizleme kanalından Office'in en son yayın öncesi sürümünü yükler.

Paket adındaki bağlantıya tıklayarak Test özeti sayfasının altında test çalıştırmalarının sonuçlarını görüntüleyebilirsiniz.

 > [!div class="mx-imgBorder"]  
 > ![Güvenlik güncelleştirmesini gösteren ekran görüntüsü](Media/testwithm365app04.png)

&nbsp;  
Ayrıntılı sayfada, office yüklemesinin durumunu temsil eden otomatik olarak yürütülen bir betik olarak Install-Office'i görürsünüz.

 > [!div class="mx-imgBorder"]  
 > ![Güvenilirlik'i gösteren ekran görüntüsü](Media/testwithm365app05.png)  
 > [!NOTE]
 > İlk çalıştırma testi türü için, kullanıcının yüklü uygulamasıyla varsayılan olarak çalışan ön sürüm Office'e yönelik çakışma sinyallerinin toplanmasına yardımcı olmak için önceden tanımlanmış bir Office birlikte çalışma test betiği yürütülür. Uygulamanızın en son Office güncelleştirmeleriyle nasıl çalıştığını test etmeye odaklanmak istiyorsanız İşlevsel testi kullanarak kendi test akışınızı tanımlayabilir ve Office test betiğini atlayabilirsiniz.
