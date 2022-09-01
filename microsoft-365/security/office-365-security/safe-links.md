---
title: Office 365 için Microsoft Defender için Tam Güvenli Bağlantılar'a genel bakış
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
ms.date: 09/08/2021
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: Bir kuruluşu kimlik avına ve kötü amaçlı URL kullanan diğer saldırılara karşı korumak için Office 365 için Defender'de Güvenli Bağlantılar koruması hakkında bilgi edinin. Teams Güvenli Bağlantılar'ı keşfedin ve Güvenli Bağlantılar iletilerinin grafiklerini görün.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 63f2a129b5a02969cdc8859611822cdb3c89ec89
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67497345"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a>Office 365 için Microsoft Defender'da Güvenli Bağlantılar

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Bu makale, [Office 365 için Microsoft Defender](defender-for-office-365.md) sahip iş müşterilerine yöneliktir. Outlook.com, Microsoft 365 Aile veya Microsoft 365 Bireysel kullanıyorsanız ve Outlook'ta Güvenli Bağlantılar hakkında bilgi arıyorsanız bkz. [Gelişmiş Outlook.com güvenliği](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Güvenli Bağlantılar[, Office 365 için Defender'de](defender-for-office-365.md) posta akışında gelen e-posta iletilerinin URL taramasını ve yeniden yazılmasını ve e-posta iletilerindeki ve diğer konumlardaki URL'lerin ve bağlantıların tıklama zamanında doğrulanmasını sağlayan bir özelliktir. Güvenli Bağlantılar taraması, Exchange Online Protection (EOP) içindeki gelen [e-posta](anti-spam-protection.md) iletilerinde normal istenmeyen posta önleme ve [kötü amaçlı yazılımdan koruma](anti-malware-protection.md) özelliklerine ek olarak gerçekleşir. Güvenli Bağlantılar taraması, kuruluşunuzun kimlik avı ve diğer saldırılarda kullanılan kötü amaçlı bağlantılardan korunmasına yardımcı olabilir.

Office 365 için Microsoft Defender'da Güvenli Bağlantılar ile kötü amaçlı bağlantılara karşı koruma hakkında bu kısa videoyu izleyin.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGzjb]

> [!NOTE]
> Varsayılan Güvenli Bağlantılar ilkesi olmasa **da, yerleşik koruma** ön ayarı güvenlik ilkesi, Office 365 için Defender lisansına sahip tüm alıcılara (özel Güvenli Bağlantılar ilkelerinde tanımlanmamış kullanıcılar veya Standart veya Katı önceden ayarlanmış güvenlik ilkeleri) e-posta iletilerinde, Microsoft Teams'de ve desteklenen Office uygulamalarındaki dosyalarda Güvenli Bağlantılar koruması sağlar. Daha fazla bilgi için bkz. [EOP'de önceden ayarlanmış güvenlik ilkeleri ve Office 365 için Microsoft Defender](preset-security-policies.md). Ayrıca, belirli kullanıcılar, gruplar veya etki alanları için geçerli olan Güvenli Bağlantılar ilkeleri de oluşturabilirsiniz. Yönergeler için bkz. [Office 365 için Microsoft Defender'de Güvenli Bağlantılar ilkelerini ayarlama](set-up-safe-links-policies.md).

Güvenli Bağlantılar koruması aşağıdaki konumlarda kullanılabilir:

- **Email iletileri**: E-posta iletilerindeki bağlantılar için Güvenli Bağlantılar korumaları, Güvenli Bağlantılar ilkeleri tarafından denetlenmektedir.

  E-posta iletileri için Güvenli Bağlantılar koruması hakkında daha fazla bilgi için, bu makalenin devamında yer alan [e-posta iletileri için Güvenli Bağlantılar ayarları](#safe-links-settings-for-email-messages) bölümüne bakın.

  > [!NOTE]
  > Güvenli Bağlantılar posta etkin ortak klasörlerde çalışmaz.
  >
  > Güvenli Bağlantılar yalnızca HTTP(S) ve FTP biçimlerini destekler.

- **Microsoft Teams**: Teams konuşmalarındaki, grup sohbetlerindeki veya kanallardaki bağlantılar için Güvenli Bağlantılar koruması Güvenli Bağlantılar ilkeleri tarafından denetlenmektedir.

  Teams'de Güvenli Bağlantılar koruması hakkında daha fazla bilgi için, bu makalenin devamında yer alan [Microsoft Teams için Güvenli Bağlantılar ayarları](#safe-links-settings-for-microsoft-teams) bölümüne bakın.

  > [!NOTE]
  > Şu anda Microsoft Teams için Güvenli Bağlantılar koruması Microsoft 365 GCC High veya Microsoft 365 DoD'da kullanılamaz.

- **Office uygulamaları**: Desteklenen Office masaüstü, mobil ve web uygulamaları için Güvenli Bağlantılar koruması, Güvenli Bağlantılar ilkeleri tarafından denetlenebilir.

  Office uygulamalarında Güvenli Bağlantılar koruması hakkında daha fazla bilgi için, bu makalenin devamında yer alan [Office uygulamaları için Güvenli Bağlantılar ayarları](#safe-links-settings-for-office-apps) bölümüne bakın.

Bu makale, aşağıdaki Güvenli Bağlantılar ayarları türlerinin ayrıntılı açıklamalarını içerir:

- **Güvenli Bağlantılar ilkelerindeki ayarlar**: Bu ayarlar yalnızca belirli ilkelere dahil olan kullanıcılar için geçerlidir ve ayarlar ilkeler arasında farklı olabilir. Bu ayarlar şunlardır:

  - [E-posta iletileri için Güvenli Bağlantılar ayarları](#safe-links-settings-for-email-messages)
  - [Microsoft Teams için Güvenli Bağlantılar ayarları](#safe-links-settings-for-microsoft-teams)
  - [Office uygulamaları için Güvenli Bağlantılar ayarları](#safe-links-settings-for-office-apps)
  - [Güvenli Bağlantılar ilkelerindeki "Aşağıdaki URL'leri yeniden yazmayın" listeleri](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **Genel Güvenli Bağlantılar ayarları**: Bu ayarlar Güvenli Bağlantılar ilkelerinde değil genel olarak yapılandırılır. Bu ayarlar şunlardır:

  - [Güvenli Bağlantılar için "Aşağıdaki URL'leri engelle" listesi](#block-the-following-urls-list-for-safe-links)

Aşağıdaki tabloda, Office 365 için Defender içeren Microsoft 365 ve Office 365 kuruluşlarında Güvenli Bağlantılar senaryoları açıklanmaktadır (örneklerde lisans eksikliğinin hiçbir zaman sorun oluşturmadığını unutmayın).

|Senaryo|Sonuç|
|---|---|
|Jean pazarlama departmanının bir üyesidir. Office uygulamaları için Güvenli Bağlantılar koruması, pazarlama departmanı üyeleri için geçerli olan Güvenli Bağlantılar ilkesinde açıktır. Jean, e-posta iletisinde bir PowerPoint sunusu açar ve ardından sunudaki bir URL'ye tıklar.|Jean, Güvenli Bağlantılar tarafından korunuyor. <p> Jean, Office uygulamaları için Güvenli Bağlantılar korumasının açık olduğu Güvenli Bağlantılar ilkesine dahildir. <p> Office uygulamalarında Güvenli Bağlantılar koruması gereksinimleri hakkında daha fazla bilgi için, bu makalenin devamında yer alan [Office uygulamaları için Güvenli Bağlantılar ayarları](#safe-links-settings-for-office-apps) bölümüne bakın.|
|Chris'in Microsoft 365 E5 kuruluşunda Yapılandırılmış Güvenli Bağlantılar ilkesi yok. Chris, dış gönderenden, sonunda tıkladığı kötü amaçlı bir web sitesinin URL'sini içeren bir e-posta alır.|Chris, Güvenli Bağlantılar tarafından korunuyor. <p> **Yerleşik koruma** önceden ayarlanmış güvenlik ilkesi, tüm alıcılara (özel Güvenli Bağlantılar ilkeleri veya Standart veya Katı önceden belirlenmiş güvenlik ilkeleri içinde tanımlanmayan kullanıcılar) Güvenli Bağlantılar koruması sağlar. Daha fazla bilgi için bkz. [EOP'de önceden ayarlanmış güvenlik ilkeleri ve Office 365 için Microsoft Defender](preset-security-policies.md).|
|Pat'in kuruluşunda yöneticiler Pat'i uygulayan bir Güvenli Bağlantılar ilkesi oluşturmuştur, ancak Office uygulamaları için Güvenli Bağlantılar koruması kapalıdır. Pat bir Word belgesi açar ve dosyadaki bir URL'ye tıklar.|Pat, Güvenli Bağlantılar tarafından korunmaz. <p> Pat etkin bir Güvenli Bağlantılar ilkesine dahil olsa da, bu ilkede Office uygulamaları için Güvenli Bağlantılar koruması kapatıldığından koruma uygulanamaz.|
|Lee'nin kuruluşunda, `https://tailspintoys.com` Güvenli Bağlantılar için genel ayarlardaki **Aşağıdaki URL'leri engelle** listesinde yapılandırılır. Lee'yi içeren bir Güvenli Bağlantılar ilkesi zaten var. Lee, URL'sini `https://tailspintoys.com/aboutus/trythispage`içeren bir e-posta iletisi alır. Lee URL'ye tıklar.|URL Lee için otomatik olarak engellenebilir; listedeki URL girdisine ve Lee'nin kullandığı e-posta istemcisine bağlıdır. Daha fazla bilgi için, bu [makalenin devamında yer alan Güvenli Bağlantılar için "Aşağıdaki URL'leri engelle" listesine](#block-the-following-urls-list-for-safe-links) bakın.|
|Jamie ve Julia contoso.com için çalışıyor. Uzun zaman önce, yöneticiler Hem Jamie hem de Julia için geçerli olan Güvenli Bağlantılar ilkeleri yapılandırdı. Jamie, e-postanın kötü amaçlı bir URL içerdiğini bilmeden Julia'ya bir e-posta gönderir.|Julia, kendisine uygulanan Güvenli Bağlantılar ilkesi iç alıcılar arasındaki iletilere uygulanacak şekilde **yapılandırılmışsa** Güvenli Bağlantılar tarafından korunur. Daha fazla bilgi için, bu makalenin devamında yer alan [e-posta iletileri için Güvenli Bağlantılar ayarları](#safe-links-settings-for-email-messages) bölümüne bakın.|

## <a name="recipient-filters-in-safe-links-policies"></a>Güvenli Bağlantılar ilkelerindeki alıcı filtreleri

İlkenin kime uygulanacağını belirleyen alıcı koşullarını ve özel durumlarını belirtmeniz gerekir. Koşullar ve özel durumlar için şu özellikleri kullanabilirsiniz:

- **Alıcı**
- **Alıcı etki alanı**
- **Alıcı,**

Bir koşulu veya özel durumu yalnızca bir kez kullanabilirsiniz, ancak koşul veya özel durum birden çok değer içerebilir. Aynı koşula veya özel duruma ait birden çok değer OR mantığını kullanır (örneğin, _\<recipient1\>_ veya _\<recipient2\>_). Farklı koşullar veya özel durumlar AND mantığını kullanır (örneğin, _\<recipient1\>_ ve _\<member of group 1\>_).

> [!IMPORTANT]
> Birden çok farklı koşul veya özel durum türü ek değildir; Onlar kapsayıcı. İlke _yalnızca_ belirtilen alıcı filtrelerinin _tümüyle_ eşleşen alıcılara uygulanır. Örneğin, ilkede aşağıdaki değerlerle bir alıcı filtresi koşulu yapılandırabilirsiniz:
>
> - Alıcı: romain@contoso.com
> - Alıcı şu üyelerin üyesidir: Yöneticiler
>
> İlke, _romain@contoso.com yalnızca_ Yöneticiler grubunun da üyesiyse uygulanır. Grubun üyesi değilse ilke ona uygulanmaz.
>
> Benzer şekilde, ilkenin özel durumu olarak aynı alıcı filtresini kullanırsanız, ilke _romain@contoso.com yalnızca_ Yöneticiler grubunun da üyesiyse uygulanmaz. Grubun üyesi değilse, ilke hala onun için geçerlidir.

## <a name="safe-links-settings-for-email-messages"></a>E-posta iletileri için Güvenli Bağlantılar ayarları

Güvenli Bağlantılar, bilinen kötü amaçlı köprüler için gelen e-postayı tarar. Taranan URL'ler, Microsoft standart URL ön eki kullanılarak yeniden yazılır veya _sarmalanmıştır_ : `https://nam01.safelinks.protection.outlook.com`. Bağlantı yeniden yazıldıktan sonra, kötü amaçlı olabilecek içerik için analiz edilir.

Güvenli Bağlantılar bir URL'yi yeniden yazdıktan sonra, ileti _el ile_ iletilmiş veya yanıtlanmış olsa bile URL yeniden yazılır (hem iç hem de dış alıcılara). İletilen veya yanıtlanan iletiye eklenen ek bağlantılar yeniden yazılmaz.

Gelen Kutusu kuralları veya SMTP iletme tarafından _otomatik_ iletme söz konusu olduğunda, aşağıdaki deyimlerden biri doğru _olmadığı sürece_ URL son alıcıya yönelik iletide yeniden yazılmaz:

- Alıcı, Güvenli Bağlantılar tarafından da korunur.
- URL önceki bir iletişimde zaten yeniden yazılmıştı.

Güvenli Bağlantılar koruması açık olduğu sürece, URL'lerin yeniden yazılıp yazılmadığına bakılmaksızın, ileti teslimi öncesinde URL'ler taranır. Outlook'un desteklenen sürümlerinde (Masaüstü için Outlook sürüm 16.0.12513 veya üzeri), eşleşmeyen URL'ler tıklandığında güvenli bağlantılar için istemci tarafı API çağrısı tarafından denetlenir.

E-posta iletilerine uygulanan Güvenli Bağlantılar ilkelerindeki ayarlar aşağıdaki listede açıklanmıştır:

- **Açık: Güvenli Bağlantılar, kullanıcılar e-postadaki bağlantılara tıkladığında bilinen, kötü amaçlı bağlantıların listesini denetler: E-posta iletilerinde** Güvenli Bağlantılar taramasını açma veya kapatma. Önerilen değer seçilidir (açık) ve aşağıdaki eylemlerle sonuçlanır:
  - Windows'da Outlook'ta (C2R) Güvenli Bağlantılar taraması açıktır.
  - URL'ler yeniden yazılır ve kullanıcılar iletilerdeki URL'lere tıkladığında Güvenli Bağlantılar koruması üzerinden yönlendirilir.
  - Tıklandığında, URL'ler bilinen kötü amaçlı URL'ler listesinde ve ["Aşağıdaki URL'leri engelle" listesinde](#block-the-following-urls-list-for-safe-links) denetlenir.
  - Geçerli bir saygınlığı olmayan URL'ler arka planda zaman uyumsuz olarak patlatılır.

  Aşağıdaki ayarlar yalnızca e-posta iletilerinde Güvenli Bağlantılar taraması açıksa kullanılabilir:

  - **Kuruluş içinde gönderilen e-posta iletilerine Güvenli Bağlantılar uygulama: Aynı Exchange Online kuruluştaki** iç gönderenler ve iç alıcılar arasında gönderilen iletilerde Güvenli Bağlantılar taramasını açın veya kapatın. Önerilen değer seçilidir (açık).

  - **Şüpheli bağlantılar ve dosyalara işaret eden bağlantılar için gerçek zamanlı URL taraması uygulayın: İndirilebilir içeriğe işaret eden** e-posta iletilerindeki bağlantılar da dahil olmak üzere bağlantıların gerçek zamanlı taramasını açar. Önerilen değer seçilidir (açık).

    - **İletiyi teslim etmeden önce URL taramasının tamamlanmasını bekleyin**:
      - Seçili (açık): URL içeren iletiler tarama tamamlanana kadar tutulur. İletiler yalnızca URL'lerin güvenli olduğu onaylandıktan sonra teslim edilir. Bu, önerilen değerdir.
      - Seçili değil (kapalı): URL taraması tamamlanamadıysa iletiyi yine de teslim edin.

  - **URL'leri yeniden yazmayın, yalnızca SafeLinks API'si aracılığıyla denetimler yapın**: Bu ayar seçiliyse (açık), URL sarmalama gerçekleşmez. Outlook'un desteklenen sürümlerinde (Masaüstü için Outlook sürüm 16.0.12513 veya üzeri), Güvenli Bağlantılar yalnızca URL tıklaması sırasında API'ler aracılığıyla çağrılır.

  Güvenli Bağlantılar ilkeleri için Standart ve Katı ilke ayarları için önerilen değerler hakkında daha fazla bilgi için bkz. [Güvenli Bağlantılar ilke ayarları](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).

### <a name="how-safe-links-works-in-email-messages"></a>Güvenli Bağlantılar e-posta iletilerinde nasıl çalışır?

Yüksek düzeyde, Güvenli Bağlantılar koruması e-posta iletilerindeki URL'lerde şu şekilde çalışır:

1. Tüm e-postalar, ileti alıcının posta kutusuna teslim etmeden önce İnternet protokolü (IP) ve zarf filtreleri, imza tabanlı kötü amaçlı yazılım koruması, istenmeyen posta önleme ve kötü amaçlı yazılımdan koruma filtrelerinin bulunduğu EOP'den geçer.

2. Kullanıcı iletiyi posta kutusunda açar ve iletideki bir URL'ye tıklar.

3. Güvenli Bağlantılar, web sitesini açmadan önce URL'yi hemen denetler:

   - URL **Aşağıdaki URL'leri engelle** listesinde yer alıyorsa [, engellenen bir URL uyarısı](#blocked-url-warning) açılır.

   - URL, kötü amaçlı olduğu belirlenen bir web sitesine işaret ederse, [kötü amaçlı bir web sitesi uyarı](#malicious-website-warning) sayfası (veya farklı bir uyarı sayfası) açılır.

   - URL indirilebilir bir dosyayı işaret ederse ve kullanıcıya uygulanan ilkede **Şüpheli bağlantılar ve dosyalara işaret eden bağlantılar için gerçek zamanlı URL taraması uygula** ayarı açıksa, indirilebilir dosya denetlenir.

   - URL'nin güvenli olduğu belirlenirse web sitesi açılır.

## <a name="safe-links-settings-for-microsoft-teams"></a>Microsoft Teams için Güvenli Bağlantılar ayarları

Güvenli Bağlantılar ilkelerinde Microsoft Teams için Güvenli Bağlantılar korumasını açar veya kapatırsınız. Özellikle Açık **: Güvenli Bağlantılar, kullanıcılar Microsoft Teams'de bağlantılara tıkladığında bilinen, kötü amaçlı bağlantıların listesini denetler** ayarını kullanırsınız. Önerilen değer açık (seçili).

> [!NOTE]
> Teams için Güvenli Bağlantılar korumasını açtığınızda veya kapattığınızda, değişikliğin geçerli olması 24 saat kadar sürebilir.
>
> Şu anda Microsoft Teams için Güvenli Bağlantılar koruması Microsoft 365 GCC High veya Microsoft 365 DoD'da kullanılamaz.

Microsoft Teams için Güvenli Bağlantılar korumasını açtıktan sonra, korumalı kullanıcı bağlantıya tıkladığında (tıklama süresi koruması) Teams'deki URL'ler bilinen kötü amaçlı bağlantıların listesiyle karşılaştırılır. URL'ler yeniden yazılmaz. Bir bağlantının kötü amaçlı olduğu tespit edilirse, kullanıcılar aşağıdaki deneyimlere sahip olur:

- Bir Teams konuşmasında, grup sohbetinde veya kanallardan bağlantıya tıklandıysa, aşağıdaki ekran görüntüsünde gösterildiği gibi uyarı sayfası varsayılan web tarayıcısında görünür.
- Sabitlenmiş bir sekmeden bağlantıya tıklandıysa, uyarı sayfası bu sekmedeki Teams arabiriminde görünür. Bağlantıyı bir web tarayıcısında açma seçeneği güvenlik nedeniyle devre dışı bırakılır.
- **İlkedeki kullanıcıların özgün URL'ye tıklamasına izin ver** ayarının nasıl yapılandırıldığına bağlı olarak, kullanıcının özgün URL'ye tıklamasına izin verilir veya izin verilmez (Ekran görüntüsünde **yine de devam edin (önerilmez**). **Kullanıcıların özgün URL'ye tıklayamamaları için Kullanıcıların özgün URL'ye tıklamasına izin ver** ayarını seçmemenizi öneririz.

Bağlantıyı gönderen kullanıcı, Teams korumasının açık olduğu Güvenli Bağlantılar ilkesi tarafından korunmuyorsa, kullanıcı kendi bilgisayarında veya cihazında özgün URL'ye tıklamakta serbesttir.

:::image type="content" source="../../media/tp-safe-links-for-teams-malicious.png" alt-text="Kötü amaçlı bir bağlantı bildiren Teams için Güvenli Bağlantılar sayfası" lightbox="../../media/tp-safe-links-for-teams-malicious.png":::

Uyarı sayfasında **Geri Dön** düğmesine tıklanması, kullanıcıyı özgün bağlamı veya URL konumuna döndürür. Ancak, özgün bağlantıya yeniden tıklanması Güvenli Bağlantılar'ın URL'yi yeniden taramasına neden olur, böylece uyarı sayfası yeniden görünür.

### <a name="how-safe-links-works-in-teams"></a>Güvenli Bağlantılar Teams'de nasıl çalışır?

Yüksek düzeyde, Microsoft Teams'deki URL'ler için Güvenli Bağlantılar koruması şu şekilde çalışır:

1. Bir kullanıcı Teams uygulamasını başlatır.

2. Microsoft 365, kullanıcının kuruluşunun Office 365 için Microsoft Defender içerdiğini ve kullanıcının Microsoft Teams için korumanın açık olduğu etkin bir Güvenli Bağlantılar ilkesine dahil olduğunu doğrular.

3. URL'ler sohbetlerde, grup sohbetlerinde, kanallarda ve sekmelerde kullanıcı için tıklandığında doğrulanır.

## <a name="safe-links-settings-for-office-apps"></a>Office uygulamaları için Güvenli Bağlantılar ayarları

Office uygulamaları için Güvenli Bağlantılar koruması, e-posta iletilerindeki bağlantıları değil, Office belgelerindeki bağlantıları denetler. Ancak, belge açıldıktan sonra e-posta iletilerinde ekli Office belgelerindeki bağlantıları denetleyebiliyor.

Güvenli Bağlantılar ilkelerinde Office uygulamaları için Güvenli Bağlantılar korumasını açar veya kapatırsınız. Özellikle Açık **: Güvenli Bağlantılar, kullanıcılar Microsoft Office uygulamalarında bağlantılara tıkladığında bilinen, kötü amaçlı bağlantıların listesini denetler** ayarını kullanırsınız. Önerilen değer açık (seçili).

Office uygulamaları için Güvenli Bağlantılar koruması aşağıdaki istemci gereksinimlerine sahiptir:

- Microsoft 365 Uygulamaları veya Microsoft 365 İş Ekstra.
  - Windows, Mac veya bir web tarayıcısında Word, Excel ve PowerPoint'in geçerli sürümleri.
  - iOS veya Android cihazlarda Office uygulamaları.
  - Windows üzerinde Visio.
  - Web tarayıcısında OneNote.
  - Kaydedilen EML veya MSG dosyalarını açarken Windows için Outlook.

- Office uygulamaları modern kimlik doğrulaması kullanacak şekilde yapılandırılmıştır. Daha fazla bilgi için bkz. [Office 2013, Office 2016 ve Office 2019 istemci uygulamaları için modern kimlik doğrulaması nasıl çalışır](../../enterprise/modern-auth-for-office-2013-and-2016.md)?

- Kullanıcılar iş veya okul hesaplarını kullanarak oturum açmışlardır. Daha fazla bilgi için bkz. [Office'te oturum açma](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).

Standart ve Katı ilke ayarları için önerilen değerler hakkında daha fazla bilgi için bkz. [Güvenli Bağlantılar için genel ayarlar](recommended-settings-for-eop-and-office365.md#global-settings-for-safe-links).

### <a name="how-safe-links-works-in-office-apps"></a>Güvenli Bağlantılar Office uygulamalarında nasıl çalışır?

Yüksek düzeyde, Office uygulamalarında URL'ler için Güvenli Bağlantılar koruması şu şekilde çalışır. Desteklenen Office uygulamaları önceki bölümde açıklanmıştır.

1. Kullanıcı, Microsoft 365 Uygulamaları veya Microsoft 365 İş Ekstra içeren bir kuruluşta iş veya okul hesabını kullanarak oturum açar.

2. Kullanıcı açılır ve desteklenen bir Office uygulamasındaki bir Office belgesinin bağlantısına tıklar.

3. Güvenli Bağlantılar, hedef web sitesini açmadan önce URL'yi hemen denetler:

   - URL, Güvenli Bağlantılar taramasını atlayan listeye dahil edilmişse ( **Aşağıdaki URL'leri engelle** listesi) [engellenen bir URL uyarı](#blocked-url-warning) sayfası açılır.

   - URL, kötü amaçlı olduğu belirlenen bir web sitesine işaret ederse, [kötü amaçlı bir web sitesi uyarı](#malicious-website-warning) sayfası (veya farklı bir uyarı sayfası) açılır.

   - URL indirilebilir bir dosyaya işaret ederse ve kullanıcıya uygulanan Güvenli Bağlantılar ilkesi indirilebilir içeriğe yönelik bağlantıları taramak için yapılandırılmışsa (**Şüpheli bağlantılar ve dosyalara işaret eden bağlantılar için gerçek zamanlı URL taraması uygula**), indirilebilir dosya denetlenir.

   - URL güvenli olarak kabul edilirse, kullanıcı web sitesine yönlendirilir.

   - Güvenli Bağlantılar taraması tamamlanamıyorsa, Güvenli Bağlantılar koruması tetiklenmez. Office masaüstü istemcilerinde, hedef web sitesine geçmeden önce kullanıcı uyarılır.

> [!NOTE]
> Office uygulamaları için Güvenli Bağlantılar'ın kullanıcının kullanımına sunulduğunun doğrulanması her oturumun başında birkaç saniye sürebilir.

## <a name="click-protection-settings-in-safe-links-policies"></a>Güvenli Bağlantılar ilkelerinde koruma ayarlarına tıklayın

Bu ayarlar e-posta, Teams ve Office uygulamalarında Güvenli Bağlantılar için geçerlidir:

- **Kullanıcı tıklamalarını izleme**: Tıklanan URL'ler için Güvenli Bağlantılar tıklama verilerinin depolanmasını açın veya kapatın. Bu ayarı seçili (açık) bırakmanızı öneririz.

  Office uygulamaları için Güvenli Bağlantılar'da bu ayar Word, Excel, PowerPoint ve Visio masaüstü sürümleri için geçerlidir.

  İç gönderenler ve iç alıcılar arasında gönderilen e-posta iletilerindeki bağlantılar için URL tıklama izlemesi şu anda desteklenmemektedir.

  Bu ayarı seçerseniz aşağıdaki ayarlar kullanılabilir:

  - **Kullanıcıların özgün URL'ye tıklamasına izin ver**: Kullanıcıların [uyarı sayfasından](#warning-pages-from-safe-links) özgün URL'ye tıklayıp tıklayamayacağını denetler. Önerilen değer seçili değil (kapalı).

    Office uygulamaları için Güvenli Bağlantılar'da bu ayar Word, Excel, PowerPoint ve Visio masaüstü sürümlerindeki özgün URL için geçerlidir.

  - **Bildirim ve uyarı sayfalarında kuruluş markasını görüntüleme**: Bu seçenek, kuruluşunuzun markasını uyarı sayfalarında gösterir. Varsayılan Microsoft uyarı sayfaları genellikle saldırganlar tarafından kullanıldığından, markalama kullanıcıların geçerli uyarıları tanımlamalarına yardımcı olur. Özelleştirilmiş markalama hakkında daha fazla bilgi için bkz. [Kuruluşunuz için Microsoft 365 temasını özelleştirme](../../admin/setup/customize-your-organization-theme.md).

## <a name="priority-of-safe-links-policies"></a>Güvenli Bağlantılar ilkelerinin önceliği

Birden çok ilke oluşturduktan sonra, uygulanacağı sırayı belirtebilirsiniz. hiçbir iki ilke aynı önceliğe sahip olamaz ve ilke işleme ilk ilke uygulandıktan sonra durur. **Yerleşik koruma** ilkesi her zaman en son uygulanır. İlişkili Güvenli Bağlantılar ilkeleri **Standart** ve **Katı** önceden ayarlanmış güvenlik ilkeleri her zaman özel Güvenli Bağlantılar ilkeleri öncesinde uygulanır.

Öncelik sırası ve birden çok ilkenin nasıl değerlendirilip uygulandığı hakkında daha fazla bilgi için bkz. [Önceden ayarlanmış güvenlik ilkeleri ve diğer ilkeler için öncelik sırası ve](preset-security-policies.md#order-of-precedence-for-preset-security-policies-and-other-policies) [E-posta korumasının sırası ve önceliği](how-policies-and-protections-are-combined.md).

## <a name="block-the-following-urls-list-for-safe-links"></a>Güvenli Bağlantılar için "Aşağıdaki URL'leri engelle" listesi

> [!NOTE]
> Artık [Kiracı İzin Ver/Engelle Listesi'nde](allow-block-urls.md#use-the-microsoft-365-defender-portal-to-create-block-entries-for-urls-in-the-tenant-allowblock-list) blok URL'si girdilerini yönetebilirsiniz. "Aşağıdaki URL'leri engelle" listesi kullanım dışı bırakılıyor. Kiracı İzin Ver/Engelle Listesindeki URL girdilerini engellemek için "Aşağıdaki URL'leri engelle" listesinden mevcut girdileri geçirmeyi deneyeceğiz. Engellenen URL'yi içeren iletiler karantinaya alınır.

**Aşağıdaki URL'leri engelle** listesi, aşağıdaki konumlarda Güvenli Bağlantılar taraması tarafından her zaman engellenen bağlantıları tanımlar:

- İletileri Email.
- Windows ve Mac'teki Office uygulamalarındaki belgeler.
- iOS ve Android için Office'teki belgeler.

Etkin bir Güvenli Bağlantılar ilkesindeki bir kullanıcı desteklenen bir uygulamada engellenen bağlantıya tıkladığında [Engellenen URL uyarı](#blocked-url-warning) sayfasına yönlendirilir.

Url listesini Güvenli Bağlantılar için genel ayarlarda yapılandırabilirsiniz. Yönergeler için bkz. ["Aşağıdaki URL'leri engelle" listesini yapılandırma](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-microsoft-365-defender-portal).

**Notlar**:

- Her yerde engellenen URL'lerin gerçekten evrensel bir listesi için bkz. [Kiracı İzin Verme/Engelleme Listesini Yönetme](manage-tenant-allow-block-list.md).
- **Aşağıdaki URL'leri engelle listesinin** sınırları:
  - En fazla giriş sayısı 500'dür.
  - Bir girişin uzunluk üst sınırı 128 karakterdir.
  - Tüm girdiler 10.000 karakteri aşamaz.
- URL'nin sonuna eğik çizgi (`/`) eklemeyin. Örneğin, yerine kullanın`https://www.contoso.com``https://www.contoso.com/`.
- Yalnızca etki alanı URL'si (örneğin `contoso.com` veya `tailspintoys.com`) etki alanını içeren tüm URL'leri engeller.
- Tam etki alanını engellemeden bir alt etki alanını engelleyebilirsiniz. Örneğin, `toys.contoso.com*` alt etki alanını içeren tüm URL'leri engeller, ancak tam etki alanını `contoso.com`içeren URL'leri engellemez.
- URL girişi başına en fazla üç joker karakter (`*`) ekleyebilirsiniz.

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a>"Aşağıdaki URL'leri engelle" listesi için giriş söz dizimi

Girebileceğiniz değerlerin ve sonuçlarının örnekleri aşağıdaki tabloda açıklanmıştır:

|Değer|Sonuç|
|---|---|
|`contoso.com` <p> veya <p> `*contoso.com*`|Etki alanı, alt etki alanları ve yolları engeller. Örneğin, `https://www.contoso.com`, `https://sub.contoso.com`ve `https://contoso.com/abc` engellenir.|
|`https://contoso.com/a`|gibi `https://contoso.com/a/b`ek alt yolları engeller `https://contoso.com/a` ancak engellemez.|
|`https://contoso.com/a*`|Bloklar `https://contoso.com/a` ve gibi `https://contoso.com/a/b`ek alt yollar.|
|`https://toys.contoso.com*`|Bir alt etki alanını (`toys`bu örnekte) engeller ancak diğer etki alanı URL'lerine (veya `https://home.contoso.com`gibi`https://contoso.com`) tıklamalara izin verir.|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>Güvenli Bağlantılar ilkelerindeki "Aşağıdaki URL'leri yeniden yazmayın" listeleri

> [!NOTE]
> "Aşağıdaki URL'leri yeniden yazmayın" listesindeki girdiler, posta akışı sırasında Güvenli Bağlantılar tarafından taranmıyor veya sarmalanmıyor. Posta akışı sırasında _ve_ tıklandığında URL'lerin Güvenli Bağlantılar tarafından taranmaması veya sarmalanmaması için [Kiracı İzin Ver/Engelle Listesi'ndeki İzin Ver URL girişlerini](allow-block-urls.md#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-urls-in-the-submissions-portal) kullanın.

Her Güvenli Bağlantılar ilkesi, Güvenli Bağlantılar taraması tarafından **yeniden yazılmayan URL'leri belirtmek için kullanabileceğiniz aşağıdaki URL'leri yeniden yazma** listesini içerir. Başka bir deyişle, liste ilkeye dahil edilen kullanıcıların, aksi takdirde Güvenli Bağlantılar tarafından engellenecek belirtilen URL'lere erişmesine izin verir. Farklı Güvenli Bağlantılar ilkelerinde farklı listeler yapılandırabilirsiniz. İlke işleme, kullanıcıya ilk (büyük olasılıkla en yüksek öncelikli) ilke uygulandıktan sonra durur. Bu nedenle, birden çok etkin Güvenli Bağlantı ilkesine dahil edilen bir kullanıcıya **yalnızca bir Tane Aşağıdaki URL'leri yeniden yazma** listesi uygulanır.

Yeni veya mevcut Güvenli Bağlantılar ilkelerinde listeye girdi eklemek için bkz. [Güvenli Bağlantılar ilkeleri oluşturma](set-up-safe-links-policies.md#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) veya [Güvenli Bağlantıları Değiştirme ilkeleri](set-up-safe-links-policies.md#use-the-microsoft-365-defender-portal-to-modify-safe-links-policies).

**Notlar**:

- Aşağıdaki istemciler, Güvenli Bağlantılar ilkelerinde **aşağıdaki URL'leri yeniden yazma** listelerini tanımaz. İlkelere dahil edilen kullanıcıların URL'lere erişmesi, bu istemcilerdeki Güvenli Bağlantılar taramasının sonuçlarına bağlı olarak engellenebilir:
  - Microsoft Teams
  - Office web uygulamaları

  Her yerde izin verilen URL'lerin gerçekten evrensel listesi için bkz. [Kiracı İzin Verme/Engelleme Listesini Yönetme](manage-tenant-allow-block-list.md). Ancak, oraya eklenen URL'lerin Güvenli Bağlantılar ilkesinde yapılması gerektiğinden Güvenli Bağlantılar yeniden yazmanın dışında tutulmayacaklarını unutmayın.

- Kullanıcı deneyimini geliştirmek için sık kullanılan iç URL'leri listeye eklemeyi göz önünde bulundurun. Örneğin, Skype Kurumsal veya SharePoint gibi şirket içi hizmetleriniz varsa, bu URL'leri taramanın dışında tutmak için ekleyebilirsiniz.
- Güvenli Bağlantılar ilkelerinizde **aşağıdaki URL girişlerini yeniden yazmadıysanız** listeleri gözden geçirmeyi ve gerektiğinde joker karakterleri eklemeyi unutmayın. Örneğin, listenizde gibi `https://contoso.com/a` bir girdi vardır ve daha sonra gibi `https://contoso.com/a/b`alt yolları dahil etmeye karar verirsiniz. Yeni bir girdi eklemek yerine, var olan girdiye joker karakter ekleyerek olur `https://contoso.com/a/*`.
- URL girişi başına en fazla üç joker karakter (`*`) ekleyebilirsiniz. Joker karakterler açıkça ön ekler veya alt etki alanları içerir. Örneğin, kişilerin belirtilen etki alanındaki alt etki alanları ve yolları ziyaret etmesine izin verdiğinden, girdi `contoso.com` ile aynı `*.contoso.com/*``*.contoso.com/*` değildir.
- URL, HTTP'den HTTPS'ye otomatik yeniden yönlendirme kullanıyorsa (örneğin, için `https://www.contoso.com`302 yeniden yönlendirmesi `http://www.contoso.com` ) ve listeye aynı URL için hem HTTP hem de HTTPS girdileri girmeye çalışırsanız, ikinci URL girişinin ilk URL girdisinin yerini aldığına dikkat edebilirsiniz. URL'nin HTTP ve HTTPS sürümleri tamamen ayrıysa bu davranış oluşmaz.
- Hem HTTP hem de HTTPS sürümlerini dışlamak için http:// veya https:// (yani contoso.com) belirtmeyin.
- `*.contoso.com` contoso.com **kapsamaz** , bu nedenle hem belirtilen etki alanını hem de alt etki alanlarını kapsamak için ikisini de dışlamanız gerekir.
- `contoso.com/*`**yalnızca** contoso.com kapsar, bu nedenle hem hem `contoso.com/*`de `contoso.com` hariç tutmanıza gerek yoktur; yalnızca `contoso.com/*` yeterli olacaktır.
- Bir etki alanının tüm yinelemelerini dışlamak için iki dışlama girdisi gerekir; `contoso.com/*` ve `*.contoso.com/*`. Bunlar hem HTTP hem de HTTPS' yi, ana etki alanı contoso.com ve alt etki alanlarının yanı sıra herhangi bir veya hiç bitmeyen bölümü dışlamak için birleştirilir (örneğin, hem contoso.com hem de contoso.com/vdir1 ele alınır).

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a>"Aşağıdaki URL'leri yeniden yazmayın" listesi için giriş söz dizimi

Girebileceğiniz değerlerin ve sonuçlarının örnekleri aşağıdaki tabloda açıklanmıştır:

|Değer|Sonuç|
|---|---|
|`contoso.com`|Alt etki alanları veya yollara erişime `https://contoso.com` izin verir ancak izin vermez.|
|`*.contoso.com/*`|Bir etki alanına, alt etki alanına ve yollara (örneğin, `https://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`veya `https://www.contoso.com/a`) erişime izin verir. <p> Bu girdi, veya gibi `https://www.falsecontoso.com` sahte olabilecek sitelere izin vermediğinden doğası gereği değerinden `*contoso.com*`daha iyidir.`https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|gibi alt yollara erişim izni `https://contoso.com/a`vermez `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|ve gibi alt yollara erişime `https://contoso.com/a` izin verir `https://contoso.com/a/b`|

## <a name="warning-pages-from-safe-links"></a>Güvenli Bağlantılar'dan uyarı sayfaları

Bu bölüm, bir URL'ye tıkladığınızda Güvenli Bağlantılar koruması tarafından tetiklenen çeşitli uyarı sayfalarının örneklerini içerir.

Çeşitli uyarı sayfalarının güncelleştirildiğini unutmayın. Güncelleştirilmiş sayfaları henüz görmüyorsanız, yakında görürsünüz. Güncelleştirilen sayfalar yeni bir renk düzeni, daha ayrıntılı bilgiler ve verilen uyarı ve önerilere rağmen bir siteye devam etme özelliği içerir.

### <a name="scan-in-progress-notification"></a>Tarama devam ediyor bildirimi

Tıklanan URL Güvenli Bağlantılar tarafından taranıyor. Bağlantıyı yeniden denemeden önce birkaç dakika beklemeniz gerekebilir.

:::image type="content" source="../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png" alt-text="Bağlantının tarandığını belirten bildirim" lightbox="../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png":::

Özgün bildirim sayfası şöyle görünüyordu:

:::image type="content" source="../../media/04368763-763f-43d6-94a4-a48291d36893.png" alt-text="Bağlantı taranıyor bildirimi" lightbox="../../media/04368763-763f-43d6-94a4-a48291d36893.png":::

### <a name="suspicious-message-warning"></a>Şüpheli ileti uyarısı

Tıklanan URL, diğer şüpheli iletilere benzer bir e-posta iletisinde yer alır. Siteye geçmeden önce e-posta iletisini iki kez denetlemenizi öneririz.

:::image type="content" source="../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png" alt-text="Şüpheli ileti uyarısından bir bağlantıya tıklandı" lightbox="../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png":::

### <a name="phishing-attempt-warning"></a>Kimlik avı girişimi uyarısı

Tıklanan URL, kimlik avı saldırısı olarak tanımlanan bir e-posta iletisinde yer alır. Sonuç olarak, e-posta iletisindeki tüm URL'ler engellenir. Siteye devam etmemenizi öneririz.

:::image type="content" source="../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png" alt-text="Kimlik avı iletisinden bir bağlantıya tıklandığını belirten uyarı" lightbox="../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png":::

### <a name="malicious-website-warning"></a>Kötü amaçlı web sitesi uyarısı

Tıklanan URL, kötü amaçlı olarak tanımlanan bir siteyi gösterir. Siteye devam etmemenizi öneririz.

:::image type="content" source="../../media/058883c8-23f0-4672-9c1c-66b084796177.png" alt-text="Web sitesinin kötü amaçlı olarak sınıflandırıldığını belirten uyarı" lightbox="../../media/058883c8-23f0-4672-9c1c-66b084796177.png":::

Özgün uyarı sayfası şöyle görünüyordu:

:::image type="content" source="../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png" alt-text="Web sitesinin kötü amaçlı olarak sınıflandırıldığını belirten özgün uyarı" lightbox="../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png":::

### <a name="blocked-url-warning"></a>Engellenen URL uyarısı

Tıklanan URL, kuruluşunuzdaki bir yönetici tarafından el ile engellendi (Güvenli Bağlantılar için genel ayarlarda **aşağıdaki URL'leri engelle** listesi). Bağlantı, el ile engellendiği için Güvenli Bağlantılar tarafından taranmadı.

Bir yöneticinin belirli URL'leri el ile engellemesi için çeşitli nedenler vardır. Sitenin engellenmemesi gerektiğini düşünüyorsanız yöneticinize başvurun.

:::image type="content" source="../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png" alt-text="Web sitesinin yöneticiniz tarafından engellendiğini belirten uyarı" lightbox="../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png":::

Özgün uyarı sayfası şöyle görünüyordu:

:::image type="content" source="../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png" alt-text="Kuruluşunuzun URL ilkesine göre web sitesinin engellendiğini belirten özgün uyarı" lightbox="../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png":::

### <a name="error-warning"></a>Hata uyarısı

Bir tür hata oluştu ve URL açılamıyor.

:::image type="content" source="../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png" alt-text="Erişmeye çalıştığınız sayfayı belirten uyarı yüklenemiyor" lightbox="../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png":::

Özgün uyarı sayfası şöyle görünüyordu:

:::image type="content" source="../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png" alt-text="Web sayfasının yüklenemediği uyarısı" lightbox="../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png":::
