---
title: Saldırı yüzeyi azaltma (ASR) kuralları raporlama
description: Saldırı yüzeyi azaltma (ASR) kuralları algılamaları, yapılandırma, engelleme tehditleri ve üç standart kural ve dışlamayı etkinleştirme yöntemleri hakkında bilgi sağlar.
keywords: Saldırı yüzeyi azaltma kuralları, ASR, asr kuralları, kalçalar, konak izinsiz giriş önleme sistemi, koruma kuralları, kötüye kullanıma karşı koruma kuralları, antiexploit, exploit kuralları, bulaşma önleme kuralları, Uç Nokta için Microsoft Defender, ASR kurallarını yapılandırma, ASR kuralı açıklaması
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: m365-security
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar,
manager: dansimp
ms.custom: asr
ms.topic: article
ms.collection: M365-security-compliance
ms.date: 08/25/2022
search.appverid: met150
ms.openlocfilehash: 5c13fb3828629c0e2690ac129aa6c5e127a0ac49
ms.sourcegitcommit: 2dedd0f594b817779e034afa6c4418def2382a22
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2022
ms.locfileid: "67799196"
---
# <a name="attack-surface-reduction-asr-rules-report"></a>Saldırı yüzeyi azaltma (ASR) kuralları raporu

**Şunlar için geçerlidir:**

- [Uç Nokta Planı 1 için Microsoft Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Platform:**

- Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> [!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

Saldırı yüzeyi azaltma (ASR) kuralları raporu, kuruluşunuzdaki cihazlara uygulanan _saldırı yüzeyi azaltma kuralları_ hakkında bilgi sağlar. Bu rapor aşağıdakiler hakkında da bilgi sağlar:

- algılanan tehditler
- engellenen tehditler
- tehditleri engellemek için standart koruma kurallarını kullanacak şekilde yapılandırılmamış cihazlar

Ayrıca, bu rapor aşağıdakileri gerçekleştirmenizi sağlayan kullanımı kolay bir arabirim sağlar:

- Tehdit algılamalarını görüntüleme
- ASR kurallarının yapılandırmasını görüntüleme
- Dışlamaları yapılandırma (ekleme)
- Tek bir geçişle en çok önerilen üç ASR kuralını etkinleştirerek _temel korumayı_ kolayca etkinleştirin
- Ayrıntılı bilgi toplamak için detaya gitme

Bireysel saldırı yüzeyi azaltma kuralları hakkında daha fazla bilgi için bkz [. Saldırı yüzeyi azaltma kuralları başvurusu](attack-surface-reduction-rules-reference.md).

## <a name="prerequisites"></a>Önkoşullar

> [!IMPORTANT]
> Windows&nbsp;Server&nbsp;2012&nbsp;R2 ve Windows&nbsp;Server&nbsp;2016'nın **Saldırı yüzeyi azaltma kuralları raporunda** görünmesi için bu cihazların modern birleşik çözüm paketi kullanılarak eklenmesi gerekir. Daha fazla bilgi için bkz. [Windows Server 2012 R2 ve 2016 için modern birleşik çözümde yeni işlevler](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution).

## <a name="report-access-permissions"></a>Rapor erişim izinleri

Microsoft 365 Güvenlik panosundaki **Saldırı yüzeyi azaltma kuralları raporuna** erişmek için aşağıdaki izinler gereklidir:

| İzin türü | Izni | İzin görünen adı |
|:---|:---|:---|
| Uygulama | Machine.Read.All | 'Tüm makine profillerini oku' |
|Temsilci (iş veya okul hesabı) | Machine.Read | 'Makine bilgilerini oku' |

Bu izinleri atamak için:

1. Güvenlik yöneticisi veya <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Genel yönetici</a> rolü atanmış hesabı kullanarak Microsoft 365 Defender oturum açın.
1. Gezinti bölmesinde **Ayarlar** \> **Uç Noktaları** \> **Rolleri'ni** seçin ( **İzinler'in** altında).
1. Düzenlemek istediğiniz rolü seçin.
1. **Düzenle'yi** seçin.
1. **Rolü düzenle'nin** **Genel** sekmesindeki **Rol adı** alanına rol için bir ad yazın.
1. **Açıklama** alanına rolün kısa bir özetini yazın.
1. **İzinler'de** **Verileri Görüntüle'yi** seçin ve **Verileri Görüntüle'nin** altında **Saldırı yüzeyi azaltma'yı** seçin.

Kullanıcı rolü yönetimi hakkında daha fazla bilgi için bkz. [Rol tabanlı erişim denetimi için rol oluşturma ve yönetme](user-roles.md).

## <a name="navigation"></a>Gezinti

Saldırı yüzeyi azaltma kuralları raporunun özet kartlarına gitmek için

1. **Microsoft 365 Defender** portalını açın.
1. Sol panelde **Raporlar'a** tıklayın ve ana bölümde, **Raporlar'ın** altında **Güvenlik raporu'na** tıklayın.
1. **Saldırı yüzeyi azaltma kuralları** özet kartlarını bulmak için aşağı kaydırarak **Cihazlar'a** gidin.

ASR kurallarının özet rapor kartları aşağıdaki şekilde gösterilmiştir.

>:::image type="content" source="images/attack-surface-reduction-rules-report-summary.png" alt-text="ASR kuralları rapor özet kartlarını gösterir" lightbox="images/attack-surface-reduction-rules-report-summary.png":::

## <a name="asr-rules-report-summary-cards"></a>ASR kuralları rapor özet kartları

ASR kuralları rapor özeti iki karta ayrılır:

- [**ASR kuralı algılamaları** özet kartı](#asr-rules-detections-summary-card)
- [**ASR kuralı yapılandırma** özet kartı](#asr-rules-configuration-summary-card)

### <a name="asr-rules-detections-summary-card"></a>ASR kuralları algılamaları özet kartı

ASR kuralları tarafından engellenen algılanan tehdit sayısının özetini gösterir.

İki 'eylem' düğmesi sağlar:

- Algılamaları görüntüle - Ana **Algılamalar** sekmesini > **Saldırı yüzeyi azaltma kurallarını** açar
- Dışlama ekleme - **Saldırı yüzeyi azaltma kurallarını** > ana **Dışlamalar** sekmesini açar

:::image type="content" source="images/attack-surface-reduction-rules-report-main-detections-card.png" alt-text="ASR kuralları rapor özeti algılamaları kartını gösterir." lightbox="images/attack-surface-reduction-rules-report-main-detections-card.png":::

Kartın üst kısmındaki **ASR kuralları algılamaları** bağlantısına tıklanması, ana [Saldırı yüzeyi azaltma kuralları Algılamalar sekmesini](#attack-surface-reduction-rules-main-detections-tab) de açar.

### <a name="asr-rules-configuration-summary-card"></a>ASR kuralları yapılandırma özet kartı

**Üst bölüm** , yaygın saldırı tekniklerine karşı koruma sağlayan önerilen üç kurala odaklanır. Bu kart, kuruluşunuzdaki aşağıdaki [Üç \(ASR\) standart koruma kuralının](#simplified-standard-protection-option) **Blok modunda**, **Denetim modunda** veya **kapalı** (yapılandırılmamış) olarak ayarlandığı bilgisayarlar hakkındaki güncel durum bilgilerini gösterir. **Cihazları koru** düğmesi yalnızca üç kural için tam yapılandırma ayrıntılarını gösterir; müşteriler bu kuralları etkinleştirmek için hızlı bir şekilde işlem yapabilir.

**Alt bölümde,** kural başına korumasız cihaz sayısına göre altı kural gösterilir. "Yapılandırmayı görüntüle" düğmesi, tüm ASR kuralları için tüm yapılandırma ayrıntılarını gösterir. "Dışlama ekle" düğmesi, Güvenlik İşlem Merkezi(SOC) tarafından değerlendirilecek tüm algılanan dosya/işlem adlarının listelendiği dışlama ekle sayfasını gösterir. **Dışlama ekle** sayfası Microsoft Endpoint Manager(MEM) ile bağlantılıdır.

İki 'eylem' düğmesi sağlar:

- Yapılandırmayı görüntüle - Ana **Algılamalar** sekmesini > **Saldırı yüzeyi azaltma kurallarını** açar
- Dışlama ekleme - **Saldırı yüzeyi azaltma kurallarını** > ana **Dışlamalar** sekmesini açar

:::image type="content" source="images/attack-surface-reduction-rules-report-main-detections-configuration-card.png" alt-text="ASR kuralları rapor özeti yapılandırma kartını gösterir." lightbox="images/attack-surface-reduction-rules-report-main-detections-configuration-card.png":::

Kartın üst kısmındaki **ASR kuralları yapılandırma** bağlantısına tıklanması ana [Saldırı yüzeyi azaltma kuralları Yapılandırma sekmesini](#attack-surface-reduction-rules-main-configuration-tab) de açar.

#### <a name="simplified-standard-protection-option"></a>Basitleştirilmiş standart koruma seçeneği

Yapılandırma özeti kartı **, Cihazları** üç standart koruma kuralıyla korumak için bir düğme sağlar. Microsoft en azından bu üç saldırı yüzeyi azaltma standart koruma kuralını etkinleştirmenizi önerir:

- [Windows yerel güvenlik yetkilisi alt sisteminden (lsass.exe) kimlik bilgilerinin çalınmalarını engelleme](attack-surface-reduction-rules-reference.md#block-credential-stealing-from-the-windows-local-security-authority-subsystem)
- [Güvenlik açığı bulunan imzalı sürücülerin kötüye kullanılması engellendi](attack-surface-reduction-rules-reference.md#block-abuse-of-exploited-vulnerable-signed-drivers)
- [Windows Yönetim Araçları (WMI) olay aboneliği aracılığıyla kalıcılığı engelleme](attack-surface-reduction-rules-reference.md#block-persistence-through-wmi-event-subscription)

Üç standart koruma kuralını etkinleştirmek için:

1. **Cihazları koru'yu** seçin. Ana **Yapılandırma** sekmesi açılır.
1. **Yapılandırma** sekmesinde **, Temel kurallar** otomatik olarak **Tüm kurallar'dan** **Standart koruma kuralları** etkin seçeneğine geçiş yapar.
1. **Cihazlar** listesinde, standart koruma kurallarının uygulanmasını istediğiniz cihazları seçin ve ardından **Kaydet'i** seçin.

Bu kartta iki gezinti düğmesi daha vardır:

- **Yapılandırmayı görüntüle** - Ana **Yapılandırma** sekmesini > **Saldırı yüzeyi azaltma kurallarını** açar.
- **Dışlama ekleme** - Ana **Dışlamalar** sekmesini > **Saldırı yüzeyi azaltma kurallarını** açar.

Kartın üst kısmındaki **ASR kuralları yapılandırma** bağlantısına tıklanması ana [Saldırı yüzeyi azaltma kuralları Yapılandırma sekmesini](#attack-surface-reduction-rules-main-configuration-tab) de açar.

## <a name="attack-surface-reduction-rules-main-tabs"></a>Saldırı yüzeyi azaltma kuralları ana sekmeleri

ASR kuralları rapor özet kartları ASR kuralları durumunuzun hızlı özetini almak için yararlı olsa da, ana sekmeler filtreleme ve yapılandırma özellikleriyle daha ayrıntılı bilgiler sağlar:

- [Algılamalar sekmesi](#attack-surface-reduction-rules-main-detections-tab)
- [Yapılandırma sekmesi](#attack-surface-reduction-rules-main-configuration-tab)
- [Dışlamalar sekmesi](#attack-surface-reduction-rules-add-exclusions-tab)

### <a name="search-capabilities"></a>Arama özellikleri

 **Arama özelliği Algılama**, **Yapılandırma** ve **Dışlama ekle** ana sekmelerine eklenir. Bu özellik sayesinde cihaz kimliğini, dosya adını veya işlem adını kullanarak arama yapabilirsiniz.

>:::image type="content" source="images/attack-surface-reduction-rules-report-main-tabs-search.png" alt-text="ASR kuralları rapor arama özelliğini gösterir." lightbox="images/attack-surface-reduction-rules-report-main-tabs-search.png":::

>:::image type="content" source="images/attack-surface-reduction-rules-report-main-tabs-search-configuration-tab.png" alt-text="Yapılandırma sekmesinde ASR kuralları rapor arama özelliğini gösterir." lightbox="images/attack-surface-reduction-rules-report-main-tabs-search-configuration-tab.png":::

### <a name="filtering"></a>Filtreleme

Filtreleme, hangi sonuçların döndürüleceğini belirtmeniz için bir yol sağlar:

- **Tarih**  , veri sonuçları için bir tarih aralığı belirtmenize olanak tanır.
- **Filtreler**

>:::image type="content" source="images/attack-surface-reduction-rules-report-main-detections-filtering.png" alt-text="ASR kuralları rapor filtreleme özelliğini gösterir" lightbox="images/attack-surface-reduction-rules-report-main-detections-filtering.png":::

### <a name="attack-surface-reduction-rules-main-detections-tab"></a>Saldırı yüzeyi azaltma kuralları ana algılamalar sekmesi

- **Denetim Algılamaları**  _Denetim_ modunda ayarlanan kurallar tarafından kaç tehdit algılaması yakalandığını gösterir.
- **Engellenen Algılamalar** _Engelle_ modunda ayarlanan kurallar tarafından kaç tehdit algılamanın engellendiğini gösterir.
- **Büyük, birleştirilmiş grafik** Engellenen ve denetlenen algılamaları gösterir.

>:::image type="content" source="images/attack-surface-reduction-rules-report-main-detections-tab.png" alt-text="_Audit detections_ ve _Blocked detections_ ana hatlarıyla asr kuralları raporu ana algılamalar sekmesini gösterir." lightbox="images/attack-surface-reduction-rules-report-main-detections-tab.png":::

Grafikler, görüntülenen tarih aralığı üzerinde algılama verileri sağlar ve tarihe özgü bilgileri toplamak için belirli bir konumun üzerine gelme özelliği sunar.

Raporun alt bölümünde algılanan tehditler (cihaz başına temelinde) aşağıdaki alanlarla listelenir:

| Alan adı| Tanım |
|:---|:---|
| Algılanan dosya | Olası veya bilinen bir tehdit içerdiği belirlenen dosya |
| Algılanan | Tehdidin algılandığı tarih |
| Engellendi\/Denetlendi mi? | Belirli bir olay için algılama kuralının Engelleme veya Denetim modunda olup olmadığı |
| Kural | Tehdidi algılayan kural |
| Kaynak uygulama | Rahatsız edici "algılanan dosyaya" çağrı yapan uygulama |
| Cihaz | Denetim veya Engelleme olayının gerçekleştiği cihazın adı |
| Cihaz grubu | Cihazın ait olduğu Active Directory grubu |
| Kullanıcı |  Aramadan sorumlu makine hesabı |
| Publisher | Belirli bir .exe veya uygulamayı yayınlayan şirket |

ASR kural denetimi ve blok modları hakkında daha fazla bilgi için bkz [. Saldırı yüzeyi azaltma kuralı modları](attack-surface-reduction-rules-reference.md#asr-rule-modes).

#### <a name="actionable-flyout"></a>Eyleme dönüştürülebilir açılır öğe

"Algılama" ana sayfasında son 30 gün içindeki tüm algılamaların (dosyalar/işlemler) listesi bulunur. Detaya gitme özellikleriyle açmak için algılamalardan herhangi birini seçin.

>:::image type="content" source="images/attack-surface-reduction-rules-report-main-detections-flyout.png" alt-text="ASR kuralları raporu ana algılamalar sekmesi açılır penceresini gösterir" lightbox="images/attack-surface-reduction-rules-report-main-detections-flyout.png":::

**Olası dışlama ve etki** bölümü, seçilen dosya veya işlemin etkisini sağlar. Şunları yapabilirsiniz:

- Gelişmiş Tehdit Avcılığı sorgu sayfasını açan **Avlanmaya Git'i** seçin
- **Dosya açma sayfası** Uç Nokta için Microsoft Defender (MDE) algılamayı açar
- **Dışlama ekle** düğmesi, dışlama ekleme ana sayfasıyla bağlantılıdır.

Aşağıdaki görüntüde, eyleme dönüştürülebilir açılır öğedeki bağlantıdan Gelişmiş Tehdit Avcılığı sorgu sayfasının nasıl açıldığını gösterilmektedir:

>:::image type="content" source="images/attack-surface-reduction-rules-report-main-detections-flyout-hunting.png" alt-text="Gelişmiş Tehdit Avcılığı'nı açan (ASR) kural raporu ana algılamalar sekmesi açılır öğesi bağlantısını gösterir" lightbox="images/attack-surface-reduction-rules-report-main-detections-flyout-hunting.png":::

Gelişmiş avcılık hakkında daha fazla bilgi için bkz. [Microsoft 365 Defender'de gelişmiş avcılık ile tehditleri proaktif olarak avlama](advanced-hunting-overview.md)

### <a name="attack-surface-reduction-rules-main-configuration-tab"></a>Saldırı yüzeyi azaltma kuralları ana Yapılandırma sekmesi

ASR kuralları ana **Yapılandırma** sekmesi, özet ve cihaz başına ASR kuralları yapılandırma ayrıntıları sağlar. Yapılandırma sekmesinin üç ana yönü vardır:

**Temel kurallar** **Temel kurallar** ve **Tüm Kurallar** arasında sonuçları değiştirmek için bir yöntem sağlar. Varsayılan olarak **, Temel kurallar** seçilidir.

**Cihaz yapılandırmasına genel bakış** Aşağıdaki durumlardan birinde cihazların geçerli anlık görüntüsünü sağlar:

- Kullanıma sunulan tüm Cihazlar (önkoşulları eksik olan cihazlar, Denetim modundaki kurallar, yanlış yapılandırılmış kurallar veya yapılandırılmamış kurallar)
- Kuralları yapılandırılmamış cihazlar
- Denetim modunda kuralları olan cihazlar
- Blok modunda kuralları olan cihazlar

Yapılandırma sekmesinin **alt, adlandırılmamış bölümü,** cihazlarınızın geçerli durumunun bir listesini sağlar (cihaz başına temelinde):

- Cihaz (ad)
- Genel yapılandırma (Herhangi bir kuralın açık veya tümünün kapalı olup olmadığı)
- Blok modundaki kurallar (blok olarak ayarlanan cihaz başına kural sayısı)
- Denetim modundaki kurallar (denetim modundaki kuralların sayısı)
- Kurallar kapalı (kapalı veya etkinleştirilmemiş kurallar)
- Cihaz Kimliği (cihaz GUID'si)

Bu öğeler aşağıdaki şekilde gösterilmiştir.

>:::image type="content" source="images/attack-surface-reduction-rules-report-main-configuration-tab.png" alt-text="ASR kuralları raporu ana yapılandırma sekmesini gösterir" lightbox="images/attack-surface-reduction-rules-report-main-configuration-tab.png":::

ASR kurallarını etkinleştirmek için:

1. **Cihaz'ın** altında ASR kurallarını uygulamak istediğiniz cihazı veya cihazları seçin.
1. Açılır pencerede seçimlerinizi doğrulayın ve **İlkeye ekle'yi** seçin.

**Yapılandırma** sekmesi ve _kural ekleme_ açılır öğesi aşağıdaki görüntüde gösterilmiştir.

> [NOT!] Farklı ASR kurallarının uygulanmasını gerektiren cihazlarınız varsa, bu cihazları tek tek yapılandırmanız gerekir.

>:::image type="content" source="images/attack-surface-reduction-rules-report-configuration-add-to-policy.png" alt-text="Cihazlara ASR kuralları eklemek için ASR kuralları açılır öğesini gösterir" lightbox="images/attack-surface-reduction-rules-report-configuration-add-to-policy.png":::

### <a name="attack-surface-reduction-rules-add-exclusions-tab"></a>Saldırı yüzeyi azaltma kuralları Dışlama ekle sekmesi

**Dışlama ekle** sekmesi, dosya adına göre sıralı bir algılama listesi sunar ve dışlamaları yapılandırmak için bir yöntem sağlar. Varsayılan olarak, **Dışlama ekleme** bilgileri üç alan için listelenir:

- **Dosya adı** ASR kuralları olayını tetikleyen dosyanın adı.
- **Algılamalar** Adlandırılmış dosya için algılanan olayların toplam sayısı. Tek tek cihazlar birden çok ASR kuralı olayını tetikleyebilir.
- **Aygıtları** Algılamanın gerçekleştiği cihaz sayısı.

>:::image type="content" source="images/attack-surface-reduction-rules-report-exclusion-tab.png" alt-text="ASR kural raporu dışlama ekleme sekmesini gösterir" lightbox="images/attack-surface-reduction-rules-report-exclusion-tab.png":::

> [!IMPORTANT]
> Dosya veya klasörlerin dışlanması ASR kuralları tarafından sağlanan korumayı ciddi ölçüde azaltabilir. Dışlanan dosyaların çalıştırılmasına izin verilir ve hiçbir rapor veya olay kaydedilmez.
> ASR kuralları algılanmaması gerektiğini inandığınız dosyaları algılarsa, [kuralı test etmek için önce denetim modunu kullanmanız](attack-surface-reduction-rules-deployment-test.md#step-1-test-asr-rules-using-audit) gerekir.

Bir dosya seçtiğinizde, aşağıdaki bilgi türlerini sunan **Bir Özet & beklenen etki** açılır:

- **Seçili dosyalar**  Dışlamak için seçtiğiniz dosya sayısı
- **(_sayısı_) algılamaları**  Seçilen dışlamaları ekledikten sonra algılamalarda beklenen azalmayı belirtir.  Algılamalardaki azalma **, Gerçek algılamalar** ve **Dışlamalardan sonra algılamalar** için grafik olarak temsil edilir
- **(_sayısı_) etkilenen cihazlar** Seçili dışlamalar için algılamaları raporlayan cihazlarda beklenen azalmayı belirtir.

Dışlama ekle sayfasında, algılanan tüm dosyalarda (seçimden sonra) kullanılabilecek eylemler için iki düğme vardır. Şunları yapabilirsiniz:

- Microsoft Endpoint Manager (MEM) ASR ilke sayfasını açacak **dışlama ekleyin**. Daha fazla bilgi için bkz. "ASR kurallarını etkinleştirme alternatif yapılandırma yöntemleri" içindeki [MEM](https://enable-attack-surface-reduction.md#mem) .
- Dosya yollarını csv biçiminde indirecek **dışlama yollarını alma**

>:::image type="content" source="images/attack-surface-reduction-rules-report-main-add-exclusions-flyout.png" alt-text="ASR kural raporu ekleme dışlamalar sekmesi açılır öğesi etki özetini gösterir" lightbox="images/attack-surface-reduction-rules-report-main-add-exclusions-flyout.png":::

## <a name="see-also"></a>Ayrıca bkz.

- [Saldırı yüzeyi azaltma kurallarını etkinleştirme](attack-surface-reduction-rules-deployment-implement.md)
- [Saldırı yüzeyi azaltma kuralları başvurusu](attack-surface-reduction-rules-reference.md)
