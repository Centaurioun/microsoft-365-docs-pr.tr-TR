---
title: DNS ile ilgili temel bilgiler
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: high
ms.collection:
- Tier2
- scotvorg
- highpri
- M365-subscription-management
- Adm_O365
ms.custom:
- VSBFY23
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- MET150
- MOE150
- GEA150
- BSA160
ms.assetid: 854b6b2b-0255-4089-8019-b765cff70377
ROBOTS: NOINDEX
description: Etki alanı adı sistemi bilgisayar ana bilgisayar adlarını IP adresleriyle eşler ve DNS ve etki alanı kayıt şirketi temellerini anlamak etki alanlarını yönetmenize yardımcı olabilir.
ms.openlocfilehash: 1ed2c07005d40c8ee010ba62c72ffcd31f9fe677
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68731447"
---
# <a name="dns-basics"></a>DNS ile ilgili temel bilgiler

 Aradığınızı bulamazsanız, **[Etki Alanları SSS sayfasını inceleyin](../setup/domains-faq.yml)**. 
  
::: moniker range="o365-worldwide"

Contoso.com gibi etki alanı adları, etki alanı kayıt şirketi ve veritabanlarının dünya çapında bir sistemi kullanılarak yönetilir. Etki alanı adı sistemi (DNS), insanlar tarafından okunabilen bilgisayar ana bilgisayarları ve ağ donatımı tarafından kullanılan IP adresleri arasında eşleme sağlar. DNS ve etki alanı kayıt şirketi temellerini anlamak, etki alanlarını yönetmenize yardımcı olabilir.

## <a name="watch-domains--dns-an-overview"></a>İzleme: DNS & Etki Alanları: Genel bakış
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-21vianet"

Contoso.com gibi etki alanı adları, etki alanı kayıt şirketi ve veritabanlarının dünya çapında bir sistemi kullanılarak yönetilir. Etki alanı adı sistemi (DNS), insanlar tarafından okunabilen bilgisayar ana bilgisayarları ve ağ donatımı tarafından kullanılan IP adresleri arasında eşleme sağlar. DNS ve etki alanı kayıt şirketi temellerini anlamak, yöneticilerin etki alanlarını yönetmesine yardımcı olur.
  
::: moniker-end

## <a name="what-are-domain-names"></a>Etki alanı adları nedir?

Etki alanı adları, URL'ler ile e-posta adreslerinde kullanılır ve farklı düzeylere sahiptir. Örneğin, mail.contoso.com aşağıdaki üç düzeye sahip bir etki alanı adıdır:
  
- **.com** en üst düzey etki alanıdır 
    
- **contoso**, ikinci düzey etki alanıdır 
    
- **mail** ise üçüncü düzey etki alanıdır 
    
Neden üçüncü düzey etki alanı kullanmalı? Pazarlama veya bir blog için farklı etki alanı adları olmasını isteyebilirsiniz. Örneğin, blog.contoso.com. Microsoft ile kullanmak için genellikle contoso.com gibi ikinci düzey bir etki alanı eklersiniz, ancak isterseniz üçüncü düzey etki alanlarını da kullanabilirsiniz.
  
[Microsoft 365 ve Office 365 platform hizmeti açıklamasında](/office365/servicedescriptions/office-365-platform-service-description/domains) her teklif türü için etki alanlarıyla neler yapabileceğiniz hakkında daha fazla bilgi edinin.
  
## <a name="understand-dns-record-types"></a>DNS kayıt türlerini anlama

Etki alanınızın DNS ana bilgisayarında depolanan DNS kayıtları, etki alanınızın trafiğini yönlendirmek için kullanılır. Aşağıdaki tabloda sık kullanılan DNS kayıtları ve bunların nasıl kullanıldığı açıklanmaktadır.
  
|**NS (ad sunucusu) kaydı**|**Bir etki alanı için "yetkili ad sunucuları" olan ad sunucularını tanımlar. Etki alanınızın ad sunucularını değiştirdiğinizde, DNS kayıtlarınızın yönetildiği yeri ve DNS sisteminin posta sunucuları hakkında bilgi arayacağı yeri değiştirirsiniz. Microsoft'un kendi ad sunucuları vardır veya etki alanınızla önceden ayarlanmış olan ad sunucularını kullanmaya devam edebilirsiniz.**|
|:-----|:-----|
|Bir kayıt (adres kaydı)  <br/> |Bir etki alanı adını bir IP adresi ile ilişkilendirir.  <br/> |
|CNAME (diğer ad veya kurallı ad) kaydı  <br/> |DNS sisteminde bir etki alanını başka bir etki alanına yönlendirir. Bir ad sunucusu bir etki alanını aradığında ve bir CNAME kaydı olduğunu bulduğunda, sunucu ilk etki alanı adını CNAME ile değiştirir ve ardından yeni adı arar.  <br/> |
|MX (mail exchanger) kaydı  <br/> |E-postanızın gönderilmesi gereken yeri gösterir. Ayrıca, öncelik sırasına göre farklı sunuculara posta gönderebilmeniz için bir öncelik alanı vardır.  <br/> |
|SPF (gönderen ilke çerçevesi) kaydı  <br/> |Kimlik sahtekarlığını ve kimlik avını önlemeye yardımcı olan TXT kaydı.  <br/> |
|SRV (hizmet) kaydı  <br/> |Skype Kurumsal Online ve Exchange Online tarafından Microsoft hizmetleri arasındaki bilgi akışını koordine etmek için kullanılır. Örneğin, SRV kayıtları Outlook Web App 'te gereken iletişim durumunu görmek ve diğer şirketlere ait kişilerle Skype Kurumsal Çevrimiçi sürüm, Skype veya diğer anlık ileti araçlarını kullanmak için gereklidir.  <br/> |
|TTL (yaşam süresi)  <br/> |Ad sunucusunun DNS kaydını, güncelleştirilmiş bir sürüm aramaya başlamadan önce tutacağı süre.  <br/> |
   
## <a name="how-does-dns-work"></a>DNS nasıl çalışır?

Etki alanınızı Microsoft 365 gibi bir bulut hizmetiyle ayarlamanın bir parçası, etki alanı için [DNS kayıtlarının](dns-basics.md) değiştirilmesini veya eklenmesini içerir. İnternet’in e-posta ve web siteleri gibi öğeleri nereye göndereceğini veya nerede bulacağını bilebilmek için DNS’yle, Etki Alanı Adı Sistemi’yle ve etki alanı adlarıyla çalışmasından dolayı, bu değişiklikler gereklidir. 
  
Internet, DNS veya etki alanı adı sistemi'ni kullanacak şekilde ayarlanmıştır. bu da, contoso.com gibi tanıdık adları, IP (Internet Protokolü) adresleri olarak adlandırılan, kapaklar 'ın altındaki özel Internet konumlarını bulabilmemizi sağlar. IP adresleri 70.42.241.42 gibi gönünür, görüyorsunuz ki e-posta sunucuları ve web siteleri gibi konumları tanımlamak için etki alanı adı kullanmak çok daha kolaydır.
  
Kısaca söylemek gerekirse: DNS kayıtları, Internet'e e-postanın nereye gönderileceğini (joe@contoso.com gibi) veya etki alanı adınızı kullanan Web sitelerini (www.contoso.com gibi) nereden bulacağını söyler. Etki alanınız için doğru DNS kayıtlarına doğru bilgileri yerleştirdiğinizde, DNS sistemi her şeyi doğru şekilde yönlendirir, böylece e-postanız başka bir yere değil Microsoft 365'e ulaşır.
  
Bir etki alanının DNS kayıtları, diğer yollarla da yararlı olabilir. Örneğin Exchange, Outlook’un otomatik olarak doğru Exchange sunucusuna bağlanmasını sağlayan bir DNS kaydı arar.
  
### <a name="dns-records-help-the-internet-send-email-to-the-right-place"></a>DNS kayıtları Internet’in e-postayı doğru yere göndermesine yardımcı olur

Yukarıda da okuduğunuz gibi, DNS temelde anımsaması zor IP adreslerini kolay etki alanı adlarına eşleyerek Internet’te trafiği yönlendirir. MX kaydı olarak adlandırılan bir DNS kaydı, özel olarak doğru sunucuya e-posta göndermeye yöneliktir.
  
DNS kayıtları, etki alanınızla ilgili bilgi veritabanı gibidir. Kayıtlar ve bunların değerleri, etki alanınızın her kaydının ve bunun değerinin ne olduğu, bölge dosyası olarak adlandırılan bir şekilde tutulur. Etki alanı kayıt şirketleri ve diğer DNS barındırma şirketleri, etki alanınızın bölge dosyasındaki kayıtları düzenleyebilmeniz için Web sitelerinde bir kullanıcı arabirimi sağlar. Bu noktada, microsoft 365'e e-posta iletileri göndermek için etki alanınızın MX kaydını güncelleştirirsiniz.
  
 *E-postanızı Microsoft 365 olarak değiştirdiğinizde, sonraki adımda etki alanınızın MX kaydını güncelleştirerek bu etki alanına gönderilen TÜM e-postalar Microsoft 365'e gelmeye başlar.*  Diğer kişiler etki alanınızı e-posta için kullanıyorsa, bu kişilerin her biri için Microsoft 365 posta kutuları ayarlamanız gerekir. 
  
Karmaşık mı geldi? Olabilir, ancak Microsoft etki alanı kurulumundaki her adımda size yol gösteririz.
  
### <a name="dns-tells-the-internet-where-to-look-for-websites-too"></a>DNS Internet’e web sitelerini nerede arayacağını da bildirir

Örneğin, www.contoso.com gibi bir Web sitesi adresini yazdığınızda, Internet önce DNS sunucularından birini (Bu örnekte) contoso.com için ad sunucusu (NS) kaydını denetler. NS kaydı, Internet'e söz konusu etki alanı için diğer tüm DNS kayıt değerlerine sahip bölge dosyasını araması gereken yeri gösterir. Hepsi birbirine bağlantılı çok sayıda DNS sunucusu vardır. Sunucular, benzersiz olması gereken ve etki alanının bölge dosyalarının bulunduğu yerdeki tüm kayıtlı etki alanı adlarını izlemek için, birlikte çalışır.
  
::: moniker range="o365-worldwide"

Contoso.com için NS kaydının "godaddy.com" olduğunu varsayalım. Şimdi İnternet contoso.com için diğer tüm DNS kayıtlarının listelendiği bölge dosyasını GoDaddy.com adresinde arayacağını bilir. Söz konusu DNS kayıtları, contoso.com için e-postaların gönderileceği yeri söyleyen MX kaydını ve diğer kayıtları içerir. MX kaydında "Microsoft 365'e e-posta gönder" (ancak teknik açıdan) yazan bir değer varsa, contoso.com e-posta adresine (joe@contoso.com gibi) gönderilen tüm e-posta iletileri burada gönderilir. Ardından, o konumda “joe” adlı bir posta kutusu olduğu sürece, e-posta teslim edilir.

::: moniker-end

::: moniker range="o365-21vianet"

Contoso.com için NS kaydının "hichina.com" olduğunu varsayalım. Şimdi İnternet contoso.com için diğer tüm DNS kayıtlarının listelendiği bölge dosyasını hichina.com adresinde arayacağını bilir. Söz konusu DNS kayıtları, contoso.com için e-postaların gönderileceği yeri söyleyen MX kaydını ve diğer kayıtları içerir. MX kaydında "Microsoft 365'e e-posta gönder" (ancak teknik açıdan) yazan bir değer varsa, contoso.com e-posta adresine (joe@contoso.com gibi) gönderilen tüm e-posta iletileri burada gönderilir. Ardından, o konumda “joe” adlı bir posta kutusu olduğu sürece, e-posta teslim edilir.

::: moniker-end

Tüm bunların Microsoft 365 ile çalışması için girmeniz gereken gerçek değerler, etki alanınızı ayarlarken etki alanı kurulum adımlarında sizin için listelenir. Kurulumu elle yapıyorsanız, değerleri DNS sunucunuzda doğru DNS kayıtlarına (MX kaydı, CNAME kayıtları vb.) kopyalar ve yapıştırırsınız. Bu, etki alanı kayıt şirketiniz olabilir ama olması gerekmez.
  
::: moniker range="o365-worldwide"

Etki alanınızın bölge dosyası, neden etki alanı kayıt şirketinizden başka bir yerde olabilir? Ayrıca, etki alanı adınızı GoDaddy gibi bir etki alanı kayıt şirketinde kaydedebilirsiniz, ancak DNS kayıtlarınız ayrı bir DNS barındırma şirketinde veya Web barındırma şirketinde herhangi bir yerde yönetilebilir. Etki alanınızın NS kayıtları, bu bilgileri depolar ve bu sayede tüm DNS sunucuları nereye bakacaklarını bilir.

::: moniker-end

::: moniker range="o365-21vianet"

Etki alanınızın bölge dosyası, neden etki alanı kayıt şirketinizden başka bir yerde olabilir? Ayrıca, etki alanı adınızı HiChina gibi bir etki alanı kayıt şirketinde kaydedebilirsiniz, ancak DNS kayıtlarınız ayrı bir DNS barındırma şirketinde veya Web barındırma şirketinde herhangi bir yerde yönetilebilir. Etki alanınızın NS kayıtları, bu bilgileri depolar ve bu sayede tüm DNS sunucuları nereye bakacaklarını bilir.

::: moniker-end

::: moniker range="o365-worldwide"
## <a name="why-add-a-domain-in-microsoft-365"></a>Microsoft 365'te neden etki alanı eklemelisiniz?


Microsoft 365'e fourthcoffee.com gibi özel bir etki alanı eklemek, hizmetle daha kısa, daha tanıdık bir e-posta adresi ve userID kullanmanıza olanak tanır. Microsoft 365 hesabına kaydolduğunda [kullanmak üzere bir etki alanı verilir](../setup/domains-faq.yml) , ancak "onmicrosoft.com" içerir. Birçok kişi, e-posta için Microsoft 365 kullanmayı planlıyorsa kuruluşlarını veya iş etki alanlarını eklemeyi tercih eder. 
  
> [!NOTE]
> Yalnızca Outlook veya Word gibi Microsoft uygulamalarını indirip kullanmak istiyorsanız, etki alanı eklemeniz gerekmez: [PC veya Mac bilgisayarınıza Office yükleme](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658). 
  
Microsoft 365'te etki alanı adınızı e-postanız, genel web siteniz ve anlık ileti adresinizle kullanabilirsiniz.
  
- **E-posta:** Etki alanınızın adı e-postanızı özelleştirmenize olanak tanır, böylece, hesabınızla birlikte gelen [ilk onmicrosoft.com e-posta adresinden](../setup/domains-faq.yml) daha kısa, daha kolay anımsanan bir adres kullanabilirsiniz. Bu nedenle joe@contoso.onmicrosoft.com yerine e-posta adresi (Microsoft 365'te oturum açmak için kullandığınız iş hesabıdır) joe@contoso.com. 
    
- **Web sitesi:** SharePoint Online Genel Web Sitesi içeren bir Microsoft 365 aboneliğiniz varsa (artık satın alınamaz), genel web siteniz şöyle bir başlangıç adresiyle birlikte gelir: contoso-public.sharepoint.com. İşletmeniz için web sitenizi ayarlarsanız, web sitesi adresini www.contoso.com gibi bir adla yeniden adlandırmak için özel bir etki alanı adı kullanabilirsiniz. 
    
- **Anlık mesajlaşma:** Kurumsal Skype Çevrimiçi adresiniz de etki alanı adınızı kullanacak şekilde özelleştirilebilir, böylece kuruluşunuzdaki kişiler daha kısa, kolay anımsanacak bir adres (joe@contoso.com gibi) kullanarak Skype Kurumsal Çevrimiçi’nde birbirleriyle bağlanabilirler. 
    
::: moniker-end

## <a name="the-dns-records-required-for-microsoft-365"></a>Microsoft 365 için gereken DNS kayıtları

Microsoft 365'in etki alanınızla çalışması için gereken bir dizi DNS kaydı vardır. E-postanın Microsoft 365'e gönderilmesi için etki alanınızın MX kaydını ayarlamaya ek olarak, Outlook'un doğru Exchange sunucusuna otomatik olarak bağlanabildiğinden emin olmak, anlık iletileri ayarlamak ve istenmeyen posta e-postasını önlemeye yardımcı olmak gibi görevlerde yardımcı olacak kayıtlar da vardır.
  
Etki alanınızı ayarlamak için [değerlerin bir listesini](information-for-dns-records.md) bulabilirsiniz. Bunlar <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">doğrudan Microsoft 365 yönetim merkezi</a> dahil. 
  
Dağıtım planlıyorsanız Microsoft 365 için gereken tüm DNS kayıtlarının listesini, işlevlerinin ne olduğunu ve örnek değerleri gözden geçirmek isteyebilirsiniz. [Microsoft 365 için Dış Etki Alanı Adı Sistemi kayıtlarına](../../enterprise/external-domain-name-system-records.md) göz atın.
  
## <a name="next-steps"></a>Sonraki adımlar

Aşağıdaki konulardan birini gözden geçirin: 
  
- Etki alanınızın nerede kayıtlı olduğundan emin değil misiniz? [Etki alanı kayıt şirketini bulma konusunda yardım alın.](find-your-domain-registrar.md)
- Etki alanınızı Microsoft 365 ile kullanabilmek [için neden sihirbaz adımlarını tamamlamanız](../setup/add-domain.md) gerekebileceğini öğrenin.

## <a name="related-content"></a>İlgili içerik

[Etki Alanları SSS](../setup/domains-faq.yml) (makale)\
[Kendi etki alanınızı veya DNS kayıtlarınızı ekledikten sonra sorunları bulma ve düzeltme](find-and-fix-issues.md) (makale)\
[Etki alanlarını yönetme](/admin) (sayfa bağlantısı)