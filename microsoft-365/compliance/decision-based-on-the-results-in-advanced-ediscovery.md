---
title: eBulma (Premium) içindeki sonuçlara dayalı karar
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: eBulma (Premium) içindeki Karar Ver sekmesinin, servis talebi dosyalarının gözden geçirme kümesinin doğru boyutunu belirlemenize yardımcı olabilecek verileri nasıl sağladığını öğrenin.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0c8f12ba2ff280bae060a16fe8f7a40e96bfe5f5
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67818489"
---
# <a name="decisions-based-on-relevance-results-in-ediscovery-premium"></a>eBulma (Premium) ile ilgili sonuçlara dayalı kararlar
  
eBulma 'daki (Premium) İlgi modülünde, Karar sekmesi olay dosyalarının gözden geçirme kümesinin boyutunu belirlemek için karar destek istatistiklerini görüntülemeye ve kullanmaya yönelik ek bilgiler sağlar.
  
## <a name="using-the-decide-tab"></a>Karar sekmesini kullanma

![İlgi Kararı.](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
Bu sekme aşağıdaki bileşenleri içerir:
  
- **Sorun**: Buradan listeden ilgilendiğiniz sorunu seçebilirsiniz.

- **Gözden geçirme-geri çağırma oranı**: İlgi puanlarına göre eBulma (Premium) incelemesi karşılaştırmaları. Grafikteki Kesme noktası, bir İlgi puanıyla eşlenmiş, gözden geçirilecek dosyaların yüzdesini temsil eder. Bu, İlgi Testi aşamasında ve hesaplama için dışarı aktarma eşiği olarak kullanılır. Gözden geçirilecek dosya sayısı için varsayılan kesme noktası, Geri Çekme ile Duyarlık arasındaki dengenin en uygun olduğu noktadadır. Gerçek kesme noktası, hedeflere ve maliyet dengesine (%gözden geçirme) ve risk (%geri çekme) bağlı olarak kullanıcı tarafından belirlenmelidir. Kaydırıcıyı kullanarak kesme noktasını ayarlayabilir ve alınacak ilgili dosyaların yüzdesini ayarlarken ve bir kararı doğrulamadan önce graf ve parametreler üzerindeki etkisini görebilirsiniz.

- **Parametreler**: Gözden Geçirme, Geri Çağırma, Sonraki ilgili ve Toplam maliyet parametreleri, tüm servis talebi için koleksiyonla ilgili olarak gözden geçirme kümesiyle ilgili toplu hesaplanan istatistiklerdir. Bu parametrelerin tanımları aşağıdaki gibidir:

  - **Gözden Geçir**: Bu kesmeye göre gözden geçirilecek dosyaların yüzdesi.

  - **Geri çağırma**: Gözden geçirme kümesindeki ilgili dosyaların yüzdesi.

  - **Sonraki ilgili**: Şu anda gözden geçirme kümesinde olmayan başka bir ilgili dosyayı gözden geçirme ve tanımlama maliyeti.

  - **Toplam maliyet**: Servis talebi dosyalarının bu yüzdesini gözden geçirme maliyeti. Maliyet parametresi ayarları Servis Talebi yöneticisi tarafından ayarlanabilir.

  - **İlgi puanına göre dağılım**: Soldaki koyu gri ekrandaki dosyalar kesme puanının altındadır. Araç ipucu, toplam dosyayla ilişkili olarak, inceleme dosyasındaki ilgi puanını ve ilgili dosya yüzdesini görüntüler.

Genişletilmiş **Ayrıntılar** bölmesinde daha fazla ayrıntı görüntülenir. Koleksiyon şekillerindeki dosyalar boş veya karmaşık dosyalar içermez. Aile dosyaları şekilleri, İlgi'ye yüklenmemiş ancak hala ailenin bir parçası olarak sayılan dosyaları temsil ediyor.
