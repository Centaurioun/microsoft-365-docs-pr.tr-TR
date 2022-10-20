---
title: Yeni Arama Denetimi
description: Yeni Arama Denetimi, sonuçların performans iyileştirmelerini, eksiksizliğini ve tutarlılığını doğrular.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- tier1
- purview-compliance
- audit
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
ms.openlocfilehash: ca1e7b519d39e558ef07b1a812f057d7c1559a89
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68643576"
---
# <a name="audit-new-search"></a>Yeni Arama Denetimi

Kuruluşunuzun içgörü elde etmek ve kullanıcı etkinliklerini daha fazla araştırmak için kritik denetim günlüğü olay verilerine erişmesi gerekiyor. Daha önce, Microsoft Purview uyumluluk portalı kullanıcı arabirimindeki arama işleriniz eşzamanlı denetim arama işleri oluşturma ve geçmiş arama işlerini gözden geçirme yetenekleriyle sınırlıydı. Bu kritik denetim arama işlerinin tamamlanması için tarayıcı penceresi açık kalan bir bağımlılığı da vardı.

Yeni Aramayı Denetle, mevcut arama işlevlerini temel alır ve aşağıdaki önemli iyileştirmeleri içerir:

- Uyumluluk portalı kullanıcı arabirimi aracılığıyla başlatılan arama işlerinin tamamlanması için artık web tarayıcısı penceresinin açık kalması gerekmez. Tarayıcı penceresi kapatıldıktan sonra bile bu işler çalışmaya devam eder.
- Tamamlanan arama işleri artık 30 gün boyunca depolanıyor ve müşterilere geçmiş denetim aramalarına başvurabilme olanağı veriyor. Bu arama işleri kullanıcı arabiriminde arama adı, arama işi durumu, ilerleme durumu %, Sonuç sayısı, Oluşturma Zamanı ve Arama ölçütü listelenerek sunulur.
- Her yönetici Denetim hesabı kullanıcısı, en fazla bir filtrelenmemiş arama işiyle devam eden en fazla 10 eşzamanlı arama işine sahip olabilir.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="information-to-get-started"></a>Başlamak için bilgiler

Arama işi oluşturma ve dışarı aktarma deneyimlerinde geçerli arama deneyimiyle birçok paralellik olduğundan, kullanılabilir Microsoft Purview Denetim belgelerini görüntüleyin:

- [Microsoft Purview uyumluluk portalı denetim günlüğünde arama](search-the-audit-log-in-security-and-compliance.md) yapın (PowerShell'in henüz Denetim Araması V2 ile uyumlu olmadığını unutmayın)
- [Denetim günlüğündeki ayrıntılı özellikler](detailed-properties-in-the-office-365-audit-log.md)
- [Denetim günlüğü kayıtlarını dışa aktarma, yapılandırma ve görüntüleme](export-view-audit-log-records.md)

Ek bilgiler:

- Search-UnifiedAuditLog cmdlet'ini kullanarak EXO PowerShell oturumu aracılığıyla arama şu anda Yeni Arama ile uyumlu değildir.
- Arama işleri şu ölçütleri alabilir: Tarih Aralığı, Zaman Aralığı, Arama İşi Adı, Etkinlikler, Kullanıcılar, Dosyalar, Klasörler ve Siteler.
- Tarih, saat, arama adı, etkinlikler ve kullanıcılar kullanılarak arama ve filtreleme tamamen işlevseldir
- Denetim Günlüğü verileri, bir arama işinin silinmesine bakılmaksızın tanımlı saklama süresi boyunca depolanır

## <a name="get-started-with-audit-new-search"></a>Yeni aramayı denetlemeye başlama

Yeni Arama Denetimi deneyimini test etmek ve doğrulamak için aşağıdaki adımları izleyin:

1. [Microsoft Purview uyumluluk portalı](https://compliance.microsoft.com) oturum açın
2. Giriş sayfasının sol panelinde **Denetim** sekmesini seçerek Denetim aracına gidin
3. **Denetim** sayfasının üst kısmındaki **Yeni Arama** sekmesini seçin

      ![Microsoft Purview'da Yeni Arama'ya genel bakış denetimi.](../media/audit-search/audit-new-search.png)

4. Çeşitli arama ölçütlerini kullanarak Yeni Arama Denetle aracında farklı arama işlerini test edin.
Farklı aramalara örnek olarak aşağıdaki ölçütler verilebilir. Denetim günlüğünde arama yaparken bu farklı arama yöntemlerini keşfedin.

    - Farklı zaman çerçeveleri arasında arama.
      - Bir gün
      - Hafta
      - Ay
      - Birkaç Ay
    - Seçili kullanıcılar arasında arama
    - Etkinlikler alanını kullanarak arama kapsamını belirleme
    - Belirli bir dosya, klasör veya site ekleme

  ![Microsoft Purview'da Yeni Arama Denetimine genel bakış oluşturma.](../media/audit-search/audit-new-search-create.png)

5. Uyumluluk portalında başka bir 2-9 araması başlatın. Bir hesapta paralel olarak en fazla 10 arama işi çalıştırılabilir.
6. Arama işi geçmişini keşfedin ve arama işi sonuçlarından ilgili verileri almak için farklı arama işleri seçin. Sonuçlar, tablonun üst kısmındaki ilgili düğme seçilerek oluşturulma saatlerine göre sıralanabilir.

  ![Microsoft Purview'da Yeni Arama Denetimine genel bakış sonuçları.](../media/audit-search/audit-new-search-columns.png)

7. İşin sonuçlarını satır öğesi biçiminde görüntülemek için bir arama işi seçin. Kullanıcı arabirimindeki çeşitli işlevleri keşfedin, örneğin:

    - Özgün arama tamamlanırken girilen tüm arama ölçütlerini içeren sayfanın en üstündeki tam arama sorgusuna başvurma
    - Açılır pencerede daha fazla bilgi için çeşitli sonuçlar seçme
    - IP adresi, Kullanıcı, Etkinlik, Tarih, Öğe ve Ayrıntılar'ı kullanarak arama işi genelinde filtreleme.
    - Hem filtrelenmemiş hem de filtrelenmiş aramaları dışarı aktarma
    - Sonuçları sıralamak için tablonun üst kısmındaki Tarih, IP Adresi (varsa), Kullanıcı, Etkinlik, Öğe ve Ayrıntı (uygun olduğunda) gibi ilgili düğmelere tıklayın.

  ![Microsoft Purview'da Yeni Arama Denetimine genel bakış sonuçlarını sıralama.](../media/audit-search/audit-new-search-result-details.png)

## <a name="audit-search-job-overview"></a>Arama işine genel bakış denetimi

- Arama işleri şu ölçütleri alabilir: Tarih Aralığı, Zaman Aralığı, Arama İşi Adı, Etkinlikler, Kullanıcılar, Dosyalar, Klasörler ve Siteler.
- Dosya, klasör veya site arama metin kutusu ilgili dosya, klasör ve siteler için tüm ilgili sonuçları döndürür
- Arama işleri, arama sayfasının en altında çalışır.
  - Arama işleri *Kuyruğa* Alınmış, *Devam Ediyor* ve *Tamamlandı* olabilir
  - Kullanıcı başına aynı anda en fazla 10 *Devam Ediyor* arama işi tamamlanabilir
- İmleci arama işinin üzerine getirerek işler için tam arama adları görülebilir
- Arama işleri Arama Adı, Durum, İlerleme % , Sonuç sayısı, oluşturma zamanı ve arama ölçütü

## <a name="audit-search-results-overview"></a>Arama sonuçlarını denetlemeye genel bakış

- Arama işi seçildikten sonra arama sonuçları satır öğesinde görüntülenir
- Arama sorgusu, başvuru ve toplam öğe sayısı için arama işi sonuçları sayfasının en üstünde görüntülenir
  > [!NOTE]
  > Toplam sonuç numarası yinelenenleri düşürür; bu nedenle ana Denetim arama penceresindeki öğe sayısından daha az olabilir
- Tarih, IP Adresi, Kullanıcı, Etkinlik ve Öğe hakkındaki bilgileri her öğenin arama işi sonuçları sayfasında bulabilirsiniz
- Etkinlik hakkında daha fazla ayrıntı içeren bir açılır pencere görmek için bir etkinlik seçin
- Arama işi sonuçları için filtreleme özelliği sonuçları ayrıştırmaya yardımcı olabilir.
- Dışarı aktarma tamamen işlevseldir ve tüm arama işi öğelerini bir .csv dosyasına aktarır. Dışarı aktarma, 50 KB'a kadar olan sonuçları destekler.

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

- **Kullanıcı başına en fazla arama işi sayısı var mı?**
  Kullanıcı başına en fazla 10 *Devam eden* arama işi vardır. Bir kullanıcı 10'dan fazla arama işi gerektiriyorsa, devam *eden* bir işin bitmesini veya bir arama işinin silinmesini beklemesi gerekir. Bu sınırla ilgili geri bildiriminiz bizim için çok önemli.
- **Arama işinin silinmesi arka uç verilerini siler mi?**
  Hayır, arama işinin silinmesi yalnızca arama işi tanımını ve ilişkili arama sonucunu siler.
