---
title: Sender Policy Framework (SPF) kimlik sahtekarlıklarını nasıl önler?
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 3aff33c5-1416-4867-a23b-e0c0c5b4d2be
ms.collection:
- m365-security
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365'in, hedef e-posta sistemlerinin özel etki alanınızdan gönderilen iletilere güvenmesini sağlamak için DNS'deki Sender Policy Framework (SPF) TXT kaydını nasıl kullandığını öğrenin.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: e72f3c12078f355617e84b19265f585ef2376377
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68625027"
---
# <a name="how-microsoft-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a>Microsoft 365, kimlik sahtekarlıklarını önlemek için Sender Policy Framework'i (SPF) nasıl kullanır?

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

 **Özet:** Bu makalede, hedef e-posta sistemlerinin özel etki alanınızdan gönderilen iletilere güvenmesini sağlamak için Microsoft 365'in DNS'deki Sender Policy Framework (SPF) TXT kaydını nasıl kullandığı açıklanmaktadır. Bu, Microsoft 365'ten gönderilen giden postalar için geçerlidir. Microsoft 365'ten Microsoft 365 içindeki bir alıcıya gönderilen iletiler her zaman SPF'yi geçirir.

SPF TXT kaydı, e-posta iletilerinin gönderildiği etki alanı adını doğrulayarak kimlik sahtekarlığı ve kimlik avının önlenmesine yardımcı olan bir DNS kaydıdır. SPF, gönderenin IP adresini gönderen etki alanının iddia edilen sahibine karşı doğrulayarak e-posta iletilerinin kaynağını doğrular.

> [!NOTE]
> SPF kayıt türleri, Internet Engineering Task Force (IETF) tarafından 2014 yılında kullanım dışı bırakılmıştır. Bunun yerine, SPF bilgilerinizi yayımlamak için DNS'de TXT kayıtlarını kullandığınızdan emin olun. Bu makalenin geri kalanında netlik için SPF TXT kaydı terimi kullanılır.

Etki alanı yöneticileri, DNS'deki TXT kayıtlarında SPF bilgilerini yayımlar. SPF bilgileri, yetkili giden e-posta sunucularını tanımlar. Hedef e-posta sistemleri, iletilerin yetkili giden e-posta sunucularından geldiğini doğrular. SPF'yi zaten biliyorsanız veya basit bir dağıtımınız varsa ve yalnızca Microsoft 365 için DNS'deki SPF TXT kaydınıza nelerin dahil edilmesini bilmeniz gerekiyorsa, kimlik [sahtekarlıklarını önlemeye yardımcı olmak için Microsoft 365'te SPF'yi ayarlama](set-up-spf-in-office-365-to-help-prevent-spoofing.md) bölümüne gidebilirsiniz. Tamamen Microsoft 365'te barındırılan bir dağıtımınız yoksa veya SPF'nin nasıl çalıştığı veya Microsoft 365 için SPF sorunlarını giderme hakkında daha fazla bilgi edinmek istiyorsanız okumaya devam edin.

> [!NOTE]
> Daha önce, SharePoint Online'ı da kullandıysanız özel etki alanınıza farklı bir SPF TXT kaydı eklemeniz gerekiyordu. Bu artık gerekli değildir. Bu değişiklik, SharePoint Online bildirim iletilerinin Gereksiz Email klasörüne düşmesi riskini azaltmalıdır. Hemen herhangi bir değişiklik yapmanız gerekmez, ancak "çok fazla arama" hatası alırsanız, [sahtekarlık önlemeye yardımcı olmak için Microsoft 365'te SPF'yi ayarlama](set-up-spf-in-office-365-to-help-prevent-spoofing.md) bölümünde açıklandığı gibi SPF TXT kaydınızı değiştirin.

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-microsoft-365"></a>MICROSOFT 365'te kimlik sahtekarlığı ve kimlik avının önlenmesi için SPF nasıl çalışır?
<a name="HowSPFWorks"> </a>

SPF, gönderenin bir etki alanı adına göndermesine izin verilip verilmeyeceğini belirler. Gönderenin bunu yapma izni yoksa, yani e-posta alıcı sunucuda SPF denetiminde başarısız olursa, iletiyle ne yapacağını o sunucuda yapılandırılan istenmeyen posta ilkesi belirler.

Her SPF TXT kaydı üç bölümden oluşur: bunun bir SPF TXT kaydı olduğu bildirimi, etki alanınızdan posta göndermesine izin verilen IP adresleri ve etki alanınızın adına gönderilebilen dış etki alanları ve bir zorlama kuralı. Üçünü de geçerli bir SPF TXT kaydında kullanmanız gerekir. Bu makalede SPF TXT kaydınızı nasıl oluşturabileceğiniz açıklanır ve Microsoft 365'teki hizmetlerle çalışmaya yönelik en iyi yöntemler sağlanır. Kaydınızı DNS'de yayımlamak için etki alanı kayıt şirketinizle çalışma yönergelerinin bağlantıları da sağlanır.

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a>SPF temel bilgileri: Özel etki alanınızdan göndermesine izin verilen IP adresleri
<a name="SPFBasicsIPaddresses"> </a>

SPF kuralının temel söz dizimine göz atın:

v=spf1 \<IP\> \<enforcement rule\>

Örneğin, contoso.com için aşağıdaki SPF kuralının mevcut olduğunu varsayalım:

v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\> \<enforcement rule\>

Bu örnekte SPF kuralı, alan e-posta sunucusuna yalnızca etki alanı contoso.com için bu IP adreslerinden gelen postaları kabul etmelerini emredmektedir:

- IP adresi #1

- IP adresi #2

- IP adresi #3

Bu SPF kuralı, alıcı e-posta sunucusuna bir ileti contoso.com geliyorsa ancak bu üç IP adreslerinden birinden gelmiyorsa, alıcı sunucunun iletiye zorlama kuralını uygulaması gerektiğini bildirir. Zorlama kuralı genellikle şu seçeneklerden biridir:

- **Zor başarısız.** İleti zarfında iletiyi 'sabit başarısız' olarak işaretleyin ve ardından bu tür bir ileti için alıcı sunucunun yapılandırılmış istenmeyen posta ilkesini izleyin.

- **Yumuşak başarısız.** İletiyi ileti zarfında 'geçici hata' ile işaretleyin. Genellikle, e-posta sunucuları bu iletileri yine de teslim edecek şekilde yapılandırılır. Çoğu son kullanıcı bu işareti görmez.

- **Nötr.** Hiçbir şey yapmayın, yani ileti zarfını işaretlemeyin. Bu, test amacıyla ayrılmıştır ve nadiren kullanılır.

Aşağıdaki örneklerde SPF'nin farklı durumlarda nasıl çalıştığı gösterilir. Bu örneklerde contoso.com gönderen ve woodgrovebank.com alıcıdır.

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a>Örnek 1: Doğrudan gönderenden alıcıya gönderilen iletinin kimlik doğrulaması Email
<a name="spfExample1"> </a>

SPF, gönderenden alıcıya giden yol doğrudan olduğunda en iyi şekilde çalışır, örneğin:

![SPF'nin doğrudan sunucudan sunucuya gönderildiğinde e-postanın kimliğini nasıl doğruladığı gösteren diyagram.](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

woodgrovebank.com iletiyi aldığında, IP adresi #1 contoso.com için SPF TXT kaydındaysa, ileti SPF denetimini geçirir ve kimliği doğrulanır.

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a>Örnek 2: Sahte gönderen adresi SPF denetiminde başarısız oluyor
<a name="spfExample2"> </a>

Kimlik avının contoso.com sahtekarlık yapmak için bir yol bulduğunu varsayalım:

![SPF'nin sahte bir sunucudan gönderildiğinde e-postanın kimliğini nasıl doğruladığı gösteren diyagram.](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

12. IP adresi contoso.com'un SPF TXT kaydında olmadığından, ileti SPF denetiminde başarısız olur ve alıcı bunu istenmeyen posta olarak işaretlemeyi seçebilir.

### <a name="example-3-spf-and-forwarded-messages"></a>Örnek 3: SPF ve iletilen iletiler
<a name="spfExample3"> </a>

SPF'nin bir dezavantajı, bir e-posta iletildiğinde çalışmamasıdır. Örneğin, woodgrovebank.com'daki kullanıcının tüm e-postaları bir outlook.com hesabına göndermek için bir iletme kuralı ayarladığını varsayalım:

![İleti iletildiğinde SPF'nin e-posta kimliğini nasıl doğrulayamadığını gösteren diyagram.](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

İleti başlangıçta woodgrovebank.com spf denetimini geçirir, ancak IP #25 contoso.com'un SPF TXT kaydında olmadığından outlook.com spf denetimi başarısız olur. Outlook.com iletiyi istenmeyen posta olarak işaretleyebilir. Bu sorunu geçici olarak çözmek için SPF'yi DKIM ve DMARC gibi diğer e-posta kimlik doğrulama yöntemleriyle birlikte kullanın.

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a>SPF temel bilgileri: Etki alanınız adına posta gönderebilen üçüncü taraf etki alanlarını ekleme
<a name="SPFBasicsIncludes"> </a>

IP adreslerine ek olarak, SPF TXT kaydınızı etki alanlarını gönderen olarak içerecek şekilde de yapılandırabilirsiniz. Bunlar SPF TXT kaydına "include" deyimleri olarak eklenir. Örneğin, contoso.com contoso.net ve contoso.org posta sunucularının ip adreslerinin tümünü dahil etmek isteyebilirsiniz. Bu adreslerin de sahibidir. Bunu yapmak için contoso.com aşağıdakine benzer bir SPF TXT kaydı yayımlar:

```text
v=spf1 include:contoso.net include:contoso.org -all
```

Alıcı sunucu bu kaydı DNS'de gördüğünde, contoso.net ve ardından contoso.org için SPF TXT kaydında bir DNS araması da gerçekleştirir. contoso.net veya contoso.org kayıtları içinde başka bir ekleme deyimi bulursa, bunları da izler. Hizmet reddi saldırılarını önlemeye yardımcı olmak için, tek bir e-posta iletisi için en fazla DNS araması sayısı 10'dur. Her include deyimi ek bir DNS araması temsil eder. İleti 10 sınırını aşarsa, ileti SPF başarısız olur. İleti bu sınıra ulaştığında, alıcı sunucunun yapılandırılma şekline bağlı olarak, gönderen iletinin "çok fazla arama" oluşturduğunu veya "ileti için en fazla atlama sayısının aşıldığını" belirten bir ileti alabilir (aramalar döngüye alındığında ve DNS zaman aşımını aştığında gerçekleşebilir). Bunu önlemeye yönelik ipuçları için bkz [. Sorun Giderme: Microsoft 365'te SPF için en iyi yöntemler](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).

## <a name="requirements-for-your-spf-txt-record-and-microsoft-365"></a>SPF TXT kaydınız ve Microsoft 365 için gereksinimler
<a name="SPFReqsinO365"> </a>

Microsoft 365'i ayarlarken postayı ayarladıysanız, Microsoft mesajlaşma sunucularını etki alanınız için geçerli bir posta kaynağı olarak tanımlayan bir SPF TXT kaydı oluşturmuştunuzdur. Bu kayıt büyük olasılıkla şöyle görünür:

```text
v=spf1 include:spf.protection.outlook.com -all
```

Tam olarak barındırılan bir müşteriyseniz, yani giden posta gönderen şirket içi posta sunucularınız yoksa, Office 365 için yayımlamanız gereken tek SPF TXT kaydı budur.

Karma dağıtımınız varsa (başka bir deyişle, bazı posta kutularınız şirket içinde ve bazıları Microsoft 365'te barındırılıyorsa) veya Exchange Online Protection (EOP) tek başına müşterisiyseniz (kuruluşunuz şirket içi posta kutularınızı korumak için EOP kullanıyorsa), şirket içi uç posta sunucularınızın her biri için giden IP adresini DNS'deki SPF TXT kaydına eklemeniz gerekir.

## <a name="form-your-spf-txt-record-for-microsoft-365"></a>Microsoft 365 için SPF TXT kaydınızı oluşturma
<a name="FormYourSPF"> </a>

Özel etki alanınız için SPF TXT kaydını oluşturmak için bu makaledeki söz dizimi bilgilerini kullanın. Burada bahsedilmeyen başka söz dizimi seçenekleri olsa da, en sık kullanılan seçenekler bunlardır. Kaydınızı oluşturduktan sonra, etki alanı kayıt şirketinizde kaydı güncelleştirmeniz gerekir.

Microsoft 365 için eklemeniz gereken etki alanları hakkında bilgi için bkz. [SPF için gereken dış DNS kayıtları](../../enterprise/external-domain-name-system-records.md). Etki alanı kayıt şirketiniz için SPF (TXT) kayıtlarını güncelleştirmek için [adım adım yönergeleri](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) kullanın.

### <a name="spf-txt-record-syntax-for-microsoft-365"></a>Microsoft 365 için SPF TXT kaydı söz dizimi
<a name="SPFSyntaxO365"> </a>

Microsoft 365 için tipik bir SPF TXT kaydı aşağıdaki söz dizimine sahiptir:

```text
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

Örneğin:

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

burada:

- **v=spf1** gereklidir. Bu, TXT kaydını SPF TXT kaydı olarak tanımlar.

- **ip4** , IP sürüm 4 adreslerini kullandığınızı gösterir. **ip6** , IP sürüm 6 adreslerini kullandığınızı gösterir. IPv6 IP adreslerini kullanıyorsanız, bu makaledeki örneklerde **ip4** yerine **ip6** yazın. IP adresi aralıklarını **ip4:192.168.0.1/26** gibi CIDR gösterimini kullanarak da belirtebilirsiniz.

- _IP adresi_ , SPF TXT kaydına eklemek istediğiniz IP adresidir. Genellikle bu, kuruluşunuz için giden posta sunucusunun IP adresidir. Birden çok giden posta sunucusunu listeleyebilirsiniz. Daha fazla bilgi için bkz [. Örnek: Birden çok giden şirket içi posta sunucusu için SPF TXT kaydı ve Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).

- _etki alanı adı_ , geçerli bir gönderen olarak eklemek istediğiniz etki alanıdır. Microsoft 365 için eklemeniz gereken etki alanı adlarının listesi için bkz. [SPF için gereken dış DNS kayıtları](../../enterprise/external-domain-name-system-records.md).

- Zorlama kuralı genellikle aşağıdakilerden biridir:

  - -Tüm

    Sabit başarısız olduğunu gösterir. Etki alanınız için tüm yetkili IP adreslerini biliyorsanız, bunları SPF TXT kaydında listeleyin ve -all (sabit başarısız) niteleyicisini kullanın. Ayrıca, yalnızca SPF kullanıyorsanız, yani DMARC veya DKIM kullanmıyorsanız - all niteleyicisini kullanmanız gerekir. Her zaman bu niteleyiciyi kullanmanızı öneririz.

  - ~Tüm

    Geçici başarısızlığa işaret eder. IP adreslerinin tam listesine sahip olduğunuzdan emin değilseniz ~all (geçici başarısız) niteleyicisini kullanmanız gerekir. Ayrıca, p=quarantine veya p=reject ile DMARC kullanıyorsanız ~ all kullanabilirsiniz. Aksi takdirde -all kullanın.

  - ?Tüm

    Nötr değeri gösterir. Bu, SPF test edilirken kullanılır. Canlı dağıtımınızda bu niteleyiciyi kullanmanızı önermiyoruz.

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-microsoft-365"></a>Örnek: Tüm postalarınız Microsoft 365 tarafından gönderildiğinde kullanılacak SPF TXT kaydı
<a name="ExampleSPFNoSP"> </a>

Tüm postalarınız Microsoft 365 tarafından gönderiliyorsa, SPF TXT kaydınızda bunu kullanın:

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-microsoft-365"></a>Örnek: Bir şirket içi Exchange Server ve Microsoft 365 ile karma senaryo için SPF TXT kaydı
<a name="ExampleSPFHybridOneExchangeServer"> </a>

Karma bir ortamda, şirket içi Exchange Server IP adresi 192.168.0.1 ise, SPF zorlama kuralını zor başarısız olacak şekilde ayarlamak için SPF TXT kaydını aşağıdaki gibi oluşturun:

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-microsoft-365"></a>Örnek: Birden çok giden şirket içi posta sunucusu ve Microsoft 365 için SPF TXT kaydı
<a name="ExampleSPFMultipleMailServerO365"> </a>

Birden çok giden posta sunucunuz varsa, SPF TXT kaydına her posta sunucusunun IP adresini ekleyin ve her IP adresini bir boşluk ve ardından bir "ip4:" deyimiyle ayırın. Örneğin:

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-microsoft-365"></a>Sonraki adımlar: Microsoft 365 için SPF'yi ayarlama
<a name="SPFNextSteps"> </a>

SPF TXT kaydınızı formüle ettikten sonra, etki alanınıza eklemek üzere kimlik [sahtekarlığına engel olmak için Microsoft 365'te SPF'yi ayarlama](set-up-spf-in-office-365-to-help-prevent-spoofing.md) başlığı altında yer alan adımları izleyin.

SPF, kimlik sahtekarlıklarını önlemeye yardımcı olacak şekilde tasarlanmış olsa da, SPF'nin koruyabileceği yanıltma teknikleri vardır. Bunlardan korunmak için SPF'yi ayarladıktan sonra Microsoft 365 için DKIM ve DMARC'yi de yapılandırmanız gerekir. Başlamak için bkz. [Microsoft 365'te özel etki alanınızdan gönderilen giden e-postayı doğrulamak için DKIM kullanma](use-dkim-to-validate-outbound-email.md). Ardından bkz. [Microsoft 365'te e-postayı doğrulamak için DMARC kullanma](use-dmarc-to-validate-email.md).

## <a name="troubleshooting-best-practices-for-spf-in-microsoft-365"></a>Sorun giderme: Microsoft 365'te SPF için en iyi yöntemler
<a name="SPFTroubleshoot"> </a>

Özel etki alanınız için yalnızca bir SPF TXT kaydı oluşturabilirsiniz. Birden çok kayıt oluşturmak hepsini bir kez deneme durumuna neden olur ve SPF başarısız olur. Bunu önlemek için her alt etki alanı için ayrı kayıtlar oluşturabilirsiniz. Örneğin, contoso.com için bir kayıt ve bulkmail.contoso.com için başka bir kayıt oluşturun.

Bir e-posta iletisi teslim etmeden önce 10'dan fazla DNS aramasına neden oluyorsa, alıcı posta sunucusu kalıcı bir hatayla yanıt verir(  _permerror_ olarak da adlandırılır) ve iletinin SPF denetiminin başarısız olmasına neden olur. Alıcı sunucu, aşağıdakine benzer bir hata içeren bir teslim edilmedi raporuyla (NDR) de yanıt verebilir:

- İleti atlama sayısını aştı.

- İleti çok fazla arama gerektiriyor.

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-microsoft-365"></a>Microsoft 365 ile üçüncü taraf etki alanlarını kullanırken "çok fazla arama" hatasından kaçınma
<a name="SPFTroubleshoot"> </a>

Üçüncü taraf etki alanları için bazı SPF TXT kayıtları, alıcı sunucuyu çok sayıda DNS araması gerçekleştirmeye yönlendirir. Örneğin, bu yazma sırasında Salesforce.com kaydında 5 include deyimi içerir:

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

Hatayı önlemek için toplu e-posta gönderen herkesin, örneğin bu amaçla özel olarak bir alt etki alanı kullanması gereken bir ilke uygulayabilirsiniz. Ardından, alt etki alanı için toplu e-postayı içeren farklı bir SPF TXT kaydı tanımlarsınız.

 bazı durumlarda, örneğin salesforce.com gibi, ETKI alanını SPF TXT kaydınızda kullanmanız gerekir, ancak diğer durumlarda, üçüncü taraf bu amaçla kullanmanız için zaten bir alt etki alanı oluşturmuş olabilir. Örneğin, exacttarget.com SPF TXT kaydınız için kullanmanız gereken bir alt etki alanı oluşturmuştur:

```text
cust-spf.exacttarget.com
```

SPF TXT kaydınıza üçüncü taraf etki alanları eklediğinizde, 10 arama sınırına girmekten kaçınmak için hangi etki alanını veya alt etki alanını kullanacağınızı üçüncü tarafla onaylamanız gerekir.

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a>Geçerli SPF TXT kaydınızı görüntüleme ve gerekli arama sayısını belirleme
<a name="SPFTroubleshoot"> </a>

SPF TXT kaydınız da dahil olmak üzere DNS kayıtlarınızı görüntülemek için nslookup kullanabilirsiniz. SPF TXT kaydınızın içeriğini görüntülemek için kullanabileceğiniz birçok ücretsiz ve çevrimiçi araç vardır. SPF TXT kaydınıza bakarak ve include deyimleri ve yeniden yönlendirmeler zincirini izleyerek kaydın kaç DNS araması gerektirdiğini belirleyebilirsiniz. Bazı çevrimiçi araçlar bu aramaları sizin için sayar ve görüntüler. Bu sayıyı izlemek, kuruluşunuzdan gönderilen iletilerin alıcı sunucudan perm hatası olarak adlandırılan kalıcı bir hata tetiklemesini önlemeye yardımcı olur.

## <a name="for-more-information"></a>Daha fazla bilgi için
<a name="SPFTroubleshoot"> </a>

SPF TXT kaydını eklerken yardıma mı ihtiyacınız var? Microsoft 365'te özel etki alanınızla Sender Policy Framework kullanımı hakkında ayrıntılı bilgi [için Microsoft 365 için herhangi bir DNS barındırma sağlayıcısında DNS kayıtları oluşturma](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) makalesini okuyun. [İstenmeyen postadan koruma iletisi üst bilgileri](anti-spam-message-headers.md) , SPF denetimleri için Microsoft 365 tarafından kullanılan söz dizimi ve üst bilgi alanlarını içerir.
