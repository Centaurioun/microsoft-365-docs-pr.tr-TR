---
title: Microsoft 365 ağ bağlantısını değerlendirme
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 6/23/2020
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 64b420ef-0218-48f6-8a34-74bb27633b10
description: Microsoft 365, tüm dünyadaki müşterilerin İnternet bağlantısı kullanarak hizmete bağlanmasını sağlamak için tasarlanmıştır. Hizmet geliştikçe Microsoft 365'in güvenliği, performansı ve güvenilirliği, hizmetle bağlantı kurmak için İnternet'i kullanan müşterilere göre geliştirilir.
ms.openlocfilehash: e2ee363f1e421eed89f3b72ff206dda3000e0c84
ms.sourcegitcommit: 62368e5a48e569c8e475b07d194d7d8ff7d167ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67560779"
---
# <a name="assessing-microsoft-365-network-connectivity"></a>Microsoft 365 ağ bağlantısını değerlendirme

*Bu makale hem Microsoft 365 Kurumsal hem de Office 365 Kurumsal için geçerlidir.*

Microsoft 365, tüm dünyadaki müşterilerin İnternet bağlantısı kullanarak hizmete bağlanmasını sağlamak için tasarlanmıştır. Hizmet geliştikçe Microsoft 365'in güvenliği, performansı ve güvenilirliği, hizmetle bağlantı kurmak için İnternet'i kullanan müşterilere göre geliştirilir.
  
Microsoft 365'i kullanmayı planan müşteriler, dağıtım projesinin bir parçası olarak mevcut ve tahmin edilen İnternet bağlantısı gereksinimlerini değerlendirmelidir. Güvenilir ve uygun boyutlandırılmış kurumsal sınıf dağıtımlar için İnternet bağlantısı, Microsoft 365 özelliklerini ve senaryolarını tüketmenin kritik bir parçasıdır.
  
Ağ değerlendirmeleri, boyutunuza ve tercihlerinize bağlı olarak birçok farklı kişi ve kuruluş tarafından gerçekleştirilebilir. Değerlendirmenin ağ kapsamı, dağıtım sürecinizde bulunduğunuz yere bağlı olarak da farklılık gösterebilir. Ağ değerlendirmesi gerçekleştirmek için gerekenleri daha iyi anlamanıza yardımcı olmak için kullanabileceğiniz seçenekleri anlamanıza yardımcı olacak bir ağ değerlendirme kılavuzu hazırladık. Bu değerlendirme, Microsoft 365'i başarıyla benimsemenizi sağlamak için dağıtım projesine hangi adımların ve kaynakların eklenmesi gerektiğini belirler.
  
Kapsamlı bir ağ değerlendirmesi, uygulama ayrıntılarıyla birlikte ağ tasarımı zorluklarına olası çözümler sağlayacaktır. Bazı ağ değerlendirmeleri, Microsoft 365'e en uygun ağ bağlantısının mevcut ağ ve İnternet çıkış altyapısında küçük yapılandırma veya tasarım değişiklikleriyle karşılanabileceğini gösterecektir.

Bazı değerlendirmeler, Microsoft 365'e ağ bağlantısının ağ bileşenlerine ek yatırımlar gerektirdiğini gösterir. Örneğin, şubelere ve birden çok coğrafi bölgeye yayılan kurumsal ağlar, Microsoft 365'e İnternet bağlantısını desteklemek için SD-WAN çözümlerine veya iyileştirilmiş yönlendirme altyapısına yatırım yapılmasını gerektirebilir. Bazen bir değerlendirme Microsoft 365'e ağ bağlantısının [Skype Kurumsal Çevrimiçi medya kalitesi](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917) gibi senaryolar için düzenleme veya performans gereksinimlerinden etkilenmiş olduğunu gösterir. Bu ek gereksinimler İnternet bağlantısı altyapısı, yönlendirme iyileştirmesi ve özelleştirilmiş doğrudan bağlantı yatırımlarına yol açabilir.

Ağınızı değerlendirmenize yardımcı olacak bazı kaynaklar:

- [Microsoft 365 ağı](microsoft-365-networking-overview.md) hakkında kavramsal bilgiler için bkz. Microsoft 365 ağ bağlantısına genel bakış.
- [Microsoft 365](./microsoft-365-network-connectivity-principles.md) trafiğini güvenli bir şekilde yönetmek ve mümkün olan en iyi performansı elde etmek için bağlantı ilkelerini anlamak için bkz. Microsoft 365 Ağ Bağlantı İlkeleri.
- Microsoft 365 planlama, tasarım ve dağıtımıyla ilgili destekli yardım için [Microsoft FastTrack](https://www.microsoft.com/fasttrack) kaydolun. 
- Belirli bir kullanıcı konumu ile [Microsoft 365](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) arasında yapılabilecek ağ bağlantısı geliştirmeleri hakkında özel rehberlik sağlayan temel bağlantı testlerini çalıştırmak için aşağıdaki Microsoft 365 bağlantı testi bölümüne bakın.

> [!NOTE]
> Office 365 için ExpressRoute kullanmak için Microsoft yetkilendirmesi gerekir. Microsoft, her müşteri isteğini inceler ve expressRoute'u yalnızca bir müşterinin yasal gereksinimi doğrudan bağlantıyı zorunlu Office 365 kullanım için yetkiler. Bu tür gereksinimleriniz varsa lütfen düzenlemenin metin alıntısını ve web bağlantısını sağlayın. Bu bağlantı, Microsoft incelemesini başlatmak [için ExpressRoute'ta Office 365 İstek Formu'nda](https://aka.ms/O365ERReview) doğrudan bağlantının gerekli olduğu anlamına gelir. Office 365 için yol filtreleri oluşturmaya çalışan yetkisiz abonelikler [bir hata iletisi](https://support.microsoft.com/kb/3181709) alır.
  
Microsoft 365 için ağ değerlendirmenizi planlarken göz önünde bulundurmanız gereken önemli noktalar:
  
- Microsoft 365, genel İnternet üzerinden çalışan güvenli, güvenilir, yüksek performanslı bir hizmettir. Hizmetin bu yönlerini geliştirmek için yatırım yapmaya devam ediyoruz. Tüm Microsoft 365 hizmetleri İnternet bağlantısı üzerinden kullanılabilir.

- Microsoft 365'in kullanılabilirlik, genel erişim ve İnternet tabanlı bağlantı performansı gibi temel yönlerini sürekli iyileştiriyoruz. Örneğin, birçok Microsoft 365 hizmeti İnternet'e yönelik uç düğümlerden oluşan genişleyen bir kümeden yararlanıyor. Bu uç ağ, İnternet üzerinden gelen bağlantılara en iyi yakınlığı ve performansı sunar.

- Teams veya Skype Kurumsal Çevrimiçi ses, video veya toplantı özellikleri gibi dahil edilen hizmetlerden herhangi biri için Microsoft 365'i kullanmayı göz önünde bulundururken, müşteriler uçtan uca ağ değerlendirmesini tamamlamalı ve [Microsoft FastTrack](https://www.microsoft.com/fasttrack) kullanarak bağlantı gereksinimlerini karşılamalıdır.

Microsoft 365'i değerlendiriyorsanız ve ağ değerlendirmenizle nereden başlayacağınızdan emin değilseniz veya üstesinden gelmek için yardıma ihtiyacınız olan ağ tasarımı güçlükleri bulduysanız lütfen Microsoft hesabı ekibinizle birlikte çalışın.

## <a name="the-microsoft-365-connectivity-test"></a>Microsoft 365 bağlantı testi

[Microsoft 365 bağlantı testi, Microsoft 365](https://aka.ms/netonboard) kiracınızda temel bağlantı testleri çalıştıran ve en iyi Microsoft 365 performansı için belirli ağ tasarımı önerilerinde bulunan bir kavram kanıtı (POC) ağ değerlendirme aracıdır. Araç, İnternet web'e gözatma için yararlı olan ancak Microsoft 365 gibi büyük SaaS uygulamalarının performansını etkileyen yaygın büyük kurumsal ağ çevre tasarımı seçimlerini vurgular.

Ağ Ekleme aracı aşağıdakileri yapar:

- Konumunuzu algılar veya test etmek için bir konum belirtebilirsiniz
- Ağ çıkışınızın konumunu denetler
- En yakın Microsoft 365 hizmeti ön kapısına giden ağ yolunu test etme
- Proxy sunucuları, güvenlik duvarları ve DNS ile ilgili çevre ağı tasarım önerileri sunan indirilebilir bir Windows 10 uygulaması kullanarak gelişmiş testler sağlar. Araç ayrıca Skype Kurumsal Online, Microsoft Teams, SharePoint Online ve Exchange Online için performans testleri çalıştırır.

Aracın iki bileşeni vardır: temel bağlantı bilgilerini toplayan tarayıcı tabanlı bir kullanıcı arabirimi ve gelişmiş testler çalıştıran ve ek değerlendirme verileri döndüren indirilebilir bir Windows 10 uygulaması.

Tarayıcı tabanlı araç aşağıdaki bilgileri görüntüler:

- Sonuçlar ve etki sekmesi
  - Kullanımdaki hizmet ön kapısının haritasındaki konum
  - En uygun bağlantıyı sağlayacak diğer hizmet ön kapılarının haritasındaki konum
  - Size yakın diğer Microsoft 365 müşterilerine kıyasla göreli performans
- Ayrıntılar ve çözümler sekmesi
  - Şehre ve ülkeye göre kullanıcı konumu
  - Şehre, eyalete ve ülkeye göre ağ çıkış konumu
  - Kullanıcıdan ağa çıkış uzaklığı
  - Microsoft 365 Exchange Online hizmeti ön kapı konumu
  - Kullanıcı konumu için en uygun Microsoft 365 Exchange Online hizmeti ön kapı(lar)
  - Metro bölgenizdeki müşteriler daha iyi performansla

Gelişmiş Testler indirilebilir uygulaması aşağıdaki ek bilgileri sağlar:

- Ayrıntılar ve çözümler sekmesi (ekli)
  - Kullanıcının varsayılan ağ geçidi
  - İstemci DNS Sunucusu
  - İstemci DNS Özyinelemeli Çözümleyicisi
  - DNS sunucusunu Exchange Online
  - SharePoint Online DNS sunucusu
  - Ara sunucu kimliği
  - Medya bağlantı denetimi
  - Medya kalitesi paket kaybı
  - Medya kalitesi gecikme süresi
  - Medya kalitesi değişimi
  - Medya kalitesi paketi yeniden sıralama
- Özelliğe özgü birden çok uç noktaya bağlantı testleri
- Exchange Online, SharePoint Online ve Teams hizmetleri için tracert ve gecikme süresi verilerini içeren ağ yolu tanılamaları

Microsoft 365 bağlantı testi hakkında bilgi edinebilir ve [Güncelleştirilmiş Microsoft 365 bağlantı testi POC ile yeni ağ tasarımı önerileri](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) blog gönderisinde geri bildirim sağlayabilirsiniz. Bu aracın gelecekteki güncelleştirmeleri ve diğer Microsoft 365 ağ güncelleştirmeleri hakkında bilgiler [Office 365 Ağ](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking) blogu'na gönderilir.
  
İşte geri dönmek için kullanabileceğiniz kısa bir bağlantı: [https://aka.ms/o365networkconnectivity.](./microsoft-365-network-connectivity-principles.md)
  
## <a name="related-topics"></a>İlgili konular

[Microsoft 365 Ağ Bağlantısına Genel Bakış](microsoft-365-networking-overview.md)

[Microsoft 365 Ağ Bağlantı İlkeleri](./microsoft-365-network-connectivity-principles.md)

[Office 365 uç noktalarını yönetme](managing-office-365-endpoints.md)

[Office 365 URL'leri ve IP adresi aralıkları](urls-and-ip-address-ranges.md)

[Office 365 IP Adresi ve URL Web hizmeti](microsoft-365-ip-web-service.md)

[Microsoft 365 ağ ve performans ayarlama](network-planning-and-performance.md)

[Microsoft 365 Kurumsal genel bakış](microsoft-365-overview.md)