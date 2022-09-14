---
title: Microsoft 365 ağ değerlendirmesi
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/06/2021
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 ağ değerlendirmesi
ms.openlocfilehash: 8c5e6d41e5aa8ba6eaa1c38454f6f2e1d428f9d0
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67670443"
---
# <a name="microsoft-365-network-assessment"></a>Microsoft 365 ağ değerlendirmesi

Microsoft 365 Yönetici Merkezi'nin ağ bağlantısında, **ağ değerlendirmeleri** birçok ağ performansı ölçümünün toplamını kurumsal ağ çevrenizin sistem durumunun anlık görüntüsüne dalar. Ağ değerlendirmesi, müşteriden sorumlu ağ tasarımının Office 365 kullanıcı deneyimini ne kadar etkilediğini bildirir. Ağ değerlendirmelerinin kapsamı hem tüm kiracıya hem de kullanıcıların kiracınıza bağlandığı her coğrafi konuma göre belirlenir. Değerlendirmeler, Microsoft 365 yöneticilerine kuruluşun ağ durumu hakkında anında fikir edinmenin ve herhangi bir genel ofis konumu için ayrıntılı raporun detayına gitmenin kolay bir yolunu sunar.

Ağ değerlendirme noktası değeri 0 ile 100 arasındadır ve ortalama TCP gecikme süresi, indirme hızı ve UDP bağlantı kalitesi ölçümleridir. Bu ölçümler günde bir kez derlenir. Microsoft'a ait ağlara yönelik performans ölçümleri, değerlendirme sonuçlarının belirsiz ve kurumsal ağa özgü olduğundan emin olmak için bu ölçümlerin dışında tutulur.

> [!div class="mx-imgBorder"]
> ![Ağ değerlendirme değeri.](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

Çok düşük bir ağ değerlendirme değeri, Microsoft 365 istemcilerinin kiracıya bağlanırken veya yanıt veren bir kullanıcı deneyimini sürdürürken önemli sorunlarla karşılaşacağını gösterir. Yüksek bir değer, devam eden birkaç performans sorunuyla düzgün yapılandırılmış bir ağı gösterir. %80 değeri iyi durumda bir temeli temsil eder. Bunun üzerinde, ağ performansı nedeniyle Microsoft 365 bağlantısı veya yanıt hızı hakkında düzenli kullanıcı şikayetleri almayı beklememelisiniz. Yinelemeli ağ bağlantısı geliştirmeleri yapıldıkçe, bu değer kullanıcı deneyimiyle birlikte artacaktır.

| Ağ değerlendirmesi | Beklenen kullanıcı deneyimi |
| :----------------- | :----------------------- |
| 100                | En iyi                     |
| 80                 | Önerileri karşılar    |
| 60                 | Kabul edilebilir               |
| 40                 | Kullanıcılar sorunlarla karşılaşabilir |
| 20                 | Kullanıcılar şikayet edebilir       |
| 0                  | Ağ sorunları yaygın bir tartışma konusudur |

## <a name="network-assessment-panel"></a>Ağ değerlendirme paneli

Kapsamı kiracı veya belirli bir ofis konumu olan her ağ değerlendirmesi, değerlendirmeyle ilgili ayrıntıları içeren bir panel gösterir. Bu panelde değerlendirmenin hem yüzde olarak hem de yalnızca ölçüm verilerinin alındığı iş yükleri dahil olmak üzere her bileşen iş yükü için toplam puan olarak çubuk grafiği gösterilir. Bir ofis konumu ağ değerlendirmesi için, ofis konumunuzla aynı şehirde veri bildiren beş beşli kuruluşun her birinde Microsoft 365 müşterilerinin yüzdesiyle bir karşılaştırma da gösteririz.

> [!div class="mx-imgBorder"]
> ![Örnek ağ değerlendirme değeri.](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

Paneldeki **Değerlendirme dökümü** , bileşen iş yüklerinin her biri için değerlendirmeyi gösterir.

**Değerlendirme geçmişi**, değerlendirmenin son 30 gününü ve karşılaştırmayı gösterir. Ayrıca geçmiş sekmesini kullanarak herhangi bir ofis konumunun ölçüm geçmişini iki yıla kadar raporlayabilirsiniz. Geçmiş sekmesi, raporlamak istediğiniz öznitelikleri seçmenize olanak tanır. Bir rapor zaman çerçevesi seçerek bir ağ güncelleştirme projesinin etkisini vurgulayabilir ve ağ değerlendirmenizde yapılan iyileştirmeyi görebilirsiniz.

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>Kiracı ağ değerlendirmeleri ve ofis konumu ağ değerlendirmeleri

Ağ değerlendirmesi, bir ofis konumunun ağ çevresinin Tasarımını Microsoft'un ağına ölçer. Ağ çevresi iyileştirmeleri en iyi şekilde her ofis konumunda yapılır.

Ağ performansına genel bakış sayfasında Tüm Microsoft 365 kiracısı için bir ağ değerlendirme değeri gösteririz. Bu değer, tüm ofis konumları için ağ değerlendirmelerinin ağırlıklı ortalamasıdır. Ayrıca, o konumun özet sayfasında algılanan her ofis konumu için belirli bir ağ değerlendirme değeri vardır.

## <a name="exchange-online"></a>Exchange Online

Exchange Online için istemci makinesinden Exchange hizmeti ön kapısına TCP gecikmesi ölçülür. Bu gecikme süresi, ağın müşterilerin LAN ve WAN üzerinden kat ettiği uzaklıktan etkilenebilir. Ayrıca, bağlantıyı geciktiren veya paketlerin yeniden gönderilmesine neden olan ağ aracı cihazları veya hizmetlerinden de etkilenebilir. Ve en yakın Exchange hizmeti ön kapısının ne kadar uzakta olduğundan etkilenir. Ortanca değer (50. yüzdebirlik veya P50 ölçüsü olarak da bilinir) önceki üç gün içindeki tüm ölçümler için alınır.

Exchange Online değerlendirmesi aşağıdaki tablo kullanılarak yapılır. Eşikler arasındaki tüm TCP gecikme süresi numaraları, bant içinde doğrusal olarak noktalara atanır.

| TCP Gecikme Süresi   | Puan |
| :------------ | :----- |
| 10 ms veya daha az  | 100    |
| 25 ms          | 80     |
| 100 ms         | 60     |
| 200 ms         | 40     |
| 300 ms         | 20     |
| 350 ms veya daha fazla | 0      |

## <a name="sharepoint-online"></a>SharePoint Online

SharePoint Online için, kullanıcının SharePoint veya OneDrive'dan bir belgeye erişmesi için kullanılabilecek indirme hızı ölçülür. Bu, istemci makine ile Microsoft'un ağı arasındaki ağ bağlantı hatlarında bulunan bant genişliğinden etkilenebilir. Ayrıca genellikle karmaşık ağ cihazlarında veya yetersiz kapsama Wi-Fi alanlarındaki performans sorunlarına neden olan ağ tıkanıklığı da etkilenir. İndirme hızı saniyede megabayt cinsinden ölçülür ve bu da saniyede megabit olarak derecelendirilmiş bir bağlantı hattının yaklaşık onda biridir. 1 saniye içinde hangi boyut dosyasının indirilebileceğini doğrudan görebildiğiniz için saniyedeki MegaByte birimi yararlı olur. 25. yüzdebirlik değer (P25 ölçüsü olarak da bilinir) önceki üç gün içindeki tüm ölçümler için alınır. Bu 25. yüzdebirlik dilim, zaman içinde değişen tıkanıklıkların etkisini azaltmaya yardımcı olur.

SharePoint Online değerlendirmesi aşağıdaki tablo kullanılarak yapılır. Eşikler arasındaki herhangi bir indirme hızı numarası, bant içinde doğrusal olarak noktalara atanır.

| İndirme hızı | Puan |
| :------------- | :----- |
| 20MBps veya daha fazlası | 100    |
| 14MBps         | 80     |
| 8MBps          | 60     |
| 4MBps          | 40     |
| 2MBps          | 20     |
| 0MBps          | 0      |

## <a name="microsoft-teams"></a>Microsoft Teams

Microsoft Teams için Ağ kalitesi UDP gecikme süresi, UDP değişimi ve UDP paket kaybı olarak ölçülür. UDP, Microsoft Teams için arama ve konferans ses ve video medya bağlantısı için kullanılır. Bu durum, bir ağın UDP desteğindeki bağlantı boşluklarına ek olarak gecikme süresi ve indirme hızıyla aynı faktörlerden etkilenebilir çünkü UDP daha yaygın TCP protokolüne ayrı olarak yapılandırılır. Ortanca değer (50. yüzdebirlik veya P50 ölçüsü olarak da bilinir) önceki üç gün içindeki tüm ölçümler için alınır. 

Bir ile beş arasında bir ölçek için bu UDP ölçümlerinden ortalama bir görüş puanı hesaplıyoruz. Ardından bunu Microsoft Teams ağ değerlendirmesi için 0-100 puan ölçeğiyle eşleriz.  Genel iyi 87,5 puanın üzerinde ve genel kötü ise 50 puanın altında.

## <a name="related-topics"></a>İlgili konular

[Microsoft 365 Yönetici Merkezi'nde ağ bağlantısı](office-365-network-mac-perf-overview.md)

[Microsoft 365 ağ performansı içgörüleri](office-365-network-mac-perf-insights.md)

[Microsoft 365 ağ bağlantısı test aracı](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Ağ Bağlantısı Konum Hizmetleri](office-365-network-mac-location-services.md)
