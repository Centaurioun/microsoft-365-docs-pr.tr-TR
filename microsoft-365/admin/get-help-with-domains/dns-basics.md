---
title: DNS ile ilgili temel bilgiler
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
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
description: Etki alanı adı sistemi, bilgisayar ana bilgisayar adlarını IP adresleriyle eşler ve DNS ile etki alanı kayıt şirketiyle ilgili temel bilgileri anlamanız, etki alanlarını yönetmenize yardımcı olabilir.
ms.openlocfilehash: 9bbd099a7c44aecdd37772cd97333a905585e33f
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/09/2021
ms.locfileid: "62996050"
---
# <a name="dns-basics"></a>DNS ile ilgili temel bilgiler

 Aradığınızı bulamazsanız, **[Etki Alanları SSS sayfasını inceleyin](../setup/domains-faq.yml)**. 
  
::: moniker range="o365-worldwide"

Contoso.com gibi etki alanı adları, etki alanı kayıt şirketi ve veritabanlarının dünya çapında bir sistemi kullanılarak yönetilir. Etki alanı adı sistemi (DNS), insanlar tarafından okunabilen bilgisayar ana bilgisayarları ve ağ donatımı tarafından kullanılan IP adresleri arasında eşleme sağlar. DNS ve etki alanı kayıt şirketiyle ilgili temel bilgilerin anlaşılması, etki alanlarını yönetmenize yardımcı olabilir.

## <a name="watch-domains--dns-an-overview"></a>İzle: Etki alanları & DNS: Genel bakış
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-21vianet"

Contoso.com gibi etki alanı adları, etki alanı kayıt şirketi ve veritabanlarının dünya çapında bir sistemi kullanılarak yönetilir. Etki alanı adı sistemi (DNS), insanlar tarafından okunabilen bilgisayar ana bilgisayarları ve ağ donatımı tarafından kullanılan IP adresleri arasında eşleme sağlar. DNS ve etki alanı kayıt şirketiyle ilgili temel bilgilerin anlaşılması, yöneticilerin etki alanlarını yönetmelerine yardımcı olur.
  
::: moniker-end

## <a name="what-are-domain-names"></a>Etki alanı adları nedir?

Etki alanı adları, URL'ler ile e-posta adreslerinde kullanılır ve farklı düzeylere sahiptir. Örneğin, mail.contoso.com aşağıdaki üç düzeye sahip bir etki alanı adıdır:
  
- **.com** en üst düzey etki alanıdır 
    
- **contoso**, ikinci düzey etki alanıdır 
    
- **mail** ise üçüncü düzey etki alanıdır 
    
Neden üçüncü düzey etki alanı kullanmalı? Pazarlama veya bir blog için farklı etki alanı adları olmasını isteyebilirsiniz. Örneğin, blog.contoso.com. Normalde, Microsoft'la kullanmak üzere contoso.com ikinci düzey etki alanı eklersiniz, ancak 3. düzey etki alanlarını da kullanabilirsiniz.
  
Her teklif türü için etki alanlarıyla neler yapabilirim hakkında daha fazla bilgi edinmek için, Microsoft 365 [ve platform Office 365 açıklamalarını tıklatın](/office365/servicedescriptions/office-365-platform-service-description/domains).
  
## <a name="understand-dns-record-types"></a>DNS kayıt türlerini anlama

Etki alanınızın DNS ana bilgisayarında depolanan DNS kayıtları, etki alanınızın trafiğini yönlendirmek için kullanılır. Aşağıdaki tabloda, sık kullanılan DNS kayıtları ve bunların nasıl kullanıldıkları açık almaktadır.
  
|**NS (ad sunucusu) kaydı**|**Etki alanı için "yetkili ad sunucuları" olan ad sunucularını tanımlar. Etki alanınız için ad sunucularını değiştirmiyorken, DNS kayıtlarınızı yönetil tam olarak nerede yönetileceğini ve DNS sisteminin posta sunucuları hakkında nerede bilgi bak diğer yeri değiştirebilirsiniz. Microsoft'un kendi ad sunucuları vardır veya etki alanınız ile zaten ayarlanmış olan ad sunucularını kullanmaya devam etmek karar veebilirsiniz.**|
|:-----|:-----|
|Bir kayıt (adres kaydı)  <br/> |Bir etki alanı adını bir IP adresi ile ilişkilendirir.  <br/> |
|CNAME (diğer ad veya kurallı ad) kaydı  <br/> |DNS sisteminde bir etki alanını başka bir etki alanına yönlendirir. Bir ad sunucusu bir etki alanını aradığında ve bir CNAME kaydı olduğunu bulduğunda, sunucu ilk etki alanı adını CNAME ile değiştirir ve ardından yeni adı arar.  <br/> |
|MX (mail exchanger) kaydı  <br/> |E-postanızın gönderilmesi gereken yeri gösterir. Ayrıca, öncelik sırasına göre farklı sunuculara posta gönderebilmeniz için bir öncelik alanı vardır.  <br/> |
|SPF (gönderen ilke çerçevesi) kaydı  <br/> |Kimlik sahtekarlığını ve kimlik avını önlemeye yardımcı olan TXT kaydı.  <br/> |
|SRV (hizmet) kaydı  <br/> |Skype Kurumsal Online ve Exchange Online akışlarını eşgüdüm için diğer Microsoft hizmetleri. Örneğin, SRV kayıtları Outlook Web App 'te gereken iletişim durumunu görmek ve diğer şirketlere ait kişilerle Skype Kurumsal Çevrimiçi sürüm, Skype veya diğer anlık ileti araçlarını kullanmak için gereklidir.  <br/> |
|TTL (yaşam süresi)  <br/> |Ad sunucusunun DNS kaydını, güncelleştirilmiş bir sürüm aramaya başlamadan önce tutacağı süre.  <br/> |
   
## <a name="how-does-dns-work"></a>DNS nasıl çalışır?

Etki alanınızı Microsoft 365 gibi bir bulut hizmetiyle ayarlamanın bir bölümü, etki alanı [için DNS kayıtlarını değiştirmeyi veya](dns-basics.md) eklemeyi içerir. İnternet’in e-posta ve web siteleri gibi öğeleri nereye göndereceğini veya nerede bulacağını bilebilmek için DNS’yle, Etki Alanı Adı Sistemi’yle ve etki alanı adlarıyla çalışmasından dolayı, bu değişiklikler gereklidir. 
  
Internet, DNS veya etki alanı adı sistemi'ni kullanacak şekilde ayarlanmıştır. bu da, contoso.com gibi tanıdık adları, IP (Internet Protokolü) adresleri olarak adlandırılan, kapaklar 'ın altındaki özel Internet konumlarını bulabilmemizi sağlar. IP adresleri 70.42.241.42 gibi gönünür, görüyorsunuz ki e-posta sunucuları ve web siteleri gibi konumları tanımlamak için etki alanı adı kullanmak çok daha kolaydır.
  
Kısaca söylemek gerekirse: DNS kayıtları, Internet'e e-postanın nereye gönderileceğini (joe@contoso.com gibi) veya etki alanı adınızı kullanan Web sitelerini (www.contoso.com gibi) nereden bulacağını söyler. Etki alanınız için doğru DNS kayıtlarına doğru bilgileri koyarak, DNS sistemi her şeyi doğru bir şekilde yönlendirmektedir ve örneğin e-postanız başka bir yere Microsoft 365 yerine Microsoft 365 gelir.
  
Bir etki alanının DNS kayıtları, diğer yollarla da yararlı olabilir. Örneğin Exchange, Outlook’un otomatik olarak doğru Exchange sunucusuna bağlanmasını sağlayan bir DNS kaydı arar.
  
### <a name="dns-records-help-the-internet-send-email-to-the-right-place"></a>DNS kayıtları Internet’in e-postayı doğru yere göndermesine yardımcı olur

Yukarıda da okuduğunuz gibi, DNS temelde anımsaması zor IP adreslerini kolay etki alanı adlarına eşleyerek Internet’te trafiği yönlendirir. MX kaydı olarak adlandırılan bir DNS kaydı, özel olarak doğru sunucuya e-posta göndermeye yöneliktir.
  
DNS kayıtları, etki alanınızla ilgili bilgi veritabanı gibidir. Kayıtlar ve bunların değerleri, etki alanınızın her kaydının ve bunun değerinin ne olduğu, bölge dosyası olarak adlandırılan bir şekilde tutulur. Etki alanı kayıt şirketleri ve diğer DNS barındırma şirketleri, etki alanınızın bölge dosyasındaki kayıtları düzenleyebilmeniz için Web sitelerinde bir kullanıcı arabirimi sağlar. İşte burada, etki alanınıza e-posta iletileri göndermek için etki alanınız için MX kaydını Microsoft 365.
  
 *E-postanızı Microsoft 365, bir sonraki adımda etki alanınıza gönderilen TÜM e-postaların MX kaydını güncelleştirerek e-postanızı Microsoft 365.*  Etki alanınızı e-posta için diğer kişiler kullanıyorsa, bu Microsoft 365 posta kutuları ayarlamanız gerekir. 
  
Karmaşık mı geldi? Olabilir, ama Microsoft etki alanı kurulumunun her adımlarında size yol sağlaruz.
  
### <a name="dns-tells-the-internet-where-to-look-for-websites-too"></a>DNS Internet’e web sitelerini nerede arayacağını da bildirir

Örneğin, www.contoso.com gibi bir Web sitesi adresini yazdığınızda, Internet önce DNS sunucularından birini (Bu örnekte) contoso.com için ad sunucusu (NS) kaydını denetler. NS kaydı, Internet'e söz konusu etki alanı için diğer tüm DNS kayıt değerlerine sahip bölge dosyasını araması gereken yeri gösterir. Hepsi birbirine bağlantılı çok sayıda DNS sunucusu vardır. Sunucular, benzersiz olması gereken ve etki alanının bölge dosyalarının bulunduğu yerdeki tüm kayıtlı etki alanı adlarını izlemek için, birlikte çalışır.
  
::: moniker range="o365-worldwide"

Contoso.com için NS kaydının "godaddy.com" olduğunu varsayalım. Şimdi İnternet contoso.com için diğer tüm DNS kayıtlarının listelendiği bölge dosyasını GoDaddy.com adresinde arayacağını bilir. Söz konusu DNS kayıtları, contoso.com için e-postaların gönderileceği yeri söyleyen MX kaydını ve diğer kayıtları içerir. MX kaydında (teknik terimlerle) "Microsoft 365'e e-posta gönder" diyen bir değer varsa, bir contoso.com e-posta adresine (örneğin joe@contoso.com) gönderilen tüm e-posta iletileri bu adrese gönderilir. Ardından, o konumda “joe” adlı bir posta kutusu olduğu sürece, e-posta teslim edilir.

::: moniker-end

::: moniker range="o365-21vianet"

Contoso.com için NS kaydının "hichina.com" olduğunu varsayalım. Şimdi İnternet contoso.com için diğer tüm DNS kayıtlarının listelendiği bölge dosyasını hichina.com adresinde arayacağını bilir. Söz konusu DNS kayıtları, contoso.com için e-postaların gönderileceği yeri söyleyen MX kaydını ve diğer kayıtları içerir. MX kaydında (teknik terimlerle) "Microsoft 365'e e-posta gönder" diyen bir değer varsa, bir contoso.com e-posta adresine (örneğin joe@contoso.com) gönderilen tüm e-posta iletileri bu adrese gönderilir. Ardından, o konumda “joe” adlı bir posta kutusu olduğu sürece, e-posta teslim edilir.

::: moniker-end

Tüm bunların etki alanı kurulum adımlarında, tüm bunlar Microsoft 365 için girmeniz gereken gerçek değerler, etki alanı kurulum adımlarında sizin için listelenir. Kurulumu elle yapıyorsanız, değerleri DNS sunucunuzda doğru DNS kayıtlarına (MX kaydı, CNAME kayıtları vb.) kopyalar ve yapıştırırsınız. Bu, etki alanı kayıt şirketiniz olabilir ama olması gerekmez.
  
::: moniker range="o365-worldwide"

Etki alanınızın bölge dosyası, neden etki alanı kayıt şirketinizden başka bir yerde olabilir? Ayrıca, etki alanı adınızı GoDaddy gibi bir etki alanı kayıt şirketinde kaydedebilirsiniz, ancak DNS kayıtlarınız ayrı bir DNS barındırma şirketinde veya Web barındırma şirketinde herhangi bir yerde yönetilebilir. Etki alanınızın NS kayıtları, bu bilgileri depolar ve bu sayede tüm DNS sunucuları nereye bakacaklarını bilir.

::: moniker-end

::: moniker range="o365-21vianet"

Etki alanınızın bölge dosyası, neden etki alanı kayıt şirketinizden başka bir yerde olabilir? Ayrıca, etki alanı adınızı HiChina gibi bir etki alanı kayıt şirketinde kaydedebilirsiniz, ancak DNS kayıtlarınız ayrı bir DNS barındırma şirketinde veya Web barındırma şirketinde herhangi bir yerde yönetilebilir. Etki alanınızın NS kayıtları, bu bilgileri depolar ve bu sayede tüm DNS sunucuları nereye bakacaklarını bilir.

::: moniker-end

::: moniker range="o365-worldwide"
## <a name="why-add-a-domain-in-microsoft-365"></a>Etki alanı neden Microsoft 365?


E-posta adresine fourthcoffee.com özel bir etki alanı Microsoft 365, hizmetle daha kısa, daha bildik bir e-posta adresi ve kullanıcı adı kullanmanızı sağlar. Microsoft 365 [hesabına](../setup/domains-faq.yml) kaydolarak kullanmak için size bir etki alanı verilir, ancak bu etki alanı "onmicrosoft.com." E-posta için E-posta hesabı kullanmayı plan eden birçok kişi, Microsoft 365 etki alanını eklemeyi tercih eder. 
  
> [!NOTE]
> Yalnızca Outlook veya Word gibi Microsoft uygulamalarını indirmek ve kullanmak için etki alanı eklemenize gerek [yok: PC veya Mac bilgisayarınıza Office uygulamaları yükleyin](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658). 
  
E-postanız, genel web siteniz Microsoft 365 anlık ileti adresinizle etki alanı adınızı aynı adreste kullanabilirsiniz.
  
- **E-posta:** Etki alanınızın adı e-postanızı özelleştirmenize olanak tanır, böylece, hesabınızla birlikte gelen [ilk onmicrosoft.com e-posta adresinden](../setup/domains-faq.yml) daha kısa, daha kolay anımsanan bir adres kullanabilirsiniz. Dolayısıyla, joe@contoso.onmicrosoft.com e-posta adresi (aynı zamanda Microsoft 365'te oturum a temlik etmek için de bu iş hesabı) joe@contoso.com. 
    
- **Web sitesi:** SharePoint Online Genel Web Sitesi (artık satın alınamaz) içeren bir Microsoft 365 aboneliğiniz varsa, genel web siteniz bunun gibi bir başlangıç adresiyle birlikte gelir: contoso-public.sharepoint.com. İşletmeniz için web sitenizi ayarlarsanız, web sitesi adresini www.contoso.com gibi bir adla yeniden adlandırmak için özel bir etki alanı adı kullanabilirsiniz. 
    
- **Anlık mesajlaşma:** Kurumsal Skype Çevrimiçi adresiniz de etki alanı adınızı kullanacak şekilde özelleştirilebilir, böylece kuruluşunuzdaki kişiler daha kısa, kolay anımsanacak bir adres (joe@contoso.com gibi) kullanarak Skype Kurumsal Çevrimiçi’nde birbirleriyle bağlanabilirler. 
    
::: moniker-end

## <a name="the-dns-records-required-for-microsoft-365"></a>Etki alanı için gereken DNS Microsoft 365

Etki alanınız ile çalışmak için Microsoft 365 DNS kayıtları gereklidir. Etki alanınıza e-postanın Microsoft 365'a göndernecek şekilde MX kaydını ayarlamaya ek olarak, Outlook'un otomatik olarak doğru Exchange sunucusuna bağlana olduğundan emin olmak, anlık iletileri ayarlama ve istenmeyen e-postayı önlemeye yardımcı olmak gibi görevlerde yardımcı olan kayıtlar da vardır.
  
Etki alanınızı ayarlamak için [değerlerin bir listesini](information-for-dns-records.md) bulabilirsiniz. Bunlar, en son <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Microsoft 365 yönetim merkezi.</a> 
  
Ya da bir dağıtım planlıyorsanız, bu dağıtım için gereken tüm DNS kayıtlarının listesini, bunların Microsoft 365 değerlerini ve örnek değerlerini gözden geçirmek de istiyor da olabilir. Dış Etki [Alanı Adı Sistemi kayıtlarına göz Microsoft 365](../../enterprise/external-domain-name-system-records.md).
  
## <a name="next-steps"></a>Sonraki adımlar

Aşağıdaki konulardan birini gözden geçirin: 
  
- Etki alanınızın nerede kayıtlı olduğundan emin değil misiniz? [Etki alanı kayıt şirketini bulma konusunda yardım alın.](find-your-domain-registrar.md)
- Etki alanını [etki alanıyla birlikte kullanmak için önce](../setup/add-domain.md) neden sihirbazın adımlarını tamamlamanız Microsoft 365.

## <a name="related-content"></a>İlgili içerik

[Etki Alanları SSS](../setup/domains-faq.yml) (makale)\
[Etki alanınızı veya DNS kayıtlarınızı ekledikten sonra sorunları bulma](find-and-fix-issues.md) ve düzeltme (makale)\
[Etki alanlarını yönetme](/admin) (bağlantı sayfası)