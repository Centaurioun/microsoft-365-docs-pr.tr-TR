---
title: Bellek regresyon analizi
description: Bellek regresyonu nasıl çıkarılır?
search.appverid: MET150
author: mansipatel-usl
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-Microsoft 365
ms.custom: ''
ms.reviewer: tinachen
f1.keywords: NOCSH
ms.openlocfilehash: 421fce87bc57f794bdf875e9bc09889bb20b62fb
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/11/2022
ms.locfileid: "67316435"
---
# <a name="memory-regression-analysis"></a>Bellek Regresyon Çözümlemesi

Test Tabanı, uygulamalarınızı çalıştıran test VM'lerinde önemli bellek kullanımı artışlarını daha net bir şekilde fark etmenizi sağlar. Bellek kullanımı gibi performans ölçümleri, genel uygulama durumunun göstergesi olabilir ve bu eklemenin uygulamalarınızın en iyi performansı göstermesini sağlamaya büyük ölçüde yardımcı olacağına inanıyoruz.

Daha fazla ayrıntı için okumaya devam edin veya en son iyileştirmeleri hızlı bir şekilde izlemek için bu videoyu izleyin. 

Microsoft 365'in regresyon analizine yardımcı olma özelliği için Test Temeli hakkında daha fazla bilgi için bkz. İşlem güvenilirliğine dayalı regresyon sonuçları.

<b>Bellek regresyonlarına daha yakından bakma</b>

Microsoft 365 için Test Temeli panosu, uygulamanız tarafından önceden yayımlanan yeni bir Windows güncelleştirmesinde tüketilen belleği gösterir ve bunu son yayımlanan Windows güncelleştirmesi tarafından kullanılan bellekle karşılaştırır. 

Bu ayın geliştirmeleriyle birlikte bellek regresyon analizi artık sık kullandığınız işlemlerde öne çıktı. Uygulamalar birden çok işlem içerebilir ve Sık kullandığınız işlemleri Güvenilirlik sekmesinden el ile seçebilirsiniz. Hizmetimiz daha sonra bu sık kullanılan işlemlerdeki bellek regresyonlarını belirlerken farklı Windows update sürümlerinde test çalıştırmalarını karşılaştıracaktır. Bir regresyon algılanırsa, regresyon hakkındaki ayrıntılar kolayca kullanılabilir.

Şimdi bu özelliğe ayrıntılı olarak göz atalım ve Windows Performans Analizi kullanarak bellek regresyonlarında nasıl sorun giderebileceğinizi tartışalım.

Bellek regresyonundan kaynaklanan hata sinyali, Bellek Kullanımı altındaki Test sonuçları sayfasındaki Microsoft 365 için Test Tabanı panosunda gösterilir:

![Bellek kullanımı sonuçları.](Media/01_memory-utilization-results.png)


Daha yüksek bellek tüketimi nedeniyle uygulama hatası, Test Özeti sayfasında olduğu gibi ```Fail``` de görüntülenir:

![Test özeti sonuçları.](Media/02_test-summary.png)

Hata sinyallerini önceden sağlayarak hedefimiz, uygulamanız için son kullanıcı deneyimini kesintiye uğratabilecek ve etkileyebilecek olası sorunları net bir şekilde işaretlemektir. 

Daha sonra günlük dosyalarını indirebilir ve daha fazla araştırma yapmak için Windows Performans Analizi veya tercih ettiğiniz araç setini kullanabilirsiniz. Ayrıca sorunu düzeltmek ve son kullanıcıları etkileyen sorunları önlemeye yardımcı olmak için Microsoft 365 için Test Tabanı ekibiyle birlikte çalışabilirsiniz.

Bellek sinyalleri, tüm test çalıştırmaları için Microsoft 365 hizmeti için Test Temeli'ndeki Bellek Kullanımı sekmesinde yakalanır. Aşağıdaki örnekte Ağustos 2020 güvenlik güncelleştirmesine karşı eklenen "Duman Testi Bellek Stresi" uygulamasıyla yapılan son test çalıştırması gösterilmektedir. (Bu uygulama, bellek regresyonlarını göstermek için ekibimiz tarafından yazılmıştır.)

![Bellek regresyonu sonuçları.](Media/03_memory-regression%20comparison.png)

Bu örnekte sık kullanılan "USLTestMemoryStress.exe" işlemi, Yayın öncesi Ağustos güncelleştirmesinde yayımlanan Temmuz güncelleştirmesine kıyasla ortalama 100 MB tüketti, bu nedenle Microsoft 365 için Test Temeli bir regresyon belirledi. 

Burada "USLTestMemoryStress_Aux1.exe" ve "USLTestMemoryStress_Aux2.exe" olarak gösterilen diğer işlemler de aynı uygulamaya aittir, ancak iki sürüm için yaklaşık olarak aynı miktarda bellek tüketerek "geçtikleri" ve iyi durumda oldukları kabul edilir.

Ana işlemdeki regresyon "istatistiksel olarak anlamlı" olarak belirlendiği için hizmet kullanıcıya bu farkı iletmiş ve vurgulamıştı. Karşılaştırma istatistiksel olarak önemli olmasaydı vurgulanamazdı. Bellek kullanımı gürültülü olabilir, bu nedenle derlemeler ve sürümler arasında, tutarsız farklardan anlamlı farkları ayırt etmek için istatistiksel modeller kullanırız. 

Karşılaştırma gerçek bir fark olmadığında (hatalı pozitif) nadiren işaretlenebilir, ancak bu, regresyonları (veya gerçek pozitifleri) doğru tanımlama olasılığını geliştirmek için gerekli bir dengedir.

Sonraki adım, bellek regresyonuna neyin neden olduğunu anlamaktır. Her iki yürütme için zip dosyalarını aşağıda gösterildiği gibi Günlük dosyalarını indir seçeneğinden indirebilirsiniz. 

Bu zip dosyaları, ETL dosyasına dahil edilen betik sonuçları ve bellek ile CPU performans verileri de dahil olmak üzere test çalıştırmanızın sonuçlarını içerir.

![Bellek regresyon testi dosyaları.](Media/04_memory-regression-test-files.png)

araştırma ve gezintiyi basitleştirmek için iki test çalıştırmasının günlüklerini indirip açabilir, ardından her klasördeki ETL dosyasını bulabilir ve target.etl (yayın öncesi güncelleştirmede çalışan test için) ve baseline.etl (son yayınlanan güncelleştirmede çalışan test için) olarak yeniden adlandırabilirsiniz.
 
## <a name="next-steps"></a>Sonraki adımlar

Akıllı CPU regresyon analizini anlamaya başlamak için sonraki makaleye ilerleyin.
> [!div class="nextstepaction"]
> [Sonraki adım](cpu.md)

<!---
Add button for next page
-->
