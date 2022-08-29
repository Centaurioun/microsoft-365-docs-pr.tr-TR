---
title: CPU regresyon analizi
description: CPU tüketimi için regresyon sonuçlarını ve ölçümlerini anlama
search.appverid: MET150
author: mansipatel-usl
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: tinachen
f1.keywords: NOCSH
ms.openlocfilehash: 59038c1bd13299587ef0ed75f446e405ed64bba5
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/11/2022
ms.locfileid: "67315887"
---
# <a name="intelligent-cpu-regression-analysis"></a>Akıllı CPU regresyon analizi

CPU kullanımı, bir uygulamanın işletim sistemi güncelleştirmesini etkileyip etkilemediğini gösterebilir. 

Microsoft 365 için Test Temeli, yazılım geliştiricilerine, uygulamaları yaklaşan bir Windows İşletim Sistemi (OS) güncelleştirmesinin farklı sürümlerinde çalıştırıldığında ortaya çıkan CPU performans regresyonları hakkında içgörü sağlar. 

Bu CPU regresyonları, geliştiricilerin işletim sistemi güncelleştirmesi geniş bir şekilde dağıtılmadan önce uygulama sorunlarını (ve olası hataları) algılayıp çözmesine olanak tanıyarak son kullanıcı için kötü bir deneyim olmasını önler.


### <a name="how-cpu-regression-analysis-works"></a>CPU regresyon analizi nasıl çalışır? ###

Test Temeli kullanıcısı olarak, uygulamanızın ikili dosyalarını (tek bir .zip dosyasında), ilişkili test betikleriyle birlikte yükleyebilir ve uygulamanızı Azure'daki Test Temeli portalında test etmek istediğiniz Windows işletim sistemi sürümünü seçebilirsiniz. 

Test Temeli hizmeti daha sonra test betiklerini çalıştırır ve **CPU Regresyon Analizini** gerçekleştirir. 

Hizmet, hedef işletim sistemine yönelik güncelleştirmenin yayın öncesi sürümünde uygulamanın CPU kullanımının, işletim sisteminin yayımlanan sürümü için CPU kullanımına uygun olup olmadığını denetler. 

İşletim sisteminin iki sürümünde çalıştırılan işlemler farklı işletim sistemi sürümleri nedeniyle tam olarak eşleşmeyebileceği veya eşleşmeyebileceği için CPU kullanımı %100 benzer karşılaştırma değildir; Ancak Test Tabanı tarafından gerçekleştirilen analiz, uygulamanız için CPU kullanımının yaklaşan bir işletim sistemi güncelleştirmesinden etkilenip etkilenmediğini ve özellikle önceki test çalıştırmalarından hangi işlemlerin gerilediğini gösterebilir.

Aşağıdaki anlık görüntüde, CPU kullanımlarının aynı uygulama için karşılaştırıldığı iki işletim sistemi sürümü vardır. 
-   CPU kullanımı sekmesi, her iki sürüm için de üst ve alt kullanım sınırlarını sırasıyla 90. ve 10. yüzdebirlik dilimlerde gösterir. 
-   Graflar, ortalama kullanımın yanı sıra CPU kullanımı zaman serisini gösterir. 

Müşteriler artık işlevlerini kullanarak uygulamalarının CPU kullanımının işletim sistemi güncelleştirmelerinden etkilenip etkilenmediğini ve özellikle önceki yürütmelerinden hangi işlemlerin gerilediğini belirleyebilir.


![CPU regresyon analizi.](Media/cpu-regression-analysis.jpg)

### <a name="relevant-process-identification"></a>İlgili İşlem Tanımlama ###

Burada, uygulamada regresyona neden olan işlemlerin nasıl tanımlandığı ele alınıyor. 

Performans regresyonunun çözümlenmesi, test çalıştırması sırasında sanal makinede çalışan her işlem için farklı türlerdeki performans sayaçlarının izlenmesini gerektirir. 

Bu tür analizler, belirli bir uygulama için çok sayıda işlem için çok sayıda değişken yakalar. Tüm işlemler bir çalıştırma veya uygulamayla ilişkilendirilmemiştir. Bu sınamayı geçici olarak çözmek için, belirli bir uygulama için en uygun süreçleri bulmak için olasılık ve bilgi teorisini kullanan bir karşılıklı bilgi derecelendirme algoritması uygulanır. 

Bir uygulama bir tür ayrık rastgele değişken olarak kabul edilirken, bir işlem başka bir tür ayrık rastgele değişken olarak kabul edilir. İki rastgele değişkenin ilişkisi, ilgi için koşullu olasılıklar kullanılarak ölçülür. 

İşlemler daha sonra her uygulama için ilgi sırasına göre görüntülenir. Ayrıca, varsayılan olarak izleyebileceğiniz işlemlerin bir alt kümesini ve CPU regresyon analizi için ilgili işlemleri sık kullanılanlara ekleyebilirsiniz. Bir regresyon algılandıktan sonra Windows Performans Analizi araç setini indirebilir ve CPU performans regresyonlarının nedenlerini analiz edebilirsiniz. 

Windows Performans Analizi giriş olarak olay izleme günlüğünü (ETL) alır ve bu .etl dosyaları portalda test çalıştırmaları için indirilebilen günlük dosyalarında kullanılabilir. CPU performansında hata ayıklama hakkında daha fazla bilgi edinmek isterseniz Windows Performans Analizi belgelerine bakın.

