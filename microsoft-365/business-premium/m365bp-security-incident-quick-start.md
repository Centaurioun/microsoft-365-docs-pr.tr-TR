---
title: Microsoft 365 İş Ekstra için güvenlik işlemleri kılavuzu
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
ms.date: 07/19/2022
ms.collection:
- m365solution-smb
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
description: 'Günlük, haftalık veya aylık işlemler söz konusu olduğunda Defender portalında çalışmalarınızı odaklamanıza yönelik bir dizi öneri. '
ms.openlocfilehash: ab444aad5980af224b2005209dc5596fcb10f899
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2022
ms.locfileid: "66894087"
---
# <a name="microsoft-365-business-premium-security-operations-guide"></a>Microsoft 365 İş Ekstra güvenlik işlemleri kılavuzu

Microsoft 365 İş Ekstra yeniyseniz veya henüz bir güvenlik işlemleri kılavuzunuz yoksa, bu makale başlangıç noktası olarak görev yapabilir. Zaten bir güvenlik işlemleri kılavuzunuz varsa, bu makaledeki önerilere karşı gözden geçirin.

Güvenlik ekibinizin Microsoft Defender portalında ([https://security.microsoft.com](https://security.microsoft.com) ) gerçekleştireceği güvenlik olayı öncelikleri ve görevleri hakkında kararlar almak için bu kılavuzu kullanabilirsiniz.

| Önerilen sıklık | Görevler  |
|---------|---------|
| Günlük  | [Tehdit güvenlik açığınızı denetleyin](#check-your-threat-vulnerability).<br/>[İşlem merkezinde bekleyen eylemleri gözden geçirin](#review-pending-actions-in-the-action-center).<br/>[Tehdit algılamaları olan cihazları gözden geçirin](#review-devices-with-threat-detections).<br/>[Yeni olaylar veya uyarılar hakkında bilgi edinin](#learn-about-new-incidents-or-alerts). |
| Hafta -lık | [Microsoft Secure puanınızı izleyin ve geliştirin](#monitor-and-improve-your-microsoft-secure-score).<br/>[Cihazlar için güvenli puanı gözden geçirin](#review-the-secure-score-for-devices).<br/>[Cihazlar için güvenli puanınızı geliştirin](#improve-your-secure-score-for-devices). |
| Aylık | [Raporları çalıştırın](#run-reports).<br/>[Bir simülasyon öğreticisi çalıştırın](#run-a-simulation-tutorial).<br/>[Öğrenme merkezini keşfedin](#explore-the-learning-hub). |
| Gerektiği gibi | [Tehdit analizi panosunu kullanın](#use-the-threat-analytics-dashboard).<br/>[Tarama veya otomatik araştırma çalıştırın](#run-a-scan-or-automated-investigation).<br/>[Öğeyi düzeltme](#remediate-an-item). | 

Aşağıdaki bölümlerde her görev hakkında daha fazla ayrıntı sağlanır.
  
## <a name="suggested-daily-tasks"></a>Önerilen günlük görevler

Güvenlik görevlerinin günlük olarak takip etmek için bazı önerileri aşağıda bulabilirsiniz.

- [Tehdit güvenlik açığınızı denetleyin](#check-your-threat-vulnerability).
- [İşlem merkezinde bekleyen eylemleri gözden geçirin](#review-pending-actions-in-the-action-center).
- [Tehdit algılamaları olan cihazları gözden geçirin](#review-devices-with-threat-detections).
- [Yeni olaylar veya uyarılar hakkında bilgi edinin](#learn-about-new-incidents-or-alerts).

### <a name="check-your-threat-vulnerability"></a>Tehdit güvenlik açığınızı denetleme

Kısaca güvenlik açığı yönetim panosuna bakarak tehdit güvenlik açığının anlık görüntüsünü alabilirsiniz. Kuruluşunuzun siber güvenlik tehditlerine karşı ne kadar savunmasız olduğunu yansıtır. Yüksek maruz kalma puanı, cihazlarınızın yararlanmaya karşı daha savunmasız olduğu anlamına gelir.

1. Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com) ) gezinti bölmesinde Güvenlik **açığı yönetimi > Pano'yu** seçin.

2. Kuruluşunuzun maruz kalma puanına göz atın. Kabul edilebilir veya "Yüksek" aralıktaysa devam edebilirsiniz. Değilse, **bu puanı geliştirmek** için daha fazla ayrıntı ve güvenlik önerileri görmek için Puanı geliştir'i seçin.

Maruz kalma puanınızın farkında olmak şunları sağlar:

- Kuruluşunuzdaki güvenlik durumuyla ilgili üst düzey bilgileri hızla anlayın ve belirleyin
- Geçerli durumu iyileştirmek için araştırma veya eylem gerektiren alanları algılama ve yanıtlama
- Güvenlik çalışmalarının etkisi hakkında eşlerle ve yönetimle iletişim kurma

### <a name="review-pending-actions-in-the-action-center"></a>İşlem merkezinde bekleyen eylemleri gözden geçirme

Tehditler algılandıkçe düzeltme eylemleri devreye girer. Belirli bir tehdide ve güvenlik ayarlarınızın nasıl yapılandırıldığına bağlı olarak, düzeltme eylemleri otomatik olarak veya yalnızca onaylandığında gerçekleştirilebilir; bu nedenle bunlar düzenli olarak izlenmelidir. Karantinaya dosya gönderme, işlemin çalışmasını durdurma ve zamanlanmış görevi kaldırma gibi düzeltme eylemlerine örnek olarak verilebilir. Tüm düzeltme eylemleri İşlem merkezinde izlenir.

1. Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com) ) gezinti bölmesinde **İşlem merkezi'ni** seçin.

2. Bekleyen eylemleri görüntülemek ve onaylamak (veya reddetmek) için **Beklemede** sekmesini seçin. Bu tür eylemler virüsten koruma veya kötü amaçlı yazılımdan koruma, otomatik araştırma, el ile yanıt etkinlikleri veya canlı yanıt oturumlarından kaynaklanabilir.

3. Tamamlanan eylemlerin listesini görüntülemek için **Geçmiş** sekmesini seçin.

### <a name="review-devices-with-threat-detections"></a>Tehdit algılamaları olan cihazları gözden geçirme

Tehdit içeren cihazlarınız olup olmadığını öğrenmek için aşağıdakileri yapın.

1. Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com) ) gezinti bölmesinde **Raporlar > Genel > Güvenlik raporu'na** tıklayın.

2. Ekranı aşağı kaydırarak Savunmasız cihazlar satırına gelin. Cihazlarda tehdit algılandıysa bu bilgileri bu satırda görürsünüz.

### <a name="learn-about-new-incidents-or-alerts"></a>Yeni olaylar veya uyarılar hakkında bilgi edinin

1. Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com) ) gezinti menüsünde **Olaylar'ı** seçin. Olaylar sayfada ilişkili uyarılarla birlikte görüntülenir.

2. Uyarı hakkında daha fazla bilgi edinebileceğiniz açılır pencere bölmesini açmak için bir uyarı seçin.

3. Açılır listede uyarı başlığını görebilir, etkilenen varlıkların (uç noktalar veya kullanıcı hesapları gibi) listesini görüntüleyebilir, kullanılabilir eylemler gerçekleştirebilir ve daha fazla bilgi görüntülemek ve hatta seçili uyarının ayrıntılar sayfasını açmak için bağlantıları kullanabilirsiniz.

### <a name="run-a-scan-or-automated-investigation"></a>Tarama veya otomatik araştırma çalıştırma

1. Microsoft 365 Defender portalında (https://security.microsoft.com)gezinti bölmesinde Cihaz envanteri'ni seçin.

2. Açılır panelini açmak için bir cihaz seçin ve görüntülenen bilgileri gözden geçirin.

3. Eylemler menüsünü açmak için üç noktayı (...) seçin.

4. **Virüsten koruma taraması çalıştır** veya **Otomatik Araştırma Başlat** gibi bir eylem seçin.

## <a name="suggested-weekly-tasks"></a>Önerilen haftalık görevler

En azından haftalık olarak yapılması gereken önemli güvenlik görevlerine ilişkin bazı öneriler aşağıdadır.

- [Microsoft Secure puanınızı izleyin ve geliştirin](#monitor-and-improve-your-microsoft-secure-score).
- [Cihazlar için güvenli puanı gözden geçirin](#review-the-secure-score-for-devices).
- [Cihazlar için güvenli puanınızı geliştirin](#improve-your-secure-score-for-devices).

### <a name="monitor-and-improve-your-microsoft-secure-score"></a>Microsoft Secure puanınızı izleme ve geliştirme

Microsoft Güvenli Puan, bir kuruluşun güvenlik duruşunun ölçümüdür ve daha az geliştirme eylemi gerektiğini gösteren daha yüksek bir sayıdır.

Güvenli Puan kuruluşlara yardımcı olur:

- Kuruluşun güvenlik duruşunun geçerli durumunu rapor edin.
- Bulunabilirlik, görünürlük, rehberlik ve denetim sağlayarak güvenlik duruşlarını geliştirin.
- Karşılaştırmalarla karşılaştırın ve ana performans göstergelerini (KPI' ler) oluşturun.

1. Güvenlik puanınızı denetlemek için Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com) ) gezinti **bölmesinden Güvenli puan'ı** seçin. 

2. Genel Microsoft güvenlik puanınızı geliştirmek için düzeltmeleri ve eylemleri gözden geçirin ve kararlar alın.

### <a name="review-the-secure-score-for-devices"></a>Cihazlar için güvenli puanı gözden geçirin

Ayrıca Güvenlik açığı yönetim panosunda bulunan cihazlar için Microsoft Güvenli puanı kartıdır. Bu kart geçerli puanınızı görüntüler ve daha yüksek bir puan uç noktalarınızın siber saldırılara karşı daha dayanıklı olduğunu gösterir. Tüm cihazların güvenlik durumunu toplu olarak yansıtır.

Bu kart üzerindeki veriler, titiz ve sürekli bir güvenlik açığı bulma işleminin ürünüdür. Sürekli olarak yapılan yapılandırma bulma değerlendirmeleriyle toplanır:

- Yanlış yapılandırılmış varlıkları bulmak için toplanan yapılandırmaları toplanan karşılaştırmalarla karşılaştırın
- Yapılandırmaları düzeltilebilen veya kısmen düzeltilebilen güvenlik açıklarıyla eşleme (risk azaltma)
- En iyi uygulama yapılandırma karşılaştırmalarını (satıcılar, güvenlik akışları, iç araştırma ekipleri) toplayın ve koruyun
- Tüm varlıklardan güvenlik denetimi yapılandırma durumu değişikliklerini toplama ve izleme

### <a name="improve-your-secure-score-for-devices"></a>Cihazlar için güvenli puanınızı geliştirme

Güvenlik önerileri listesini kullanarak sorunları gidererek güvenlik yapılandırmanızı geliştirin. Bunu yaparken Cihazlar için Microsoft Güvenli Puanınız iyileşir ve kuruluşunuz bundan sonra siber güvenlik tehditlerine ve güvenlik açıklarına karşı daha dayanıklı hale gelir. Puanınızı gözden geçirmek ve geliştirmek için gereken zamana her zaman değer.

1. Güvenli puanınızı denetlemek için Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com) ) gezinti **bölmesinden Güvenli puan'ı** seçin.

2. Defender Güvenlik Açığı Yönetimi panosundaki **Cihazlar için Microsoft Güvenli Puanı** kartından kategorilerden birini seçin. Bu kategoriyle ilgili önerilerin listesi, önerilerle birlikte görüntülenir.

3. Öneriyle ilgili ayrıntıları görüntülemek için listeden bir öğe seçin.

4. **Düzeltme seçenekleri'ni** seçin.

5. Sorunun bağlamını ve bundan sonra yapılacakları anlamak için açıklamayı okuyun. Son tarih seçin, not ekleyin ve tüm düzeltme etkinlik verilerini CSV'ye aktar'ı seçerek izleme için e-postaya ekleyebilirsiniz. Düzeltme görevinin oluşturulduğunu belirten bir onay iletisi.

6. BT Yöneticinize bir izleme e-postası gönderin ve düzeltmenin sisteme yayılması için ayırdığınız süreye izin verin.

7. Panodaki Cihazlar için Microsoft Güvenli Puanı kartına dönün. Eylemleriniz sonucunda güvenlik denetimleri önerilerinin sayısı azaldı.

8. **Güvenlik önerileri** sayfasına dönmek için Güvenlik denetimleri'ni seçin. Adreslediğiniz öğe artık burada listelenmez ve bu da Microsoft güvenlik puanınızın iyileşmesine neden olur.

## <a name="suggested-monthly-tasks"></a>Önerilen aylık görevler

Bu görevler, daha sık değilse en az aylık olarak yapılmalıdır. 

- [Raporları çalıştırın](#run-reports).
- [Bir simülasyon öğreticisi çalıştırın](#run-a-simulation-tutorial).
- [Öğrenme merkezini keşfedin](#explore-the-learning-hub).

### <a name="run-reports"></a>Raporları çalıştırma

Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com)) çeşitli raporlar mevcuttur.

1. Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com) ) gezinti bölmesinde **Raporlar'ı** seçin.

2. Gözden geçirebileceğiniz bir rapor seçin. Her rapor, bu rapor için birçok ilgili kategori görüntüler.

3. Her kategoriye ilişkin daha ayrıntılı bilgileri görmek için **Ayrıntıları görüntüle'yi** seçin.

4. Belirli bir tehdidin başlığını seçerek ilgili ayrıntıları görebilirsiniz.

### <a name="run-a-simulation-tutorial"></a>Simülasyon öğreticisi çalıştırma

Eğitim aracılığıyla hem sizin hem de ekibiniz için güvenlik hazırlığını artırmak her zaman iyi bir fikirdir. Simülasyon öğreticilerine Microsoft 365 Defender portalından erişebilirsiniz. Öğreticiler çeşitli siber tehdit türlerini kapsar. 

Başlamak için: 

1. Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com) ) gezinti bölmesinde **Öğreticiler'i** seçin.

2. Çalıştırmak istediğiniz öğreticinin kılavuzunu okuyun ve ardından dosyayı indirin veya simülasyonu çalıştırmak için gereken betiği yönergelere göre kopyalayın.

### <a name="explore-the-learning-hub"></a>Öğrenme merkezini keşfetme

Öğrenme merkezinde, mevcut tehditlerin birçoğu ve bunların nasıl ele alınabileceği hakkında bilginizi artırabileceğiniz birçok alan vardır. Sizin ve ekiplerinizin özellikle Microsoft 365 Defender ve Uç Noktalar bölümlerinde sunulan kaynakları keşfetmek için biraz zaman harcamanızı öneririz.

1. Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com) ) gezinti bölmesinde **Öğrenme merkezi'ni** seçin.

2. **Microsoft 365 Defender** veya **Uç Noktalar** gibi bir alan seçin.

3. Her kavram hakkında daha fazla bilgi edinmek için bir öğe seçin. 

> [!NOTE]
> Öğrenme hub'ında bazı kaynaklar, aslında Microsoft 365 İş Ekstra dahil olmayan işlevleri kapsayabilir. Örneğin gelişmiş tehdit avcılığı özellikleri, Uç Nokta için Defender Plan 2 veya Microsoft 365 Defender gibi kurumsal aboneliklere dahil edilir ancak Microsoft 365 İş Ekstra dahil değildir. [Küçük ve orta ölçekli işletmeler için Microsoft 365 planlarındaki güvenlik özelliklerini karşılaştırın](../security/defender-business/compare-mdb-m365-plans.md).

## <a name="as-needed"></a>Gerektiği gibi

Bu görevleri gerektiği gibi veya uygun şekilde gerçekleştirin:

- [Tehdit analizi panosunu kullanın](#use-the-threat-analytics-dashboard).
- [Tarama veya otomatik araştırma çalıştırın](#run-a-scan-or-automated-investigation).
- [Öğeyi düzeltme](#remediate-an-item).

### <a name="use-the-threat-analytics-dashboard"></a>Tehdit analizi panosunu kullanma

Kuruluşunuza en uygun raporları vurgulayarak geçerli tehdit ortamına genel bir bakış elde etmek için tehdit analizi panosunu kullanın. 

1. Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com) ) gezinti bölmesinde **Tehdit analizi'ni seçerek Tehdit analizi** panosunu görüntüleyin. 

   Pano, tehditleri aşağıdaki bölümlerde özetler:

   - En son tehditler— en son yayımlanan veya güncelleştirilen tehdit raporlarının yanı sıra etkin ve çözümlenmiş uyarı sayısını listeler.
   - Yüksek etkili tehditler— kuruluşunuz üzerinde en yüksek etkiye sahip olan tehditleri listeler. Bu bölümde, en fazla etkin ve çözümlenmiş uyarı sayısına sahip tehditler listelenir.
   - En yüksek maruz kalma: En yüksek maruz kalma düzeyine sahip tehditler listelenir. Bir tehdidin maruz kalma düzeyi iki bilgi parçası kullanılarak hesaplanır: tehditle ilişkili güvenlik açıklarının ne kadar ciddi olduğu ve kuruluşunuzdaki kaç cihazın bu güvenlik açıklarından yararlanabileceği.

2. Araştırmak istediğiniz kişinin başlığını seçin ve ilişkili raporu okuyun. 

3. Ayrıca daha fazla ayrıntı için Analist raporunun tamamını gözden geçirebilir veya ilgili olayları, etkilenen varlıkları, açığa çıkarma ve risk azaltmaları görüntülemek için diğer başlıkları seçebilirsiniz.

### <a name="remediate-an-item"></a>Öğeyi düzeltme

Microsoft 365 İş Ekstra çeşitli düzeltme eylemleri içerir. Bu eylemler el ile yanıt eylemlerini, otomatik araştırmadan sonraki eylemleri ve canlı yanıt eylemlerini içerir.

1. Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com) ) gezinti bölmesinde **Cihaz envanteri'ni** seçin.

   :::image type="content" source="./../media/defender-business/mdb-deviceinventory.png" alt-text="Cihaz envanterinin ekran görüntüsü":::

2. Yüksek risk düzeyine veya maruz kalma düzeyine sahip bir cihaz gibi bir cihaz seçin. Bir açılır pencere bölmesi açılır ve aşağıdaki görüntüde gösterildiği gibi bu öğe için oluşturulan uyarılar ve olaylar hakkında daha fazla bilgi görüntüler:  

   :::image type="content" source="./../media/defender-business/mdb-deviceinventory-selecteddeviceflyout.png" alt-text="Seçili cihaz için açılır pencere bölmesinin ekran görüntüsü":::

3. Açılır öğede görüntülenen bilgileri görüntüleyin. Aşağıdaki görüntüde gösterildiği gibi kullanılabilir eylemlerin listelendiğini belirten bir menü açmak için üç noktayı (...) seçin: 

   :::image type="content" source="./../media/defender-business/mdb-deviceinventory-selecteddeviceflyout-menu.png" alt-text="Seçili cihaz için kullanılabilir eylemlerin ekran görüntüsü":::

4. Kullanılabilir bir eylem seçin. Örneğin, Microsoft Defender Virüsten Koruma'nın cihazda hızlı bir tarama başlatmasına neden olacak **virüsten koruma taraması çalıştır'ı** seçebilirsiniz. Alternatif olarak, cihazda otomatik bir araştırma tetikleme için **Otomatik Araştırma Başlat'ı** da seçebilirsiniz.

#### <a name="remediation-actions-in-microsoft-365-business-premium"></a>Microsoft 365 İş Ekstra'de düzeltme eylemleri

Aşağıdaki tabloda, Microsoft 365 İş Ekstra'de kullanılabilen düzeltme eylemleri özetlenir:

| Kaynak  | Eylem  |
|---------|---------|
| Otomatik araştırma      | - Dosyayı karantinaya al <br/>- Kayıt defteri anahtarını kaldırma <br/>- Bir işlemi sonlandırma <br/>- Hizmeti durdurma <br/>- Sürücüyü devre dışı bırakma <br/>- Zamanlanmış görevi kaldırma        |
| El ile yanıt eylemleri   | - Virüsten koruma taraması çalıştırma <br/>- Cihazı yalıtma <br/>- Durdurma ve karantinaya al <br/>- Bir dosyayı engellemek veya dosyaya izin vermek için gösterge ekleme       |
| Canlı yanıt  | - Adli veri toplama <br/>- Bir dosyayı analiz etme <br/>- Betik çalıştırma <br/>- Şüpheli bir varlığı analiz için Microsoft'a gönderme <br/>- Dosyayı düzeltme <br/>- Tehditleri proaktif olarak avlama  |




## <a name="see-also"></a>Ayrıca bkz.

[İş için Microsoft 365 planlarının güvenliğini sağlamaya yönelik en iyi yöntemler](../admin/security-and-compliance/secure-your-business-data.md)