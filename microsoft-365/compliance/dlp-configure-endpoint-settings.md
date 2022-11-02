---
title: Uç nokta DLP ayarlarını yapılandırma
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- tier1
- purview-compliance
- SPO_Content
search.appverid:
- MET150
description: Uç nokta veri kaybı önleme (DLP) merkezi ayarlarını yapılandırmayı öğrenin.
ms.openlocfilehash: 155de9a60966f53b1b0e8b8d41e2d1e7e8e8a063
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2022
ms.locfileid: "68813207"
---
# <a name="configure-endpoint-data-loss-prevention-settings"></a>Uç noktada veri kaybı önleme ayarlarını yapılandırma

Uç nokta veri kaybı önleme (DLP) davranışının birçok yönü merkezi olarak yapılandırılmış ayarlar tarafından denetlenmektedir. Ayarlar cihazlar için tüm DLP ilkelerine uygulanır.

![Uç nokta DLP ayarları](../media/endpoint-dlp-1-using-dlp-settings.png)

Şunları denetlemek istiyorsanız bu ayarları yapılandırmanız gerekir:

- Bulut çıkış kısıtlamaları
- Uygulama başına kullanıcı etkinlikleri üzerinde çeşitli kısıtlayıcı eylem türleri.
- Windows ve macOS cihazları için dosya yolu dışlamaları.
- Tarayıcı ve etki alanı kısıtlamaları.
- İlkeleri geçersiz kılmaya yönelik iş gerekçeleri ilke ipuçlarında nasıl görünür?
- Office, PDF ve CSV dosyalarındaki etkinlikler otomatik olarak denetleniyorsa.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="dlp-settings"></a>DLP ayarları

Başlamadan önce DLP ayarlarınızı ayarlamanız gerekir. 

### <a name="endpoint-dlp-windows-1011-and-macos-settings"></a>Uç nokta DLP Windows 10/11 ve macOS ayarları

|Ayar |Windows 10, 1809 ve üzeri, Windows 11  |macOS (en son yayınlanan üç sürüm) |Notlar  |
|---------|---------|---------|---------|
|Dosya yolu dışlamaları     |Destekleniyor         |Destekleniyor         |macOS varsayılan olarak açık olan dışlamaların önerilen bir listesini içerir          |
|Kısıtlı uygulamalar     |Destekleniyor         |Destekleniyor         |         |
|Kısıtlı uygulama grupları |Destekleniyor |Desteklenmiyor
|İzin verilmeyen Bluetooth uygulamaları    |Destekleniyor         |Desteklenmiyor         |         |
|Hassas öğelere yönelik tarayıcı ve etki alanı kısıtlamaları      |Destekleniyor         |Destekleniyor         |         |
|Uç Nokta DLP için ek ayarlar     |Destekleniyor         |Destekleniyor         |MacOS cihazları için yalnızca varsayılan iş gerekçeleri desteklenir         |
|Cihazlar için her zaman dosya etkinliğini denetleme     |Destekleniyor         |Destekleniyor         |         |
|İzin verilmeyen uygulamalardan dosyayı otomatik olarak karantinaya al | Destekleniyor | Desteklenmiyor| |
|Gelişmiş sınıflandırma | Destekleniyor | Desteklenmiyor| |
|İlke ipuçlarında iş gerekçesi | Destekleniyor | Destekleniyor| |

### <a name="advanced-classification-scanning-and-protection"></a>Gelişmiş sınıflandırma tarama ve koruma

Gelişmiş sınıflandırma tarama ve koruma, daha gelişmiş Microsoft Purview bulut tabanlı veri sınıflandırma hizmetinin öğeleri taramasına, sınıflandırmasına ve sonuçları yerel makineye döndürmesine olanak tanır. Bu, [DLP ilkelerinizdeki tam veri eşleştirme](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) sınıflandırması ve [adlandırılmış varlıklar](named-entities-learn.md) gibi sınıflandırma tekniklerinden yararlanabileceğiniz anlamına gelir.

Gelişmiş sınıflandırma etkinleştirildiğinde, içerik yerel cihazdan tarama ve sınıflandırma için bulut hizmetlerine gönderilir. Bant genişliği kullanımıyla ilgili bir sorun varsa, 24 saatlik bir süre içinde ne kadarın kullanılabileceğini belirleyebilirsiniz. Sınır Uç Nokta DLP ayarlarında yapılandırılır ve cihaz başına uygulanır. Bant genişliği kullanım sınırını ayarlarsanız ve bu sınır aşılırsa, DLP kullanıcı içeriğini buluta göndermeyi durdurur. Bu noktada veri sınıflandırması cihazda yerel olarak devam eder ancak tam veri eşleşmesi, adlandırılmış varlıklar ve eğitilebilir sınıflandırıcılar kullanılarak sınıflandırma kullanılamaz. Toplu bant genişliği kullanımı sıralı 24 saat sınırının altına düştüğünde bulut hizmetleriyle iletişim devam eder.

Bant genişliği kullanımı önemli değilse sınırsız bant genişliği kullanımına izin vermek için **Sınır yok'a** tıklayın.

Bu Windows sürümleri gelişmiş sınıflandırma taramasını ve korumasını destekler:

- Windows 10 sürümleri 20H1/20H2/21H1 (KB 5006738)
- Windows 10 sürümleri 19H1/19H2 (KB 5007189)
- Windows 10 RS5 (KB 5006744)

> [!NOTE]
> Office (Word, Excel, PowerPoint) ve PDF dosya türleri için gelişmiş sınıflandırma desteği sağlanır.

> [!NOTE]
> DLP ilkesi değerlendirmesi, kullanıcı içeriği gönderilmese bile her zaman bulutta gerçekleşir.

### <a name="file-path-exclusions"></a>Dosya yolu dışlamaları

[Microsoft Purview uyumluluk portalı](https://compliance.microsoft.com) >  **Veri kaybı önleme** > **Uç Noktası DLP ayarları** > **Dosya yolu dışlamalarını** açın.

Cihazlarınızda DLP izleme, DLP uyarısı ve DLP ilkesi zorlamasından belirli yolları dışlamak isteyebilirsiniz çünkü bunlar çok gürültülü veya ilgilendiğiniz dosyaları içermez. Bu konumlardaki dosyalar denetlenmeyecek ve bu konumlarda oluşturulan veya değiştirilen dosyalar DLP ilkesi uygulamasına tabi olmayacaktır. DLP ayarlarında yol dışlamalarını yapılandırabilirsiniz.

#### <a name="windows-10-devices"></a>cihazları Windows 10

Windows 10 cihazlar için dışlama yollarınızı oluşturmak için bu mantığı kullanabilirsiniz:

- ile `\`biten geçerli dosya yolu, yalnızca doğrudan klasörün altındaki dosyalar anlamına gelir. <br/>Örneğin: `C:\Temp\`

- ile `\*`biten geçerli dosya yolu, yalnızca alt klasörlerin altındaki dosyalar anlamına gelir. Doğrudan klasörün altındaki dosyalar dışlanmaz. <br/>Örneğin: `C:\Temp\*`

- veya `\*`olmadan `\` biten geçerli dosya yolu, tüm dosyaların doğrudan klasörün altında ve tüm alt klasörlerin altında olduğu anlamına gelir. <br/>Örneğin: `C:\Temp`

- Her iki tarafından arasında `\` joker karakter bulunan bir yol. <br/>Örneğin: `C:\Users\*\Desktop\`

- Her iki tarafından ve ile arasında `\` joker karakter bulunan ve `(number)` tam alt klasör sayısını veren bir yol. <br/>Örneğin: `C:\Users\*(1)\Downloads\`

- SYSTEM ortam değişkenlerini içeren bir yol. <br/>Örneğin: `%SystemDrive%\Test\*`

- Yukarıdakilerin bir karışımı. <br/>Örneğin: `%SystemDrive%\Users\*\Documents\*(2)\Sub\`

#### <a name="macos-devices"></a>macOS cihazları

Windows 10 cihazlara benzer şekilde, macOS cihazları için kendi dışlamalarınızı ekleyebilirsiniz.

- Dosya yolu tanımları büyük/küçük harfe duyarlı değildir, bu nedenle `User` ile `user`aynıdır.

- Joker değerler desteklenir. Bu nedenle yol tanımı, yolun ortasında veya sonunda bir `*` içerebilir. Örneğin: `/Users/*/Library/Application Support/Microsoft/Teams/*`

##### <a name="recommended-file-path-exclusions-preview"></a>Önerilen dosya yolu dışlamaları (önizleme)

Performans nedenleriyle Endpoint DLP, macOS cihazları için önerilen dosya yolu dışlamalarının listesini içerir. Bu dışlamalar varsayılan olarak açıktır. **Mac için önerilen dosya yolu dışlamalarını ekle iki durumlu** düğmesini açarak bunları devre dışı bırakabilirsiniz. Liste şunları içerir:

- /Uygulama/*
- /Sistem/*
- /Usr/*
- /Kitaplığı/*
- /Özel/*
- /Tercih/*
- /Users/*/Library/Application Support/Microsoft/Teams/*

### <a name="restricted-apps-and-app-groups"></a>Kısıtlı uygulamalar ve uygulama grupları

#### <a name="restricted-apps"></a>Kısıtlı uygulamalar

**Kısıtlanmış uygulamalar** (eski **adıyla İzin verilmeyen uygulamalar**), oluşturduğunuz uygulamaların listesidir. Kullanıcı bir cihazda DLP korumalı bir dosyaya **_erişmek_** için listedeki bir uygulamayı kullandığında DLP'nin gerçekleştireceği eylemleri yapılandırabilirsiniz. Windows 10 ve macOS cihazlarda kullanılabilir.

Bir ilkede **Kısıtlı uygulamalar tarafından erişim** seçildiğinde ve kullanıcı korumalı bir dosyaya erişmek için kısıtlanmış uygulamalar listesinde yer alan bir uygulamayı kullandığında, etkinlik , `blocked`veya `blocked with override` nasıl yapılandırdığınıza bağlı olarak olur`audited`. Bu, aynı uygulama **Kısıtlı bir uygulama grubunun** üyesi olmadığı sürece, **Kısıtlı uygulama grubundaki** etkinlikler için yapılandırılan eylemler **Kısıtlı uygulamalar** listesi için erişim etkinliği için yapılandırılan eylemleri geçersiz kılar. Tüm etkinlikler denetlenip etkinlik gezgininde gözden geçirilebilir.

> [!IMPORTANT]
> Yürütülebilir dosyanın yolunu değil, yalnızca yürütülebilir adı (browser.exe gibi) eklemeyin.

> [!IMPORTANT]
> Kısıtlı uygulamalar listesinde yer alan uygulamalar için tanımlanan eylem (`audit`, `block with override`veya `block`) yalnızca kullanıcı korumalı bir öğeye ***erişmeye*** çalıştığında geçerlidir. 

#### <a name="file-activities-for-apps-in-restricted-app-groups"></a>Kısıtlı uygulama gruplarındaki uygulamalar için dosya etkinlikleri

Kısıtlı uygulama grupları, DLP ayarlarında oluşturduğunuz ve ardından ilkedeki bir kurala eklediğiniz uygulama koleksiyonlarıdır. İlkeye kısıtlı bir uygulama grubu eklediğinizde, bu tabloda tanımlanan eylemleri gerçekleştirebilirsiniz.

|Kısıtlı Uygulama grubu seçeneği  |Yapmanıza olanak sağlayan şey  |
|---------|---------|
|Dosya etkinliğini kısıtlama     |DLP'ye, kullanıcıların uygulama grubundaki uygulamaları kullanarak DLP korumalı öğelere erişmesine izin vermelerini ve kullanıcı **Panoya kopyalama**, **USB çıkarılabilir sürücüye kopyalama**, **Ağ sürücüsüne kopyalama** ve uygulamadan **yazdırma** girişimlerinde hiçbir işlem yapmamalarını bildirir.          |
|Tüm etkinliklere kısıtlama uygulama     |DLP'ye `Audit only`, `Block with override`veya `Block` kullanıcı bu uygulama grubunda yer alan bir uygulamayı kullanarak DLP korumalı bir öğeye erişmeye çalıştığında bildirir         |
|Belirli bir etkinliğe kısıtlama uygulama     |Bu ayar, bir kullanıcının uygulama grubunda yer alan bir uygulama kullanarak DLP korumalı bir öğeye erişmesine olanak tanır ve kullanıcı **Panoya Kopyalama**, **USB çıkarılabilir sürücüye kopyalama**, `Block`**Ağ sürücüsüne kopyala** ve **Yazdır'ı** denediğinde DLP'nin gerçekleştirmesi için varsayılan bir eylem (`Audit only`, , veya `Block with override`) seçmenize olanak tanır.          |

> [!IMPORTANT]
> Kısıtlı uygulama grubundaki ayarlar, aynı kuralda yer alan kısıtlı uygulamalar listesinde ayarlanan kısıtlamaları geçersiz kılar. Bu nedenle, bir uygulama kısıtlı uygulamalar listesindeyse ve kısıtlı bir uygulama grubunun üyesiyse, kısıtlanmış uygulamalar grubunun ayarları uygulanır.

#### <a name="how-dlp-applies-restrictions-to-activities"></a>DLP etkinliklere kısıtlamaları nasıl uygular?

**Kısıtlı uygulama gruplarındaki uygulamalar için Dosya etkinlikleri**, **Tüm uygulamalar için Dosya etkinlikleri** ve **Kısıtlanmış uygulama etkinlikleri listesi arasındaki etkileşimler** aynı kural kapsamındadır.

##### <a name="restricted-app-groups-overrides"></a>Kısıtlanmış uygulama grupları geçersiz kılmaları

**Kısıtlı uygulama gruplarındaki uygulamalar için Dosya etkinlikleri'nde** tanımlanan yapılandırmalar **, Kısıtlanmış uygulama etkinlikleri** listesindeki yapılandırmaları ve aynı kuraldaki **tüm uygulamalar için Dosya etkinlikleri'ni** geçersiz kılar.

##### <a name="restricted-app-activities-and-file-activities-for-all-apps"></a>Tüm uygulamalar için kısıtlı uygulama etkinlikleri ve Dosya etkinlikleri

**Kısıtlı uygulama etkinlikleri** için tanımlanan eylem veya `Audit only``Block with override` aynı kuraldaysa **, tüm uygulamalar** için **Kısıtlı uygulama etkinlikleri ve Dosya etkinlikleri yapılandırmaları** aynı şekilde çalışır. Bunun nedeni **Kısıtlı uygulama etkinlikleri** için tanımlanan eylemlerin yalnızca bir kullanıcı listede yer alan bir uygulamayı kullanarak bir dosyaya eriştiğinde geçerli olmasıdır. Kullanıcı erişime sahip olduktan sonra **, tüm uygulamalar için Dosya etkinliklerindeki etkinlikler için** tanımlanan eylemler uygulanır. 

İşte bir örnek:

**Kısıtlı uygulamalar'a** Notepad.exe eklenirse ve **Tüm uygulamalar için Dosya etkinlikleri** **belirli etkinliklere kısıtlama uygula** olarak yapılandırılmışsa ve her ikisi de aşağıdaki gibi yapılandırılır:

|İlkedeki ayar  |Uygulama adı  |Kullanıcı etkinliği  |Yürütülecek DLP eylemi  |
|---------|---------|---------|---------|
|Kısıtlı uygulama etkinlikleri     |Not defteri        |DLP korumalı bir öğeye erişme         |Yalnızca denetim         |
|Tüm uygulamalar için dosya etkinlikleri   |Tüm uygulamalar        | Panoya kopyala        |Yalnızca denetim         |
|Tüm uygulamalar için dosya etkinlikleri     |Tüm uygulamalar         |USB kaldırılabilir bir cihaza kopyalama | Engelle       |
|Tüm uygulamalar için dosya etkinlikleri     |Tüm uygulamalar         |Ağ paylaşımına kopyalama         |Yalnızca denetim         |
|Tüm uygulamalar için dosya etkinlikleri   |Tüm uygulamalar         |Yazdırma         |Engelle         |
|Tüm uygulamalar için dosya etkinlikleri     |Tüm uygulamalar         |İzin verilmeyen Bluetooth uygulamasını kullanarak kopyalama veya taşıma         |Engellenen         |
|Tüm uygulamalar için dosya etkinlikleri     |Tüm uygulamalar         |Uzak masaüstü hizmetleri         |Geçersiz kılma ile engelle         |

A kullanıcısı, Not Defteri'nin kullanıldığı DLP korumalı bir dosyayı açar. DLP, erişime izin verir ve etkinliği denetler. Not Defteri'ndeyken, A Kullanıcısı korumalı öğeden panoya kopyalamayı dener; bu işlem çalışır ve DLP etkinliği denetler. A kullanıcısı korumalı öğeyi Not Defteri'nden yazdırmayı dener ve etkinlik engellenir.

> [!NOTE]
> **Kısıtlı uygulama etkinliklerinde** gerçekleştirilecek DLP eylemi olarak `block`ayarlandığında, tüm erişim engellenir ve kullanıcı dosya üzerinde herhangi bir etkinlik gerçekleştiremez.
   
##### <a name="file-activities-for-all-apps-only"></a>Yalnızca tüm uygulamalar için dosya etkinlikleri

Bir uygulama **kısıtlı uygulama gruplarındaki uygulamalar için Dosya etkinliklerinde** değilse veya **Kısıtlanmış uygulama etkinlikleri** listesinde değilse veya bir eylemiyle `Audit only`**Kısıtlanmış uygulama etkinlikleri** listesindeyse veya 'Geçersiz kılmayla engelle' durumundaysa, **tüm uygulamalar için Dosya etkinliklerinde** tanımlanan tüm kısıtlamalar aynı kuralda uygulanır.  

#### <a name="macos-devices"></a>macOS cihazları

Windows cihazlarında olduğu gibi, artık macOS uygulamalarının hassas verilere erişmesini **Kısıtlanmış uygulama etkinlikleri** listesinde tanımlayarak engelleyebilirsiniz. 

> [!NOTE]
> Platformlar arası uygulamaların, üzerinde çalıştıkları işletim sistemine göre benzersiz yolları ile girilmesi gerektiğini unutmayın.

Mac uygulamalarının tam yolunu bulmak için:

1. macOS cihazında **Etkinlik İzleyicisi'ni** açın. Kısıtlamak istediğiniz işlemi bulma ve çift tıklama

2. **Dosyaları ve Bağlantı Noktalarını Aç** sekmesini seçin.
  
3. macOS uygulamaları için, uygulamanın adı da dahil olmak üzere tam yol adına ihtiyacınız vardır.

#### <a name="protect-sensitive-data-from-cloud-synchronization-apps"></a>Hassas verileri bulut eşitleme uygulamalarından koruma

onedrive.exe *gibi hassas* öğelerin bulut eşitleme uygulamaları tarafından bulutla eşitlenmesini önlemek için bulut eşitleme uygulamasını **İzin verilmeyen uygulamalar** listesine ekleyin. İzin verilmeyen bir bulut eşitleme uygulaması, engelleyici bir DLP ilkesi tarafından korunan bir öğeye erişmeye çalıştığında, DLP yinelenen bildirimler oluşturabilir. **İzin verilmeyen uygulamalar** altında **Otomatik karantinaya alma** seçeneğini etkinleştirerek bu yinelenen bildirimleri önleyebilirsiniz.  

##### <a name="auto-quarantine-preview"></a>Otomatik karantina (önizleme)

> [!NOTE]
> Otomatik karantina yalnızca Windows 10 desteklenir

Etkinleştirildiğinde, izin verilmeyen bir uygulama DLP korumalı hassas bir öğeye erişmeye çalıştığında otomatik karantina devreye giriyor. Otomatik karantina, hassas öğeyi yönetici tarafından yapılandırılmış bir klasöre taşır ve özgün klasörün yerine bir yer tutucu **.txt** dosyası bırakabilir. Yer tutucu dosyasındaki metni, kullanıcılara öğenin nereye taşındığını ve diğer ilgili bilgileri söyleyecek şekilde yapılandırabilirsiniz.  

Kullanıcı ve yöneticiler için sonsuz DLP bildirimleri zincirini önlemek için otomatik karantinayı kullanabilirsiniz. Bkz [. Senaryo 4: Otomatik karantina (önizleme) ile bulut eşitleme uygulamalarından DLP bildirimlerini döngüye almaktan kaçının](endpoint-dlp-using.md#scenario-4-avoid-looping-dlp-notifications-from-cloud-synchronization-apps-with-auto-quarantine-preview).

### <a name="unallowed-bluetooth-apps"></a>İzin verilmeyen Bluetooth uygulamaları

Kişilerin ilkeleriniz tarafından korunan dosyaları belirli Bluetooth uygulamaları aracılığıyla aktarmasını engelleyin.

### <a name="browser-and-domain-restrictions-to-sensitive-data"></a>Hassas verilere yönelik tarayıcı ve etki alanı kısıtlamaları

İlkelerinizle eşleşen hassas dosyaların sınırsız bulut hizmeti etki alanlarıyla paylaşılmasını kısıtlayın.

#### <a name="unallowed-browsers"></a>İzin verilmeyen tarayıcılar

Windows cihazları için, yürütülebilir adlarıyla tanımlanan ve bulut hizmetlerine yükleme kısıtlamasının geçersiz kılmayı engelleyecek veya engelleyecek şekilde ayarlandığı zorunlu bir DLP ilkesinin koşullarıyla eşleşen dosyalara erişimi engellenecek tarayıcılar eklersiniz. Bu tarayıcıların bir dosyaya erişimi engellendiğinde, son kullanıcılar dosyayı Microsoft Edge aracılığıyla açmalarını isteyen bir bildirim görür.

macOS cihazları için tam dosya yolunu eklemeniz gerekir. Mac uygulamalarının tam yolunu bulmak için:

1. macOS cihazında **Etkinlik İzleyicisi'ni** açın. Kısıtlamak istediğiniz işlemi bulma ve çift tıklama

2. **Dosyaları ve Bağlantı Noktalarını Aç** sekmesini seçin.
  
3. macOS uygulamaları için, uygulamanın adı da dahil olmak üzere tam yol adına ihtiyacınız vardır.

#### <a name="service-domains"></a>Hizmet etki alanları

> [!NOTE]
> **Hizmet etki alanları** ayarı yalnızca Microsoft Edge veya Microsoft [Purview Uzantısı](dlp-chrome-learn-about.md#learn-about-the-microsoft-purview-extension) yüklü Google Chrome kullanılarak karşıya yüklenen dosyalar için geçerlidir.

İlkeleriniz tarafından korunan hassas dosyaların Microsoft Edge'den belirli hizmet etki alanlarına yüklenip yüklenemeyeceğini denetleyebilirsiniz.

##### <a name="allow"></a>İzin ver

**Hizmet etki alanları** listesi **İzin Ver** olarak ayarlandığında, kullanıcı listedeki etki alanlarından herhangi birine hassas bir dosya yüklemeyi denediğinde DLP ilkeleri uygulanmaz.

Liste modu **İzin Ver** olarak ayarlanırsa, hassas bir öğe ve listede yer alan bir etki alanı içeren tüm kullanıcı etkinlikleri denetlenecektir. Etkinliğe izin verilir. Kullanıcı hassas bir öğe ve listede *olmayan* bir etki alanı içeren bir etkinliği denediğinde DLP ilkeleri ve ilkelerde tanımlanan eylemler uygulanır.

Örneğin, bu yapılandırmayla:

- **Hizmet etki alanları** liste modu **İzin Ver** olarak ayarlanır.
    - Contoso.com listede.
    -  DLP ilkesi, Kredi kartı numaraları içeren hassas öğelerin karşıya yüklenmesini **engelle** olarak ayarlanır.
 
Kullanıcı şu işlemleri yapmaya çalışır:

- Contoso.com kredi kartı numaralarını içeren hassas bir dosyayı karşıya yükleyin.
    - Kullanıcı etkinliğine izin verilir, denetlenir, bir olay oluşturulur, ancak olay ayrıntılarında ilke adını veya tetikleyici kuralı adını listelemez ve hiçbir uyarı oluşturulmaz. 

ancak bir kullanıcı aşağıdaki işlemleri yapmaya çalışırsa: 

- wingtiptoys.com (listede olmayan) kredi kartı numaralarını içeren hassas bir dosyayı karşıya yükleyin.
    - İlke uygulanır ve kullanıcı etkinliği engellenir. Bir olay oluşturulur ve bir uyarı oluşturulur. 
 
##### <a name="block"></a>Engelle
 
**Hizmet etki alanları** listesi **Engelle** olarak ayarlandığında, kullanıcı listedeki etki alanlarından herhangi birine hassas bir dosya yüklemeyi denediğinde DLP ilkeleri uygulanır.

Liste modu **Engelle** olarak ayarlanırsa, kullanıcı hassas bir öğe ve listede yer alan bir etki alanı içeren bir etkinliği denediğinde DLP ilkeleri ve ilkelerde tanımlanan eylemler uygulanır. Hassas bir öğe ve listede olmayan bir etki alanı içeren tüm etkinlikler denetlenecek ve kullanıcı etkinliğine izin verilir.

Örneğin, bu yapılandırmayla:

- **Hizmet etki alanları** liste modu **Engelle** olarak ayarlanır.
    - Contoso.com listede.
-  Bir DLP ilkesi, kredi kartı numaraları içeren hassas öğelerin karşıya yüklenmesi için **geçersiz kılma ile engelle** olarak ayarlanır.
 
Kullanıcı şu işlemleri yapmaya çalışır:

- Contoso.com kredi kartı numaralarını içeren hassas bir dosyayı karşıya yükleyin.
    - Kullanıcı etkinliği engellenir, ancak kullanıcı bloğu geçersiz kılabilir, bir olay oluşturulur ve bir uyarı tetiklenir.

ancak bir kullanıcı aşağıdaki işlemleri yapmaya çalışırsa: 

- wingtiptoys.com (listede olmayan) kredi kartı numaralarını içeren hassas bir dosyayı karşıya yükleyin.
    - İlke *uygulanmaz* ve kullanıcı etkinliği denetlener. Bir olay oluşturulur, ancak olay ayrıntılarında ilke adını veya tetikleyici kuralı adını listelemez ve hiçbir uyarı oluşturulmaz. 

> [!IMPORTANT]
> Hizmet kısıtlama modu "İzin Ver" olarak ayarlandığında, kısıtlamalar uygulanmadan önce en az bir hizmet etki alanı yapılandırmış olmanız gerekir.

Özet tablosu


|Hizmet etki alanı listesi ayarı |Hassas öğeyi listedeki siteye yükleme  |Hassas öğeyi listede olmayan siteye yükleme  |
|---------|---------|---------|
|İzin ver   |- DLP ilkeleri uygulanmaz </br> - Kullanıcı etkinliği denetlendi </br> - Olay oluşturuldu        | - DLP ilkeleri uygulanır </br> - Yapılandırılmış eylemler gerçekleştirilen </br>- Olay oluşturulur </br>- Uyarı oluşturulur          |
|Engelle    | - DLP ilkeleri uygulanır </br> - Yapılandırılmış eylemler gerçekleştirilen </br> - Olay oluşturulur </br> - Uyarı oluşturulur         | - DLP ilkeleri uygulanmaz </br> - Kullanıcı etkinliği denetlendi </br>- Olay oluşturulur         |


Listeye bir etki alanı eklediğinizde hizmet etki alanının FQDN biçimini bitiş `.` olmadan kullanın.

Örneğin:

| Giriş | URL eşleştirme davranışı |
|---|---|
| **CONTOSO.COM** |**Belirtilen etki alanı adıyla ve herhangi bir alt siteyle eşleşir**: <p>*://contoso.com<p>*:/ /contoso.com/ <p>*://contoso.com/anysubsite1 <p>*:/ /contoso.com/anysubsite1/anysubsite2 (vb.) <p>**Alt etki alanları veya belirtilmemiş etki alanlarıyla eşleşmiyor**: <p>*://anysubdomain.contoso.com <p>*:/ /anysubdomain.contoso.com.AU |
| ***.CONTOSO.COM** |**Belirtilen etki alanı adı, herhangi bir alt etki alanı ve herhangi bir siteyle eşleşir**: <p>*://contoso.com <p>*:/ /contoso.com/anysubsite <p>*://contoso.com/anysubsite1/anysubsite2 <p>*:/ /anysubdomain.contoso.com/ <p>*://anysubdomain.contoso.com/anysubsite/ <p>*:/ /anysubdomain1.anysubdomain2.contoso.com/anysubsite/ <p>*://anysubdomain1.anysubdomain2.contoso.com/anysubsite1/anysubsite2 (vb.) <p>**Belirtilmemiş etki alanlarıyla eşleşmiyor** <p>*://anysubdomain.contoso.com.AU/ |
| **`www.contoso.com`** |**Belirtilen etki alanı adıyla eşleşir**: <p>`www.contoso.com` <p>**Belirtilmemiş etki alanları veya alt etki alanlarıyla eşleşmiyor** <p>*://anysubdomain.contoso.com/, bu durumda FQDN etki alanı adının kendisini koymanız gerekir `www.contoso.com`|

#### <a name="sensitive-service-domains"></a>Hassas hizmet etki alanları

Hassas hizmetler etki alanlarında bir web sitesini listelediğinizde şunları yapmaya çalışan kullanıcıları denetleyebilir, geçersiz kılmayla engelleyebilir veya engelleyebilirsiniz:

- web sitesinden yazdırma
- web sitesinden veri kopyalama
- web sitesini yerel dosyalar olarak kaydetme
- hariç tutulan bir web sitesine hassas bir dosya yükleme (bu ilkede yapılandırılır)

Yazdırma, veri kopyalama ve kaydetme eylemleri için her web sitesinin bir web sitesi grubunda listelenmiş olması ve kullanıcının Microsoft Edge üzerinden web sitesine erişmesi gerekir. Karşıya yükleme eylemi için kullanıcı Purview uzantısıyla Microsoft Edge veya Google Chrome kullanıyor olabilir. Hassas hizmet etki alanları, Cihazlar için DLP ilkesiyle birlikte kullanılır. İlke eylemleri atamak istediğiniz ve genel web sitesi grubu eylemlerinden farklı web sitesi grupları da tanımlayabilirsiniz. Daha fazla bilgi için bkz [. Senaryo 6 Hassas hizmet etki alanlarında kullanıcı etkinliklerini izleme veya kısıtlama](endpoint-dlp-using.md#scenario-6-monitor-or-restrict-user-activities-on-sensitive-service-domains) .


### <a name="additional-settings-for-endpoint-dlp"></a>Uç nokta DLP'leri için ek ayarlar

#### <a name="business-justification-in-policy-tips"></a>İlke ipuçlarında iş gerekçesi

DLP ilkesi ipucu bildirimlerinde kullanıcıların iş gerekçesi seçeneğiyle nasıl etkileşim kuracağını denetleyebilirsiniz. Bu seçenek, kullanıcılar bir DLP ilkesindeki **Geçersiz kılma ile engelle** ayarı tarafından korunan bir etkinlik gerçekleştirdiğinde görüntülenir. Bu genel bir ayardır. Aşağıdaki seçeneklerden birini seçebilirsiniz:

- **Varsayılan seçenekleri ve özel metin kutusunu göster**: Varsayılan olarak, kullanıcılar yerleşik bir gerekçe seçebilir veya kendi metinlerini girebilir.
- **Yalnızca varsayılan seçenekleri göster**: Kullanıcılar yalnızca yerleşik bir gerekçe seçebilir.
- **Yalnızca özel metin kutusunu göster**: Kullanıcılar yalnızca kendi gerekçelerini girebilir. Son kullanıcı ilkesi ipucu bildiriminde yalnızca metin kutusu görünür. 

##### <a name="customizing-the-options-in-the-drop-down-menu"></a>Açılan menüde seçenekleri özelleştirme

Kullanıcılar ilke bildirim ipucuyla etkileşime geçtiğinde seçenekleri **özelleştir açılan menüsünü** seçerek en fazla beş özelleştirilmiş seçenek oluşturabilirsiniz. 


|Seçeneği |Varsayılan metin  |
|---------|---------|
|seçenek 1    | **Bu, yerleşik bir iş iş akışının parçasıdır**  veya özelleştirilmiş metin girebilirsiniz        |
|seçenek 2  |**Yöneticim bu eylemi onayladı** veya özelleştirilmiş metin girebilirsiniz         |
|seçenek 3   |**Acil erişim gerekli; Yöneticimi ayrıca bilgilendireceğim** veya özelleştirilmiş metin girebilirsiniz          |
|Hatalı pozitif seçeneği göster     |**Bu dosyalardaki bilgiler hassas değil** veya özelleştirilmiş metin girebilirsiniz          |
|seçenek 5    |**Diğer** veya özelleştirilmiş metin girebilirsiniz         |

### <a name="always-audit-file-activity-for-devices"></a>Cihazlar için her zaman dosya etkinliğini denetleme

Varsayılan olarak, cihazlar eklendiğinde Office, PDF ve CSV dosyalarına yönelik etkinlik otomatik olarak denetlenip etkinlik gezgininde gözden geçirilebilir. Bu etkinliğin yalnızca eklenen cihazlar etkin bir ilkeye dahil edildiğinde denetlenmesini istiyorsanız bu özelliği kapatın.

Dosya etkinliği, etkin bir ilkeye dahil olup olmadıklarına bakılmaksızın eklenen cihazlar için her zaman denetlenecektir.

> [!IMPORTANT]
> [Yazıcı gruplarını (önizleme)](#printer-groups-preview), [Çıkarılabilir depolama cihazı gruplarını](#removable-storage-device-groups-preview), [Ağ paylaşım gruplarını](#network-share-groups-preview) ve [VPN ayarlarını](#vpn-settings-preview) kullanabilmeniz için [buraya](https://forms.office.com/r/GNVTFvxuZv) kaydetmeniz gerekir.

### <a name="printer-groups-preview"></a>Yazıcı grupları (önizleme)

İlke eylemleri atamak istediğiniz ve genel yazdırma eylemlerinden farklı yazıcı gruplarını tanımlamak için bu ayarı kullanın. Örneğin, DLP ilkenizin hukuk departmanındaki yazıcılar dışında tüm yazıcılara sözleşme yazdırmayı engellemesini istediğinizi varsayalım.

Bu özellik, aşağıdaki Windows sürümlerinden herhangi birini çalıştıran cihazlarda kullanılabilir:  

- Windows 10 ve üzeri (20H2, 21H1, 21H2) 
- Win 11 21H2, 22H2
- Windows Server 2022

Yazıcıyı şu parametrelerle tanımlarsınız:

- Kolay yazıcı adı - Cihaz yöneticisindeki yazıcı cihazı özellik ayrıntılarından Kolay yazıcı adı değerini alın.
- USB ürün kimliği - Cihaz yöneticisindeki yazıcı cihazı özellik ayrıntılarından Cihaz Örneği yol değerini alın. Ürün Kimliği ve Satıcı Kimliği biçimine dönüştürün, bkz. [Standart USB tanımlayıcıları](/windows-hardware/drivers/install/standard-usb-identifiers).
- USB satıcı kimliği - Cihaz yöneticisindeki yazıcı cihazı özellik ayrıntılarından Cihaz Örneği yol değerini alın. Ürün Kimliği ve Satıcı Kimliği biçimine dönüştürün, bkz. [Standart USB tanımlayıcıları](/windows-hardware/drivers/install/standard-usb-identifiers).
- IP aralığı
- Dosyaya yazdır - Örneğin, Microsoft PDF'ye Yazdır veya Microsoft XPS Belge Yazıcısı.
- Yazıcıda dağıtılan evrensel yazdırma - Evrensel yazıcılar hakkında daha fazla bilgi için bkz. [Evrensel Yazdırmayı Ayarlama](/universal-print/fundamentals/universal-print-getting-started.md)
- Şirket yazıcısı - etki alanınızdaki şirket içi Windows yazdırma sunucusu aracılığıyla paylaşılan bir yazdırma kuyruğudur. Yolu print-server\contoso.com\legal_printer_001 gibi  \\görünebilir
- Yerel ortama yazdır

Gruptaki her yazıcıya bir **Görünen ad** atarsınız. Ad yalnızca Purview konsolunda görünür. Bu nedenle, örneğe devam ederek **Legal printers** adlı bir yazıcı grubu oluşturur ve kolay adlarına göre tek tek yazıcılar (diğer adla) eklersiniz, örneğin `legal_printer_001`, `legal_printer_002` ve `legal_color_printer`.

Belirli bir yazıcıyı kesin olarak tanımlamanıza yardımcı olması için parametreleri birden çok kez seçebilirsiniz.

Bu ilke eylemlerini bir DLP ilkesinde gruba atayabilirsiniz:

- İzin ver (kullanıcı bildirimleri veya uyarıları olmadan denetim)
- Yalnızca denetim (bildirim ve uyarı ekleyebilirsiniz)
- Geçersiz kılma ile engelle (eylemi engeller, ancak kullanıcı geçersiz kılabilir)
- Engelle (ne olursa olsun bloklar)

#### <a name="create-a-printer-group"></a>Yazıcı grubu oluşturma

1. [Microsoft Purview uyumluluk portalı](https://compliance.microsoft.com) >  **Veri kaybı önleme** > **Uç Nokta DLP ayarları** > **Yazıcı gruplarını** açın.
1. **Yazıcı grubu oluştur'u** seçin.
1. Gruba bir ad verin.
1. **Yazıcı ekle'yi** seçin.
1. Yazıcıya yalnızca burada görünecek bir **Diğer ad verin.
1. Parametreleri seçin ve belirli bir yazıcıyı kesin olarak tanımlamak için değerleri sağlayın.
1. **Ekle**'yi seçin.
1. Gerektiğinde diğer yazıcıları ekleyin.
1. **Kapat**'ı seçin.

En yaygın kullanım örneği, sözleşmelerin yalnızca hukuk departmanındaki yazıcılara yazdırılması için yukarıdaki örnekte olduğu gibi yazıcı gruplarını izin verilenler listesi olarak kullanmaktır. Burada bir yazıcı grubu tanımladıktan sonra, kapsamı **Cihazlar** olarak belirlenmiş ilkelerinizde kullanılabilir. [İlke eylemlerini yetkilendirme gruplarını](endpoint-dlp-using.md#scenario-7-authorization-groups-preview) kullanacak şekilde yapılandırma hakkında daha fazla bilgi için bkz. Senaryo 7 Yetkilendirme grupları.

### <a name="removable-storage-device-groups-preview"></a>Çıkarılabilir depolama cihazı grupları (önizleme)

Genel yazdırma eylemlerinden farklı ilke eylemleri atamak istediğiniz USB başparmak sürücüleri gibi çıkarılabilir depolama cihazı gruplarını tanımlamak için bu ayarı kullanın. Örneğin, DLP ilkenizin verileri yedeklemek için kullanılan ve ardından site dışına gönderilen USB bağlantılı sabit sürücüler dışında mühendislik belirtimlerine sahip öğelerin tüm kaldırılabilir depolama cihazlarına kopyalanmasını engellemesini istediğinizi varsayalım.

Bu özellik, aşağıdaki Windows sürümlerinden herhangi birini çalıştıran cihazlarda kullanılabilir:  

- Windows 10 ve üzeri (20H2, 21H1, 21H2) 
- Win 11 21H2, 22H2
- Windows 10 RS5 (KB 5006744) ve Windows Server 2022 

Kaldırılabilir depolama cihazlarını şu parametrelerle tanımlayabilirsiniz:

- Depolama cihazı kolay adı - Cihaz yöneticisindeki depolama cihazı özellik ayrıntılarından Kolay ad değerini alın.
- USB ürün kimliği - Cihaz yöneticisindeki USB cihaz özelliği ayrıntılarından Cihaz Örneği yol değerini alın. Ürün Kimliği ve Satıcı Kimliği biçimine dönüştürün, bkz. [Standart USB tanımlayıcıları](/windows-hardware/drivers/install/standard-usb-identifiers).
- USB satıcı kimliği - Cihaz yöneticisindeki USB cihaz özelliği ayrıntılarından Cihaz Örneği yol değerini alın. Ürün Kimliği ve Satıcı Kimliği biçimine dönüştürün, bkz. [Standart USB tanımlayıcıları](/windows-hardware/drivers/install/standard-usb-identifiers).
- Seri numarası kimliği - Cihaz yöneticisindeki depolama cihazı özellik ayrıntılarından seri numarası kimliği değerini alın.
- Cihaz Kimliği - Cihaz yöneticisindeki depolama cihazı özellik ayrıntılarından cihaz kimliği değerini alın.
- Örnek yolu kimliği - Cihaz yöneticisindeki depolama cihazı özellik ayrıntılarından cihaz kimliği değerini alın.
- Donanım Kimliği - Cihaz yöneticisindeki depolama cihazı özellik ayrıntılarından donanım kimliği değerini alın.

Gruptaki her çıkarılabilir depolama cihazına bir **Diğer Ad** atarsınız. Diğer ad, yalnızca Purview konsolunda görünen bir addır. Bu nedenle, örneğe devam ederek **Backup** adlı çıkarılabilir bir depolama cihazı grubu oluşturup , ve `backup_drive_002`gibi `backup_drive_001`kolay adlarına göre tek tek cihazları (diğer adla) ekleyebilirsiniz.

Parametreleri birden çok kez seçebilirsiniz ve yazıcı grubu bu parametreleri karşılayan tüm cihazları içerir.

Bu ilke eylemlerini bir DLP ilkesinde gruba atayabilirsiniz:

- İzin ver (kullanıcı bildirimleri veya uyarıları olmadan denetim)
- Yalnızca denetim (bildirim ve uyarı ekleyebilirsiniz)
- Geçersiz kılma ile engelle (eylemi engeller, ancak kullanıcı geçersiz kılabilir)
- Engelle (ne olursa olsun bloklar)

#### <a name="create-a-removable-storage-device-group"></a>Çıkarılabilir depolama cihazı grubu oluşturma

1. [Microsoft Purview uyumluluk portalı](https://compliance.microsoft.com) >  **Veri kaybı önleme** > **Uç Nokta DLP ayarları** > **Çıkarılabilir depolama cihazı gruplarını** açın.
1. **Çıkarılabilir depolama cihazı grubu oluştur'u** seçin.
1. **Bir Grup adı** girin.
1. **Çıkarılabilir depolama cihazı ekle'yi** seçin.
1. **Diğer ad sağlayın**.
1. Parametreleri seçin ve belirli bir cihazı kesin olarak tanımlamak için değerleri sağlayın.
1. **Ekle**'yi seçin.
1. Gerektiğinde gruba başka cihazlar ekleyin.
1. **Kapat**'ı seçin.

En yaygın kullanım örneği, dosyaların yalnızca **Yedekleme** grubundaki cihazlara kopyalanmasını sağlamak için yukarıdaki örnekte olduğu gibi çıkarılabilir depolama cihazları gruplarını izin verilenler listesi olarak kullanmaktır. Burada çıkarılabilir bir depolama cihazı grubu tanımladıktan sonra, kapsamı **Cihazlar** olarak belirlenmiş ilkelerinizde kullanılabilir. [İlke eylemlerini yetkilendirme gruplarını](endpoint-dlp-using.md#scenario-7-authorization-groups-preview) kullanacak şekilde yapılandırma hakkında daha fazla bilgi için bkz. Senaryo 7 Yetkilendirme grupları. Senaryo 7 örnek olarak yazıcı yetkilendirme gruplarını kullansa da, ilkeler aynıdır. Değişen tek şey grupların adları ve seçtiğiniz eylemlerdir.

### <a name="network-share-groups-preview"></a>Ağ paylaşımı grupları (önizleme)

İlke eylemleri atamak istediğiniz ve genel ağ paylaşım yolu eylemlerinden farklı ağ paylaşım yolu gruplarını tanımlamak için bu ayarı kullanın. Örneğin, kullanıcılar korumalı dosyaları bu gruptaki ağ paylaşımları dışında ağ paylaşımlarına kaydetmeye veya kopyalamaya çalıştığında DLP ilkenizin engellemesini istediğinizi varsayalım.


Bu özellik, aşağıdaki Windows sürümlerinden herhangi birini çalıştıran cihazlarda kullanılabilir:  

- Windows 10 ve üzeri (20H2, 21H1, 21H2) 
- Win 11 21H2, 22H2
- Windows 10 RS5 (KB 5006744) ve Windows Server 2022 


Ağ paylaşımı yollarını, hepsinin başlangıç ön ekini tanımlayarak eklersiniz. Örneğin:

- '\\Kitaplık' şu şekilde eşleşecektir:
    -  \Kitaplık klasörü ve tüm alt klasörleri.

- Joker karakterler kullanabilirsiniz, örneğin '\\Kullanıcılar\*\Masaüstü' aşağıdakilerle eşleşecektir:
    - '\\USers\user1\Desktop'
    - '\\USers\user1\user2\Desktop'
    - '\\Users\*\Desktop'

- Ortam değişkenlerini kullanabilirsiniz, örneğin:
    - %AppData%\app123

Bu ilke eylemlerini bir DLP ilkesinde gruba atayabilirsiniz:

- İzin ver (kullanıcı bildirimleri veya uyarıları olmadan denetim)
- Yalnızca denetim (bildirim ve uyarı ekleyebilirsiniz)
- Geçersiz kılma ile engelle (eylemi engeller, ancak kullanıcı geçersiz kılabilir)
- Engelle (ne olursa olsun bloklar)

#### <a name="create-a-network-share-group"></a>Ağ Paylaşımı grubu oluşturma

1. [Microsoft Purview uyumluluk portalı](https://compliance.microsoft.com) >  **Veri kaybı önleme** > **Uç Noktası DLP ayarları** > **Ağ paylaşımı gruplarını** açın.
**1.Ağ paylaşım grubu oluştur'u** seçin.
1. **Bir Grup adı** girin.
1. Dosya yolunu paylaşıma ekleyin.
1. **Ekle**'yi seçin.
1. Gerektiğinde gruba diğer paylaşım yollarını ekleyin.
1. **Kapat**'ı seçin.


En yaygın kullanım örneği, kullanıcıların korumalı dosyaları yalnızca grupta tanımlanan ağ paylaşımlarına kaydetmesine veya kopyalamasına izin vermek için ağ paylaşımı grubunu yukarıdaki örnekte olduğu gibi izin verilenler listesi olarak kullanmaktır. Burada bir ağ paylaşım grubu tanımladıktan sonra, kapsamı **Cihazlar** olarak belirlenmiş ilkelerinizde kullanılabilir. [İlke eylemlerini yetkilendirme gruplarını](endpoint-dlp-using.md#scenario-7-authorization-groups-preview) kullanacak şekilde yapılandırma hakkında daha fazla bilgi için bkz. Senaryo 7 Yetkilendirme grupları.

### <a name="vpn-settings-preview"></a>VPN ayarları (önizleme)

YALNıZCA bu VPN üzerinden gerçekleştirilen eylemleri denetlemek için VPN listesini kullanın.

Bu özellik, şu Windows sürümlerinden herhangi birini çalıştıran cihazlarda kullanılabilir:  
    
- Windows 10 ve üzeri (20H2, 21H1, 21H2) 
- Windows 11 21H2, 22H2
- Windows 10 RS5 (KB 5006744)

**VPN Ayarları'nda bir VPN'yi** listelediğinizde, bu ilke eylemlerini bunlara atayabilirsiniz:

- İzin ver (kullanıcı bildirimleri veya uyarıları olmadan denetim)
- Yalnızca denetim (bildirim ve uyarı ekleyebilirsiniz)
- Geçersiz kılma ile engelle (eylemi engeller, ancak kullanıcı geçersiz kılabilir)
- Engelle (ne olursa olsun bloklar)

Bu eylemler, bu kullanıcı etkinliklerine tek tek veya toplu olarak uygulanabilir:

- Panoya kopyala
- USB çıkarılabilir cihaza kopyalama
- Ağ paylaşımına kopyalama
- Yazdırma
- İzin verilmeyen Bluetooth uygulamasını kullanarak kopyalama veya taşıma
- RDP kullanarak kopyalama veya taşıma

Cihazlarda etkinliği kısıtlamak için bir DLP ilkesi yapılandırırken, kullanıcılar listelenen VPN'lerden herhangi biri içinde kuruluşunuza bağlandığında gerçekleştirilen her etkinliğe ne olacağını denetleyebilirsiniz.

VPN'i bu Sunucu **adresi** veya **Ağ adresi** parametreleriyle tanımlarsınız. 

#### <a name="get-the-server-address-or-network-address"></a>Sunucu adresini veya Ağ adresini alma

1. DLP tarafından izlenen bir Windows cihazında yönetici olarak **bir Windows PowerShell** penceresi açın.
1. Bu cmdlet'i çalıştırın

```powershell-interactive
Get-VpnConnection
```
3. Bu cmdlet'i çalıştırmak birden çok alan ve değer döndürür.
1. **ServerAddress** alanını bulun ve bu değeri kaydedin. VPN listesinde bir VPN girişi oluşturduğunuzda bunu kullanacaksınız.
1. **Ad** alanını bulun ve bu değeri kaydedin. **AD** alanı, VPN listesinde bir VPN girişi oluşturduğunuzda **Ağ adresi** alanına eşler.

#### <a name="add-a-vpn"></a>VPN ekleme

1. [Microsoft Purview uyumluluk portalı](https://compliance.microsoft.com) >  **Veri kaybı önleme** > **Uç Noktası DLP ayarları****VPN ayarlarını** >  açın.
1. **VPN adresleri ekle veya düzenle'yi** seçin.
1. Get-VpnConnection'ı çalıştırmak için **Sunucu adresini** veya **Ağ adresini** belirtin.
1. **Kaydet**'i seçin.
1. Öğeyi kapatın.

> [!IMPORTANT]
> bir ilkenin eylemlerini tanımlarken VPN listesini kullandığınızda, seçenek olarak **Kurumsal ağ** seçeneğini de görürsünüz. **Kurumsal ağ** bağlantıları, kuruluşunuzun kaynaklarına yönelik bağlantılardır. Bu bağlantılar VPN'leri içerebilir. 

İlke [eylemlerini ağ özel durumlarını](endpoint-dlp-using.md#scenario-8-network-exceptions-preview)kullanacak şekilde yapılandırma hakkında daha fazla bilgi için bkz. Senaryo 8 Ağ özel durumları.

## <a name="see-also"></a>Ayrıca bkz.

- [Uç nokta veri kaybı önleme hakkında daha fazla bilgi edinme](endpoint-dlp-learn-about.md)
- [Uç noktada veri kaybı önlemeyi kullanmaya başlama](endpoint-dlp-getting-started.md)
- [Veri kaybı önleme hakkında daha fazla bilgi edinme](dlp-learn-about-dlp.md)
- [Bir DLP ilkesi oluşturma, test etme ve ayarlama](create-test-tune-dlp-policy.md)
- [Etkinlik gezginini kullanmaya başlama](data-classification-activity-explorer.md)
- [Uç Nokta için Microsoft Defender](/windows/security/threat-protection/)
- [Windows 10 ve Windows 11 cihazlarını Microsoft Purview'a eklemeye genel bakış](/microsoft-365/compliance/device-onboarding-overview)
- [Microsoft 365 aboneliği](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Azure Active Directory 'ye (AAD) katılmış](/azure/active-directory/devices/concept-azure-ad-join)
- [Chromium tabanlı yeni Microsoft Edge'i indirin](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [Varsayılan DLP ilkesini kullanmaya başlama](get-started-with-the-default-dlp-policy.md)
- [Bir şablondan DLP ilkesi oluşturma](create-a-dlp-policy-from-a-template.md)
