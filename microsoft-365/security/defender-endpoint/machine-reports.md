---
title: Uç Nokta için Microsoft Defender'da cihaz durumu raporu
description: Cihaz durumunu, virüsten koruma durumunu ve sürümlerini, işletim sistemi platformlarını ve Windows 10 sürümlerini izlemek için cihaz durumu raporunu kullanın.
keywords: sistem durumu, virüsten koruma, işletim sistemi platformu, windows 10 sürümü, sürüm, sistem durumu, uyumluluk, durum
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
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.reviewer: mkaminska
ms.openlocfilehash: a3ae7658ecfab9b0c92be3f75a3aa24ed2dfb7a8
ms.sourcegitcommit: 02a9c7f915d3a795a373b62dbdee2925966703f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2022
ms.locfileid: "67623735"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender'da cihaz durumu ve uyumluluk raporu

**Şunlar için geçerlidir:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Uç Nokta için Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [İş için Microsoft Defender](../defender-business/mdb-overview.md)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Cihaz Durumu raporu, kuruluşunuzdaki cihazlar hakkında üst düzey bilgiler sağlar. Rapor algılayıcı durumunu, virüsten koruma durumunu, işletim sistemi platformlarını, Windows 10 sürümlerini ve Microsoft Defender Virüsten Koruma güncelleştirme sürümlerini gösteren popüler bilgileri içerir.

> [!IMPORTANT]
> Windows&nbsp;Server&nbsp;2012&nbsp;R2 ve Windows&nbsp;Server&nbsp;2016'nın cihaz durumu raporlarında görünmesi için bu cihazların modern birleşik çözüm paketi kullanılarak eklenmesi gerekir. Daha fazla bilgi için bkz. [Windows Server 2012 R2 ve 2016 için modern birleşik çözümde yeni işlevler](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution).

Microsoft 365 Güvenlik panosu gezinti panelinde **Raporlar'ı** seçin ve ardından **Cihaz durumu ve uyumluluğu'nu** açın.
Cihaz durumu ve uyumluluk panosu iki sekmede yapılandırılmıştır:

- [**Algılayıcı sistem durumu & işletim** sistemi sekmesi](#sensor-health--os-tab), aşağıdaki cihaz özniteliklerini görüntüleyen üç karta ayrılmış genel işletim sistemi bilgileri sağlar:
  - [Algılayıcı sistem durumu kartı](#sensor-health-card)
  - [İşletim sistemleri ve platformlar kartı](#operating-systems-and-platforms-card)
  - [Windows sürümleri kartı](#windows-versions-card)

- [**Microsoft Defender Virüsten Koruma sistem durumu sekmesinde,**](#microsoft-defender-antivirus-health-tab) Microsoft Defender Virüsten Koruma'nın (MDAV) özelliklerini bildiren sekiz kart vardır:
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

## <a name="sensor-health--os-tab"></a>Algılayıcı sistem durumu & işletim sistemi sekmesi

Algılayıcı durumu ve işletim sistemi kartları algılama algılayıcısı durumu, güncel ve güncel olmayan işletim sistemleri ve Windows 10 sürümleri içeren genel işletim sistemi durumu hakkında rapor sunar.

>:::image type="content" source="images/device-health-sensor-health-os-tab.png" alt-text="Algılayıcı sistem durumu ve İşletim sistemi bilgilerini gösterir." lightbox="images/device-health-sensor-health-os-tab.png":::

**Algılayıcı sistem durumu** sekmesindeki üç kartın her birinde _geçerli durum_ ve _cihaz eğilimleri_ şeklinde grafik olarak sunulan iki raporlama bölümü vardır:

### <a name="current-state-graph"></a>Geçerli durum grafiği

Her kartta Geçerli durum (bazı belgelerde _Cihaz özeti_ olarak adlandırılır) en üstteki yatay çubuk grafiktir. Geçerli durum, kuruluşunuzdaki cihazlar hakkında toplanan bilgileri gösteren ve kapsamı geçerli güne göre belirlenmiş bir anlık görüntüdür. Bu grafik, kuruluşunuz genelinde durum bildiren veya belirli bir durumda olduğu algılanan cihazların dağıtımını temsil eder.

>:::image type="content" source="images/device-health-sensor-health-os-current-state-graph.png" alt-text="Geçerli durum grafiğini gösterir." lightbox="images/device-health-sensor-health-os-current-state-graph.png":::

### <a name="device-trends-graph"></a>Cihaz eğilimleri grafiği

Üç kartın her birinin alt grafiğinin adı yoktur, ancak genellikle _cihaz eğilimleri_ olarak bilinir. Cihaz eğilimleri grafiği, doğrudan grafiğin üzerinde belirtilen zaman aralığı boyunca kuruluşunuz genelindeki cihaz koleksiyonunu gösterir.
Varsayılan olarak, cihaz eğilimleri grafiği 30 günlük dönemdeki cihaz bilgilerini görüntüler ve en son tam gün ile biter. Kuruluşunuzda gerçekleşen eğilimler hakkında daha iyi bir bakış açısı elde etmek için, gösterilen zaman aralığını ayarlayarak raporlama dönemine ince ayar yapabilirsiniz. Zaman aralığını ayarlamak için filtreyi açın ve bir başlangıç günü ile bitiş günü seçin.

>:::image type="content" source="images/device-health-sensor-health-os-device-trends-graph.png" alt-text="Cihaz Durumu sürüm eğilimleri grafiğini gösterir." lightbox="images/device-health-sensor-health-os-device-trends-graph.png":::

### <a name="filtering-data"></a>Verileri filtreleme

Belirli özniteliklere sahip cihazları dahil etmek veya hariç tutmak için sağlanan filtreleri kullanın. Cihaz özniteliklerinden uygulanacak birden çok filtre seçebilirsiniz. Filtreler uygulandığında rapordaki üç karta da uygulanır.

Örneğin, Etkin algılayıcı sistem durumu olan Windows 10 cihazlar hakkındaki verileri göstermek için:

1. **Filtreler** > **Algılayıcı sistem durumu Etkin altında** > .
2. Ardından **işletim sistemi platformları** >  **Windows 10'ni** seçin.
3. **Uygula'yı** seçin.

### <a name="sensor-health-card"></a>Algılayıcı sistem durumu kartı

Algılayıcı sistem durumu kartı, cihazlardaki algılayıcı durumu hakkında bilgi görüntüler. Algılayıcı durumu, şu cihazların toplam görünümünü sağlar:

- Etkin
- Etkin olmayan
- sorun yaşayan iletişimler
- veya algılayıcı verilerinin bildirildiği yerler

İletişim bozukluğu yaşayan cihazlar veya algılayıcı verilerinin algılanmadığı cihazlar kuruluşunuzu risklere maruz kalabilir ve araştırmayı garanti edebilir. Benzer şekilde, uzun süre etkin olmayan cihazlar, güncel olmayan yazılımlar nedeniyle kuruluşunuzu tehditlere maruz bırakabilir. Uzun süre etkin olmayan cihazlar da araştırmayı garanti eder.

> [!NOTE]
>
> Vakaların küçük bir bölümünde, yatay Algılayıcı sistem durumu çubuğu grafiğine tıklandığında bildirilen sayılar ve dağılımlar **, Cihaz envanteri** sayfasında gösterilen değerlerle eşitlenmez. Algılayıcı Sistem Durumu Raporları Cihaz Envanteri sayfasından farklı bir yenileme temposunda olduğundan değerlerdeki eşitsizlik oluşabilir.

### <a name="operating-systems-and-platforms-card"></a>İşletim sistemleri ve platformlar kartı

Bu kart, kuruluşunuzda bulunan işletim sistemlerinin ve platformların dağılımını gösterir.
_İşletim sistemi sistemleri ve platformları_ , kuruluşunuzdaki cihazların güncel veya güncel olmayan işletim sistemlerini çalıştırıp çalıştırmadığına ilişkin yararlı içgörüler sağlayabilir. Yeni işletim sistemleri kullanıma sunulduğunda, kuruluşunuzun güvenlik tehditlerine karşı duruşunu geliştiren güvenlik geliştirmeleri sık sık eklenir.

Örneğin, Güvenli Önyükleme (Windows 8'de tanıtılan), en zararlı kötü amaçlı yazılım türlerinden gelen tehdidi neredeyse ortadan kaldırdı. Windows 10 geliştirmeleri, bilgisayar üreticilerine kullanıcıların Güvenli Önyükleme'yi devre dışı bırakmasını önleme seçeneği sağlar. Kullanıcıların Güvenli Önyükleme'yi devre dışı bırakmasını önlemek, kötü amaçlı rootkit'lerin veya diğer düşük düzeyli kötü amaçlı yazılımların önyükleme işlemine bulaşma ihtimalini ortadan kaldırır.

İdeal olarak, "Geçerli durum" grafiği, işletim sistemi sayısının eski sürümlere göre daha güncel işletim sistemi lehine ağırlıklı olduğunu gösterir. Aksi takdirde eğilim grafiği yeni sistemlerin benimsendiğini ve/veya eski sistemlerin güncelleştirildiğini veya değiştirildiğini gösterir.

### <a name="windows-versions-card"></a>Windows sürümleri kartı

Windows 10 sürümleri kartı, Windows cihazlarının ve bunların kuruluşunuzdaki sürümlerinin dağıtımını gösterir.
Windows 8'den Windows 10'ye yükseltmenin kuruluşunuzda güvenliği geliştirmesi gibi, Windows'un erken sürümlerinden daha güncel sürümlere geçmek olası tehditlere karşı duruşunuzu geliştirir.

Windows sürümü eğilim grafiği, Windows 10 en son ve en güvenli sürümlerine güncelleştirerek kuruluşunuzun güncel olup olmadığını hızla belirlemenize yardımcı olabilir.

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

İşlevsellik temelde tüm kartlar için aynıdır. Herhangi bir karttaki numaralandırılmış çıtaya tıklayarak **Microsoft Defender Virüsten Koruma ayrıntıları** açılır öğesi açılır ve bu karttaki bir yönün sürüm numarasıyla yapılandırılan tüm cihazlar hakkındaki bilgileri gözden geçirmenizi sağlar.

>:::image type="content" source="images/device-health-defender-antivirus-health-antivirus-details.png" alt-text="Microsoft Defender Virüsten Koruma ayrıntıları açılır öğesini gösterir." lightbox="images/device-health-defender-antivirus-health-antivirus-details.png":::

Tıkladığınız sürüm numarası şuysa:

- Geçerli bir sürüm, ardından **Düzeltme gerekli** ve **Güvenlik önerisi** yok
- Güncel olmayan bir sürüm, raporun üst kısmında **Düzeltme gerektiğini** belirten bir bildirim bulunur ve **bir Güvenlik önerisi** bağlantısı bulunur. Uygun virüsten koruma güncelleştirmelerini önerebilen Tehdit ve Güvenlik Açığı Yönetimi konsoluna gitmek için güvenlik önerisi bağlantısını seçin.

**Microsoft Defender Virüsten Koruma ayrıntıları** açılır öğesinde belirli türlerdeki bilgileri eklemek veya kaldırmak için **Sütunları Özelleştir'i** seçin. **Sütunları Özelleştir** bölümünde, Microsoft Defender Virüsten Koruma ayrıntıları raporuna eklenmesini istediklerinizi belirtmek için öğeleri seçin veya temizleyin.

>:::image type="content" source="images/device-health-defender-antivirus-engine-version-details-custom-columns.png" alt-text="Microsoft Defender Virüsten Koruma sistem durumu raporlaması için özel sütun seçeneklerini gösterir." lightbox="images/device-health-defender-antivirus-engine-version-details-custom-columns.png":::

#### <a name="new-microsoft-defender-antivirus-filter-definitions"></a>Yeni Microsoft Defender Virüsten Koruma filtre tanımları

Aşağıdaki tabloda, Microsoft Defender Virüsten Koruma raporlamasına yeni eklenen terimlerin listesi yer alır.

| Sütun adı | Açıklama |
|:---|:---|
| Güvenlik intel'i yayımlama süresi  | Microsoft'un cihazdaki güvenlik bilgileri güncelleştirme sürümünün yayın tarihini gösterir. Güvenlik bilgileri yayımlama süresi 7 günden uzun olan cihazlar raporlarda güncel değil olarak kabul edilir. |
| Son görülme | Cihazın en son ne zaman bağlantı olduğunu gösterir. |
| Veri yenileme zaman damgası  | İSTEMCI olaylarının AV modunda, AV altyapısı sürümünde, AV platformu sürümünde, AV güvenlik zekası sürümünde ve tarama bilgilerinde raporlama için en son ne zaman alındığını gösterir. |
| İmza yenileme zamanı | Altyapı, platform ve imza durumuyla ilgili raporlama için istemci olaylarının en son ne zaman alındığını gösterir. |

Açılır listede: Cihazın adına tıkladığınızda, ayrıntılı raporlara erişebileceğiniz bu cihazın "Cihaz sayfası"na yönlendirilirsiniz.

#### <a name="export-report"></a>Raporu dışarı aktarma

Dışarı aktarabileceğiniz iki rapor düzeyi vardır:

##### <a name="top-level-export"></a>Üst düzey dışarı aktarma

Portal aracılığıyla iki farklı dışarı aktarma csv işlevi vardır:

- **Üst düzey dışarı aktarma** Microsoft Defender Virüsten Koruma sistem durumu raporunu (500.000 sınırı) toplamak için en üst düzey **Dışarı Aktar** düğmesini kullanabilirsiniz.

>:::image type="content" source="images/device-health-defender-antivirus-health-tab-export.png" alt-text="En üst düzey dışarı aktarma raporu düğmesini gösterir" lightbox="images/device-health-defender-antivirus-health-tab-export.png":::

- **Açılır öğe düzeyi dışarı aktarma** Bir raporu Excel elektronik tablosuna (100.000 sınır) dışarı aktarmak için açılır listelerdeki **Dışarı Aktar** düğmesini kullanabilirsiniz.

Dışarı aktarılan raporlar, ayrıntılar raporuna giriş noktanızı ve hangi filtreleri veya özelleştirilmiş sütunları ayarladığınızı temel alarak bilgileri yakalar.

API kullanarak dışarı aktarma hakkında bilgi için aşağıdaki makalelere bakın:

- [Cihaz virüsten koruma sistem durumu raporunu dışarı aktarma](device-health-export-antivirus-health-report-api.md)
- [Cihaz virüsten koruma sistem durumu ayrıntılarını API yöntemleri ve özelliklerini dışarı aktarma](device-health-api-methods-properties.md)

> [!IMPORTANT]
>
> Şu anda yalnızca **Virüsten Koruma Durumu JSON Yanıtı** genel kullanıma sunulmuştur. **Dosyalar aracılığıyla Virüsten Koruma Sistem Durumu API'sini** yalnızca genel önizlemede kullanabilirsiniz.
>
> **Gelişmiş Tehdit Avcılığı özel sorgusu** şu anda sorgular hala görünür olsa bile yalnızca genel önizlemede kullanılabilir.

### <a name="microsoft-defender-antivirus-version-and-update-cards-functionality"></a>Microsoft Defender Virüsten Koruma sürümü ve güncelleştirme kartları işlevselliği

Microsoft Defender Virüsten Koruma altyapısı, güvenlik bilgileri ve platform bileşenleri için _sürüm_ ve _güncelleştirme_ bilgileri hakkında rapor veren altı kartın açıklamaları aşağıdadır:

#### <a name="full-report"></a>Tam rapor

Üç _sürüm_ kartından herhangi birinde **Tam raporu görüntüle'yi** seçerek üç cihaz türünün her biri için en son dokuz Microsoft Defender Virüsten Koruma _sürümü_ raporunu görüntüleyin: Windows, Mac ve Linux; dokuzdan az varsa, hepsi gösterilir. **Diğer** kategorisi, algılanırsa onuncu ve altındaki en son virüsten koruma altyapısı sürümlerini yakalar.

>:::image type="content" source="images/device-health-defender-antivirus-health-view-full-report.png" alt-text="Her türden ilk dokuz işletim sisteminin dağılımını gösterir" lightbox="images/device-health-defender-antivirus-health-view-full-report.png":::

Üç _sürüm_ kartının birincil avantajlarından biri, virüsten koruma motorlarının, platformlarının ve güvenlik zekasının en güncel sürümlerinin kullanılıp kullanılmadığına ilişkin hızlı göstergeler sağlamasıdır. Sürüm kartları, karta bağlı ayrıntılı bilgilerle birlikte sürümlerin güncel olup olmadığını denetlemek ve tek tek bilgisayarlar veya bilgisayar grupları hakkında bilgi toplamak için güçlü bir araç haline gelir.
İdeal olarak, bu raporları çalıştırdığınızda, eski sürümlerin aksine en güncel virüsten koruma sürümlerinin yüklü olduğunu gösterirler.
Kuruluşunuzun en güncel sürümlerden tam olarak yararlanıp yararlanmadığını belirlemek için bu raporları kullanın.

>:::image type="content" source="images/device-health-defender-antivirus-health-antivirus-details-up-to-date.png" alt-text="Microsoft Defender Virüsten Koruma sürüm ayrıntılarını gösterir" lightbox="images/device-health-defender-antivirus-health-antivirus-details-up-to-date.png":::

Kötü amaçlı yazılımdan koruma çözümünüzün en son tehditleri algılamasına yardımcı olmak için güncelleştirmeleri Windows Update bir parçası olarak otomatik olarak alın.

Geçerli sürümler ve farklı Microsoft Defender Virüsten Koruma bileşenlerini güncelleştirme hakkında daha fazla bilgi için [Microsoft Defender Virüsten Koruma platformu desteği](manage-updates-baselines-microsoft-defender-antivirus.md) sayfasını ziyaret edin.

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

>:::image type="content" source="images/device-health-defender-antivirus-health-antivirus-mode.png" alt-text="Microsoft Defender Virüsten Koruma modlarını filtrelemeyi gösterir" lightbox="images/device-health-defender-antivirus-health-antivirus-mode.png":::

Her modun açıklamaları aşağıdadır:

- **Etkin** mod - Etkin modda Microsoft Defender Virüsten Koruma, cihazda birincil virüsten koruma uygulaması olarak kullanılır. Dosyalar taranır, tehditler düzeltilir ve algılanan tehditler, kuruluşunuzun güvenlik raporlarında ve Windows Güvenliği uygulamanıza listelenir.
- **Pasif** mod - Pasif modda Microsoft Defender Virüsten Koruma, cihazda birincil virüsten koruma uygulaması olarak kullanılmaz. Dosyalar taranır ve algılanan tehditler bildirilir, ancak tehditler Microsoft Defender Virüsten Koruma tarafından düzeltilmemiştir. ÖNEMLİ: Microsoft Defender Virüsten Koruma, pasif modda sadece Uç Nokta için Microsoft Defender’a eklenmiş uç noktalarda çalıştırılabilir. [Microsoft Defender Virüsten Koruma’nın pasif modda çalıştırılması için gereksinimlere](microsoft-defender-antivirus-compatibility.md#requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode) bakın.
- **Devre dışı** modu - ile eş anlamlı: kaldırıldı, devre dışı, sideBySidePassive ve Düşük Düzenli Tarama. Devre dışı bırakıldığında Microsoft Defender Virüsten Koruma kullanılmaz. Dosyalar taranmıyor ve tehditler düzeltilmemiş. Genel olarak, Microsoft, Microsoft Defender Virüsten Koruma'yı devre dışı bırakmanızı veya kaldırmanızı önermez.
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
Geçerli sürümler ve farklı Microsoft Defender Virüsten Koruma bileşenlerini güncelleştirme hakkında daha fazla bilgi için bkz. [Microsoft Defender Virüsten Koruma platformu desteği](manage-updates-baselines-microsoft-defender-antivirus.md).

#### <a name="antivirus-security-intelligence-version-card"></a>Virüsten koruma güvenlik bilgileri sürüm kartı

Ağınızdaki cihazlarda yüklü en yaygın _Microsoft Defender Virüsten Koruma güvenlik zekası_ sürümlerini listeler.
Microsoft, en son tehditleri ele almak ve algılama mantığını geliştirmek için Microsoft Defender güvenlik zekasını sürekli olarak güncelleştirir. Güvenlik zekasına yönelik bu iyileştirmeler, Olası tehditleri doğru bir şekilde tanımlamak için Microsoft Defender Virüsten Koruma'nın (ve diğer Microsoft kötü amaçlı yazılımdan koruma çözümlerinin) özelliğini geliştirir. Bu güvenlik zekası, hızlı ve güçlü yapay zeka destekli yeni nesil koruma sağlamak için doğrudan bulut tabanlı koruma ile çalışır.

##### <a name="antivirus-platform-version-card"></a>Virüsten koruma platformu sürüm kartı

Kuruluşunuzdaki Windows, Mac ve Linux cihazlarında yüklü olan en güncel Microsoft Defender Virüsten Koruma platformu sürümlerinin gerçek zamanlı sonuçlarını gösterir. Microsoft Defender Virüsten Koruma platformu aylık olarak güncelleştirilir.
Geçerli sürümler ve farklı Microsoft Defender Virüsten Koruma bileşenlerini güncelleştirme hakkında daha fazla bilgi için bkz. [Microsoft Defender Virüsten Koruma platformu desteği](manage-updates-baselines-microsoft-defender-antivirus.md)

#### <a name="up-to-date-cards"></a>Güncel kartlar

Güncel kartlar  **Virüsten Koruma altyapısı, Virüsten Koruma**  **platformu** ve **Güvenlik bilgileri** güncelleştirme sürümleri için güncel durumu gösterir. Üç olası durum vardır:  _Güncel_ ('Doğru'), _güncel değil_ ('Yanlış') ve _kullanılabilir veri yok_ ('Bilinmiyor').

Aşağıdaki her kart için  _Güncel_, date_ dışında ve _kullanılabilir veri yok_ tanımları sağlanmıştır.

Microsoft Defender Virüsten Koruma, aşağıdaki ölçütlere göre güncel raporlar ve belirlemeler yapar:

- **Altyapı & platformu güncelleştirmeleri için**: "İmza Yenileme Zamanı" (istemci olaylarının en son güncel raporlar için alındığı saat) ve "Güvenlik Zekası Yayımlama Zamanı" (güvenlik zekası VDM'leri altyapı & platform sürümlerini belirlemek için kullanılır)
- **Güvenlik bilgileri güncelleştirmeleri için**: "İmza Yenileme Zamanı" (istemci olaylarının en son güncel raporlar için alındığı saat), Güvenlik Zekası Yayımlama Zamanı ve istemciden iletilen son güncel durum

Yukarıda belirtilen terimler hakkında daha fazla bilgi için şu bölüme bakın: [Yeni Microsoft Defender Virüsten Koruma filtre tanımları](#new-microsoft-defender-antivirus-filter-definitions)

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
| **Güncel** | cihaz, son 7 gün içinde Defender rapor olayıyla ('İmza yenileme süresi') iletişim kurar ve son 7 gün içinde bir güvenlik zekası yayımlama süresine sahiptir ve Altyapı veya Platform sürümü derleme süresi son 60 gün içindedir. |
| **Güncel** | cihaz, son 7 gün içinde Defender rapor olayıyla ('İmza yenileme süresi') iletişim kurar ve son 7 gün içinde bir güvenlik zekası yayımlama süresine sahiptir, ancak Altyapı veya Platform sürümü derleme süresi 60 günden eskidir. |
| **bilinmiyor (kullanılabilir veri yok)** | cihaz 7 günden uzun süredir rapor olayıyla ('İmza yenileme süresi') iletişim kurmadı veya güvenlik bilgileri yayımlama süresi 7 günden uzundur. |

Güvenlik zekası için güncel tanımlar aşağıdadır:

| Güvenlik bilgileri güncelleştirmesi dikkate alınır | Eğer: |
|:---|:---|
|Güncel | cihazdaki güvenlik bilgileri sürümü son 7 gün içinde yazılmıştır ve cihaz son 7 gün içinde rapor olayıyla iletişim kurar. |

Bunlar hakkında daha fazla bilgi için bkz:

- [Virüsten koruma altyapısı güncelleştirme kartı](#antivirus-engine-updates-card)
- [Güvenlik bilgileri güncelleştirme kartı](#security-intelligence-updates-card)
- [Virüsten koruma platformu güncelleştirme kartı](#antivirus-platform-updates-card)

##### <a name="antivirus-engine-updates-card"></a>Virüsten koruma altyapısı güncelleştirme kartı

Bu kart, virüsten koruma altyapısı sürümleri güncel ve güncel olmayan cihazları tanımlar.

**'_Güncel_' genel tanımı** - Cihazdaki altyapı sürümü en son altyapı sürümüdür. Motor _genellikle_ Windows Update (WU) aracılığıyla aylık olarak serbest bırakılır. Windows Update (WU) serbest bırakıldığından itibaren üç günlük yetkisiz kullanım süresi vardır.

Aşağıdaki tabloda **Virüsten Koruma Altyapısı** için güncel raporlar için olası değerler yer alır. Bildirilen Durum, raporlama olayının son alındığı zamanı ve güvenlik zekası yayımlama süresini temel alır.  

| Olayın Son Yenileme Zamanı (raporlarda "İmza Yenileme Zamanı" olarak da bilinir) | Güvenlik Zekası Yayımlama Zamanı | _Bildirilen Durum_: |
|:----|:----|:----|
| < 7 gün (yeni) | < 7 gün (yeni) | _Güncel Olmayan <br/> Bilinmeyen (istemci raporları ne olursa olsun) güncel <br/> değil_ |
| > 7 gün (eski) | > 7 gün (eski) | _Unknown_ |
| < 7 gün (yeni) | > 7 gün (eski) | _Unknown_ |
| > 7 gün (eski) | < 7 gün (yeni) | _Unknown_ |

Microsoft Defender Virüsten Koruma güncelleştirme sürümlerini yönetme hakkında bilgi için bkz.  [Aylık platform ve altyapı sürümleri](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

#### <a name="antivirus-platform-updates-card"></a>Virüsten koruma platformu güncelleştirme kartı

Bu kart, Virüsten Koruma platformu sürümlerinin güncel ve güncel olmayan cihazları tanımlar.

**'Güncel' genel tanımı** Cihazdaki platform sürümü en son platform sürümüdür. Platform genellikle Windows Update) aracılığıyla aylık olarak yayınlanır. WU serbest bırakıldığından itibaren üç günlük yetkisiz kullanım süresi vardır.

Aşağıdaki tabloda **Virüsten Koruma Platformu** için olası güncel rapor değerleri yer almaktadır. Bildirilen değerler raporlama olayının son alındığı zamanı ve güvenlik zekası yayımlama süresini temel alır.

| Olayın Son Yenileme Zamanı (raporlarda "İmza Yenileme Zamanı" olarak da bilinir) | Güvenlik Zekası Yayımlama Zamanı | _Bildirilen Durum_: |
|:----|:----|:----|
| < 7 gün (yeni) | < 7 gün (yeni) | _Güncel Olmayan <br/> Bilinmeyen (istemci raporları ne olursa olsun) güncel <br/> değil_ |
| > 7 gün (eski) | > 7 gün (eski) | _Unknown_ |
| < 7 gün (yeni) | > 7 gün (eski) | _Unknown_ |
| > 7 gün (eski) | < 7 gün (yeni) | _Unknown_ |

Microsoft Defender Virüsten Koruma güncelleştirme sürümlerini yönetme hakkında bilgi için bkz. [Aylık platform ve altyapı sürümleri](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

##### <a name="security-intelligence-updates-card"></a>Güvenlik bilgileri güncelleştirme kartı

Bu kart, güncel ve güncel olmayan güvenlik bilgileri sürümlerine sahip cihazları tanımlar.

**'Güncel' genel tanımı** – cihazdaki güvenlik zekası sürümü son 7 gün içinde yazılmıştır.

Aşağıdaki tabloda **Güvenlik Bilgileri** güncelleştirmeleri için olası güncel rapor değerleri yer alır. Bildirilen değerler raporlama olayının son alındığı zamanı, güvenlik zekası yayımlama süresini ve istemciden alınan son durumu temel alır.

| Olayın Son Yenileme Zamanı <br/> (raporlarda "İmza Yenileme Zamanı" olarak da bilinir) | Güvenlik Zekası Yayımlama Zamanı | İstemciden alınan son durum | _Bildirilen Durum_: |
|:----|:----|:----|:----|
| >7 gün (eski) | >7 gün (eski) | Modern | _Unknown_ |
| <7 gün (yeni) | >7 gün (eski) | Modern | _Unknown_ |
| >7 gün (eski) | <7 gün (yeni) | Modern |  _Unknown_ |
| <7 gün (yeni) | <7 gün (yeni) | Unknown | _Unknown_|
| <7 gün (yeni) | <7 gün (yeni) | Modern | _Modern_ |
| >7 gün (eski) | <7 gün (yeni) | Güncel değil | _Güncel değil_ |
| >7 gün (eski) | >7 gün (eski) | Güncel değil | _Güncel değil_ |
| <7 gün (yeni) | >7 gün (eski) | Güncel değil | _Güncel değil_ |

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
