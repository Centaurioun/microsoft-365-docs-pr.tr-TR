---
title: güvenlik ayarlarınızı İş için Microsoft Defender görüntüleme ve düzenleme
description: İş için Defender'da güvenlik ilkelerini ve ayarlarını görüntüleme ve düzenleme
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365solution-mdb-setup
- highpri
ms.openlocfilehash: 189cfb05ad41e967ac61c1ca73c5f8feeab1f411
ms.sourcegitcommit: 511d15831b97d02e5a0f5e11834ad52617abd0f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67600301"
---
# <a name="view-and-edit-security-policies-and-settings-in-microsoft-defender-for-business"></a>güvenlik ilkelerini ve ayarlarını İş için Microsoft Defender görüntüleme ve düzenleme

Şirketinizin cihazlarını İş için Defender'a ekledikten sonra, sonraki adım güvenlik ilkelerinizi gözden geçirmektir. 

> [!TIP]
> İş için Defender, önerilen ayarlarla önceden yapılandırılmış güvenlik ilkeleri içerir. Bu ayarları iş gereksinimlerinize uyacak şekilde düzenleyebilirsiniz.

Gözden geçirilip yapılandırılan güvenlik ilkeleri şunlardır:

- Şirketinizin cihazları için virüsten koruma ve kötü amaçlı yazılımdan korumayı belirleyen **[yeni nesil koruma ilkeleri](#view-or-edit-your-next-generation-protection-policies)**
- Şirketinizin cihazlarına hangi ağ trafiğinin akışına izin verileceğini belirleyen **[güvenlik duvarı koruması ve kuralları](#view-or-edit-your-firewall-policies-and-custom-rules)**
- **[Kullanıcıların](#set-up-web-content-filtering)** yetişkinlere yönelik içerik veya yasal sorumluluk gibi kategorilere göre belirli web sitelerini (URL' ler) ziyaret etmesini engelleyen web içeriği filtreleme
- Blok modunda otomatik araştırma ve yanıt ile uç nokta algılama ve yanıt (EDR) gibi **[gelişmiş özellikler](#review-settings-for-advanced-features)**

İş için Defender'da güvenlik ilkeleri cihaz [grupları](mdb-create-edit-device-groups.md#what-is-a-device-group) aracılığıyla cihazlara uygulanır. 

Güvenlik ilkelerinize ek olarak, Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com)) hangi saat diliminin kullanılacağı ve önizleme özelliklerinin kullanıma sunulduklarında alınıp alınmayacağı gibi [ayarları görüntüleyebilir ve düzenleyebilirsiniz](#view-and-edit-other-settings-in-the-microsoft-365-defender-portal).

Güvenlik ilkelerinizi ve ayarlarınızı yönetmek için bu makaleyi kılavuz olarak kullanın.

## <a name="what-to-do"></a>Yapılması gerekenler

1. [Güvenlik ilkelerinizi ve cihazlarınızı yöneteceğiniz yeri seçin](#choose-where-to-manage-security-policies-and-devices).
2. [Yeni nesil koruma ilkelerinizi gözden geçirin](#view-or-edit-your-next-generation-protection-policies).
3. [Güvenlik duvarı ilkelerinizi ve özel kurallarınızı gözden geçirin](#view-or-edit-your-firewall-policies-and-custom-rules).
4. [Web içeriği filtrelemeyi ayarlayın](#set-up-web-content-filtering).
5. [Gelişmiş özellikler için ayarları gözden geçirin](#review-settings-for-advanced-features).
6. [Microsoft 365 Defender portalında diğer ayarları görüntüleyin](#view-and-edit-other-settings-in-the-microsoft-365-defender-portal). 
7. [Sonraki adımlarınıza geçin](#next-steps).


## <a name="choose-where-to-manage-security-policies-and-devices"></a>Güvenlik ilkelerinin ve cihazların nerede yönetileceğini seçme

İş için Defender, kurulum ve [yapılandırma sürecini](mdb-simplified-configuration.md) kolaylaştırmaya yardımcı olan basitleştirilmiş bir yapılandırma işlemine sahiptir. Basitleştirilmiş yapılandırma işlemini seçerseniz güvenlik ilkelerinizi Microsoft 365 Defender portalında ([https://security.microsoft.com/](https://security.microsoft.com/) ) görüntüleyebilir ve yönetebilirsiniz. Ancak, bu seçenekle sınırlı değilsiniz. Microsoft Intune kullanıyorsanız, Microsoft Endpoint Manager yönetim merkezini kullanmaya devam edebilirsiniz.

Aşağıdaki tablo, güvenlik ilkelerinizi ve cihazlarınızı yöneteceğiniz yeri seçmenize yardımcı olabilir.

| Seçeneği | Açıklama |
|:---|:---|
| **Microsoft 365 Defender portalını kullanma** (*önerilen*) | Microsoft 365 Defender portalı ([https://security.microsoft.com/](https://security.microsoft.com/)), şirketinizin cihazlarını, güvenlik ilkelerini ve güvenlik ayarlarını yönetmek için tek noktadan bir mağazadır. Güvenlik ilkelerinize ve ayarlarınıza erişebilir, [Microsoft Defender Güvenlik Açığı Yönetimi panosunu](mdb-view-tvm-dashboard.md) kullanabilir ve olayları tek bir yerden [görüntüleyip yönetebilirsiniz](mdb-view-manage-incidents.md). <p>Intune kullanıyorsanız, İş için Defender'a eklediğiniz cihazlar ve güvenlik ilkeleriniz Endpoint Manager yönetim merkezinde görünür. Daha fazla bilgi edinmek için aşağıdaki makalelere bakın:<ul><li>[İş için Defender varsayılan ayarları ve Microsoft Intune](mdb-next-gen-configuration-settings.md#defender-for-business-default-settings-and-microsoft-intune)</li><li>[İş için Defender'da Güvenlik Duvarı](mdb-firewall.md)</li></ul>   |
| **Microsoft Endpoint Manager yönetim merkezini kullanma** | Şirketiniz güvenlik ilkelerini yönetmek için zaten Intune kullanıyorsa, cihazlarınızı ve güvenlik ilkelerinizi yönetmek için Endpoint Manager yönetim merkezini kullanmaya devam edebilirsiniz. Daha fazla bilgi için bkz. [Microsoft Intune'da uç nokta güvenlik ilkeleriyle cihaz güvenliğini yönetme](/mem/intune/protect/endpoint-security-policy). <p>[İş için Defender'da basitleştirilmiş yapılandırma işlemine](mdb-simplified-configuration.md) geçmeye karar verirseniz, daha sonra [ilke çakışmalarını](mdb-troubleshooting.yml) önlemek için Intune'daki mevcut güvenlik ilkelerini silmeniz istenir. |

> [!IMPORTANT]
> güvenlik ilkelerini Microsoft 365 Defender portalında yönetiyorsanız, bu ilkeleri **Virüsten Koruma** veya **Güvenlik Duvarı** ilkeleri olarak listelendikleri Endpoint Manager yönetim merkezinde ([https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) *görüntüleyebilirsiniz*. Yönetim merkezinde güvenlik duvarı ilkelerinizi görüntülediğinizde listelenen iki ilke görürsünüz: biri güvenlik duvarı koruması ve diğeri özel kurallar için.

## <a name="view-or-edit-your-next-generation-protection-policies"></a>Yeni nesil koruma ilkelerinizi görüntüleme veya düzenleme

Yeni nesil koruma ilkelerinizi yönetmek için Microsoft 365 Defender portalını mı yoksa Microsoft Endpoint Manager yönetim merkezini mi kullandığınıza bağlı olarak aşağıdaki yordamlardan birini kullanın:

| Portal | Yordam |
|:---|:---|
| Microsoft 365 Defender portalı ([https://security.microsoft.com](https://security.microsoft.com)) |<ol><li>Microsoft 365 Defender portalına ()[https://security.microsoft.com](https://security.microsoft.com) gidin ve oturum açın.</li><li>Gezinti bölmesinde **Cihaz yapılandırması'nı** seçin. İlkeler işletim sistemine ve ilke türüne göre düzenlenir.</li><li>bir işletim sistemi sekmesi ( **Windows istemcileri** gibi) seçin.</li><li>İlke listenizi görüntülemek için **Yeni nesil koruma'yi** genişletin.</li><li>İlke hakkında daha fazla ayrıntı görüntülemek için bir ilke seçin.</li><li>Değişiklik yapmak veya ilke ayarları hakkında daha fazla bilgi edinmek için aşağıdaki makalelere bakın: <ul><li>[Cihaz ilkelerini görüntüleme veya düzenleme](mdb-view-edit-policies.md)</li><li>[Yeni nesil yapılandırma ayarlarını anlama](mdb-next-gen-configuration-settings.md)</li></ul></li><ol>  |
| Microsoft Endpoint Manager yönetim merkezi ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) |Intune'da güvenlik ayarlarınızı yönetme konusunda yardım için [Microsoft Intune'da uç nokta güvenliğini yönetme](/mem/intune/protect/endpoint-security) ile başlayın. <ol><li>[https://endpoint.microsoft.com](https://endpoint.microsoft.com) adresine gidin ve oturum açın. Artık Endpoint Manager yönetim merkezindesiniz.</li><li>**Uç nokta güvenliği'ne** tıklayın.</li><li>Bu kategorideki ilkelerinizi görüntülemek için **Virüsten Koruma'ya** tıklayın.</li></ol>|

## <a name="view-or-edit-your-firewall-policies-and-custom-rules"></a>Güvenlik duvarı ilkelerinizi ve özel kurallarınızı görüntüleme veya düzenleme

Güvenlik duvarı korumanızı yönetmek için Microsoft 365 Defender portalını mı yoksa Microsoft Endpoint Manager yönetim merkezini mi kullandığınıza bağlı olarak aşağıdaki yordamlardan birini kullanın.

| Portal | Yordam |
|:---|:---|
| Microsoft 365 Defender portalı ([https://security.microsoft.com](https://security.microsoft.com)) |<ol><li>Microsoft 365 Defender portalına ()[https://security.microsoft.com](https://security.microsoft.com) gidin ve oturum açın.</li><li>Gezinti bölmesinde **Cihaz yapılandırması'nı** seçin. İlkeler işletim sistemine ve ilke türüne göre düzenlenir.</li><li>bir işletim sistemi sekmesi ( **Windows istemcileri** gibi) seçin.</li><li>İlke listenizi görüntülemek için **Güvenlik Duvarı'nı** genişletin.</li><li>Ayrıntıları görüntülemek için bir ilke seçin. </li><li>Değişiklik yapmak veya ilke ayarları hakkında daha fazla bilgi edinmek için aşağıdaki makalelere bakın:<ul><li>[Cihaz ilkelerini görüntüleme veya düzenleme](mdb-view-edit-policies.md)</li><li>[Güvenlik duvarı ayarları](mdb-firewall.md)</li><li>[Güvenlik duvarı ilkeleri için özel kurallarınızı yönetme](mdb-custom-rules-firewall.md)</li><ul></li><ol>  |
| Microsoft Endpoint Manager yönetim merkezi ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) |Intune'da güvenlik ayarlarınızı yönetme konusunda yardım için [Microsoft Intune'da uç nokta güvenliğini yönetme](/mem/intune/protect/endpoint-security) ile başlayın. <ol><li>[https://endpoint.microsoft.com](https://endpoint.microsoft.com) adresine gidin ve oturum açın. Artık Endpoint Manager yönetim merkezindesiniz.</li><li>**Uç nokta güvenliği'ne** tıklayın.</li><li>Bu kategorideki ilkelerinizi görüntülemek için **Güvenlik Duvarı'nı** seçin. Güvenlik duvarı koruması için tanımlanan özel kurallar ayrı ilkeler olarak listelenir.</li></ol>|

## <a name="set-up-web-content-filtering"></a>Web içeriği filtrelemeyi ayarlama

Web içeriği filtreleme, güvenlik ekibinizin web sitelerine erişimi aşağıdaki gibi içerik kategorilerine göre izlemesine ve düzenlemesine olanak tanır:

- Yetişkin içeriği: Tarikatlar, kumar, çıplaklık, pornografi, cinsel içerikli malzeme veya şiddet ile ilgili siteler
- Yüksek bant genişliği: Siteleri, görüntü paylaşım sitelerini veya eşler arası konakları indirme
- Yasal sorumluluk: Çocuk istismarı görüntülerini içeren, yasa dışı etkinlikleri teşvik eden, intihal veya okul dolandırıcılığına teşvik eden veya zararlı etkinlikleri teşvik eden siteler
- Boş zaman: Web tabanlı sohbet odaları, çevrimiçi oyun, web tabanlı e-posta veya sosyal ağ sağlayan siteler
- Kategorilere ayrılmamış: İçeriği olmayan veya yeni kaydedilen siteler

Bu kategorilerdeki tüm web siteleri kötü amaçlı değildir, ancak uyumluluk düzenlemeleri, bant genişliği kullanımı veya diğer endişeler nedeniyle şirketiniz için sorunlu olabilir. Güvenlik ekibinizin herhangi bir web sitesi kategorisini engellemesi gerekip gerekmediğini daha iyi anlamak için yalnızca denetim ilkesi oluşturabilirsiniz.

Web içeriği filtreleme, Windows Defender SmartScreen (Microsoft Edge) ve Ağ Koruması (Chrome, Firefox, Brave ve Opera) tarafından gerçekleştirilen bloklarla büyük web tarayıcılarında kullanılabilir. Daha fazla bilgi için bkz. [Web içeriği filtreleme önkoşulları](../defender-endpoint/web-content-filtering.md#prerequisites).

### <a name="to-set-up-web-content-filtering"></a>Web içeriği filtrelemeyi ayarlamak için

1. Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com) ), **Ayarlar** > **Web içeriği filtreleme+ İlke** >  **ekle'yi** seçin.

2. İlkeniz için bir ad ve açıklama belirtin.

3. Engellenmesi gereken kategorileri seçin. Her üst kategoriyi tamamen genişletmek için genişlet simgesini kullanın ve ardından belirli web içeriği kategorilerini seçin. Hiçbir web sitesini engellemeyen yalnızca denetim ilkesi ayarlamak için hiçbir kategori seçmeyin.

   **Kategorilere Ayrılmamış'ı** seçmeyin.

4. İlkenin uygulanacağı cihaz gruplarını seçerek ilke kapsamını belirtin. Yalnızca seçili cihaz gruplarındaki cihazların seçilen kategorilerdeki web sitelerine erişmesi engellenir.

5. Özeti gözden geçirin ve ilkeyi kaydedin. İlke yenilemesinin seçili cihazlarınıza uygulanması iki saat kadar sürebilir.

> [!TIP]
> Web içeriği filtreleme hakkında daha fazla bilgi edinmek için bkz. [Web içeriği filtreleme](../defender-endpoint/web-content-filtering.md).

## <a name="review-settings-for-advanced-features"></a>Gelişmiş özellikler için ayarları gözden geçirme

Yeni nesil koruma, güvenlik duvarı ve web içeriği filtreleme ilkelerine ek olarak, İş için Defender gelişmiş güvenlik özellikleri içerir. Bu özellikler önerilen ayarlar için önceden yapılandırılmıştır. Ayarları iş gereksinimlerinize uyacak şekilde gözden geçirebilir ve düzenleyebilirsiniz.

Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com) ) gelişmiş özelliklerin ayarlarına erişmek için **Ayarlar** > **Uç Noktaları** > **Genel** > **Gelişmiş özellikler'e** gidin.

Aşağıdaki tabloda gelişmiş özellik ayarları açıklanmaktadır.

| Ayar | Açıklama |
|:---|:---|
| **Otomatik Araştırma** <br/>(varsayılan olarak açıktır) | Uyarılar oluşturuldukçe otomatik araştırma yapılabilir. Her otomatik araştırma, algılanan bir tehdidin eylem gerektirip gerektirmediğini belirler ve ardından karantinaya dosya gönderme, işlemi durdurma, cihazı yalıtma veya URL'yi engelleme gibi düzeltme eylemleri gerçekleştirir veya önerir. Araştırma çalıştırılırken, ortaya çıkan tüm ilgili uyarılar tamamlanana kadar araştırmaya eklenir. Etkilenen bir varlık başka bir yerde görülürse, otomatik araştırma kapsamını bu varlığı içerecek şekilde genişletir ve araştırma işlemi yinelenir.<p>Araştırmalara **Olaylar** sayfasından bakabilirsiniz. Bir olay seçin ve ardından **Araştırmalar** sekmesini seçin.<p>Varsayılan olarak, kiracı genelinde otomatik araştırma ve yanıt özellikleri açıktır. **Otomatik araştırmayı açık tutmanızı öneririz**. Bu özelliği kapatırsanız, Microsoft Defender Virüsten Koruma'daki gerçek zamanlı koruma etkilenir ve genel koruma düzeyiniz azalır. <p>[Otomatik araştırmalarla ilgili Mer informasjon](../defender-endpoint/automated-investigations.md).   |
| **Canlı Yanıt**  | İş için Defender aşağıdaki el ile yanıt eylemi türlerini içerir: <ul><li>Antivirüs taraması başlat</li><li>Cihazı yalıtma</li><li>Dosyayı durdurma ve karantinaya al</li><li>Bir dosyayı engellemek veya dosyaya izin vermek için gösterge ekleme</li></ul> <p>[Yanıt eylemleri hakkında Mer informasjon](../defender-endpoint/respond-machine-alerts.md). |
| **Sunucular için Canlı Yanıt** | (Bu ayar şu anda İş için Defender'da kullanılamıyor.)   |
| **Canlı Yanıt imzasız betik yürütme** | (Bu ayar şu anda İş için Defender'da kullanılamıyor.)  | 
| **Blok modunda EDR'yi etkinleştirme**<br/>(varsayılan olarak açıktır) | Microsoft Defender Virüsten Koruma birincil virüsten koruma ürünü olmadığında ve bir cihazda pasif modda çalıştığında kötü amaçlı yapıtlara karşı ek koruma sağlar. Blok modunda uç nokta algılama ve yanıt (EDR), EDR özellikleri tarafından algılanan kötü amaçlı yapıtları düzeltmek için arka planda çalışır. Bu tür yapıtlar birincil, Microsoft dışı virüsten koruma ürünü tarafından kaçırılmış olabilir.<p>[Blok modunda EDR hakkında Mer informasjon](../defender-endpoint/edr-in-block-mode.md). |
| **Dosyaya izin verme veya dosyayı engelleme** <br/>(varsayılan olarak açıktır) | [Göstergeleri](../defender-endpoint/indicator-file.md) kullanarak bir dosyaya izin vermenizi veya dosyayı engellemenizi sağlar. Bu özellik, Microsoft Defender Virüsten Koruma'nın etkin modda ve [bulut korumasının](../defender-endpoint/cloud-protection-microsoft-defender-antivirus.md) açık olmasını gerektirir.<p>Bir dosyanın engellenmesi, dosyanın kuruluşunuzdaki cihazlarda okunmasını, yazılmasını veya yürütülmesini engeller. <p>[Dosyalar için göstergeler hakkında Mer informasjon](../defender-endpoint/indicator-file.md).  |
| **Özel ağ göstergeleri**<br/>(varsayılan olarak açıktır) | [Ağ göstergelerini](../defender-endpoint/indicator-ip-domain.md) kullanarak BIR IP adresine, URL'ye veya etki alanına izin vermenizi veya engellemenizi sağlar. Bu özellik, Microsoft Defender Virüsten Koruma'nın etkin modda ve [ağ korumasının](../defender-endpoint/enable-network-protection.md) açık olmasını gerektirir.<p>Tehdit bilgilerinize göre IP'lere, URL'lere veya etki alanlarına izin verebilir veya bunları engelleyebilirsiniz. Ayrıca kullanıcılara riskli bir uygulama açıp açmadıklarını sorabilirsiniz, ancak istem uygulamayı kullanmalarını engellemez.<p>[Ağ koruması hakkında Mer informasjon](../defender-endpoint/network-protection.md). |
| **Kurcalama koruması**<br/>(bu ayarı açmanızı öneririz) | Kurcalama koruması, kötü amaçlı uygulamaların aşağıdaki gibi eylemler gerçekleştirmesini önler:<ul><li>Virüs ve tehdit korumasını devre dışı bırakma</li><li>Gerçek zamanlı korumayı devre dışı bırakma</li><li>Davranış izlemeyi kapatma</li><li>Bulut korumasını devre dışı bırakma</li><li>Güvenlik bilgileri güncelleştirmelerini kaldırma</li><li>Algılanan tehditlerde otomatik eylemleri devre dışı bırakma</li></ul><p>Kurcalama koruması temelde Microsoft Defender Virüsten Koruma'yı güvenli, varsayılan değerlerine kilitler ve güvenlik ayarlarınızın uygulamalar ve yetkisiz yöntemler tarafından değiştirilmesini önler. <p>[Kurcalama koruması hakkında Mer informasjon](../defender-endpoint/prevent-changes-to-security-settings-with-tamper-protection.md).  |
| **Kullanıcı ayrıntılarını göster**<br/>(varsayılan olarak açıktır) | Kuruluşunuzdaki kişilerin çalışanların resimleri, adları, başlıkları ve departmanları gibi ayrıntıları görmesini sağlar. Bu ayrıntılar Azure Active Directory'de (Azure AD) depolanır.<p>[Azure AD kullanıcı profilleri hakkında Mer informasjon](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).  |
| **Skype Kurumsal tümleştirmesi**<br/>(varsayılan olarak açıktır) | Skype Kurumsal Temmuz 2021'de kullanımdan kaldırıldı. Henüz Microsoft Teams'e taşınmadıysanız bkz. [Küçük işletmenizde Microsoft Teams'i ayarlama](/microsoftteams/deploy-small-business). <p>Microsoft Teams (veya eski Skype Kurumsal) ile tümleştirme, işletmenizdeki kişiler arasında tek tıklamayla iletişime olanak tanır.   |
| **Web içeriği filtreleme**<br/>(varsayılan olarak açıktır) | İstenmeyen içerik içeren web sitelerine erişimi engeller ve tüm etki alanlarındaki web etkinliğini izler. Bkz. [Web içeriği filtrelemeyi ayarlama](#set-up-web-content-filtering). |
| **Microsoft Intune bağlantısı**<br/>(Intune kullanıyorsanız bu ayarı açmanızı öneririz) | Kuruluşunuzun aboneliği Microsoft Intune içeriyorsa ([Microsoft 365 İş Ekstra](../../business/index.yml) dahil), bu ayar İş için Defender'ın cihazlar hakkındaki bilgileri Intune ile paylaşmasını sağlar.  |
| **cihaz keşfi**<br/>(varsayılan olarak açıktır) | Güvenlik ekibinizin şirket ağınıza bağlı yönetilmeyen cihazları bulmasını sağlar. Bilinmeyen ve yönetilmeyen cihazlar, eşleşmeyen bir yazıcı, zayıf güvenlik yapılandırmasına sahip bir ağ cihazı veya güvenlik denetimi olmayan bir sunucu olsun ağınızda önemli riskler getirir.<p>Cihaz bulma, yönetilmeyen cihazları bulmak için eklenen cihazları kullanır, böylece güvenlik ekibiniz yönetilmeyen cihazları ekleyebilir ve güvenlik açığınızı azaltabilir. <p>[Cihaz bulma hakkında Mer informasjon](../defender-endpoint/device-discovery.md).    |
| **Özellikleri önizleyin** | Microsoft, yeni özellik geliştirmeleri ve özellikleri içerecek şekilde İş için Defender gibi hizmetleri sürekli güncelleştirmektedir. Önizleme özelliklerini almayı kabul ederseniz, önizleme deneyiminde yaklaşan özellikleri ilk deneyenler arasında yer alırsınız. <p>[Önizleme özellikleri hakkında Mer informasjon](../defender-endpoint/preview.md).  |

## <a name="view-and-edit-other-settings-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender portalında diğer ayarları görüntüleme ve düzenleme

Cihazlara uygulanan güvenlik ilkelerine ek olarak, İş için Defender'da görüntüleyebileceğiniz ve düzenleyebileceğiniz başka ayarlar da vardır. Örneğin, kullanılacak saat dilimini belirtirsiniz ve cihazları ekleyebilir (veya devre dışı bırakabilirsiniz). 

> [!NOTE]
> Kiracınızda bu makalede listelenenden daha fazla ayar görebilirsiniz. Bu makalede, İş için Defender'da gözden geçirmeniz gereken en önemli ayarlar vurgulanır.

### <a name="settings-to-review-for-defender-for-business"></a>İş için Defender'ı gözden geçirme ayarları

Aşağıdaki tabloda, İş için Defender'da görüntüleyebileceğiniz ve düzenleyebileceğiniz ayarlar açıklanmaktadır:

| Kategori | Ayar | Açıklama |
|:---|:---|:---|
| **Güvenlik merkezi** | **Saat dilimi** | Olaylarda görüntülenen tarih ve saatler, algılanan tehditler ve otomatik araştırma ve düzeltme için kullanılacak saat dilimini seçin. UTC veya yerel saat diliminizi kullanabilirsiniz (*önerilir*).  |
| **Microsoft 365 Defender** | **Hesabı** | Verilerinizin depolandığı yer, kiracı kimliğiniz ve kuruluşunuzun (kuruluş) kimliği gibi ayrıntıları görüntüleyin. |
| **Microsoft 365 Defender**  | **Özellikleri önizleyin**  | Yaklaşan özellikleri ve yeni özellikleri denemek için önizleme özelliklerini açın. Yeni özellikleri ilk önizleyip geri bildirim sağlayanlar arasında olabilirsiniz. |
| **Bitiş noktası**  | **E-posta bildirimleri** | E-posta bildirim kurallarınızı ayarlayın veya düzenleyin. Güvenlik açıkları algılandığında veya bir uyarı oluşturulduğunda, e-posta bildirim kurallarınızda belirtilen alıcılar bir e-posta alır. [E-posta bildirimleri hakkında Mer informasjon](mdb-email-notifications.md). |
| **Bitiş noktası**   | **Cihaz yönetimi** >  **Ekleme** | İndirilebilir bir betik kullanarak cihazları İş için Defender'a ekleyin. Daha fazla bilgi edinmek için bkz. [Cihazları İş için Defender'a ekleme](mdb-onboard-devices.md).   |  
| **Bitiş noktası**  |  **Cihaz yönetimi** >  **Çıkarma** | Cihazları İş için Defender'dan çıkarın (kaldırın). Bir cihazı kullanıma aldığınızda, bu cihaz artık İş için Defender'a veri göndermez, ancak kullanıma alınmadan önce alınan veriler korunur. Daha fazla bilgi için bkz. [Cihazı çıkarma](mdb-offboard-devices.md).  |

### <a name="access-your-settings-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender portalında ayarlarınıza erişme

1. Microsoft 365 Defender portalına ()[https://security.microsoft.com/](https://security.microsoft.com/) gidin ve oturum açın.

2. **Ayarlar'ı** seçin ve ardından bir kategori (**Güvenlik merkezi**, **Microsoft 365 Defender** veya **Uç Noktalar** gibi) seçin.

3. Ayarlar listesinde, görüntülemek veya düzenlemek için bir öğe seçin.

## <a name="next-steps"></a>Sonraki adımlar

- [İş için Defender'ı kullanmaya başlama](mdb-get-started.md)
- [İş için Defender'da cihazları yönetme](mdb-manage-devices.md)
- [İş için Defender'da olayları görüntüleme ve yönetme](mdb-view-manage-incidents.md)
- [İş için Defender'da ilkeleri görüntüleme veya düzenleme](mdb-view-edit-policies.md)
