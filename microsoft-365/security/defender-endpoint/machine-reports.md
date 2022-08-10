---
title: Uç Nokta için Microsoft Defender'da cihaz durumu ve uyumluluk raporu
description: Cihaz durumunu, virüsten koruma durumunu ve sürümlerini, işletim sistemi platformlarını ve Windows 10 sürümlerini izlemek için cihaz durumu ve uyumluluk raporunu kullanın.
keywords: sistem durumu, virüsten koruma, işletim sistemi platformu, windows 10 sürümü, sürüm, sistem durumu, uyumluluk, durum
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
ms.date: 08/08/2022
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 00a43da0c6b817c6e53ef93ae27fa8e59d7c5341
ms.sourcegitcommit: 6bff75867764335685f972943170c7db46e33a6f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2022
ms.locfileid: "67300465"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender'da cihaz durumu ve uyumluluk raporu

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.
> _Ticari olarak yayınlanan_ özelliklerle ilgili bilgiler, [Genel kullanıma sunuldu: Uç Nokta için Microsoft Defender'da cihaz durumu ve uyumluluk raporu başlıklı bölümdeki](#publicly-released-device-health-and-compliance-report-in-microsoft-defender-for-endpoint) yayın öncesi bilgileri izler.

## <a name="public-preview---device-health-and-antivirus-compliance-report-in-microsoft-defender-for-endpoint"></a>Genel Önizleme - Uç Nokta için Microsoft Defender'de cihaz durumu ve virüsten koruma uyumluluk raporu

Cihazlar durum raporu, kuruluşunuzdaki cihazlar hakkında üst düzey bilgiler sağlar. Rapor algılayıcı durumunu, virüsten koruma durumunu, işletim sistemi platformlarını ve Windows 10 sürümlerini gösteren popüler bilgiler içerir.

> [!IMPORTANT]
> Windows&nbsp;Server&nbsp;2012&nbsp;R2 ve Windows&nbsp;Server&nbsp;2016'nın cihaz durumu raporlarında görünmesi için bu cihazların modern birleşik çözüm paketi kullanılarak eklenmesi gerekir. Daha fazla bilgi için bkz. [Windows Server 2012 R2 ve 2016 için modern birleşik çözümde yeni işlevler](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution).

Microsoft 365 Güvenlik panosu gezinti panelinde **Raporlar'ı** seçin ve ardından **Cihaz durumu ve uyumluluğu'nu** açın.
Cihaz durumu ve uyumluluk panosu iki sekmede yapılandırılmıştır:

- [**Algılayıcı sistem durumu & işletim** sistemi sekmesi](#sensor-health--os-tab), aşağıdaki cihaz özniteliklerini görüntüleyen üç karta ayrılmış genel işletim sistemi bilgileri sağlar:
  - [Algılayıcı sistem durumu kartı](#sensor-health-card)
  - [İşletim sistemleri ve platformlar kartı](#operating-systems-and-platforms-card)
  - [Windows 10 sürüm kartı](#windows-10-versions-card)

- [**Microsoft Defender Virüsten Koruma sistem durumu sekmesinde Microsoft**](#microsoft-defender-antivirus-health-tab) Defender Virüsten Koruma'nın özelliklerini bildiren sekiz kart vardır:
  - [Virüsten koruma modu kartı](#antivirus-mode-card)
  - [Virüsten koruma altyapısı sürüm kartı](#antivirus-engine-version-card)
  - [Virüsten koruma güvenlik bilgileri sürüm kartı](#antivirus-security-intelligence-version-card)
  - [Virüsten koruma platformu sürüm kartı](#antivirus-platform-version-card)
  - [En son virüsten koruma tarama sonuçları kartı](#recent-antivirus-scan-results-card)
  - [Virüsten koruma altyapısı güncelleştirme kartı](#antivirus-engine-updates-card)
  - [Güvenlik bilgileri güncelleştirme kartı](#security-intelligence-updates-card)
  - [Virüsten koruma platformu güncelleştirme kartı](#antivirus-platform-updates-card)

### <a name="sensor-health--os-tab"></a>Algılayıcı sistem durumu & işletim sistemi sekmesi

Algılayıcı durumu ve işletim sistemi kartları algılama algılayıcısı durumu, güncel ve güncel olmayan işletim sistemleri ve Windows 10 sürümleri içeren genel işletim sistemi durumu hakkında rapor sunar.

> [!div class="mx-imgBorder"]
> ![Algılayıcı sistem durumu ve İşletim sistemi bilgilerini gösterir. Virüsten koruma altyapısı, virüsten koruma güvenlik bilgileri, virüsten koruma platformu ayrıntıları içeren Microsoft Defender Virüsten Koruma sistem durumu sekmesi. ](images/device-health-sensor-health-os-tab.png)

**Algılayıcı sistem durumu** sekmesindeki üç kartın her birinde _geçerli durum_ ve _cihaz eğilimleri_ şeklinde grafik olarak sunulan iki raporlama bölümü vardır:

#### <a name="current-state-graph"></a>Geçerli durum grafiği

Her kartta Geçerli durum (bazı belgelerde _Cihaz özeti_ olarak adlandırılır) en üstteki yatay çubuk grafiktir. Geçerli durum, kuruluşunuzdaki cihazlar hakkında toplanan bilgileri gösteren ve kapsamı geçerli güne göre belirlenmiş bir anlık görüntüdür. Bu grafik, kuruluşunuz genelinde durum bildiren veya belirli bir durumda olduğu algılanan cihazların dağıtımını temsil eder.

> [!div class="mx-imgBorder"]
> ![Cihaz Durumu içindeki geçerli durum grafiğini gösterir](images/device-health-sensor-health-os-current-state-graph.png)

#### <a name="device-trends-graph"></a>Cihaz eğilimleri grafiği

Üç kartın her birinin alt grafiğinin adı yoktur, ancak genellikle _cihaz eğilimleri_ olarak bilinir. Cihaz eğilimleri grafiği, doğrudan grafiğin üzerinde belirtilen zaman aralığı boyunca kuruluşunuz genelindeki cihaz koleksiyonunu gösterir.
Varsayılan olarak, cihaz eğilimleri grafiği 30 günlük dönemdeki cihaz bilgilerini görüntüler ve en son tam gün ile biter. Kuruluşunuzda gerçekleşen eğilimler hakkında daha iyi bir bakış açısı elde etmek için, gösterilen zaman aralığını ayarlayarak raporlama dönemine ince ayar yapabilirsiniz. Zaman aralığını ayarlamak için filtreyi açın ve bir başlangıç günü ile bitiş günü seçin.

> [!div class="mx-imgBorder"]
> ![Cihaz Durumu sürüm eğilimlerini gösterir](images/device-health-sensor-health-os-device-trends-graph.png)

#### <a name="filtering-data"></a>Verileri filtreleme

Belirli özniteliklere sahip cihazları dahil etmek veya hariç tutmak için sağlanan filtreleri kullanın. Cihaz özniteliklerinden uygulanacak birden çok filtre seçebilirsiniz. Filtreler uygulandığında rapordaki üç karta da uygulanır.

Örneğin, Etkin algılayıcı sistem durumu olan Windows 10 cihazlar hakkındaki verileri göstermek için:

1. **Filtreler** > **Algılayıcı sistem durumu Etkin altında** > .
2. Ardından **işletim sistemi platformları** >  **Windows 10'ni** seçin.
3. **Uygula'yı** seçin.

#### <a name="sensor-health-card"></a>Algılayıcı sistem durumu kartı

Algılayıcı sistem durumu kartı, cihazlardaki algılayıcı durumu hakkında bilgi görüntüler. Algılayıcı durumu, şu cihazların toplam görünümünü sağlar:

- Etkin
- Etkin olmayan
- sorun yaşayan iletişimler
- veya algılayıcı verilerinin bildirildiği yerler

İletişim bozukluğu yaşayan cihazlar veya algılayıcı verilerinin algılanmadığı cihazlar kuruluşunuzu risklere maruz kalabilir ve araştırmayı garanti edebilir. Benzer şekilde, uzun süre etkin olmayan cihazlar, güncel olmayan yazılımlar nedeniyle kuruluşunuzu tehditlere maruz bırakabilir. Uzun süre etkin olmayan cihazlar da araştırmayı garanti eder.

#### <a name="operating-systems-and-platforms-card"></a>İşletim sistemleri ve platformlar kartı

Bu kart, kuruluşunuzda bulunan işletim sistemlerinin ve platformların dağılımını gösterir.
_İşletim sistemi sistemleri ve platformları_ , kuruluşunuzdaki cihazların güncel veya güncel olmayan işletim sistemlerini çalıştırıp çalıştırmadığına ilişkin yararlı içgörüler sağlayabilir. Yeni işletim sistemleri kullanıma sunulduğunda, kuruluşunuzun güvenlik tehditlerine karşı duruşunu geliştiren güvenlik geliştirmeleri sık sık eklenir.

Örneğin, Windows 8'de sunulan Güvenli Önyükleme, en zararlı kötü amaçlı yazılım türlerinden bazılarının tehdidini neredeyse ortadan kaldırdı. Windows 10 geliştirmeleri, bilgisayar üreticilerine kullanıcıların Güvenli Önyükleme özelliğini devre dışı bırakmasını önleme seçeneği sağlar. Kullanıcıların Güvenli Önyükleme özelliğini devre dışı bırakmasını engellemek, kötü amaçlı rootkit'lerin veya diğer düşük düzeyli kötü amaçlı yazılımların önyükleme işlemine bulaşma olasılığını ortadan kaldırır.
İdeal olarak, "Geçerli durum" grafiği, işletim sistemi sayısının eski sürümlere göre daha güncel işletim sistemi lehine ağırlıklı olduğunu gösterir.  Aksi takdirde eğilim grafiği yeni sistemlerin benimsendiğini ve/veya eski sistemlerin güncelleştirildiğini veya değiştirildiğini gösterir.

#### <a name="windows-10-versions-card"></a>Windows 10 sürüm kartı

Kart, Windows cihazlarının ve bunların kuruluşunuzdaki sürümlerinin dağıtımını gösterir.
Windows 8'den Windows 10'ye yükseltmenin kuruluşunuzda güvenliği geliştirmesi gibi, Windows'un erken sürümlerinden daha güncel sürümlere geçmek olası tehditlere karşı duruşunuzu geliştirir.

Windows sürümü eğilim grafiği, Windows 10 en son ve en güvenli sürümlerine güncelleştirerek kuruluşunuzun güncel olup olmadığını hızla belirlemenize yardımcı olabilir.

### <a name="microsoft-defender-antivirus-health-tab"></a>Microsoft Defender Virüsten Koruma sistem durumu sekmesi  

Microsoft Defender Virüsten Koruma sistem durumu sekmesi, kuruluşunuzdaki Microsoft Defender Virüsten Koruma'nın çeşitli yönlerini bildiren sekiz kart içerir:

İki kart, [Virüsten koruma modu kartı](#antivirus-mode-card) ve [En son virüsten koruma tarama sonuçları kartı](#recent-antivirus-scan-results-card), Microsoft Defender Virüsten Koruma işlevleri hakkında rapor sağlar.

Kalan altı kart, kuruluşunuzdaki cihazlar için Microsoft Defender Virüsten Koruma durumu hakkında rapor verir:

| _sürüm_ kartları: | _güncelleştirme_ kartları{<a id="fn1">1</a>} |
|:---|:---|
| [Virüsten koruma altyapısı sürüm kartı](#antivirus-engine-version-card) <br> [Virüsten koruma güvenlik bilgileri sürüm kartı](#antivirus-security-intelligence-version-card) <br> [Virüsten koruma platformu sürüm kartı](#antivirus-platform-version-card) | [Virüsten koruma altyapısı güncelleştirme kartı](#antivirus-engine-updates-card) <br> [Güvenlik bilgileri güncelleştirme kartı](#security-intelligence-updates-card) <br> [Virüsten koruma platformu güncelleştirme kartı](#antivirus-platform-updates-card) |
| Üç güncelleştirme kartı daha fazla bilgi edinmek için ek kaynaklara bağlantılar sağlar. | Üç sürüm kartı, ek bilgi sağlayan ve daha fazla incelemeye olanak tanıyan açılır raporlar sağlar. |

<sup>{[1](#fn1)}</sup> Üç _güncelleştirme_ kartı için "**Kullanılabilir veri yok**" ifadesi, güncelleştirme durumunu raporlamamış cihazları gösterir. Güncelleştirme durumunu bildirmemeyen cihazlar çeşitli nedenlerden kaynaklanabilir, örneğin:

- Bilgisayarın ağ bağlantısı kesildi
- Bilgisayar kapatıldı veya hazırda bekleme durumunda
- Microsoft Defender Virüsten Koruma devre dışı bırakıldı
- Cihaz Windows olmayan (Mac veya Linux) bir cihazdır
- Bulut koruması etkin değil

> [!NOTE]
> Şu anda "Güncel" raporlama yalnızca Windows cihazları için kullanılabilir.  Güncel raporlama, bulut koruması etkinleştirilmiş ve altyapı sürümü 1.1.19300.2 ve daha yeni olan Windows cihazları hakkında bilgi oluşturur. Mac ve Linux gibi platformlar arası cihazlar "kullanılabilir veri yok" altında listelenir.

> [!div class="mx-imgBorder"]
> ![Microsoft Defender Virüsten Koruma sistem durumu sekmesini gösterir](images/device-health-defender-antivirus-health-tab.png)

#### <a name="card-functionality"></a>Kart işlevselliği

İşlevsellik temelde tüm kartlar için aynıdır. Herhangi bir karttaki numaralandırılmış çıtaya tıklayarak **Microsoft Defender Virüsten Koruma ayrıntıları** açılır öğesi açılır ve bu karttaki bir yönün sürüm numarasıyla yapılandırılan tüm cihazlar hakkındaki bilgileri gözden geçirmenizi sağlar.

> [!div class="mx-imgBorder"]
> ![Microsoft Defender Virüsten Koruma sistem durumu ayrıntılarını gösterir](images/device-health-defender-antivirus-health-antivirus-details.png)

Tıkladığınız sürüm numarası şuysa:

- Geçerli bir sürüm, ardından **Düzeltme gerekli** ve **Güvenlik önerisi** yok
- Güncel olmayan bir sürüm, raporun üst kısmında **Düzeltme gerektiğini** belirten bir bildirim bulunur ve **bir Güvenlik önerisi** bağlantısı bulunur. Uygun virüsten koruma güncelleştirmelerini önerebilen Tehdit ve Güvenlik Açığı Yönetimi konsoluna gitmek için güvenlik önerisi bağlantısını seçin.

**Microsoft Defender Virüsten Koruma ayrıntıları** açılır öğesinde belirli türlerdeki bilgileri eklemek veya kaldırmak için **Sütunları Özelleştir'e** tıklayın. **Sütunları Özelleştir** bölümünde, Microsoft Defender Virüsten Koruma ayrıntıları raporuna eklenmesini istediklerinizi belirtmek için öğeleri seçin veya temizleyin.

> [!div class="mx-imgBorder"]
> ![Microsoft Defender Virüsten Koruma sistem durumu raporlaması için özel sütun seçeneklerini gösterir](images/device-health-defender-antivirus-engine-version-details-custom-columns.png)

Açılır listede: Cihazın adına tıkladığınızda, ayrıntılı raporlara erişebileceğiniz bu cihazın "Cihaz sayfası"na yönlendirilirsiniz.

Raporu Excel elektronik tablosuna aktarmak için _Microsoft Defender Virüsten Koruma ayrıntıları_ açılır öğesindeki **Dışarı Aktar** düğmesini kullanabilirsiniz. Dışarı aktarılan raporlar, ayrıntılar raporuna giriş noktanızı ve hangi filtreleri veya özelleştirilmiş sütunları ayarladığınızı temel alarak bilgileri yakalar.

API kullanarak dışarı aktarma hakkında ek bilgi için aşağıdaki makalelere bakın:

- [Cihaz virüsten koruma sistem durumu raporunu dışarı aktarma](device-health-export-antivirus-health-report-api.md)
- [Cihaz virüsten koruma sistem durumu ayrıntılarını API yöntemleri ve özelliklerini dışarı aktarma](device-health-api-methods-properties.md)

#### <a name="microsoft-defender-antivirus-version-and-update-cards-functionality"></a>Microsoft Defender Virüsten Koruma sürümü ve güncelleştirme kartları işlevselliği

Microsoft Defender Virüsten Koruma altyapısı, güvenlik bilgileri ve platform bileşenleri için _sürüm_ ve _güncelleştirme_ bilgileri hakkında rapor veren altı kartın açıklamaları aşağıdadır:

##### <a name="full-report"></a>Tam rapor

Üç _sürüm_ kartından herhangi birinde **Tam raporu görüntüle'ye** tıklayarak üç cihaz türünün her biri için en son dokuz Microsoft Defender Virüsten Koruma _sürümü_ raporunu görüntüleyin: Windows, Mac ve Linux; dokuzdan az varsa, hepsi gösterilir. **Diğer** kategorisi, algılanırsa onuncu ve altındaki en son virüsten koruma altyapısı sürümlerini yakalar.

> [!div class="mx-imgBorder"]
> ![Her türden ilk dokuz işletim sisteminin dağılımını gösterir](images/device-health-defender-antivirus-health-view-full-report.png)

Üç _sürüm_ kartının birincil avantajlarından biri, virüsten koruma motorlarının, platformlarının ve güvenlik zekasının en güncel sürümlerinin kullanılıp kullanılmadığına ilişkin hızlı göstergeler sağlamasıdır. Sürüm kartları, karta bağlı ayrıntılı bilgilerle birlikte sürümlerin güncel olup olmadığını denetlemek ve tek tek bilgisayarlar veya bilgisayar grupları hakkında bilgi toplamak için güçlü bir araç haline gelir.
İdeal olarak, bu raporları çalıştırdığınızda, eski sürümlerin aksine en güncel virüsten koruma sürümlerinin yüklü olduğunu gösterirler.
Kuruluşunuzun en güncel sürümlerden tam olarak yararlanıp yararlanmadığını belirlemek için bu raporları kullanın.

> [!div class="mx-imgBorder"]
> ![Microsoft Defender Virüsten Koruma sürüm ayrıntılarını gösterir](images/device-health-defender-antivirus-health-antivirus-details-up-to-date.png)

Kötü amaçlı yazılımdan koruma çözümünüzün en son tehditleri algılamasına yardımcı olmak için güncelleştirmeleri Windows Update bir parçası olarak otomatik olarak alın.

Geçerli sürümler ve farklı Microsoft Defender Virüsten Koruma bileşenlerini güncelleştirme hakkında daha fazla bilgi için [Microsoft Defender Virüsten Koruma platformu desteği](manage-updates-baselines-microsoft-defender-antivirus.md) sayfasını ziyaret edin.

#### <a name="card-descriptions"></a>Kart açıklamaları

_Virüsten Koruma sürüm_ kartlarının her birinde bildirilen toplanan bilgilerin kısa özetleri aşağıdadır:

##### <a name="antivirus-mode-card"></a>Virüsten koruma modu kartı

Kuruluşunuzdaki kaç cihazın (kartta belirtilen tarihte) aşağıdaki Microsoft Defender Virüsten Koruma modlarından birinde olduğunu bildirir:

| Değer | Modu |
|---|---|
| 0 | Etkin |
| 1 | Pasif |
| 2 | Devre dışı (kaldırıldı, devre dışı veya SideBySidePassive {Düşük Düzenli Tarama olarak da bilinir}) |
| 3 | Diğerleri (Çalışmıyor, Bilinmiyor) |
| 4 | EDRBlocked |

> [!div class="mx-imgBorder"]
> ![Microsoft Defender Virüsten Koruma modlarını filtrelemeyi gösterir](images/device-health-defender-antivirus-health-antivirus-mode.png)

Her modun açıklamaları aşağıdadır:

- **Etkin** mod - Etkin modda Microsoft Defender Virüsten Koruma, cihazda birincil virüsten koruma uygulaması olarak kullanılır. Dosyalar taranır, tehditler düzeltilir ve algılanan tehditler, kuruluşunuzun güvenlik raporlarında ve Windows Güvenliği uygulamanıza listelenir.
- **Pasif** mod - Pasif modda Microsoft Defender Virüsten Koruma, cihazda birincil virüsten koruma uygulaması olarak kullanılmaz. Dosyalar taranır ve algılanan tehditler bildirilir, ancak tehditler Microsoft Defender Virüsten Koruma tarafından düzeltilmemiştir. ÖNEMLİ: Microsoft Defender Virüsten Koruma, pasif modda sadece Uç Nokta için Microsoft Defender’a eklenmiş uç noktalarda çalıştırılabilir. [Microsoft Defender Virüsten Koruma’nın pasif modda çalıştırılması için gereksinimlere](microsoft-defender-antivirus-compatibility.md#requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode) bakın.
- **Devre dışı** modu - ile eş anlamlı: kaldırıldı, devre dışı, sideBySidePassive ve Düşük Düzenli Tarama. Devre dışı bırakıldığında Microsoft Defender Virüsten Koruma kullanılmaz. Dosyalar taranmıyor ve tehditler düzeltilmemiş. Genel olarak, Microsoft, Microsoft Defender Virüsten Koruma'yı devre dışı bırakmanızı veya kaldırmanızı önermez.
- **Diğer** modu - Çalışmıyor, Bilinmiyor
- **Blok modunda EDR** - Uç nokta algılama ve yanıt (EDR) engellenmiş modunda. Bkz [. Blok modunda uç nokta algılama ve yanıt](edr-in-block-mode.md)

Pasif, LPS veya Kapalı olan cihazlar olası bir güvenlik riski sunar ve araştırılmalıdır.

LPS hakkında ayrıntılı bilgi için bkz. [Microsoft Defender Virüsten Koruma'da sınırlı düzenli tarama kullanma](limited-periodic-scanning-microsoft-defender-antivirus.md).

##### <a name="recent-antivirus-scan-results-card"></a>En son virüsten koruma tarama sonuçları kartı

Bu kartta hızlı taramalar ve tam taramalar için tüm sonuçları gösteren iki çubuk grafik vardır. Her iki grafikte de ilk çubuk taramaların tamamlanma hızını gösterir ve **Tamamlandı**, **İptal Edildi** veya **Başarısız'ı** gösterir. Her bölümdeki ikinci çubuk, başarısız taramalar için hata kodları sağlar.
**Mod** ve **Son tarama sonuçları** sütunlarını tarayarak etkin virüsten koruma tarama modunda olmayan cihazları ve son virüsten koruma taramalarını başarısız olan veya iptal eden cihazları hızla belirleyebilirsiniz. Bu bilgilerle rapora dönebilir, daha fazla ayrıntı ve güvenlik önerileri toplayabilirsiniz. Bu kartta herhangi bir hata kodu bildirilirse, hata kodları hakkında daha fazla bilgi edinmek için bir bağlantı olacaktır.

Geçerli Microsoft Defender Virüsten Koruma sürümleri ve farklı Microsoft Defender Virüsten Koruma bileşenlerini güncelleştirme hakkında daha fazla bilgi için [Microsoft Defender Virüsten Koruma güncelleştirmelerini yönetme ve temelleri uygulama](manage-updates-baselines-microsoft-defender-antivirus.md) sayfasını ziyaret edin.

##### <a name="antivirus-engine-version-card"></a>Virüsten koruma altyapısı sürüm kartı

Kuruluşunuzdaki Windows Cihazları, Mac cihazları ve Linux cihazları arasında yüklü olan en güncel Microsoft Defender Virüsten Koruma altyapısı sürümlerinin gerçek zamanlı sonuçlarını gösterir. Microsoft Defender Virüsten Koruma altyapısı aylık olarak güncelleştirilir.
Geçerli sürümler ve farklı Microsoft Defender Virüsten Koruma bileşenlerini güncelleştirme hakkında daha fazla bilgi için bkz. [Microsoft Defender Virüsten Koruma platformu desteği](manage-updates-baselines-microsoft-defender-antivirus.md).

##### <a name="antivirus-security-intelligence-version-card"></a>Virüsten koruma güvenlik bilgileri sürüm kartı

Ağınızdaki cihazlarda yüklü en yaygın _Microsoft Defender Virüsten Koruma güvenlik zekası_ sürümlerini listeler.
Microsoft, en son tehditleri ele almak ve algılama mantığını geliştirmek için Microsoft Defender güvenlik zekasını sürekli olarak güncelleştirir. Güvenlik zekasına yönelik bu iyileştirmeler, Olası tehditleri doğru bir şekilde tanımlamak için Microsoft Defender Virüsten Koruma'nın (ve diğer Microsoft kötü amaçlı yazılımdan koruma çözümlerinin) özelliğini geliştirir. Bu güvenlik zekası, hızlı ve güçlü yapay zeka destekli yeni nesil koruma sağlamak için doğrudan bulut tabanlı koruma ile çalışır.

##### <a name="antivirus-platform-version-card"></a>Virüsten koruma platformu sürüm kartı

Kuruluşunuzdaki Windows, Mac ve Linux cihazlarında yüklü olan en güncel Microsoft Defender Virüsten Koruma platformu sürümlerinin gerçek zamanlı sonuçlarını gösterir. Microsoft Defender Virüsten Koruma platformu aylık olarak güncelleştirilir.
Geçerli sürümler ve farklı Microsoft Defender Virüsten Koruma bileşenlerini güncelleştirme hakkında daha fazla bilgi için bkz. [Microsoft Defender Virüsten Koruma platformu desteği](manage-updates-baselines-microsoft-defender-antivirus.md)

##### <a name="antivirus-engine-updates-card"></a>Virüsten koruma altyapısı güncelleştirme kartı

Bu kart, virüsten koruma altyapısı sürümleri güncel ve güncel olmayan cihazları tanımlar.
'_Güncel_' genel tanımı: Cihazdaki altyapı sürümü en son altyapı sürümüdür {Motor genellikle Windows Update (WU)} aracılığıyla aylık olarak yayınlanır.  WU'nun serbest bırakıldığından itibaren üç günlük yetkisiz kullanım süresi vardır.

| Microsoft, **Virüsten Koruma altyapısı güncelleştirmelerine** sahip cihazları dikkate alır:  |  olmak için:  |
|:----|:----|
| Son 7 gün içinde son 7 gün içinde İmza Yayımlama süresi ile Defender'a iletildi ve son 60 gün _içinde_ Altyapı veya Platform sürümü derleme _süresine sahip_   | Güncel  |
| Son 7 gün içinde Son 7 gün içinde İmza Yayımlama süresiyle Defender'a iletildi ancak Altyapı veya Platform sürümü derleme süresi 60 günden _eski_ | Güncel  |
| Son 7 gün içinde İmza Yayımlama süresi günden _uzun bir_  süreyle Defender'a iletildi  | Kullanılabilir veri yok  |
| Son 7 gün içinde Defender'a iletilmiyor ve son durumu "Güncel"  | Kullanılabilir veri yok  |
| Son 7 gün içinde Defender'a iletilmiyor ve son durumu "Güncel değil"  | Kullanılabilir veri yok |

##### <a name="security-intelligence-updates-card"></a>Güvenlik bilgileri güncelleştirme kartı

Bu kart, güncel ve güncel olmayan güvenlik bilgileri sürümlerine sahip cihazları tanımlar.
'**Güncel**' genel tanımı – cihazdaki güvenlik zekası sürümü son 7 gün içinde yazılmıştır.

| Microsoft, **Güvenlik Zekası güncelleştirmelerine** sahip cihazları dikkate alır:  | olmak için:  |
|:----|:----|
|  Son 7 gün içinde yazılmış bir güvenlik zekası sürümü | Güncel  |
| Son 7 gün içinde İmza Yayımlama süresiyle Son 7 gün içinde Defender'a iletildi | Güncel  |
| Son 7 gün içinde Defender'a İmza Yayımlama süresi son 7 günden uzun bir süreyle iletildi | Güncel |
| Son 7 gün içinde Defender'a iletilmiyor ve son durumu "Güncel"  |  Kullanılabilir veri yok  |
| Son 7 gün içinde Defender ile iletişim kurmadı ve son durumu güncel değil  | Güncel |

##### <a name="antivirus-platform-updates-card"></a>Virüsten koruma platformu güncelleştirme kartı

Bu kart, Virüsten Koruma platformu sürümlerinin güncel ve güncel olmayan cihazları tanımlar.
'_Güncel_' genel tanımı – cihazdaki platform sürümü en son platform sürümüdür (Platform genellikle Windows Update aracılığıyla aylık olarak yayınlanır).  WU'nun serbest bırakıldığından itibaren üç günlük yetkisiz kullanım süresi vardır.

| Microsoft, **Virüsten Koruma platformu güncelleştirmelerine** sahip cihazları dikkate alır:  |  olmak için:  |
|:----|:----|
| Son 7 gün içinde son 7 gün içinde İmza Yayımlama süresi ile Defender'a iletildi ve son 60 gün _içinde_ Altyapı veya Platform sürümü derleme _süresine sahip_   | Güncel  |
| Son 7 gün içinde Son 7 gün içinde İmza Yayımlama süresiyle Defender'a iletildi ancak Altyapı veya Platform sürümü derleme süresi 60 günden _eski_ | Güncel  |
| Son 7 gün içinde İmza Yayımlama süresi günden _uzun bir_  süreyle Defender'a iletildi  | Kullanılabilir veri yok  |
| Son 7 gün içinde Defender'a iletilmiyor ve son durumu "Güncel"  | Kullanılabilir veri yok  |
| Son 7 gün içinde Defender'a iletilmiyor ve son durumu "Güncel değil"  | Kullanılabilir veri yok |

Microsoft Defender Virüsten Koruma güncelleştirme sürümlerini yönetme hakkında bilgi için bkz. [Aylık platform ve altyapı sürümleri](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

### <a name="see-also"></a>Ayrıca bkz.

- [Cihaz virüsten koruma sistem durumu ayrıntılarını API yöntemleri ve özelliklerini dışarı aktarma](device-health-api-methods-properties.md)
- [Device-health-export-antivirus-health-report-api.md](device-health-api-methods-properties.md)
- [Tehdit koruma raporu](threat-protection-reports.md)

## <a name="publicly-released-device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a>Genel kullanıma sunuldu: Uç Nokta için Microsoft Defender'de cihaz durumu ve uyumluluk raporu

Cihaz durumu raporu, kuruluşunuzdaki cihazlar hakkında üst düzey bilgiler sağlar. Rapor algılayıcı durumunu, virüsten koruma durumunu, işletim sistemi platformlarını ve Windows 10 sürümlerini gösteren popüler bilgiler içerir.

Pano iki bölümde yapılandırılmıştır:

![Cihaz raporunun görüntüsü.](images/device-reports.png)

|Bölüm|Açıklama|
|---|---|
|1|Cihaz eğilimleri|
|2|Cihaz özeti (geçerli gün)|

### <a name="device-trends"></a>Cihaz eğilimleri

Varsayılan olarak, cihaz eğilimleri grafiği en son tam gün ile biten 30 günlük dönemdeki cihaz bilgilerini görüntüler. Kuruluşunuzda gerçekleşen eğilimlere daha iyi bir bakış açısı elde etmek için, gösterilen zaman aralığını ayarlayarak raporlama dönemine ince ayar yapabilirsiniz. Zaman aralığını ayarlamak için açılan seçeneklerden bir zaman aralığı seçin:

- 30 gün
- Üç ay
- Altı ay
- Özel

> [!NOTE]
> Bu filtreler yalnızca cihaz eğilimleri bölümüne uygulanır. Cihaz özeti bölümünü etkilemez.

### <a name="device-summary"></a>Cihaz özeti

Cihaz eğilimleri grafiğinden farklı olarak, cihaz özet grafiğinde cihaz bilgilerinin kapsamı geçerli güne göre belirlenmiş olarak gösterilir.

> [!NOTE]
> Özet bölümüne yansıtılan verilerin kapsamı geçerli tarihten 180 gün öncesine kadar belirlenmiştir. Örneğin bugünün tarihi 27 Mart 2019 ise, özet bölümündeki veriler 28 Eylül 2018 ile 27 Mart 2019 arasında başlayan sayıları yansıtır.
> Eğilimler bölümüne uygulanan filtre özet bölümüne uygulanmaz.

Cihaz eğilimleri bölümü, ilgili filtrenin uygulandığı cihazlar listesinde detaya gitmenizi sağlar. Örneğin, Algılayıcı sistem durumu kartındaki Etkin Değil çubuğuna tıklandığında, yalnızca algılayıcı durumu etkin olmayan cihazları gösteren sonuçların yer aldığı cihazlar listesi görüntülenir.

### <a name="device-attributes"></a>Cihaz öznitelikleri

Rapor, aşağıdaki cihaz özniteliklerini görüntüleyen kartlardan oluşur:

- **Sistem durumu**: Cihazlardaki algılayıcı durumu hakkındaki bilgileri gösterir. Bu grafik, etkin olmayan, iletişim bozukluğu yaşayan, etkin olmayan veya algılayıcı verilerinin görülmediği cihazların tamamen görünümünü sağlar.
- **Etkin Windows 10 cihazları için virüsten koruma durumu**: Cihaz sayısını ve Microsoft Defender Virüsten Koruma'nın durumunu gösterir.
- **İşletim sistemi platformları**: Kuruluşunuzda var olan işletim sistemi platformlarının dağıtımını gösterir.
- **Windows 10 sürümleri**: Windows 10 cihazların ve bunların kuruluşunuzdaki sürümlerinin dağıtımını gösterir.

### <a name="filter-data"></a>Verileri filtreleme

Belirli özniteliklere sahip cihazları dahil etmek veya hariç tutmak için sağlanan filtreleri kullanın.

Cihaz özniteliklerinden uygulanacak birden çok filtre seçebilirsiniz.

> [!NOTE]
> Bu filtreler rapordaki **tüm** kartlar için geçerlidir.

Örneğin, Etkin algılayıcı sistem durumu olan Windows 10 cihazlar hakkındaki verileri göstermek için:

1. **Filtreler > Algılayıcı sistem durumu > Etkin** altında.
2. Ardından **> Windows 10 işletim sistemi platformlarını** seçin.
3. **Uygula'yı** seçin.

### <a name="related-articles"></a>İlgili makaleler

- [Tehdit koruma raporu](threat-protection-reports.md)

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)
