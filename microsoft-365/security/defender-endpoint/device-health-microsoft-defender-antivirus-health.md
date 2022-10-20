---
title: Cihaz durumu Microsoft Defender Virüsten Koruma sistem durumu raporu
description: Virüsten koruma durumunu izlemek ve Virüsten koruma altyapısı, zeka ve platform sürümlerini Microsoft Defender için Microsoft Defender Virüsten Koruma raporunu kullanın.
keywords: Microsoft Defender Virüsten Koruma raporu, altyapı sürümü, akıllı sürüm ve platform sürümleri, virüsten koruma
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
ms.date: 09/06/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.subservice: mde
ms.reviewer: mkaminska
ms.openlocfilehash: a5641725f9f259064c7d380da470353395335363
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68635564"
---
# <a name="device-health-microsoft-defender-antivirus-health-report"></a>Cihaz durumu, Microsoft Defender Virüsten Koruma sistem durumu raporu

**Şunlar için geçerlidir:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Uç Nokta için Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [İş için Microsoft Defender](../defender-business/mdb-overview.md)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Cihaz Durumu raporu, kuruluşunuzdaki cihazlar hakkında bilgi sağlar. Rapor virüsten koruma durumunu ve virüsten koruma altyapısı, zeka ve platform sürümlerini Microsoft Defender gösteren popüler bilgileri içerir.

> [!IMPORTANT]
> Windows&nbsp;Server&nbsp;2012&nbsp;R2 ve Windows&nbsp;Server&nbsp;2016'nın cihaz durumu raporlarında görünmesi için bu cihazların modern birleşik çözüm paketi kullanılarak eklenmesi gerekir. Daha fazla bilgi için bkz. [Windows Server 2012 R2 ve 2016 için modern birleşik çözümde yeni işlevler](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution).

Microsoft 365 Güvenlik panosu gezinti panelinde **Raporlar'ı** seçin ve ardından **Cihaz durumu ve uyumluluğu'nu** açın.

- [**Microsoft Defender Virüsten Koruma sistem durumu** sekmesinde](#microsoft-defender-antivirus-health-tab), Microsoft Defender Virüsten Koruma'nın aşağıdaki yönlerini bildiren sekiz kart vardır:
  - [Virüsten koruma modu kartı](#antivirus-mode-card)
  - [Virüsten koruma altyapısı sürüm kartı](#antivirus-engine-version-card)
  - [Virüsten koruma güvenlik bilgileri sürüm kartı](#antivirus-security-intelligence-version-card)
  - [Virüsten koruma platformu sürüm kartı](#antivirus-platform-version-card)
  - [En son virüsten koruma tarama sonuçları kartı](#recent-antivirus-scan-results-card)
  - [Virüsten koruma altyapısı güncelleştirme kartı](#antivirus-engine-updates-card)
  - [Güvenlik bilgileri güncelleştirme kartı](#security-intelligence-updates-card)
  - [Virüsten koruma platformu güncelleştirme kartı](#antivirus-platform-updates-card)

## <a name="report-access-permissions"></a>Rapor erişim izinleri

Microsoft 365 Güvenlik panosunda Cihaz durumu ve virüsten koruma uyumluluk raporuna erişmek için aşağıdaki izinler gereklidir:

| İzin adı | İzin türü |
|:---|:---|
| Verileri Görüntüle | Tehdit ve güvenlik açığı yönetimi (TVM) |

Bu izinleri atamak için:

1. Güvenlik yöneticisi veya <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Genel yönetici</a> rolü atanmış hesabı kullanarak Microsoft 365 Defender oturum açın.
1. Gezinti bölmesinde **Ayarlar** \> **Uç Noktaları** \> **Rolleri'ni** seçin ( **İzinler'in** altında).
1. Düzenlemek istediğiniz rolü seçin.
1. **Düzenle'yi** seçin.
1. **Rolü düzenle'nin** **Genel** sekmesindeki **Rol adı** alanına rol için bir ad yazın.
1. **Açıklama** alanına rolün kısa bir özetini yazın.
1. **İzinler'de** **Verileri Görüntüle'yi** seçin ve **Verileri Görüntüle'nin** altında **Tehdit ve güvenlik açığı yönetimi** (TVM) öğesini seçin.

Kullanıcı rolü yönetimi hakkında daha fazla bilgi için bkz. [Rol tabanlı erişim denetimi için rol oluşturma ve yönetme](user-roles.md).

## <a name="microsoft-defender-antivirus-health-tab"></a>Microsoft Defender Virüsten Koruma sistem durumu sekmesi  

Microsoft Defender Virüsten Koruma sistem durumu sekmesi, kuruluşunuzdaki Microsoft Defender Virüsten Koruma'nın çeşitli yönlerini bildiren sekiz kart içerir:

İki kart, [Virüsten koruma modu kartı](#antivirus-mode-card) ve [En son virüsten koruma tarama sonuçları kartı](#recent-antivirus-scan-results-card), Microsoft Defender Virüsten Koruma işlevleri hakkında rapor sağlar.

Kalan altı kart, kuruluşunuzdaki cihazlar için Microsoft Defender Virüsten Koruma durumu hakkında rapor verir:

| _sürüm_ kartları: | _güncelleştirme_ kartları{<a id="fn1">1</a>} |
|:---|:---|
| [Virüsten koruma altyapısı sürüm kartı](#antivirus-engine-version-card) <br> [Virüsten koruma güvenlik bilgileri sürüm kartı](#antivirus-security-intelligence-version-card) <br> [Virüsten koruma platformu sürüm kartı](#antivirus-platform-version-card) | [Virüsten koruma altyapısı güncelleştirme kartı](#antivirus-engine-updates-card) <br> [Güvenlik bilgileri güncelleştirme kartı](#security-intelligence-updates-card) <br> [Virüsten koruma platformu güncelleştirme kartı](#antivirus-platform-updates-card) |
| Üç sürüm kartı, ek bilgi sağlayan ve daha fazla incelemeye olanak tanıyan açılır raporlar sağlar. | Üç güncel raporlama kartı, daha fazla bilgi edinmek için kaynaklara bağlantılar sağlar. |

<sup>{[1](#fn1)}</sup> Üç _güncelleştirme_ kartı için (güncel raporlama kartları olarak da bilinir), "**Kullanılabilir veri yok**" (veya "Bilinmeyen" değer), güncelleştirme durumunu bildirmemiş cihazları gösterir. Güncelleştirme durumunu bildirmemeyen cihazlar çeşitli nedenlerden kaynaklanabilir, örneğin:

- Bilgisayarın ağ bağlantısı kesildi
- Bilgisayar kapatıldı veya hazırda bekleme durumunda
- Microsoft Defender Virüsten Koruma devre dışı bırakıldı
- Cihaz Windows olmayan (Mac veya Linux) bir cihazdır
- Bulut koruması etkin değil
- Cihaz Virüsten Koruma altyapısı veya platform sürümü için önkoşulları karşılamıyor

### <a name="prerequisites"></a>Önkoşullar

Güncel raporlama, aşağıdaki ölçütlere uyan cihazlar için bilgi oluşturur:

- Altyapı sürümü: 1.1.19300.2+
- Platform sürümü: 4.18.2202.1+
- Bulut koruması etkin
- Windows işletim sistemi*

*Şu anda güncel raporlama yalnızca Windows cihazları için kullanılabilir. Mac ve Linux gibi platformlar arası cihazlar "Kullanılabilir veri yok"/Bilinmiyor altında listelenir

>:::image type="content" source="images/device-health-defender-antivirus-health-tab.png" alt-text="Microsoft Defender Virüsten Koruma Durumu sekmesini gösterir." lightbox="images/device-health-defender-antivirus-health-tab.png":::

### <a name="card-functionality"></a>Kart işlevselliği

İşlevsellik temelde tüm kartlar için aynıdır. Kartlardan herhangi birinde numaralandırılmış bir çıtaya tıklayarak **Virüsten Koruma ayrıntıları** açılır Microsoft Defender açılır ve bu karttaki bir yönün sürüm numarasıyla yapılandırılmış tüm cihazlar hakkındaki bilgileri gözden geçirmenizi sağlar.

>:::image type="content" source="images/device-health-defender-antivirus-health-antivirus-details.png" alt-text="virüsten koruma ayrıntıları açılır Microsoft Defender gösterir." lightbox="images/device-health-defender-antivirus-health-antivirus-details.png":::

Tıkladığınız sürüm numarası şuysa:

- Geçerli bir sürüm, ardından **Düzeltme gerekli** ve **Güvenlik önerisi** yok
- Güncel olmayan bir sürüm, raporun üst kısmında **Düzeltme gerektiğini** belirten bir bildirim bulunur ve **bir Güvenlik önerisi** bağlantısı bulunur. Uygun virüsten koruma güncelleştirmelerini önerebilen Tehdit ve Güvenlik Açığı Yönetimi konsoluna gitmek için güvenlik önerisi bağlantısını seçin.

**virüsten koruma ayrıntıları açılır Microsoft Defender belirli türlerdeki** bilgileri eklemek veya kaldırmak için **Sütunları Özelleştir'i** seçin. **Sütunları Özelleştir** bölümünde, Microsoft Defender Virüsten Koruma ayrıntıları raporuna eklenmesini istediklerinizi belirtmek için öğeleri seçin veya temizleyin.

>:::image type="content" source="images/device-health-defender-antivirus-engine-version-details-custom-columns.png" alt-text="Microsoft Defender Virüsten Koruma sistem durumu raporlaması için özel sütun seçeneklerini gösterir." lightbox="images/device-health-defender-antivirus-engine-version-details-custom-columns.png":::

#### <a name="new-microsoft-defender-antivirus-filter-definitions"></a>Yeni Microsoft Defender Virüsten Koruma filtresi tanımları

Aşağıdaki tabloda Virüsten Koruma raporlama Microsoft Defender yeni olan terimlerin listesi yer alır.

| Sütun adı | Açıklama |
|:---|:---|
| Güvenlik bilgileri yayımlama süresi  | Microsoft'un cihazdaki güvenlik bilgileri güncelleştirme sürümünün yayın tarihini gösterir. Güvenlik bilgileri yayımlama süresi yedi günden uzun olan cihazlar raporlarda güncel değil olarak kabul edilir. |
| Son görülme | Cihazın en son ne zaman bağlantı olduğunu gösterir. |
| Veri yenileme zaman damgası  | İstemci olaylarının raporlama için en son ne zaman alındığını gösterir: AV modu, AV altyapısı sürümü, AV platformu sürümü, AV güvenlik zekası sürümü ve tarama bilgileri. |
| İmza yenileme zamanı | Altyapı, platform ve imza durumuyla ilgili raporlama için istemci olaylarının en son ne zaman alındığını gösterir. |

Açılır listede: Cihazın adına tıkladığınızda, ayrıntılı raporlara erişebileceğiniz bu cihazın "Cihaz sayfası"na yönlendirilirsiniz.

#### <a name="export-report"></a>Raporu dışarı aktarma

Dışarı aktarabileceğiniz iki rapor düzeyi vardır:

##### <a name="top-level-export"></a>Üst düzey dışarı aktarma

Portal aracılığıyla iki farklı dışarı aktarma csv işlevi vardır:

- **Üst düzey dışarı aktarma** Tüm Microsoft Defender Virüsten Koruma sistem durumu raporunu (500 K sınırı) toplamak için en üst düzey **Dışarı Aktar** düğmesini kullanabilirsiniz.

>:::image type="content" source="images/device-health-defender-antivirus-health-tab-export.png" alt-text="En üst düzey dışarı aktarma raporu düğmesini gösterir" lightbox="images/device-health-defender-antivirus-health-tab-export.png":::

- **Açılır öğe düzeyi dışarı aktarma** Bir raporu Excel elektronik tablosuna (100 K sınırı) dışarı aktarmak için açılır listelerdeki **Dışarı Aktar** düğmesini kullanabilirsiniz.

Dışarı aktarılan raporlar, ayrıntılar raporuna giriş noktanızı ve hangi filtreleri veya özelleştirilmiş sütunları ayarladığınızı temel alarak bilgileri yakalar.

API kullanarak dışarı aktarma hakkında bilgi için aşağıdaki makalelere bakın:

- [Cihaz virüsten koruma sistem durumu raporunu dışarı aktarma](device-health-export-antivirus-health-report-api.md)
- [Cihaz virüsten koruma sistem durumu ayrıntılarını API yöntemleri ve özelliklerini dışarı aktarma](device-health-api-methods-properties.md)

> [!IMPORTANT]
>
> Şu anda yalnızca **Virüsten Koruma Durumu JSON Yanıtı** genel kullanıma sunulmuştur. **Dosyalar aracılığıyla Virüsten Koruma Sistem Durumu API'sini** yalnızca genel önizlemede kullanabilirsiniz.
>
> **Gelişmiş Tehdit Avcılığı özel sorgusu** şu anda sorgular hala görünür olsa bile yalnızca genel önizlemede kullanılabilir.

### <a name="microsoft-defender-antivirus-version-and-update-cards-functionality"></a>Microsoft Defender Virüsten koruma sürümü ve güncelleştirme kartları işlevselliği

Aşağıda, Microsoft Defender Virüsten Koruma altyapısı, güvenlik bilgileri ve platform bileşenleri için _sürüm_ ve _güncelleştirme_ bilgileri hakkında rapor veren altı kartın açıklamaları yer alır:

#### <a name="full-report"></a>Tam rapor

Üç _sürüm_ kartından herhangi birinde **Tam raporu görüntüle'yi** seçerek üç cihaz türünün her biri için en son dokuz Microsoft Defender Virüsten Koruma _sürümü_ raporunu görüntüleyin: Windows, Mac ve Linux; dokuzdan az varsa hepsi gösterilir. **Diğer** kategorisi, algılanırsa onuncu ve altındaki en son virüsten koruma altyapısı sürümlerini yakalar.

>:::image type="content" source="images/device-health-defender-antivirus-health-view-full-report.png" alt-text="Her türden ilk dokuz işletim sisteminin dağılımını gösterir" lightbox="images/device-health-defender-antivirus-health-view-full-report.png":::

Üç _sürüm_ kartının birincil avantajlarından biri, virüsten koruma motorlarının, platformlarının ve güvenlik zekasının en güncel sürümlerinin kullanılıp kullanılmadığına ilişkin hızlı göstergeler sağlamasıdır. Sürüm kartları, karta bağlı ayrıntılı bilgilerle birlikte sürümlerin güncel olup olmadığını denetlemek ve tek tek bilgisayarlar veya bilgisayar grupları hakkında bilgi toplamak için güçlü bir araç haline gelir.
İdeal olarak, bu raporları çalıştırdığınızda, eski sürümlerin aksine en güncel virüsten koruma sürümlerinin yüklü olduğunu gösterirler.
Kuruluşunuzun en güncel sürümlerden tam olarak yararlanıp yararlanmadığını belirlemek için bu raporları kullanın.

>:::image type="content" source="images/device-health-defender-antivirus-health-antivirus-details-up-to-date.png" alt-text="Microsoft Defender Virüsten Koruma sürümü ayrıntılarını gösterir" lightbox="images/device-health-defender-antivirus-health-antivirus-details-up-to-date.png":::

Kötü amaçlı yazılımdan koruma çözümünüzün en son tehditleri algılamasına yardımcı olmak için güncelleştirmeleri Windows Update bir parçası olarak otomatik olarak alın.

Geçerli sürümler ve farklı Microsoft Defender Virüsten Koruma bileşenlerini güncelleştirme hakkında daha fazla bilgi için [Virüsten Koruma platformu desteği Microsoft Defender](manage-updates-baselines-microsoft-defender-antivirus.md) adresini ziyaret edin.

### <a name="card-descriptions"></a>Kart açıklamaları

_Virüsten Koruma sürüm_ kartlarının her birinde bildirilen toplanan bilgilerin kısa özetleri aşağıdadır:

#### <a name="antivirus-mode-card"></a>Virüsten koruma modu kartı

Kuruluşunuzdaki kaç cihazın (kartta belirtilen tarihte) aşağıdaki Microsoft Defender Virüsten Koruma modlarından birinde olduğunu bildirir:

| Değer | Modu |
|---|---|
| 0 | Etkin |
| 1 | Pasif |
| 2 | Devre dışı (kaldırıldı, devre dışı veya SideBySidePassive {Düşük Düzenli Tarama olarak da bilinir}) |
| 3 | Diğerleri (Çalışmıyor, Bilinmiyor) |
| 4 | EDRBlocked |

>:::image type="content" source="images/device-health-defender-antivirus-health-antivirus-mode.png" alt-text="Virüsten Koruma modlarını Microsoft Defender filtrelemeyi gösterir" lightbox="images/device-health-defender-antivirus-health-antivirus-mode.png":::

Her modun açıklamaları aşağıdadır:

- **Etkin** mod - Etkin modda Microsoft Defender Virüsten Koruma, cihazdaki birincil virüsten koruma uygulaması olarak kullanılır. Dosyalar taranır, tehditler düzeltilir ve algılanan tehditler, kuruluşunuzun güvenlik raporlarında ve Windows Güvenliği uygulamanıza listelenir.
- **Pasif** mod - Pasif modda Microsoft Defender Virüsten Koruma, cihazdaki birincil virüsten koruma uygulaması olarak kullanılmaz. Dosyalar taranır ve algılanan tehditler bildirilir, ancak tehditler Microsoft Defender Virüsten Koruma tarafından düzeltilmemiştir. ÖNEMLİ: Microsoft Defender Virüsten Koruma, pasif modda sadece Uç Nokta için Microsoft Defender’a eklenmiş uç noktalarda çalıştırılabilir. [Microsoft Defender Virüsten Koruma’nın pasif modda çalıştırılması için gereksinimlere](microsoft-defender-antivirus-compatibility.md#requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode) bakın.
- **Devre dışı** modu - ile eş anlamlı: kaldırıldı, devre dışı, sideBySidePassive ve Düşük Düzenli Tarama. Devre dışı bırakıldığında Microsoft Defender Virüsten Koruma kullanılmaz. Dosyalar taranmıyor ve tehditler düzeltilmemiş. Genel olarak, Microsoft Microsoft Defender Virüsten Koruma'yı devre dışı bırakmanızı veya kaldırmanızı önermez.
- **Diğer** modu - Çalışmıyor, Bilinmiyor
- **Blok modunda EDR** - Uç nokta algılama ve yanıt (EDR) engellenmiş modunda. Bkz [. Blok modunda uç nokta algılama ve yanıt](edr-in-block-mode.md)

Pasif, LPS veya Kapalı olan cihazlar olası bir güvenlik riski sunar ve araştırılmalıdır.

LPS hakkında ayrıntılı bilgi için bkz. [Microsoft Defender Virüsten Koruma'da sınırlı düzenli tarama kullanma](limited-periodic-scanning-microsoft-defender-antivirus.md).

#### <a name="recent-antivirus-scan-results-card"></a>En son virüsten koruma tarama sonuçları kartı

Bu kartta hızlı taramalar ve tam taramalar için tüm sonuçları gösteren iki çubuk grafik vardır. Her iki grafikte de ilk çubuk taramaların tamamlanma hızını gösterir ve **Tamamlandı**, **İptal Edildi** veya **Başarısız'ı** gösterir. Her bölümdeki ikinci çubuk, başarısız taramalar için hata kodları sağlar.
**Mod** ve **Son tarama sonuçları** sütunlarını tarayarak etkin virüsten koruma tarama modunda olmayan cihazları ve son virüsten koruma taramalarını başarısız olan veya iptal eden cihazları hızla belirleyebilirsiniz. Bu bilgilerle rapora dönebilir, daha fazla ayrıntı ve güvenlik önerileri toplayabilirsiniz. Bu kartta herhangi bir hata kodu bildirilirse, hata kodları hakkında daha fazla bilgi edinmek için bir bağlantı olacaktır.

Geçerli Microsoft Defender Virüsten Koruma sürümleri ve farklı Microsoft Defender Virüsten Koruma bileşenlerini güncelleştirme hakkında daha fazla bilgi için [Microsoft Defender Virüsten Koruma güncelleştirmelerini yönetme ve temelleri uygulama](manage-updates-baselines-microsoft-defender-antivirus.md) sayfasını ziyaret edin.

#### <a name="antivirus-engine-version-card"></a>Virüsten koruma altyapısı sürüm kartı

Kuruluşunuzdaki Windows Cihazları, Mac cihazları ve Linux cihazları arasında yüklü olan en güncel Microsoft Defender Virüsten Koruma altyapısı sürümlerinin gerçek zamanlı sonuçlarını gösterir. Microsoft Defender Virüsten Koruma altyapısı aylık olarak güncelleştirilir.
Geçerli sürümler ve farklı Microsoft Defender Virüsten Koruma bileşenlerini güncelleştirme hakkında daha fazla bilgi için bkz[. Virüsten Koruma platformu desteği Microsoft Defender](manage-updates-baselines-microsoft-defender-antivirus.md).

#### <a name="antivirus-security-intelligence-version-card"></a>Virüsten koruma güvenlik bilgileri sürüm kartı

Ağınızdaki cihazlarda yüklü _virüsten koruma güvenlik bilgileri sürümlerinin_ en yaygın Microsoft Defender listeler.
Microsoft, en son tehditleri ele almak ve algılama mantığını geliştirmek için Microsoft Defender güvenlik bilgilerini sürekli olarak güncelleştirir. Güvenlik bilgilerine yönelik bu iyileştirmeler, olası tehditleri doğru bir şekilde tanımlama Microsoft Defender Virüsten Koruma'nın (ve diğer Microsoft kötü amaçlı yazılımdan koruma çözümlerinin) becerisini geliştirir. Bu güvenlik zekası, hızlı ve güçlü yapay zeka destekli yeni nesil koruma sağlamak için doğrudan bulut tabanlı koruma ile çalışır.

##### <a name="antivirus-platform-version-card"></a>Virüsten koruma platformu sürüm kartı

Kuruluşunuzdaki Windows, Mac ve Linux cihazlarında yüklü olan en güncel Microsoft Defender Virüsten Koruma platformu sürümlerinin gerçek zamanlı sonuçlarını gösterir. Microsoft Defender Virüsten Koruma platformu aylık olarak güncelleştirilir.
Geçerli sürümler ve farklı Microsoft Defender Virüsten Koruma bileşenlerini güncelleştirme hakkında daha fazla bilgi için bkz[. virüsten koruma platformu desteği Microsoft Defender](manage-updates-baselines-microsoft-defender-antivirus.md)

#### <a name="up-to-date-cards"></a>Güncel kartlar

Güncel kartlar  **Virüsten Koruma altyapısı, Virüsten Koruma**  **platformu** ve **Güvenlik bilgileri** güncelleştirme sürümleri için güncel durumu gösterir. Üç olası durum vardır:  _Güncel_ ('Doğru'), _güncel değil_ ('Yanlış') ve _kullanılabilir veri yok_ ('Bilinmiyor').

> [!IMPORTANT]
>
> Güncel belirlemeyi yapmak için kullanılan mantık yakın zamanda geliştirilmiş ve basitleştirilmiştir. Yeni davranış bu bölümde belgelenmiştir.

Aşağıdaki her kart için  _Güncel_, _güncel_ olmayan ve _kullanılabilir veri yok_ tanımları sağlanmıştır.

Microsoft Defender Virüsten Koruma, altyapı, platform ve güvenlik bilgileri güncelleştirmeleri için güncel raporlar ve belirlemeler yapmak için "İmza yenileme süresi" (cihazın en son güncel raporlarla iletişim kurması) ölçütlerini kullanır.

Cihaz yedi günden uzun süredir raporlarla iletişim kurmadıysa güncel durum otomatik olarak "bilinmiyor" veya "kullanılabilir veri yok" olarak işaretlenir (imza yenileme süresi >7).

Yukarıda belirtilen terimler hakkında daha fazla bilgi için şu bölüme bakın: [Yeni Microsoft Defender Virüsten Koruma filtresi tanımları](#new-microsoft-defender-antivirus-filter-definitions)

> [!NOTE]
>
> Güncel raporlama **önkoşulları**
>
> Güncel raporlama, aşağıdaki ölçütlere uyan cihazlar için bilgi oluşturur:
>
> - Altyapı sürümü: 1.1.19300.2+
> - Platform sürümü: 4.18.2202.1+
> - Bulut koruması etkin
> - Windows işletim sistemi*
>
>*Şu anda güncel raporlama yalnızca Windows cihazları için kullanılabilir. Mac ve Linux gibi platformlar arası cihazlar "kullanılabilir veri yok" altında listelenir
>

##### <a name="up-to-date-definitions"></a>Güncel tanımlar

Altyapı ve platform için güncel tanımlar aşağıdadır:

| Cihazdaki motor/platform dikkate alınır: | Eğer: |
|:---|:---|
| **Güncel** | son yedi gün içinde Defender rapor olayıyla ('İmza yenileme süresi') iletişim kuran cihaz ve Altyapı veya Platform sürümü derleme süresi son 60 gün içindedir. |
| **Güncel** | son yedi gün içinde Defender rapor olayıyla ('İmza yenileme süresi') iletişim kuran cihaz, ancak Altyapı veya Platform sürümü derleme süresi 60 günden eskidir. |
| **bilinmiyor (kullanılabilir veri yok)** | cihaz yedi günden uzun süredir rapor olayıyla ('İmza yenileme süresi') iletişim kurmadı. |

Güvenlik zekası için güncel tanımlar aşağıdadır:

| Güvenlik bilgileri güncelleştirmesi dikkate alınır | Eğer: |
|:---|:---|
|**Güncel** | cihazdaki güvenlik bilgileri sürümü son yedi gün içinde yazılmıştır ve cihaz son yedi gün içinde rapor olayıyla iletişim kurar. |

Daha fazla bilgi için bkz.:

- [Virüsten koruma altyapısı güncelleştirme kartı](#antivirus-engine-updates-card)
- [Güvenlik bilgileri güncelleştirme kartı](#security-intelligence-updates-card)
- [Virüsten koruma platformu güncelleştirme kartı](#antivirus-platform-updates-card)

##### <a name="antivirus-engine-updates-card"></a>Virüsten koruma altyapısı güncelleştirme kartı

Bu kart, virüsten koruma altyapısı sürümleri güncel ve güncel olmayan cihazları tanımlar.

**'_Güncel_' genel tanımı** - Cihazdaki altyapı sürümü en son altyapı sürümüdür. Altyapı _genellikle_ Windows Update (WU) aracılığıyla aylık olarak yayınlanır. Windows Update (WU) serbest bırakıldığında verilen üç günlük yetkisiz kullanım süresi vardır.

Aşağıdaki tabloda **Virüsten Koruma Altyapısı** için güncel raporlar için olası değerler yer alır. Bildirilen Durum, raporlama olayının son alındığı zamanı (_imza yenileme zamanı_) temel alır. Cihaz yedi günden uzun süredir raporlarla iletişim kurmadıysa (imza yenileme süresi >7 gün), durum otomatik olarak 'Bilinmiyor' / 'Kullanılabilir Veri Yok' olarak işaretlenir.

| Olayın Son Yenileme Zamanı (raporlarda "İmza Yenileme Zamanı" olarak da bilinir) | _Bildirilen Durum_: |
|:----|:----|
| < 7 gün (yeni) | hangi istemcinin rapor verdiği (_Güncel <br/> Olmayan <br/> Bilinmeyen)_ |
| > 7 gün (eski) | _Unknown_ |

Microsoft Defender Virüsten Koruma güncelleştirme sürümlerini yönetme hakkında bilgi için bkz.  [Aylık platform ve altyapı sürümleri](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

#### <a name="antivirus-platform-updates-card"></a>Virüsten koruma platformu güncelleştirme kartı

Bu kart, Virüsten Koruma platformu sürümlerinin güncel ve güncel olmayan cihazları tanımlar.

**'Güncel' genel tanımı** Cihazdaki platform sürümü en son platform sürümüdür. Platform _genellikle_ Windows Update (WU) aracılığıyla aylık olarak yayınlanır. WU'nun serbest bırakıldığından itibaren üç günlük yetkisiz kullanım süresi vardır.

Aşağıdaki tabloda **Virüsten Koruma Platformu** için olası güncel rapor değerleri yer almaktadır. Bildirilen değerler, raporlama olayının son alındığı zamanı (imza yenileme zamanı) temel alır. Cihaz raporlarla yedi günden fazla iletişim kurmadıysa (imza yenileme süresi >7 gün) otomatik olarak "Bilinmiyor"/ "Kullanılabilir Veri Yok" olarak işaretlenir.

| Olayın Son Yenileme Zamanı (raporlarda "İmza Yenileme Zamanı" olarak da bilinir) | _Bildirilen Durum_: |
|:----|:----|
| < 7 gün (yeni) | hangi istemcinin rapor verdiği (_Güncel <br/> Olmayan <br/> Bilinmeyen)_ |
| > 7 gün (eski) | _Unknown_ |

Microsoft Defender Virüsten Koruma güncelleştirme sürümlerini yönetme hakkında bilgi için bkz. [Aylık platform ve altyapı sürümleri](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

##### <a name="security-intelligence-updates-card"></a>Güvenlik bilgileri güncelleştirme kartı

Bu kart, güncel ve güncel olmayan güvenlik bilgileri sürümlerine sahip cihazları tanımlar.

**'Güncel' genel tanımı** – cihazdaki güvenlik zekası sürümü son 7 gün içinde yazılmıştır.

Aşağıdaki tabloda **Güvenlik Bilgileri** güncelleştirmeleri için olası güncel rapor değerleri yer alır. Bildirilen değerler raporlama olayının son alındığı zamanı ve güvenlik zekası yayımlama süresini temel alır. Cihaz yedi günden uzun süredir raporlarla iletişim kurmadıysa (imza yenileme süresi >7 gün), durum otomatik olarak 'Bilinmiyor/ Kullanılabilir Veri Yok' olarak işaretlenir. Aksi takdirde, güvenlik bilgileri yayımlama süresinin yedi gün içinde olup olmadığına bağlı olarak belirleme yapılır.

| Olayın Son Yenileme Zamanı <br/> (Raporlarda "İmza Yenileme Zamanı" olarak da bilinir) | Güvenlik Zekası Yayımlama Zamanı | _Bildirilen Durum_: |
|:----|:----|:----|
| >7 gün (eski) | >7 gün (eski) | _Unknown_ |
| <7 gün (yeni) | >7 gün (eski) | _Güncel değil_ |
| >7 gün (eski) | <7 gün (yeni) |  _Unknown_ |
| <7 gün (yeni) | <7 gün (yeni) | Modern |

## <a name="see-also"></a>Ayrıca bkz.

- [Cihaz virüsten koruma sistem durumu ayrıntılarını API yöntemleri ve özelliklerini dışarı aktarma](device-health-api-methods-properties.md)
- [Cihaz virüsten koruma sistem durumu raporunu dışarı aktarma](device-health-api-methods-properties.md)
- [Tehdit koruma raporu](threat-protection-reports.md)

> [!TIP]
> Diğer platformlar için virüsten korumayla ilgili bilgiler için bkz:
>
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)
