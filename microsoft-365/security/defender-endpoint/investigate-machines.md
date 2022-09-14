---
title: Uç Nokta Cihazları için Defender listesindeki cihazları araştırma
description: Uyarıları, ağ bağlantısı bilgilerini gözden geçirerek, cihaz etiketleri ve grupları ekleyerek ve hizmet durumunu denetleyerek etkilenen cihazları araştırın.
keywords: cihazlar, etiketler, gruplar, uç nokta, uyarılar kuyruğu, uyarılar, cihaz adı, etki alanı, son görülen, iç IP, etkin uyarılar, tehdit kategorisi, filtreleme, sıralama, uyarıları gözden geçirme, ağ, bağlantı, tür, parola çalan, fidye yazılımı, yararlanma, tehdit, düşük önem derecesi, hizmet durumu
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: ad6cf3d61efec199d9a30ba67e06829b6f1feccb
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67688131"
---
# <a name="investigate-devices-in-the-microsoft-defender-for-endpoint-devices-list"></a>Uç Nokta için Microsoft Defender Cihazlar listesindeki cihazları araştırma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatemachines-abovefoldlink)

Uyarıyla veya ihlalin olası kapsamıyla ilgili olabilecek diğer davranışları veya olayları belirlemek için belirli bir cihazda tetiklenen uyarının ayrıntılarını araştırın.

> [!NOTE]
> Araştırma veya yanıt sürecinin bir parçası olarak bir cihazdan araştırma paketi toplayabilirsiniz. Şu şekilde yapılır: [Cihazlardan araştırma paketi toplayın](/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).

Etkilenen cihazları portalda her gördüğünüzde tıklayarak ilgili cihaz hakkında ayrıntılı bir rapor açabilirsiniz. Etkilenen cihazlar aşağıdaki alanlarda tanımlanır:

- [Cihazlar listesi](investigate-machines.md)
- [Uyarı sırası](alerts-queue.md)
- [Güvenlik işlemleri panosu](security-operations-dashboard.md)
- Tek tek uyarılar
- Tek tek dosya ayrıntıları görünümü
- Herhangi bir IP adresi veya etki alanı ayrıntıları görünümü

Belirli bir cihazı araştırdığınızda şunları görürsünüz:

- Cihaz ayrıntıları
- Yanıt eylemleri
- Sekmeler (genel bakış, uyarılar, zaman çizelgesi, güvenlik önerileri, yazılım envanteri, bulunan güvenlik açıkları, eksik KB'ler)
- Kartlar (etkin uyarılar, oturum açmış kullanıcılar, güvenlik değerlendirmesi, cihaz sistem durumu) 
 

:::image type="content" source="images/specific-device.png" alt-text="Cihaz görünümü" lightbox="images/specific-device.png":::

> [!NOTE]
> Ürün kısıtlamaları nedeniyle, cihaz profili 'Son Görülme' zaman çerçevesini belirlerken (cihaz sayfasında da görüldüğü gibi) tüm siber kanıtları dikkate almaz.
> Örneğin, makinenin zaman çizelgesinde daha yeni uyarılar veya veriler bulunsa bile, Cihaz sayfasındaki 'Son görülen' değeri daha eski bir zaman dilimi gösterebilir.

## <a name="device-details"></a>Cihaz ayrıntıları

Cihaz ayrıntıları bölümünde cihazın etki alanı, işletim sistemi ve sistem durumu gibi bilgiler sağlanır. Cihazda bir araştırma paketi varsa paketi indirmenizi sağlayan bir bağlantı görürsünüz.

## <a name="response-actions"></a>Yanıt eylemleri

Yanıt eylemleri belirli bir cihaz sayfasının üst kısmında çalışır ve şunları içerir:

- Etiketleri yönetin
- Cihazı yalıtma
- Uygulama yürütmeyi kısıtlayın
- Antivirüs taraması başlat
- Soruşturma paketini toplayın
- Canlı Yanıt Oturumu Başlat
- Otomatik araştırma başlatma
- Tehdit uzmanına danışın
- İşlem merkezi

yanıt eylemlerini İşlem merkezinde, belirli bir cihaz sayfasında veya belirli bir dosya sayfasında gerçekleştirebilirsiniz.

Cihazda eylem gerçekleştirme hakkında daha fazla bilgi için bkz. Cihazda [yanıt eylemi gerçekleştirme](respond-machine-alerts.md).

Daha fazla bilgi için bkz [. Kullanıcı varlıklarını araştırma](investigate-user.md).

## <a name="tabs"></a>Sekme

Sekmeler, cihazla ilgili ilgili güvenlik ve tehdit önleme bilgilerini sağlar. Her sekmede, sütun üst bilgilerinin üstündeki çubuktan **Sütunları özelleştir'i** seçerek gösterilen sütunları özelleştirebilirsiniz.

### <a name="overview"></a>Genel bakış

**Genel Bakış** sekmesinde etkin uyarıların, oturum açmış kullanıcıların ve güvenlik değerlendirmesinin [kartları](#cards) görüntülenir.

:::image type="content" source="images/overview-device.png" alt-text="Cihaz sayfasındaki Genel Bakış sekmesi" lightbox="images/overview-device.png":::

### <a name="alerts"></a>Uyarılar

**Uyarılar** sekmesi, cihazla ilişkili uyarıların listesini sağlar. Bu liste [, Uyarılar kuyruğunun](alerts-queue.md) filtrelenmiş bir sürümüdür ve uyarının kısa bir açıklamasını, önem derecesini (yüksek, orta, düşük, bilgilendirici), kuyruktaki durumu (yeni, devam ediyor, çözüldü), sınıflandırmayı (ayarlanmamış, yanlış uyarı, doğru uyarı), araştırma durumunu, uyarı kategorisini, uyarıyı ele alan kişiyi ve son etkinliği gösterir. Uyarıları da filtreleyebilirsiniz.

:::image type="content" source="images/alerts-device.png" alt-text="Cihazla ilgili uyarıların sekmesi" lightbox="images/alerts-device.png":::

Uyarının solundaki daire simgesi seçildiğinde, bir açılır menü görüntülenir. Bu panelden uyarıyı yönetebilir ve olay numarası ve ilgili cihazlar gibi diğer ayrıntıları görüntüleyebilirsiniz. Aynı anda birden çok uyarı seçilebilir.

Olay grafiği ve işlem ağacı dahil olmak üzere bir uyarının tam sayfa görünümünü görmek için uyarının başlığını seçin.

### <a name="timeline"></a>Zaman çizelgesi

**Zaman Çizelgesi** sekmesi, cihazda gözlemlenen olayların ve ilişkili uyarıların kronolojik bir görünümünü sağlar. Bu, cihazla ilgili olarak tüm olayları, dosyaları ve IP adreslerini ilişkilendirmenize yardımcı olabilir.

Zaman çizelgesi ayrıca belirli bir süre içinde gerçekleşen olaylara seçmeli olarak detaya gitmenizi sağlar. Seçili bir zaman aralığında bir cihazda gerçekleşen olayların zamansal sırasını görüntüleyebilirsiniz. Görünümünüzü daha fazla denetlemek için olay gruplarına göre filtreleyebilir veya sütunları özelleştirebilirsiniz.

> [!NOTE]
> Güvenlik duvarı olaylarının görüntülenmesi için denetim ilkesini etkinleştirmeniz gerekir. Bkz. [Denetim Filtreleme Platformu bağlantısı](/windows/security/threat-protection/auditing/audit-filtering-platform-connection).
>
> Güvenlik duvarı aşağıdaki olayları kapsar:
>
> - [5025](/windows/security/threat-protection/auditing/event-5025) - Güvenlik duvarı hizmeti durduruldu
> - [5031](/windows/security/threat-protection/auditing/event-5031) - Uygulamanın ağda gelen bağlantıları kabul etme engeli
> - [5157](/windows/security/threat-protection/auditing/event-5157) - engellenen bağlantı

:::image type="content" source="images/timeline-device.png" alt-text="Olaylar içeren cihaz zaman çizelgesi" lightbox="images/timeline-device.png":::

İşlevlerden bazıları şunlardır:

- Belirli olayları arama
  - Belirli zaman çizelgesi olaylarını aramak için arama çubuğunu kullanın.
- Belirli bir tarihteki olayları filtreleme
  - Son gün, hafta, 30 gün veya özel aralıktaki etkinlikleri görüntülemek için tablonun sol üst kısmındaki takvim simgesini seçin. Varsayılan olarak, cihaz zaman çizelgesi son 30 güne ait olayları görüntüleyecek şekilde ayarlanır.
  - Bölümü vurgulayarak zaman çizelgesini kullanarak belirli bir ana atlayın. Zaman çizelgesindeki oklar otomatik araştırmalara işaret eder
- Ayrıntılı cihaz zaman çizelgesi olaylarını dışarı aktarma
  - Geçerli tarih veya belirtilen tarih aralığı için cihaz zaman çizelgesini yedi güne kadar dışarı aktarın.

Bazı olaylar hakkında daha fazla bilgi **Ek bilgiler** bölümünde verilmiştir. Bu ayrıntılar olayın türüne bağlı olarak değişiklik gösterir, örneğin:

- Application Guard tarafından kapsanan - web tarayıcısı olayı yalıtılmış bir kapsayıcı tarafından kısıtlandı
- Etkin tehdit algılandı - tehdit çalışırken tehdit algılama oluştu
- Düzeltme başarısız - algılanan tehdidi düzeltme girişimi çağrıldı ancak başarısız oldu
- Düzeltme başarılı - algılanan tehdit durduruldu ve temizlendi
- Uyarı kullanıcı tarafından atlandı - Windows Defender SmartScreen uyarısı bir kullanıcı tarafından kapatıldı ve geçersiz kılındı
- Şüpheli betik algılandı - çalışan kötü amaçlı olabilecek bir betik bulundu
- Uyarı kategorisi - olay bir uyarının oluşturulmasına yol açtıysa, uyarı kategorisi ("YanAl Hareket", örneğin) sağlanır

#### <a name="event-details"></a>Olay ayrıntıları

Bu olayla ilgili ayrıntıları görüntülemek için bir olay seçin. Genel olay bilgilerini göstermek için bir panel görüntülenir. Uygun olduğunda ve veriler kullanılabilir olduğunda, ilgili varlıkları ve ilişkilerini gösteren bir grafik de gösterilir.

Olayı ve ilgili olayları daha fazla incelemek **için, ilgili olayları avla'yı** seçerek hızlı bir şekilde [gelişmiş bir avcılık](advanced-hunting-overview.md) sorgusu çalıştırabilirsiniz. Sorgu, seçilen olayı ve aynı uç noktada aynı anda gerçekleşen diğer olayların listesini döndürür.

:::image type="content" source="images/event-details.png" alt-text="Olay ayrıntıları paneli" lightbox="images/event-details.png":::

### <a name="security-recommendations"></a>Güvenlik önerileri

**Güvenlik önerileri** Uç Nokta için Microsoft Defender [Güvenlik Açığı Yönetimi](tvm-dashboard-insights.md) özelliğinden oluşturulur. Bir öneri seçildiğinde, önerinin açıklaması ve önerinin yapılmamasıyla ilişkili olası riskler gibi ilgili ayrıntıları görüntüleyebileceğiniz bir panel gösterilir. Ayrıntılar için bkz [. Güvenlik önerisi](tvm-security-recommendation.md) .

:::image type="content" source="images/security-recommendations-device.png" alt-text="Güvenlik önerileri sekmesi" lightbox="images/security-recommendations-device.png":::

### <a name="software-inventory"></a>Yazılım envanteri

**Yazılım envanteri** sekmesi, cihazdaki yazılımları ve tüm zayıflıkları veya tehditleri görüntülemenizi sağlar. Yazılımın adını seçtiğinizde güvenlik önerilerini, bulunan güvenlik açıklarını, yüklü cihazları ve sürüm dağıtımını görüntüleyebileceğiniz yazılım ayrıntıları sayfasına yönlendirilirsiniz. Ayrıntılar için bkz[. Yazılım envanteri](tvm-software-inventory.md)

:::image type="content" source="images/software-inventory-device.png" alt-text="Yazılım envanteri sekmesi" lightbox="images/software-inventory-device.png":::

### <a name="discovered-vulnerabilities"></a>Bulunan güvenlik açıkları

**Bulunan güvenlik açıkları sekmesi cihazda bulunan güvenlik açıklarının** adını, önem derecesini ve tehdit içgörülerini gösterir. Belirli güvenlik açıkları seçildiğinde bir açıklama ve ayrıntılar gösterilir.

:::image type="content" source="images/discovered-vulnerabilities-device.png" alt-text="Bulunan güvenlik açıkları sekmesi" lightbox="images/discovered-vulnerabilities-device.png":::

### <a name="missing-kbs"></a>Eksik KB'ler
**Eksik KB'ler** sekmesinde cihaz için eksik güvenlik güncelleştirmeleri listelenir.

:::image type="content" source="images/missing-kbs-device.png" alt-text="Eksik KB sekmesi" lightbox="images/missing-kbs-device.png":::

## <a name="cards"></a>Kart

### <a name="active-alerts"></a>Etkin uyarılar

**Azure Gelişmiş Tehdit Koruması** kartı, Kimlik için Microsoft Defender özelliğini etkinleştirdiyseniz ve etkin uyarılar varsa cihazla ve bunların risk düzeyiyle ilgili uyarılara üst düzey bir genel bakış görüntüler. "Uyarılar" detayına giderek daha fazla bilgi edinebilirsiniz.

:::image type="content" source="images/risk-level-small.png" alt-text="Etkin uyarılar kartı" lightbox="images/risk-level-small.png":::

> [!NOTE]
> Bu özelliği kullanmak için hem Kimlik için Microsoft Defender hem de Uç Nokta için Defender'da tümleştirmeyi etkinleştirmeniz gerekir. Uç Nokta için Defender'da bu özelliği gelişmiş özelliklerde etkinleştirebilirsiniz. Gelişmiş özellikleri etkinleştirme hakkında daha fazla bilgi için bkz. [Gelişmiş özellikleri açma](advanced-features.md).

### <a name="logged-on-users"></a>Oturum açan kullanıcılar

**Oturum açan kullanıcılar** kartı, son 30 gün içinde en sık ve en az sıklıktaki kullanıcılarla birlikte kaç kullanıcının oturum açtığını gösterir. "Tüm kullanıcıları görüntüle" bağlantısı seçildiğinde, kullanıcı türü, oturum açma türü ve kullanıcının ilk ve son görüldüğü zaman gibi bilgileri görüntüleyen ayrıntılar bölmesi açılır. Daha fazla bilgi için bkz [. Kullanıcı varlıklarını araştırma](investigate-user.md).

:::image type="content" source="images/logged-on-users.png" alt-text="Kullanıcı ayrıntıları bölmesi" lightbox="images/logged-on-users.png":::

> [!NOTE]
> 'En sık' kullanıcı değeri yalnızca etkileşimli olarak başarıyla oturum açan kullanıcıların kanıtlarına göre hesaplanır.
> Bununla birlikte, "Tüm kullanıcılar" yan bölmesi her türlü kullanıcı oturum açma işlemini hesaplar, böylece bu kullanıcıların etkileşimli olmayabileceği göz önüne alındığında, yan bölmede daha sık kullanıcı görmesi beklenir.

### <a name="security-assessments"></a>Güvenlik değerlendirmeleri

**Güvenlik değerlendirmeleri** kartı genel açığa çıkarma düzeyini, güvenlik önerilerini, yüklü yazılımları ve bulunan güvenlik açıklarını gösterir. Bir cihazın maruz kalma düzeyi, bekleyen güvenlik önerilerinin birikmeli etkisine göre belirlenir.

:::image type="content" source="images/security-assessments.png" alt-text="Güvenlik değerlendirmeleri kartı" lightbox="images/security-assessments.png":::


### <a name="device-health-status"></a>Cihaz durumu

**Cihaz sistem durumu** kartı, belirli bir cihaz için özetlenmiş bir sistem durumu raporu gösterir. Cihazın genel durumunu belirtmek için kartın üst kısmında aşağıdaki iletilerden biri görüntülenir (en yüksek ve en düşük önceliğe göre listelenir):

- Defender Virüsten Koruma etkin değil
- Güvenlik bilgileri güncel değil
- Altyapı güncel değil
- Hızlı tarama başarısız oldu
- Tam tarama başarısız oldu
- Platform güncel değil
- Güvenlik bilgileri güncelleştirme durumu bilinmiyor
- Altyapı güncelleştirme durumu bilinmiyor
- Hızlı tarama durumu bilinmiyor
- Tam tarama durumu bilinmiyor
- Platform güncelleştirme durumu bilinmiyor
- Cihaz güncel
- macOS & Linux için durum kullanılamıyor

Karttaki diğer bilgiler şunlardır: son tam tarama, son hızlı tarama, güvenlik zekası güncelleştirme sürümü, altyapı güncelleştirme sürümü, platform güncelleştirme sürümü ve Defender Virüsten Koruma modu. 

Gri dairenin verilerin bilinmediğini gösterdiğini lütfen unutmayın. 

>[!NOTE]
>macOS ve Linux cihazları için genel durum iletisi şu anda 'MacOS & Linux için durum kullanılamıyor' olarak görünüyor. Şu anda durum özeti yalnızca Windows cihazları için kullanılabilir. Tablodaki diğer tüm bilgiler, desteklenen tüm platformlar için her cihaz sistem durumu sinyalinin tek tek durumlarını göstermek için günceldir. 

Cihaz durumu raporunun ayrıntılı bir görünümünü elde etmek için **Raporlar > Cihaz durumu'na** gidebilirsiniz. Daha fazla bilgi için bkz[. Uç Nokta için Microsoft Defender'de cihaz durumu ve uyumluluk raporu](/microsoft-365/security/defender-endpoint/machine-reports). 

:::image type="content" source="images/device-health-status.png"  alt-text="Cihaz sistem durumu kartı" lightbox="images/device-health-status.png":::



## <a name="related-topics"></a>İlgili konular

- [Uç Nokta için Microsoft Defender Uyarıları kuyruğu görüntüleme ve düzenleme](alerts-queue.md)
- [Uç Nokta için Microsoft Defender uyarılarını yönetme](manage-alerts.md)
- [Uç Nokta için Microsoft Defender uyarılarını araştırma](investigate-alerts.md)
- [Uç Nokta için Defender uyarısıyla ilişkilendirilmiş bir dosyayı araştırma](investigate-files.md)
- [Uç Nokta için Defender uyarısıyla ilişkilendirilmiş bir IP adresini araştırma](investigate-ip.md)
- [Uç Nokta için Defender uyarısıyla ilişkilendirilmiş bir etki alanını araştırma](investigate-domain.md)
- [Uç Nokta için Defender'da kullanıcı hesabını araştırma](investigate-user.md)
- [Güvenlik önerisi](tvm-security-recommendation.md)
- [Yazılım envanteri](tvm-software-inventory.md)
