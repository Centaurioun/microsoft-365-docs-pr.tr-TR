---
title: Hatalı sitelere Linux bağlantılarını önlemeye yardımcı olmak için ağ korumasını kullanma
description: Linux kullanıcılarının bilinen kötü amaçlı ve şüpheli ağ adreslerine erişmesini engelleyerek ağınızı koruyun
keywords: Ağ koruması, Linux açıklarından yararlanma, kötü amaçlı web sitesi, ip, etki alanı, etki alanları, komut ve denetim, SmartScreen, bildirim
ms.service: microsoft-365-security
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
ms.subservice: mde
ms.topic: overview
ms.collection:
- m365-security
- tier2
ms.date: ''
search.appverid: met150
ms.openlocfilehash: 4f087588f122748220947f9d115f07f9e87b0577
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68227162"
---
# <a name="network-protection-for-linux"></a>Linux için ağ koruması

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

## <a name="overview"></a>Genel bakış

Microsoft, Ağ Koruması işlevselliğini Linux'a getiriyor.

Ağ koruması, cihazlarınızın saldırı yüzeyini İnternet tabanlı olaylardan azaltmaya yardımcı olur. Çalışanların aşağıdakileri barındırabilecek tehlikeli etki alanlarına erişmek için herhangi bir uygulama kullanmasını engeller:

- kimlik avı dolandırıcılığı
- Patla -tır
- İnternet'te diğer kötü amaçlı içerikler

Ağ koruması, Microsoft Defender [SmartScreen'in](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview.md) kapsamını genişleterek düşük saygınlık kaynaklarına bağlanmaya çalışan tüm giden HTTP trafiğini engeller. Giden HTTP trafiğindeki bloklar etki alanına veya konak adına bağlıdır.

## <a name="web-content-filtering-for-linux"></a>Linux için web içeriği filtreleme

Linux için Ağ koruması ile test için web içeriği filtrelemeyi kullanabilirsiniz. Bkz. [Web içeriği filtreleme](web-content-filtering.md).

### <a name="known-issues"></a>Bilinen sorunlar

- Ağ Koruması, sanal özel ağ (VPN) tüneli olarak uygulanır. Özel nftables/iptables betiklerini kullanan gelişmiş paket yönlendirme seçenekleri mevcuttur.
- Block/Warn UX kullanılamıyor
  - Daha fazla tasarım iyileştirmesi yapmak için müşteri geri bildirimleri toplanıyor

> [!NOTE]
> Linux Web Tehdit Koruması'nın etkinliğini değerlendirmek için, tüm dağıtımlar için varsayılan olan Firefox tarayıcısını kullanmanızı öneririz.

### <a name="prerequisites"></a>Önkoşullar

- Lisanslama: [Windows olmayan platformlar için](non-windows.md#licensing-requirements) Uç Nokta için Microsoft Defender bulunan Uç Nokta için Microsoft Defender kiracı (deneme olabilir) ve platforma özgü gereksinimler
- Eklenen Makineler:
  - **En düşük Linux sürümü**: Desteklenen dağıtımların listesi için bkz. [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md).
  - **Uç Nokta için Microsoft Defender Linux istemci sürümü**: 101.78.13 -insiderSlow(Önizleme)

## <a name="instructions"></a>Talimat -ları

Linux'ı el ile dağıtma, bkz[. Linux'ta Uç Nokta için Microsoft Defender el ile dağıtma](linux-install-manually.md)

Aşağıdaki örnekte insider-Slow kanalı için ubuntu 20.04 üzerindeki mdatp paketine gereken komut dizisi gösterilmektedir.

```bash
curl -o microsoft.list https://packages.microsoft.com/config/ubuntu/20.04/insiders-slow.list 
sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-insiders-slow.list 
sudo apt-get install gpg 
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add - 
sudo apt-get install apt-transport-https 
sudo apt-get update 
sudo apt install -y mdatp 
```

### <a name="device-onboarding"></a>Cihaz Ekleme

Cihazı eklemek için Linux sunucusu için Python ekleme paketini Microsoft 365 Defender -> Ayarlar -> Cihaz Yönetimi -> Ekleme'den indirmeniz ve çalıştırmanız gerekir:

```bash
sudo python3 MicrosoftDefenderATPOnboardingLinuxServer.py 
```

### <a name="manually-enable-network-protection"></a>Ağ korumasını el ile etkinleştirme

1. "networkProtection" özelliğini açın, "/etc/opt/microsoft/mdatp/wdavcfg" öğesini düzenleyin ve **networkProtection** ayarını **etkin** olarak ayarlayın.  
2. Aşağıdaki komutu çalıştırarak mdatp hizmetini yeniden başlatın:

```bash
sudo systemctl restart mdatp 
```
> :::image type="content" source="images/network-protection-linux-mdatp-restart.png" alt-text="Linux mdatp yeniden başlatmayı gösterir." lightbox="images/network-protection-linux-mdatp-restart.png":::

### <a name="configure-the-enforcement-level"></a>Zorlama düzeyini yapılandırma

Ağ koruması varsayılan olarak devre dışıdır, ancak aşağıdaki modlardan birinde (zorlama düzeyleri olarak da adlandırılır) çalışacak şekilde yapılandırılabilir:

- **Denetim**: İş kolu uygulamalarını etkilemediğinden emin olmak veya blokların ne sıklıkta oluştuğu hakkında fikir edinmek için kullanışlıdır
- **Engelle**: ağ koruması kötü amaçlı web sitelerine bağlantıyı engeller
- **Devre dışı**: Ağ Koruması ile ilişkili tüm bileşenler devre dışı bırakıldı

```bash
sudo mdatp config network-protection enforcement-level --value block
```

veya

```bash
sudo mdatp config network-protection enforcement-level --value audit
```

Ağ Koruması'nın başarıyla başlatıldığını onaylamak için Terminal'den aşağıdaki komutu çalıştırın; "started" yazdırdığını doğrulayın:

```bash
mdatp health --field network_protection_status
```

### <a name="validation"></a>Doğrulama

C. Ağ Koruması'nın her zaman engellenen siteler üzerinde etkisi olup olmadığını denetleyin:

- [http://www.smartscreentestratings2.net](http://www.smartscreentestratings2.net)
- [https://www.smartscreentestratings2.net](https://www.smartscreentestratings2.net)
- [http://malw-090-0-1.phsh-005-0-1.smartscreentestratings.com/](http://malw-090-0-1.phsh-005-0-1.smartscreentestratings.com/)

B. Tanılama günlüklerini inceleme

```bash
$ sudo mdatp log level set --level debug 
$ sudo tail -f /var/log/microsoft/mdatp/microsoft_defender_np_ext.log 
```

#### <a name="to-exit-the-validation-mode"></a>Doğrulama modundan çıkmak için

Ağ korumasını devre dışı bırakın ve ağ bağlantısını yeniden başlatın:

```bash
$ sudo mdatp config network-protection enforcement-level --value disabled
```

## <a name="advanced-configuration"></a>Gelişmiş yapılandırma

Varsayılan olarak, Linux ağ koruması varsayılan ağ geçidinde etkindir; yönlendirme ve tünel oluşturma dahili olarak yapılandırılır.
Ağ arabirimlerini özelleştirmek için **networkSetupMode** parametresini **/opt/microsoft/mdatp/conf/**  yapılandırma dosyasından değiştirin ve hizmeti yeniden başlatın:

```bash
sudo systemctl restart  mdatp 
```

Yapılandırma dosyası, kullanıcının şunları özelleştirmesine de olanak tanır:

- proxy ayarı
- SSL sertifika depoları
- tünel cihazı adı
- IP
- ve daha fazlası

Varsayılan değerler[, Linux üzerinde Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md) açıklandığı gibi tüm dağıtımlar için test edilmiştir

### <a name="microsoft-defender-portal"></a>Microsoft Defender portalı

Ayrıca **, Microsoft Defender** >  **Settings Endpoints** >  > **Gelişmiş özelliklerinde** **'Özel ağ göstergeleri'** iki durumlu düğmesinin _etkinleştirildiğinden_ emin olun.

> [!IMPORTANT]
> Yukarıdaki **'Özel ağ göstergeleri'** iki durumlu düğmesi, Windows dahil olmak üzere Ağ Koruması desteğine sahip TÜM **platformlar için Özel Göstergeler** etkinleştirmesini **denetler. Göstergelerin zorunlu kılınması için Windows'ta Ağ Koruması'nın da açıkça etkinleştirilmiş olması gerektiğini anımsatıcı.

>:::image type="content" source="images/network-protection-linux-defender-security-center-advanced-features-settings.png" alt-text="MEM Profil Oluştur" lightbox="images/network-protection-linux-defender-security-center-advanced-features-settings.png":::

## <a name="how-to-explore-the-features"></a>Özellikleri keşfetme

1. Web tehdit koruması kullanarak [kuruluşunuzu web tehditlerine karşı korumayı](web-threat-protection.md) öğrenin.
   - Web tehdit koruması, Uç Nokta için Microsoft Defender'da web korumasının bir parçasıdır. Cihazlarınızın web tehditlerine karşı güvenliğini sağlamak için ağ koruması kullanır.
2. [Özel Gösterge türündeki blokları almak için Özel Risk Göstergeleri](indicator-ip-domain.md) akışında ilerleyin.
3. [Web içeriği filtrelemeyi keşfedin](web-content-filtering.md).
   > [!NOTE]
   > Bir ilkeyi kaldırıyorsanız veya cihaz gruplarını aynı anda değiştiriyorsanız, bu durum ilke dağıtımında gecikmeye neden olabilir.
   > Profesyonel ipucu: Bir cihaz grubunda herhangi bir kategori seçmeden bir ilke dağıtabilirsiniz. Bu eylem, engelleme ilkesi oluşturmadan önce kullanıcı davranışını anlamanıza yardımcı olmak için yalnızca denetim ilkesi oluşturur.
   >
   > Cihaz grubu oluşturma, Uç Nokta Için Defender Plan 1 ve Plan 2'de desteklenir.  
 
4. [Uç Nokta için Microsoft Defender Cloud Apps için Defender ile tümleştirin](/defender-cloud-apps/mde-integration) ve ağ koruması etkinleştirilmiş macOS cihazlarınız uç nokta ilkesi zorlama özelliklerine sahip olur.
   > [!NOTE]
   > Bulma ve diğer özellikler şu anda bu platformlarda desteklenmiyor.

## <a name="scenarios"></a>Senaryo

Genel önizleme sırasında aşağıdaki senaryolar desteklenir:

### <a name="web-threat-protection"></a>Web tehdit koruması

Web tehdit koruması, Uç Nokta için Microsoft Defender'da Web korumasının bir parçasıdır. Cihazlarınızın web tehditlerine karşı güvenliğini sağlamak için ağ koruması kullanır. Web tehdit koruması, Microsoft Edge ve Chrome ve Firefox gibi popüler üçüncü taraf tarayıcılarla tümleştirilerek web proxy'si olmadan web tehditlerini durdurur. Web tehdit koruması, cihazları şirket içinde veya dışarıdayken koruyabilir. Web tehdit koruması aşağıdaki site türlerine erişimi durdurur:

- kimlik avı siteleri
- kötü amaçlı yazılım vektörleri
- sitelerinden yararlanma
- güvenilmeyen veya saygınlığı düşük siteler
- özel gösterge listenizde engellediğiniz siteler

>:::image type="content" source="images/network-protection-reports-web-protection.png" alt-text="Web Koruması, web tehdit algılamalarını bildirir." lightbox="images/network-protection-reports-web-protection.png":::

Daha fazla bilgi için bkz [. Kuruluşunuzu web tehdidine karşı koruma](web-threat-protection.md)

#### <a name="custom-indicators-of-compromise"></a>Güvenliğin Aşılmasına ilişkin Özel Göstergeler  

Risk (ICS) eşleştirmesinin göstergesi, her uç nokta koruma çözümünde önemli bir özelliktir. Bu özellik SecOps'a algılama ve engelleme (önleme ve yanıt) için göstergelerin listesini ayarlama olanağı verir.

Varlıkların algılanmasını, önlenmesini ve dışlanmasını tanımlayan göstergeler oluşturun. Gerçekleştirilecek eylemin yanı sıra eylemin ne zaman uygulanacağı ve uygulanacağı cihaz grubunun kapsamını tanımlayabilirsiniz.

Şu anda desteklenen kaynaklar Uç Nokta için Defender'ın bulut algılama altyapısı, otomatik araştırma ve düzeltme altyapısı ve uç nokta önleme altyapısıdır (virüsten koruma Microsoft Defender).

>:::image type="content" source ="images/network-protection-add-url-domain-indicator.png" alt-text="Ağ koruması ekleme URL'sini veya etki alanı göstergesini gösterir." lightbox="images/network-protection-add-url-domain-indicator.png":::

Daha fazla bilgi için bkz. [IP'ler ve URL'ler/etki alanları için göstergeler oluşturma](indicator-ip-domain.md).

### <a name="web-content-filtering"></a>Web içeriği filtreleme

Web içeriği filtreleme, Uç Nokta için Microsoft Defender ve [İş için Microsoft Defender'daki Web koruma](web-protection-overview.md) özelliklerinin bir parçasıdır. Web içeriği filtreleme, kuruluşunuzun web sitelerine erişimi içerik kategorilerine göre izlemesine ve düzenlemesine olanak tanır. Bu web sitelerinin çoğu (kötü amaçlı olmasalar bile) uyumluluk düzenlemeleri, bant genişliği kullanımı veya diğer endişeler nedeniyle sorunlu olabilir.

Belirli kategorileri engellemek için cihaz gruplarınız genelinde ilkeleri yapılandırın. Kategorinin engellenmesi, belirtilen cihaz grupları içindeki kullanıcıların kategoriyle ilişkili URL'lere erişmesini engeller. Engellenmeyen tüm kategoriler için URL'ler otomatik olarak denetlenür. Kullanıcılarınız URL'lere kesinti olmadan erişebilir ve daha özel bir ilke kararı oluşturmaya yardımcı olmak için erişim istatistiklerini toplarsınız. Görüntüledikleri sayfadaki bir öğe engellenen bir kaynağa çağrı yapıyorsa kullanıcılarınız bir engelleme bildirimi görür.

Web içeriği filtreleme, Windows Defender SmartScreen (Microsoft Edge) ve Ağ Koruması (Chrome, Firefox, Brave ve Opera) tarafından gerçekleştirilen bloklarla büyük web tarayıcılarında kullanılabilir. Tarayıcı desteği hakkında daha fazla bilgi için bkz [. Önkoşullar](#prerequisites).

> :::image type="content" source="images/network-protection-wcf-add-policy.png" alt-text="Ağ koruması web içeriği filtreleme ekleme ilkesini gösterir." lightbox="images/network-protection-wcf-add-policy.png":::

Raporlama hakkında daha fazla bilgi için bkz [. Web içeriği filtreleme](web-content-filtering.md).

### <a name="microsoft-defender-for-cloud-applications"></a>Bulut Uygulamaları için Microsoft Defender

Bulut Uygulamaları /Bulut Uygulaması Kataloğu için Microsoft Defender, uç nokta için Microsoft 365 Defender erişirken son kullanıcıların uyarılmasını istediğiniz uygulamaları tanımlar ve _bunları İzlendi_ olarak işaretler. İzlenen uygulamalar altında listelenen etki alanları daha sonra Uç Nokta için Microsoft 365 Defender eşitlenir:

> :::image type="content" source="images/network-protection-macos-mcas-monitored-apps.png" alt-text="Ağ koruması mcas izlenen uygulamaları gösterir." lightbox="images/network-protection-macos-mcas-monitored-apps.png":::

10-15 dakika içinde, bu etki alanları Uç Nokta Güvenlik Merkezi için Microsoft 365 Defender'nde Action=Warn ile URL'ler/Etki Alanları > altında listelenir. Zorlama SLA'sı içinde (bu makalenin sonundaki ayrıntılara bakın).

> :::image type="content" source="images/network-protection-macos-mcas-cloud-app-security.png" alt-text="Ağ koruması mcas bulut uygulaması güvenliğini gösterir." lightbox="images/network-protection-macos-mcas-cloud-app-security.png":::

## <a name="see-also"></a>Ayrıca bkz.

- [Ağınızı koruyun](network-protection.md)
- [Ağ korumasını açın](enable-network-protection.md)
- [Web koruması](web-protection-overview.md)
- [Göstergeleri oluşturun](manage-indicators.md)
- [Web içeriği filtreleme](web-content-filtering.md)
- [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
