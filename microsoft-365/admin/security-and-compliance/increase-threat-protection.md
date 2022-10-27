---
title: İş için Microsoft 365 için tehdit korumasını artırma
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- highpri
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- VSBFY23
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
- adminvideo
search.appverid:
- BCS160
- MET150
description: Office 365 için Microsoft Defender ayarlayın ve hassas verileri kimlik avına, kötü amaçlı yazılımlara ve diğer tehditlere karşı koruma altına alın.
ms.openlocfilehash: 6d604cec1925259ba1378153afe7feeb299b1628
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68731117"
---
# <a name="increase-threat-protection-for-microsoft-365-for-business"></a>İş için Microsoft 365 için tehdit korumasını artırma

YouTube'da [Microsoft 365 küçük işletme yardımına](https://go.microsoft.com/fwlink/?linkid=2197659) göz atın.

Bu makale, kimlik avına, kötü amaçlı yazılımlara ve diğer tehditlere karşı korunmak için Microsoft 365 aboneliğinizdeki korumayı artırmanıza yardımcı olur. Bu öneriler, hukuk büroları ve sağlık klinikleri gibi daha fazla güvenlik gereksinimi olan kuruluşlar için uygundur.

Başlamadan önce Office 365 Güvenli Puanınızı denetleyin. Office 365 Güvenli Puan, kuruluşunuzun güvenliğini normal etkinliklerinize ve güvenlik ayarlarınıza göre analiz eder ve bir puan atar. Geçerli puanınızı not alarak başlayın. Puanınızı artırmak için bu makalede önerilen eylemleri tamamlayın. Amaç maksimum puanı elde etmek değil, ortamınızı korumak için kullanıcılarınız için üretkenliği olumsuz etkilemeyen fırsatların farkında olmaktır.

Daha fazla bilgi için bkz. [Microsoft Güvenli Puanı](../../security/defender/microsoft-secure-score.md).

## <a name="watch-raise-the-level-of-protection-against-malware-in-mail"></a>İzleyin: Postada kötü amaçlı yazılımlara karşı koruma düzeyini yükseltme

Office 365 veya Microsoft 365 ortamınız kötü amaçlı yazılımlara karşı koruma içerir. Kötü amaçlı yazılımlarda yaygın olarak kullanılan dosya türlerine sahip ekleri engelleyerek bu korumayı artırabilirsiniz. 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OA7Z?autoplay=false]

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 yönetim merkezi</a> **Daha fazlasını göster**, **Yönetici merkezleri** ve ardından **Güvenlik'i** seçin.

1. **Email & işbirliği** \> **İlkeleri & kurallar** \> **Tehdit ilkeleri'ne** gidin.

1. Kullanılabilir ilkelerden **Kötü amaçlı yazılımdan koruma'yı** seçin.

E-postada kötü amaçlı yazılım korumasını artırmak için:

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalında</a>, İlkeler **bölümünde** **Email & işbirliği** \> **İlkeleri & kuralları** \> **Tehdit ilkeleri** \> **Kötü amaçlı yazılımdan koruma** bölümüne gidin.

1. **Kötü amaçlı yazılımdan koruma** sayfasında **Varsayılan (Varsayılan)** seçeneğine çift tıklayın. Açılır öğe görüntülenir. 

1. Açılır pencerenin alt kısmındaki **Koruma ayarlarını düzenle'yi** seçin. 

1. **Koruma ayarları'nın** altında **Ortak ekler filtresini etkinleştir'in** yanındaki onay kutusunu seçin. Engellenen dosya türleri bu denetimin hemen altında listelenir. Şu dosya türlerini eklediğinizden emin olun:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Dosya türleri eklemek veya silmek için listenin sonundaki **Dosya türlerini özelleştir'i** seçin.

1. **Kaydet'i seçin.**

Daha fazla bilgi için bkz. [EOP'de kötü amaçlı yazılımdan koruma](../../security/office-365-security/anti-malware-protection.md).

## <a name="watch-protect-against-ransomware"></a>İzleyin: Fidye yazılımlarından koruma

[YouTube kanalımızda](https://go.microsoft.com/fwlink/?linkid=2198018) bu videoya ve diğer videolara göz atın.

Fidye yazılımı, dosyaları şifreleyerek veya bilgisayar ekranlarını kilitleyerek verilere erişimi kısıtlar. Daha sonra verilere erişim karşılığında genellikle Bitcoin gibi kripto para birimleri biçiminde "fidye" isteyerek kurbanlardan para sızdırmaya çalışır.

Fidye yazılımlarına karşı koruma sağlamak için, fidye yazılımı için yaygın olarak kullanılan dosya uzantılarını engellemek için bir veya daha fazla posta akışı kuralı oluşturun. ( [Bu kuralları İzleme: Postadaki kötü amaçlı yazılımlara karşı koruma düzeyini yükseltme adımına](#watch-raise-the-level-of-protection-against-malware-in-mail) eklediniz.) Bu ekleri alan kullanıcıları e-postayla da uyarabilirsiniz.

Önceki adımda engellediğiniz dosyalara ek olarak, makro içeren Office dosya eklerini açmadan önce kullanıcıları uyarmak için bir kural oluşturmak iyi bir uygulamadır. Fidye yazılımı makroların içine gizlenebilir, bu nedenle kullanıcıları tanımadıkları kişilerden bu dosyaları açmamaları konusunda uyarabilirsiniz.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

1. konumundaki yönetim merkezinden [https://admin.microsoft.com](https://admin.microsoft.com)**, Yönetici merkezleri** altında **Exchange'i** seçin.

1. Sol taraftaki menüden **posta akışı'nı** seçin.
 
1. Kurallar sekmesinde, artı (+) simgesinin yanındaki oku seçin ve ardından **Yeni kural oluştur'u** seçin.

1. **Yeni kural** sayfasında, kuralınız için bir ad girin, en alta kaydırın ve **diğer seçenekler'i** seçin.

Posta taşıma kuralı oluşturmak için:

1. konumundaki yönetim merkezine gidin ve **Exchange'i**<https://admin.microsoft.com> **Yönetici merkezleri'ni** \> seçin.

2. **Posta akışı** kategorisinde **kurallar'ı** seçin.

3. öğesini ve **+** ardından **Yeni kural oluştur'u** seçin.

4. Tüm **seçenekler** kümesini görmek için iletişim kutusunun alt kısmındaki Diğer seçenekler'i seçin.

5. Kural için aşağıdaki tabloda yer alan ayarları uygulayın. Değiştirmek istemediğiniz sürece ayarların geri kalanı için varsayılan değerleri kullanın.

6. **Kaydet**'i seçin.

|Ayar|Office dosyalarının eklerini açmadan önce kullanıcıları uyarma|
|---|---|
|Name|Fidye yazılımı önleme kuralı: kullanıcıları uyarma|
|ise bu kuralı uygulayın. . .|Herhangi bir ek . . . dosya uzantısı ile eşleşir. . .|
|Sözcükleri veya tümcecikleri belirtme|Şu dosya türlerini ekleyin:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm|
|Aşağıdakini yapın. . .|Alıcıya iletiyle bildirme|
|İleti metni sağlama|Kötü amaçlı kod içeren makrolar içerebileceğinden, bu tür dosyaları bilmediğiniz kişilerden açmayın.|

Daha fazla bilgi için bkz.:

- [Fidye yazılımı: riski azaltma](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [OneDrive'ınızı geri yükleme](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="stop-auto-forwarding-for-email"></a>E-posta için otomatik iletmeyi durdurma

Kullanıcının posta kutusuna erişim elde eden bilgisayar korsanları, posta kutusunu e-postayı otomatik olarak iletecek şekilde ayarlayarak postaları çalabilir. Bu, kullanıcının farkındalığı olmadan bile gerçekleşebilir. Bunun olmasını önlemek için bir posta akışı kuralı yapılandırın.

Posta taşıma kuralı oluşturmak için şu adımları izleyin:

1. Microsoft 365 yönetim merkezi **Exchange'i Yönetici merkezleri'ni** \> **seçin.**

2. **Posta akışı** kategorisinde **kurallar'ı** seçin.

3. öğesini ve **+** ardından **Yeni kural oluştur'u** seçin.

4. Tüm seçenekleri görmek için iletişim kutusunun altındaki **Diğer seçenekler'i** seçin.

5. Aşağıdaki tabloda yer alan ayarları uygulayın. Değiştirmek istemediğiniz sürece ayarların geri kalanı için varsayılan değerleri kullanın.

6. **Kaydet**'i seçin.

|Ayar|Office dosyalarının eklerini açmadan önce kullanıcıları uyarma|
|---|---|
|Name|E-postanın dış etki alanlarına otomatik olarak iletilmesini engelleme|
|Eğer bu kuralı uygula ...|Gönderen. . . dış/iç şeklindedir. . . Kuruluşun içinde|
|Koşul ekle|İleti özellikleri. . . ileti türünü ekleyin. . . Otomatik iletme|
|Aşağıdakini yapın...|iletisini engelleyin. . . iletisini reddedin ve bir açıklama ekleyin.|
|İleti metni sağlama|E-postanın bu kuruluş dışında otomatik olarak iletilmesi güvenlik nedeniyle engellenir.|

## <a name="watch-protect-your-email-from-phishing-attacks"></a>İzleyin: E-postanızı kimlik avı saldırılarına karşı koruma

[YouTube kanalımızda](https://go.microsoft.com/fwlink/?linkid=2198014) bu videoya ve diğer videolara göz atın.

Office 365 veya Microsoft 365 ortamınız için bir veya daha fazla özel etki alanı yapılandırdıysanız, hedeflenen kimlik avı koruması yapılandırabilirsiniz. Office 365 için Microsoft Defender bir parçası olan kimlik avı koruması, kuruluşunuzun kötü amaçlı kimliğe bürünme tabanlı kimlik avı saldırılarına ve diğer kimlik avı saldırılarına karşı korunmasına yardımcı olabilir. Özel bir etki alanı yapılandırmadıysanız bunu yapmanız gerekmez.

En önemli kullanıcılarınızı ve özel etki alanınızı korumak için bir ilke oluşturarak bu korumayı kullanmaya başlamanızı öneririz.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalına</a> gidin.

2. İlkeler **bölümünde** **Email & işbirliği** \> **İlkeleri & kuralları** \> **Tehdit ilkeleri** \> **Kimlik avı önleme** bölümüne gidin.

3. **Kimlik avı önleme** sayfasında **+ Oluştur'u** seçin. Kimlik avı önleme ilkenizi tanımlama işleminde size yol gösteren bir sihirbaz başlatılır.

4. Aşağıdaki tabloda önerilen ilkenizin adını, açıklamasını ve ayarlarını belirtin. Diğer ayrıntılar için bkz. [Office 365 için Microsoft Defender seçeneklerinde kimlik avı önleme ilkesi hakkında bilgi edinin](../../security/office-365-security/set-up-anti-phishing-policies.md).

5. Ayarlarınızı gözden geçirdikten sonra **, Uygun şekilde Bu ilkeyi oluştur** veya **Kaydet'i** seçin.

|Ayar veya seçenek|Önerilen ayar|
|---|---|
|Name|Etki alanı ve en değerli kampanya personeli|
|Açıklama|En önemli personelin ve etki alanımızın kimliğine bürünülmediğinden emin olun.|
|Korunacak kullanıcıları ekleme|**+ Koşul ekle'yi seçin, Alıcıdır**. Kullanıcı adlarını yazın veya adayın, kampanya yöneticisinin ve diğer önemli personel üyelerinin e-posta adresini girin. Kimliğe bürünmeye karşı korumak istediğiniz en fazla 20 iç ve dış adres ekleyebilirsiniz.|
|Korunacak etki alanları ekleme|**+ Koşul ekle'yi seçin, Alıcı etki alanı.** Tanımladıysanız Microsoft 365 aboneliğinizle ilişkili özel etki alanını girin. Birden fazla etki alanı girebilirsiniz.|
|Eylemleri seçme|E-posta kimliğine bürünülen bir kullanıcı tarafından gönderiliyorsa: **İletiyi başka bir e-posta adresine yeniden yönlendir'i** seçin ve güvenlik yöneticisinin e-posta adresini yazın; örneğin, *Alice<span><span>@contoso.com*. E-posta kimliğine bürünülen bir etki alanı tarafından gönderiliyorsa: **İletiyi karantinaya al'ı** seçin.|
|Posta kutusu zekası|Varsayılan olarak, yeni bir kimlik avı önleme ilkesi oluşturduğunuzda posta kutusu zekası seçilir. En iyi sonuçlar için bu ayarı **Açık** bırakın.|
|Güvenilir gönderenler ve etki alanları ekleme|Burada kendi etki alanınızı veya diğer güvenilen etki alanlarını ekleyebilirsiniz.|
|Uygulandığı yer|**Alıcı etki alanı'nı** seçin. **Bunlardan herhangi biri'nin** altında **Seç'i** seçin. **+ Ekle'yi** seçin. Etki alanı adının yanındaki onay kutusunu (örneğin, *contoso) seçin.<span><span> listesinden com'a* gidin ve **Ekle'yi** seçin. **Bitti'yi** seçin.|

## <a name="watch-protect-against-malicious-attachments-and-files-with-safe-attachments"></a>İzleyin: Güvenli Ekler ile kötü amaçlı eklere ve dosyalara karşı koruma

[YouTube kanalımızda](https://go.microsoft.com/fwlink/?linkid=2198019) bu videoya ve diğer videolara göz atın.

Kişiler belgeler, sunular, elektronik tablolar ve daha fazlası gibi ekleri düzenli olarak gönderin, alın ve paylaşın. Yalnızca e-posta iletisine bakarak bir ekin güvenli mi yoksa kötü amaçlı mı olduğunu söylemek her zaman kolay değildir. Daha önce Microsoft 365 ATP veya Gelişmiş Tehdit Koruması olarak adlandırılan Office 365 için Microsoft Defender, Güvenli Ek koruması içerir, ancak bu koruma varsayılan olarak açık değildir. Bu korumayı kullanmaya başlamak için yeni bir kural oluşturmanızı öneririz. Bu koruma SharePoint, OneDrive ve Microsoft Teams'deki dosyalara genişletir.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWtn3I?autoplay=false]

1. [Yönetim merkezine](https://admin.microsoft.com) gidin ve **Kurulum'u** seçin.
1. **Gelişmiş tehditlere karşı korumayı artırmak** için ekranı aşağı kaydırın. **Görünüm**, **Yönet** ve ardından **ATP güvenli eklerini** seçin.
1. Güvenli ekler kuralınızı ve ardından **Düzenle** simgesini seçin.
1. **Ayarlar'ı** seçin ve engelle'nin seçili olduğunu doğrulayın.
1. Aşağı kaydırın. **Yeniden yönlendirmeyi etkinleştir'i** seçin ve e-posta adresinizi veya engellenen ekleri gözden geçirmek istediğiniz kişinin adresini girin.
1. **Uygulanan'ı** seçin ve ardından etki alanı adınızı seçin.
1. Kuralın uygulanmasını istediğiniz ek etki alanlarını (onmicrosoft.com etki alanınız gibi) seçin. **Ekle'yi** ve ardından **Tamam'ı** seçin.
1. **Kaydet**'i seçin.

ATP güvenli ekler kuralınız güncelleştirildi. Artık koruma uygulandığına göre Outlook, OneDrive, SharePoint veya Teams'den kötü amaçlı bir dosya alamayacaksınız. Etkilenen dosyaların yanında kırmızı kalkanlar bulunur. Birisi engellenen bir dosyayı açmaya çalışırsa bir uyarı iletisi alır.

İlkeniz bir süre uygulandıktan sonra, nelerin tarandığını görmek için Raporlar sayfasını ziyaret edin.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalına</a> gidin ve yönetici hesabınızla oturum açın.

2. **İlkeler bölümünde Email & işbirliği** \> **İlkeleri & kuralları** \> **Tehdit ilkeleri** \> **Kötü amaçlı yazılımdan koruma** bölümüne gidin.

3. Yeni bir ilke oluşturmak için **+ Oluştur'u** seçin.

4. Aşağıdaki tabloda yer alan ayarları uygulayın.

5. Ayarlarınızı gözden geçirdikten sonra **, Bu ilkeyi oluştur'u** veya **Uygun şekilde Kaydet'i** seçin.

|Ayar veya seçenek|Önerilen ayar|
|---|---|
|Name|Algılanan kötü amaçlı yazılımlarla geçerli ve gelecekteki e-postaları engelleyin.|
|Açıklama|Algılanan kötü amaçlı yazılımlarla geçerli ve gelecekteki e-postaları ve ekleri engelleyin.|
|Ekleri kaydetme bilinmeyen kötü amaçlı yazılım yanıtı|**Engelle - Algılanan kötü amaçlı yazılım içeren geçerli ve gelecekteki e-postaları ve ekleri engelle'yi** seçin.|
|Algılamada eki yeniden yönlendirme|Yeniden yönlendirmeyi etkinleştir (bu kutuyu seçin) Karantina için yönetici hesabını veya posta kutusu kurulumunu girin.          Eklerde kötü amaçlı yazılım taraması zaman aşımına uğradıysa veya hata oluşursa yukarıdaki seçimi uygulayın (bu kutuyu seçin).|
|Uygulandığı yer|Alıcı etki alanı şeklindedir. . . etki alanınızı seçin.|

Daha fazla bilgi için bkz. [Office 365 için Microsoft Defender'de kimlik avı önleme ilkelerini ayarlama](../../security/office-365-security/set-up-anti-phishing-policies.md).

## <a name="watch-protect-against-phishing-attacks-with-safe-links"></a>İzleyin: Güvenli Bağlantılar ile kimlik avı saldırılarına karşı koruma

[YouTube kanalımızda](https://go.microsoft.com/fwlink/?linkid=2198201) bu videoya ve diğer videolara göz atın.

Korsanlar bazen kötü amaçlı web sitelerini e-posta veya diğer dosyalardaki bağlantılarda gizler. Office 365 için Microsoft Defender parçası olan Güvenli Bağlantılar, e-posta iletilerinde ve Office belgelerinde web adreslerinin (URL' ler) tıklama zamanında doğrulanmasını sağlayarak kuruluşunuzun korunmasına yardımcı olabilir. Koruma, Güvenli Bağlantılar ilkeleri aracılığıyla tanımlanır.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Eski adı Microsoft 365 ATP veya Gelişmiş Tehdit Koruması olan Office 365 için Microsoft Defender, kişiler Office uygulamalarındaki bağlantılara tıkladığında işletmenizin kötü amaçlı sitelere karşı korunmasına yardımcı olur.

1. [Yönetim merkezine](https://admin.microsoft.com) gidin ve **Kurulum'u** seçin.

1. **Gelişmiş tehditlere karşı korumayı artırmak** için ekranı aşağı kaydırın. **Yönet'i** ve ardından **Güvenli Bağlantılar'ı** seçin.

1. **Genel Ayarlar'ı** seçin ve **Aşağıdaki URL'leri engelle** alanına engellemek istediğiniz URL'yi girin.

Aşağıdakileri yapmanızı öneririz:

- Korumayı artırmak için varsayılan ilkeyi değiştirin.

- Etki alanınızdaki tüm alıcıları hedefleyen yeni bir ilke ekleyin.

Güvenli Bağlantılar'ı ayarlamak için aşağıdaki adımları tamamlayın:

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalına</a> gidin ve yönetici hesabınızla oturum açın.

2. o **Email & işbirliği** \> **İlkeleri & kuralları** \> **tehdit ilkeleri** \> **İlkeler** bölümünde **kötü amaçlı yazılımdan koruma**.

3. Yeni bir ilke oluşturmak veya varsayılan ilkeyi değiştirmek için **+ Oluştur'u** seçin.

Varsayılan ilkeyi değiştirmek için:

1. **Varsayılan** ilkeye çift tıklayın. Açılır öğe görüntülenir. 

2. Açılır pencerenin alt kısmındaki **Koruma ayarlarını düzenle'yi** seçin.

3. Varsayılan ilkeyi değiştirdikten sonra **Kaydet'i** seçin.

|Ayar veya seçenek|Önerilen ayar|
|---|---|
|Name|Etki alanındaki tüm alıcılar için güvenli bağlantılar ilkesi|
|İletilerde bilinmeyen kötü amaçlı olabilecek URL'ler için eylemi seçin|**Açık - URL'ler yeniden yazılır ve kullanıcı bağlantıya tıkladığında bilinen kötü amaçlı bağlantıların listesiyle karşılaştırılır**.|
|İndirilebilir içeriği taramak için Güvenli Ekler'i kullanma|Bu kutuyu seçin.|
|Uygulandığı yer|Alıcı etki alanı şeklindedir. . . etki alanınızı seçin.|

Daha fazla bilgi için bkz. [Güvenli Bağlantılar](../../security/office-365-security/safe-links.md).

## <a name="go-to-intune-admin-center"></a>Intune yönetim merkezine gidin

1. [Azure portal](https://portal.azure.com/) oturum açın.

2. **Tüm hizmetler'i** seçin ve **Arama Kutusuna** *Intune* yazın.

3. Sonuçlar göründükten sonra, sık kullanılanlara eklemek ve daha sonra kolayca bulmak için **Microsoft Intune** yanındaki başlangıcı seçin.

Yönetim merkezine ek olarak, kuruluşunuzun cihazlarını kaydetmek ve yönetmek için Intune kullanabilirsiniz. Daha fazla bilgi için bkz[. Windows cihazları için kayıt yöntemine göre özellikler](/intune/enrollment/enrollment-method-capab) ve [Intune tarafından yönetilen cihazlar için kayıt seçenekleri](/intune/enrollment-options).
