---
title: Hatalı sitelere macOS bağlantılarını önlemeye yardımcı olmak için ağ korumasını kullanma
description: macOS kullanıcılarının bilinen kötü amaçlı ve şüpheli ağ adreslerine erişmesini engelleyerek ağınızı koruyun
keywords: Ağ koruması, MacOS açıklarından yararlanma, kötü amaçlı web sitesi, ip, etki alanı, etki alanları, komut ve denetim, SmartScreen, bildirim
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: overview
ms.collection:
- m365initiative-m365-defender
- M365-security-compliance
ms.date: ''
ms.openlocfilehash: 103268e8b1cd1090d2ec6815a414164a63e83606
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67497059"
---
# <a name="network-protection-for-macos"></a>macOS için ağ koruması

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta Planı 1 için Microsoft Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta Planı 2 için Microsoft Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

## <a name="overview"></a>Genel bakış

Microsoft, ağ koruma işlevselliğini macOS'a getiriyor (en az macOS 11).

Microsoft Ağ koruması, cihazlarınızın İnternet tabanlı olaylardan saldırı yüzeyini azaltmaya yardımcı olur. Çalışanların aşağıdakileri barındırabilecek tehlikeli etki alanlarına erişmek için herhangi bir uygulama kullanmasını engeller:

- kimlik avı dolandırıcılığı
- Patla -tır
- İnternet'te diğer kötü amaçlı içerikler

Ağ koruması, düşük saygınlık kaynaklarına bağlanmaya çalışan tüm giden HTTP trafiğini engellemek için [smartscreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview.md) Microsoft 365 Defender kapsamını genişletir. Giden HTTP trafiğindeki bloklar etki alanına veya konak adına bağlıdır.

## <a name="new-and-updated-capabilities"></a>Yeni ve güncelleştirilmiş özellikler

- Kurumsal VPN'nizi ağ koruması ile birlikte veya "yan yana" çalıştırabilirsiniz. Şu anda hiçbir VPN çakışması tanımlanmış değildir. Çakışmalarla karşılaşırsanız, bu sayfanın en altında listelenen geri bildirim kanalı aracılığıyla geri bildirim sağlayabilirsiniz.
  - Web içeriği filtreleme, macOS için ağ koruması ile desteklenir.  
  - Ağ koruması yapılandırıldıysa ve cihazda etkinse, MDEP Portalı'nda oluşturulan web içeriği filtreleme (WCF) ilkeleri, macOS için Microsoft Edge'Chromium de dahil olmak üzere tarayıcılarda dikkate alınır. Mac üzerinde Microsoft Edge'de web içeriği filtrelemesi şu anda ağ koruması gerektirir; Bulut Uygulamaları için Microsoft Defender veya Özel Göstergeler gibi diğer E5 özellikleri de şu anda ağ koruması gerektirir.

### <a name="known-issues"></a>Bilinen sorunlar

- Block/Warn UX özelleştirilebilir değildir ve diğer genel görünüm değişiklikleri gerektirebilir
  - Daha fazla tasarım iyileştirmesi yapmak için müşteri geri bildirimleri toplanıyor

### <a name="important-notes"></a>Önemli notlar

- Bağlantıyı Kes düğmesini kullanarak Sistem Tercihleri'nden ağ korumasını denetlemenizi önermiyoruz. Bunun yerine, macOS için ağ korumasını denetlemek için mdatp komut satırı aracını veya JAMF / Intune kullanın.
- macOS web tehdit korumasının etkinliğini değerlendirmek için, macOS için Microsoft Edge dışındaki tarayıcılarda denemenizi öneririz (örneğin, Safari). macOS için Microsoft Edge, değerlendirdiğiniz Mac ağ koruması özelliğinin açık olup olmamasına bakılmaksızın etkinleştirilen yerleşik web tehdit korumasına sahiptir.

> [!NOTE]
>
> macOS için Microsoft Edge şu anda web içeriği filtrelemeyi, özel göstergeleri veya diğer kurumsal özellikleri desteklememektedir. Ancak ağ koruması, ağ koruması etkinse macOS için Microsoft Edge'e de bu korumayı sağlar.

## <a name="prerequisites"></a>Önkoşullar

- Lisanslama: Uç nokta kiracısı için Microsoft 365 Defender (deneme olabilir)
- Eklenen Makineler:
  - En düşük macOS sürümü: 11
  - Ürün sürümü 101.78.13 veya üzeri
  - Cihazınızın InsiderSlow (Önizleme) veya InsiderFast (Beta) Microsoft AutoUpdate güncelleştirme kanalında olması gerekir. Güncelleştirme kanalını denetlemek için aşağıdaki komutu kullanabilirsiniz:

```bash
mdatp health --field release_ring 
```

Cihazınız insiderSlow(Önizleme) güncelleştirme kanalında değilse Terminal'den aşağıdaki komutu yürütür. Kanal güncelleştirmesi, ürün bir sonraki başlatıldığında (bir sonraki ürün güncelleştirmesi yüklendiğinde veya cihaz yeniden başlatıldığında) geçerlilik kazanır.

```bash
defaults write com.microsoft.autoupdate2 ChannelName -string InsiderSlow
```

Alternatif olarak, yönetilen bir ortamdaysanız (JAMF veya Intune), cihaz grubunu uzaktan yapılandırabilirsiniz. Daha fazla bilgi için bkz. [macOS'ta Uç Nokta için Microsoft 365 Defender tercihlerini ayarlama](mac-preferences.md).

## <a name="deployment-instructions"></a>Dağıtım yönergeleri

### <a name="microsoft-365-defender-for-endpoint"></a>Uç Nokta için Microsoft 365 Defender

Cihazınızı InsiderSlow(önizleme) güncelleştirme kanalında olacak şekilde yapılandırdıktan sonra Microsoft AutoUpdate aracılığıyla en son ürün sürümünü yükleyin. Microsoft AutoUpdate'i açmak için Terminal'den aşağıdaki komutu çalıştırın:

```bash
open /Library/Application\ Support/Microsoft/MAU2.0/Microsoft\ AutoUpdate.app
```

Genel belgelerimizdeki yönergeleri kullanarak ürünü kuruluş bilgilerinizle yapılandırın.  

Ağ koruması varsayılan olarak devre dışıdır, ancak aşağıdaki modlardan birinde (zorlama düzeyleri olarak da adlandırılır) çalışacak şekilde yapılandırılabilir:

- **Denetim**: İş kolu uygulamalarını etkilemediğinden emin olmak veya blokların ne sıklıkta oluştuğu hakkında fikir edinmek için kullanışlıdır
- **Engelle**: ağ koruması kötü amaçlı web sitelerine bağlantıyı engeller
- **Devre dışı**: Ağ korumasıyla ilişkili tüm bileşenler devre dışı bırakıldı

Bu özelliği şu yollardan biriyle dağıtabilirsiniz: el ile, JAMF aracılığıyla veya Intune aracılığıyla. Aşağıdaki bölümlerde bu yöntemlerin her biri ayrıntılı olarak açıklanmaktadır.

#### <a name="manual-deployment"></a>El ile dağıtım

Zorlama düzeyini yapılandırmak için Terminal'den aşağıdaki komutu çalıştırın:

```bash
mdatp config network-protection enforcement-level --value [enforcement-level]
```

Örneğin, ağ korumasını engelleme modunda çalışacak şekilde yapılandırmak için aşağıdaki komutu yürütebilirsiniz:

```bash
mdatp config network-protection enforcement-level --value block
```

Ağ korumasının başarıyla başlatıldığını onaylamak için Terminal'den aşağıdaki komutu çalıştırın ve "başlatıldı" yazdırdığını doğrulayın:

```bash
mdatp health --field network_protection_status
```

#### <a name="jamf-deployment"></a>JAMF dağıtımı

Başarılı bir JAMF dağıtımı, ağ korumasının zorlama düzeyini ayarlamak için bir yapılandırma profili gerektirir.  
Bu yapılandırma profilini oluşturduktan sonra ağ korumasını etkinleştirmek istediğiniz cihazlara atayın.

##### <a name="configure-the-enforcement-level"></a>Zorlama düzeyini yapılandırma

Not: Burada listelenen yönergeleri kullanarak Mac'te Endpoint için Microsoft 365 Defender zaten yapılandırdıysanız, daha önce dağıtmış olduğunuz plist dosyasını aşağıda listelenen içerikle güncelleştirin ve JAMF'den yeniden dağıtın.

1.  **Bilgisayar** > **Yapılandırma Profilleri'nde** **, Özel****Ayarlar & Seçenekler** >  Uygulamaları'nı seçin
2. **Dosyayı Karşıya Yükle 'yi** seçin (PLIST dosyası)
3. Tercih etki alanını _com.microsoft.wdav_ olarak ayarlayın
4. Aşağıdaki plist dosyasını karşıya yükleyin

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>networkProtection</key> 
    <dict> 
        <key>enforcementLevel</key> 
        <string>block</string> 
    </dict> 
</dict> 
</plist> 
```

#### <a name="intune-deployment"></a>Intune dağıtımı

Başarılı bir Intune dağıtımı, ağ korumasının zorlama düzeyini ayarlamak için bir yapılandırma profili gerektirir.  
Bu yapılandırma profilini oluşturduktan sonra ağ korumasını etkinleştirmek istediğiniz cihazlara atayın.

##### <a name="configure-the-enforcement-level-using-intune"></a>Intune kullanarak zorlama düzeyini yapılandırma

> [!NOTE]
> Mac'te Uç Nokta için Microsoft Defender burada listelenen yönergeleri kullanarak zaten yapılandırdıysanız, daha önce dağıtmış olduğunuz plist dosyasını aşağıda listelenen içerikle güncelleştirin ve Intune'dan yeniden dağıtın.

1.  **Cihaz yapılandırmasını yönet'i** **** > açın. Profilleri **Yönet** > **Profil Oluştur'u** > seçin. ****
2. Profil için bir ad belirtin.  **Platform=macOS**  **değerini Profil türü=Özel** olarak değiştirin. **Yapılandır'ı** seçin.
3. Aşağıdaki yükü _com.microsoft.wdav.xml_ olarak kaydedin

```xml
<?xml version="1.0" encoding="utf-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1"> 
    <dict> 
        <key>PayloadUUID</key> 
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string> 
        <key>PayloadType</key> 
        <string>Configuration</string> 
        <key>PayloadOrganization</key> 
        <string>Microsoft</string> 
        <key>PayloadIdentifier</key> 
        <string>com.microsoft.wdav</string> 
        <key>PayloadDisplayName</key> 
        <string>Microsoft Defender ATP settings</string> 
        <key>PayloadDescription</key> 
        <string>Microsoft Defender ATP configuration settings</string> 
        <key>PayloadVersion</key> 
        <integer>1</integer> 
        <key>PayloadEnabled</key> 
        <true/> 
        <key>PayloadRemovalDisallowed</key> 
        <true/> 
        <key>PayloadScope</key> 
        <string>System</string> 
        <key>PayloadContent</key> 
        <array> 
            <dict> 
                <key>PayloadUUID</key> 
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string> 
                <key>PayloadType</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadOrganization</key> 
                <string>Microsoft</string> 
                <key>PayloadIdentifier</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadDisplayName</key> 
                <string>Microsoft Defender ATP configuration settings</string> 
                <key>PayloadDescription</key> 
                <string/> 
                <key>PayloadVersion</key> 
                <integer>1</integer> 
                <key>PayloadEnabled</key> 
                <true/> 
                <key>networkProtection</key> 
                <dict> 
                    <key>enforcementLevel</key> 
                    <string>block</string> 
                </dict> 
            </dict> 
        </array> 
    </dict> 
</plist>
```

4. Yukarıdaki dosyanın doğru kopyalandığını doğrulayın. Terminal'den aşağıdaki komutu çalıştırın ve Tamam çıkışını elde ettiğini doğrulayın:

```bash
plutil -lint com.microsoft.wdav.xml
```

5. Özel yapılandırma profili adı olarak _com.microsoft.wdav_ girin.
6. Yapılandırma profilini açın ve com.microsoft.wdav.xml dosyasını karşıya yükleyin. (Bu dosya 3. adımda oluşturulmuştur.)
7.  **Tamam'ı** seçin
8.  **Atamaları**  **Yönet'i** > seçin.  **Ekle** sekmesinde, ağ korumasını etkinleştirmek istediğiniz cihazları seçin.

## <a name="how-to-explore-the-features"></a>Özellikleri keşfetme

1. Web tehdit koruması kullanarak [kuruluşunuzu web tehditlerine karşı korumayı](web-threat-protection.md) öğrenin.
   - Web tehdit koruması, Uç Nokta için Microsoft Defender'da web korumasının bir parçasıdır. Cihazlarınızın web tehditlerine karşı güvenliğini sağlamak için ağ koruması kullanır.
2. [Özel Gösterge türündeki blokları almak için Özel Risk Göstergeleri](indicator-ip-domain.md) akışında ilerleyin.
3. [Web içeriği filtrelemeyi keşfedin](web-content-filtering.md).
   > [!NOTE]
   > Bir ilkeyi kaldırıyorsanız veya cihaz gruplarını aynı anda değiştiriyorsanız, bu durum ilke dağıtımında gecikmeye neden olabilir.
   > Profesyonel ipucu: Bir cihaz grubunda herhangi bir kategori seçmeden bir ilke dağıtabilirsiniz. Bu eylem, engelleme ilkesi oluşturmadan önce kullanıcı davranışını anlamanıza yardımcı olmak için yalnızca denetim ilkesi oluşturur.
4. [Uç Nokta için Microsoft Defender Cloud Apps için Defender ile tümleştirin](/defender-cloud-apps/mde-integration) ve ağ koruması etkinleştirilmiş macOS cihazlarınız uç nokta ilkesi zorlama özelliklerine sahip olur.
   > [!NOTE]
   > Bulma ve diğer özellikler şu anda bu platformlarda desteklenmiyor.

## <a name="scenarios"></a>Senaryo

Genel önizleme sırasında aşağıdaki senaryolar desteklenir:

### <a name="web-threat-protection"></a>Web tehdit koruması

Web tehdit koruması, Uç Nokta için Microsoft 365 Defender web korumasının bir parçasıdır. Cihazlarınızın web tehditlerine karşı güvenliğini sağlamak için ağ koruması kullanır. Web tehdit koruması, macOS için Microsoft Edge ve Chrome ve Firefox gibi popüler üçüncü taraf tarayıcılarla tümleştirilerek web ara sunucusu olmadan web tehditlerini durdurur. Web tehdit koruması, cihazları şirket içinde veya dışarıdayken koruyabilir. Web tehdit koruması aşağıdaki site türlerine erişimi durdurur:

- kimlik avı siteleri
- kötü amaçlı yazılım vektörleri
- sitelerinden yararlanma
- güvenilmeyen veya saygınlığı düşük siteler
- özel gösterge listenizde engellediğiniz siteler

:::image type="content" source="images/network-protection-reports-web-protection.png" alt-text="Web Koruması, web tehdit algılamalarını bildirir." lightbox="images/network-protection-reports-web-protection.png":::

Daha fazla bilgi için bkz [. Kuruluşunuzu web tehdidine karşı koruma](web-threat-protection.md)

### <a name="custom-indicators-of-compromise"></a>Güvenliğin Aşılmasına ilişkin Özel Göstergeler  

Risk (ICS) eşleştirmesinin göstergesi, her uç nokta koruma çözümünde önemli bir özelliktir. Bu özellik SecOps'a algılama ve engelleme (önleme ve yanıt) için göstergelerin listesini ayarlama olanağı verir.

Varlıkların algılanmasını, önlenmesini ve dışlanmasını tanımlayan göstergeler oluşturun. Gerçekleştirilecek eylemin yanı sıra eylemin ne zaman uygulanacağı ve uygulanacağı cihaz grubunun kapsamını tanımlayabilirsiniz.

Şu anda desteklenen kaynaklar Uç Nokta için Defender'ın bulut algılama altyapısı, otomatik araştırma ve düzeltme altyapısı ve uç nokta önleme altyapısıdır (Microsoft Defender Virüsten Koruma).

:::image type="content" source="images/network-protection-add-url-domain-indicator.png" alt-text="Ağ koruması ekleme URL'sini veya etki alanı göstergesini gösterir." lightbox="images/network-protection-add-url-domain-indicator.png":::

Daha fazla bilgi için bkz. [IP'ler ve URL'ler/etki alanları için göstergeler oluşturma](indicator-ip-domain.md).

### <a name="web-content-filtering"></a>Web içeriği filtreleme

Web içeriği filtreleme, Uç Nokta için Microsoft Defender ve [İş için Microsoft Defender'daki Web koruma](web-protection-overview.md) özelliklerinin bir parçasıdır. Web içeriği filtreleme, kuruluşunuzun web sitelerine erişimi içerik kategorilerine göre izlemesine ve düzenlemesine olanak tanır. Bu web sitelerinin çoğu (kötü amaçlı olmasalar bile) uyumluluk düzenlemeleri, bant genişliği kullanımı veya diğer endişeler nedeniyle sorunlu olabilir.

Belirli kategorileri engellemek için cihaz gruplarınız genelinde ilkeleri yapılandırın. Kategorinin engellenmesi, belirtilen cihaz grupları içindeki kullanıcıların kategoriyle ilişkili URL'lere erişmesini engeller. Engellenmeyen tüm kategoriler için URL'ler otomatik olarak denetlenür. Kullanıcılarınız URL'lere kesinti olmadan erişebilir ve daha özel bir ilke kararı oluşturmaya yardımcı olmak için erişim istatistiklerini toplarsınız. Görüntüledikleri sayfadaki bir öğe engellenen bir kaynağa çağrı yapıyorsa kullanıcılarınız bir engelleme bildirimi görür.

Web içeriği filtreleme, Ağ Koruması (Safari, Chrome, Firefox, Brave ve Opera) tarafından gerçekleştirilen bloklarla birlikte ana web tarayıcılarında kullanılabilir. Tarayıcı desteği hakkında daha fazla bilgi için bkz [. Önkoşullar](#prerequisites).

:::image type="content" source="images/network-protection-wcf-add-policy.png" alt-text="Ağ koruması web içeriği filtreleme ekleme ilkesini gösterir." lightbox="images/network-protection-wcf-add-policy.png":::

Raporlama hakkında daha fazla bilgi için bkz [. Web içeriği filtreleme](web-content-filtering.md).

### <a name="microsoft-defender-for-cloud-applications"></a>Bulut Uygulamaları için Microsoft Defender

Bulut Uygulamaları için Microsoft Defender / Bulut Uygulaması Kataloğu, uç nokta için Microsoft 365 Defender erişirken son kullanıcıların uyarılmasını istediğiniz uygulamaları tanımlar ve _bunları İzlendi_ olarak işaretler. İzlenen uygulamalar altında listelenen etki alanları daha sonra Uç Nokta için Microsoft 365 Defender eşitlenir:

:::image type="content" source="images/network-protection-macos-mcas-monitored-apps.png" alt-text="Ağ koruması izlenen uygulamaları gösterir.":::

10-15 dakika içinde, bu etki alanları Uç Nokta Güvenlik Merkezi için Microsoft 365 Defender'nde Action=Warn ile URL'ler/Etki Alanları > altında listelenir. Zorlama SLA'sı içinde (bu makalenin sonundaki ayrıntılara bakın), son kullanıcılar bu etki alanlarına erişmeye çalışırken uyarı iletileri alır:

:::image type="content" source="images/network-protection-macos-indicators-urls-domains-warn.png" alt-text="URL'ler veya etki alanları uyarısı için ağ koruma göstergelerini gösterir.":::

Son kullanıcı izlenen etki alanlarına erişmeye çalıştığında Uç Nokta için Microsoft 365 Defender tarafından uyarılır.

- Kullanıcı, engellenen uygulamanın adı (örneğin Blogger.com) dahil olmak üzere işletim sistemi tarafından görüntülenecek olan aşağıdaki bildirim iletisiyle birlikte düz blok deneyimi elde eder

  :::image type="content" source="images/network-protection-macos-content-blocked.png" alt-text="Son kullanıcı ağ koruması içeriği engellendi bildirimini gösterir.":::

Son kullanıcı bir _blokla_ karşılaşırsa, kullanıcının iki olası çözümü olur:

#### <a name="user-bypass"></a>Kullanıcı atlama

- **Bildirim iletisi deneyimi için**: Engellemeyi kaldır düğmesine basın. Kullanıcı web sayfasını yeniden yükleyerek devam edip bulut uygulamasını kullanabilir. (Bu eylem, sonraki 24 saat için geçerlidir ve bundan sonra kullanıcının engellemesini bir kez daha kaldırması gerekir)

#### <a name="user-education"></a>Kullanıcı eğitimi

- **Bildirim iletisi deneyimi için**: Bildirim iletisinin kendisine basın. Son kullanıcı, Bulut Uygulamaları için Microsoft Defender'da genel olarak ayarlanan özel bir yeniden yönlendirme URL'sine yönlendirilir (Bu sayfanın en altında daha fazla bilgi)

> [!NOTE]
> İzleme uygulama başına atlar** – Bulut Uygulamaları için Microsoft Defender'ın _Uygulama_ sayfasında kaç kullanıcının uyarıyı atlamış olduğunu izleyebilirsiniz.

  :::image type="content" source="images/network-protection-macos-mcas-cloud-app-security.png" alt-text="Ağ koruması bulut uygulaması güvenliğine genel bakış bilgilerini gösterir.":::

## <a name="appendix"></a>Ek

### <a name="end-user-education-center-sharepoint-site-template"></a>Son kullanıcı eğitim merkezi SharePoint site şablonu

Birçok kuruluş için, Bulut Uygulamaları için Microsoft Defender tarafından sağlanan bulut denetimlerini almak ve yalnızca gerektiğinde son kullanıcılarla ilgili sınırlamalar belirlemek değil, aynı zamanda onları aşağıdaki konularda eğitmek ve onlara koçluk yapmak da önemlidir:

- belirli bir olay
- neden oldu?
- bu kararın arkasındaki düşünce nedir?
- blok sitelerle karşılaşmanın riski nasıl azaltılabilir?

Beklenmeyen bir davranışla karşılaştığında, kullanıcıların karışıklıkları mümkün olduğunca fazla bilgi vererek, yalnızca neler olduğunu açıklamakla kalmaz, aynı zamanda işlerini tamamlamak üzere bir bulut uygulaması seçtiklerinde daha fazla bilgi edinmelerini sağlamak için de azaltılabilir. Örneğin, bu bilgiler şunları içerebilir:

- İnternet ve bulut kullanımı için kuruluş güvenlik ve uyumluluk ilkeleri ve yönergeleri
- Kullanım için onaylı/önerilen bulut uygulamaları
- Kullanım için kısıtlanmış/engellenen bulut uygulamaları

Bu sayfa için, kuruluşunuzun temel bir SharePoint sitesi kullanmasını öneririz.  

### <a name="important-things-to-know"></a>Bilmeniz gereken önemli şeyler

1. Uygulama etki alanlarının yayılması ve uç nokta cihazlarında güncelleştirilerek _İzlendi_ olarak işaretlenmesi iki saate kadar (genellikle daha az) sürebilir.  
2. Varsayılan olarak, kuruluştaki tüm eklenen uç noktalar için Bulut Uygulamaları için Microsoft Defender portalında İzlendi olarak işaretlenmiş tüm uygulamalar ve etki alanları için eylem gerçekleştirilir.  
3. Tam URL'ler şu anda desteklenmemektedir ve Bulut Uygulamaları için Microsoft Defender'dan Uç Nokta için Microsoft 365 Defender'a gönderilmez. Bulut Uygulamaları için Microsoft Defender izlenen uygulamalar altında tam URL'ler listeleniyorsa, kullanıcı erişim girişimi konusunda uyarı almaz (örneğin, drive.google.com desteklenirken google.com/drive desteklenmez).  

Üçüncü taraf tarayıcılarda son kullanıcı bildirimi yok mu? Bildirim iletisi ayarlarınızı denetleme

## <a name="see-also"></a>Ayrıca bkz.

- [Mac'te Uç Nokta için Microsoft 365 Defender](microsoft-defender-endpoint-mac.md)
- [Bulut Uygulamaları için Microsoft Microsoft 365 Defender ile Uç Nokta tümleştirmesi için Microsoft 365 Defender](/defender-cloud-apps/mde-integration.md)
- [Microsoft Edge'deki yenilikçi özellikleri tanımaya başlama](https://www.microsoft.com/edge/features)
- [Ağınızı koruyun](network-protection.md)
- [Ağ korumasını açın](enable-network-protection.md)
- [Web koruması](web-protection-overview.md)
- [Göstergeleri oluşturun](manage-indicators.md)
- [Web içeriği filtreleme](web-content-filtering.md)
- [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
