---
title: Çin kullanıcıları için Microsoft 365 genel kiracı performansı iyileştirmesi
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 3/3/2022
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- Ent_O365
- Strat_O365_Enterprise
- remotework
search.appverid: MET150
f1.keywords:
- NOCSH
description: Bu makalede, genel Microsoft 365 kiracılarının Çin kullanıcıları için ağ performansını iyileştirmeye yönelik yönergeler sağlanmaktadır.
ms.openlocfilehash: 22df77f23d1c02caac222e71ffd3ef7e86a771c4
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68178767"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Çin kullanıcıları için Microsoft 365 genel kiracı performansı iyileştirmesi

> [!IMPORTANT]
> Bu kılavuz, **Çin'de bulunan kurumsal Microsoft 365 kullanıcılarının** genel bir **Microsoft 365 kiracısına** bağlandığı kullanım senaryolarına özgüdür. Bu kılavuz, 21Vianet tarafından sağlanan Office 365 kiracılar için geçerli **değildir**.

>[!NOTE]
>Bu makale, uzak kullanıcılar için Microsoft 365 iyileştirmesini ele alan bir makale kümesinin parçasıdır.

>- Uzak kullanıcılar için Microsoft 365 bağlantısını iyileştirmek üzere VPN bölünmüş tünel kullanmaya genel bakış için bkz [. Genel Bakış: Microsoft 365 için VPN bölünmüş tünel oluşturma](microsoft-365-vpn-split-tunnel.md).
>- VPN bölünmüş tüneli uygulama hakkında ayrıntılı yönergeler için bkz. [Microsoft 365 için VPN bölünmüş tüneli uygulama](microsoft-365-vpn-implement-split-tunnel.md).
>- VPN bölünmüş tünel senaryolarının ayrıntılı listesi için bkz. [Microsoft 365 için yaygın VPN bölünmüş tünel senaryoları](microsoft-365-vpn-common-scenarios.md).
>- VPN bölünmüş tünel ortamlarında Teams medya trafiğinin güvenliğini sağlama yönergeleri için bkz. [VPN bölünmüş tüneli için Teams medya trafiğinin güvenliğini sağlama](microsoft-365-vpn-securing-teams.md).
>- VPN ortamlarında Stream ve canlı etkinlikleri yapılandırma hakkında bilgi için bkz. [VPN ortamlarında Akış ve canlı etkinlikler için dikkat edilmesi gereken özel noktalar](microsoft-365-vpn-stream-and-live-events.md).

Küresel Microsoft 365 kiracıları ve Çin'de şirket varlığı olan kuruluşlar için, Çin tabanlı kullanıcılar için Microsoft 365 istemci performansı Çin Telco'nun İnternet mimarisine özgü faktörlerle karmaşık olabilir.

Çin ISS'leri, yüksek sınır ötesi ağ tıkanıklığı düzeyine eğilimli çevre cihazlarından geçen küresel genel İnternet'e yönelik offshore bağlantıları düzenlemektedir. Bu tıkanıklık, Çin'e giren ve giden tüm İnternet trafiği için paket kaybı ve gecikme süresi oluşturur.

![Microsoft 365 trafiği - iyileştirilmemiş.](../media/O365-networking/China-O365-unoptimized.png)

Paket kaybı ve gecikme süresi ağ hizmetlerinin performansına, özellikle de büyük veri alışverişleri gerektiren (büyük dosya aktarımları gibi) veya gerçek zamanlıya yakın performans gerektiren hizmetlere (ses ve video uygulamaları) zarar verir.

Bu konunun amacı, Çin sınır ötesi ağ tıkanıklığının Microsoft 365 hizmetleri üzerindeki etkisini azaltmak için en iyi yöntemleri sağlamaktır. Bu konu, Çin taşıyıcıları içindeki karmaşık yönlendirme nedeniyle yüksek paket gecikme süresi sorunları gibi diğer yaygın son kilometre performans sorunlarını ele almaz.

## <a name="corporate-network-best-practices"></a>Kurumsal ağ en iyi yöntemleri

Çin'de küresel Microsoft 365 kiracıları ve kullanıcıları olan birçok kuruluş, Çin ofis konumları ile dünyanın dört bir yanındaki offshore konumları arasında kurumsal ağ trafiği taşıyan özel ağlar uygulamış. Bu kuruluşlar sınır ötesi ağ tıkanıklığını önlemek ve Çin'deki Microsoft 365 hizmet performansını iyileştirmek için bu ağ altyapısından yararlanabilir.

> [!IMPORTANT]
> Tüm özel WAN uygulamalarında olduğu gibi, ağ yapılandırmanızın uyumlu olduğundan emin olmak için ülkeniz ve/veya bölgeniz için her zaman yasal gereksinimlere başvurmanız gerekir.

İlk adım olarak, [Microsoft 365 için ağ planlama ve performans ayarlama](./network-planning-and-performance.md) makalesinde kıyaslama ağı kılavuzumuzu izlemeniz çok önemlidir. Birincil hedef, mümkünse Çin'de İnternet'ten küresel Microsoft 365 hizmetlerine erişmekten kaçınmak olmalıdır.

- Microsoft 365 ağ trafiğini Çin ofis ağları ile Çin dışında genel İnternet'e çıkan offshore konumlar arasında taşımak için mevcut özel ağınızdan yararlanın. Çin dışındaki neredeyse tüm konumlar net bir fayda sağlayacaktır. Ağ yöneticileri [, Microsoft genel ağıyla](/azure/networking/microsoft-global-network) düşük gecikme süreli bağlantı olan alanlarda çıkış yaparak daha da iyileştirebilir. Hong Kong, Singapur, Japonya ve Güney Kore örnek olarak verilebilir.
- Microsoft 365 trafiğinin şirket ağının özel offshore bağlantısını geçirmesine izin vermek için kullanıcı cihazlarını bir VPN bağlantısı üzerinden şirket ağına erişecek şekilde yapılandırın. VPN istemcilerinin bölünmüş tünel kullanacak şekilde yapılandırılmadığından veya kullanıcı cihazlarının Microsoft 365 trafiği için bölünmüş tüneli yoksayacak şekilde yapılandırıldığından emin olun. Teams ve gerçek zamanlı medya trafiği için VPN bağlantısını iyileştirme hakkında ek bilgi için [bu bölüme](#optimizing-microsoft-teams-meetings-network-performance-for-users-in-china) bakın.
- Ağınızı, tüm Microsoft 365 trafiğini özel offshore bağlantınız üzerinden yönlendirecek şekilde yapılandırın. Özel bağlantınızdaki trafik hacmini en aza indirmeniz gerekiyorsa, yalnızca **İyileştir** kategorisindeki uç noktaları yönlendirmeyi ve **İzin Ver** ve **Varsayılan** uç noktalara yönelik isteklerin İnternet'i aktarmasına izin vermeyi seçebilirsiniz. Bu, iyileştirilmiş trafiği yüksek gecikme süresi ve paket kaybına en duyarlı kritik hizmetlerle sınırlayarak performansı artırır ve bant genişliği tüketimini en aza indirir.
- Mümkünse Teams gibi canlı medya akış trafiği için TCP yerine UDP kullanın. UDP, TCP'den daha iyi canlı medya akışı performansı sunar.

Microsoft 365 trafiğini seçmeli olarak yönlendirme hakkında bilgi için bkz. [Office 365 uç noktalarını yönetme](managing-office-365-endpoints.md). Dünya çapındaki tüm Office 365 URL'lerinin ve IP adreslerinin listesi için bkz. [OFFICE 365 URL'ler ve IP adresi aralıkları](urls-and-ip-address-ranges.md).

![Microsoft 365 trafiği - iyileştirilmiş.](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>Kullanıcı için en iyi yöntemler

Çin'deki ev, kafe, otel ve şube ofisleri gibi uzak konumlardan kurumsal ağlara bağlantısı olmayan küresel Microsoft 365 kiracılarına bağlanan kullanıcılar, cihazlarıyla Microsoft 365 arasındaki trafiğin Çin'in yoğun sınır ötesi ağ devrelerini aktarması gerektiğinden düşük ağ performansıyla karşılaşabilir.

Sınır ötesi özel ağlar ve/veya şirket ağına VPN erişimi bir seçenek değilse, Çin merkezli kullanıcılarınızı bu en iyi yöntemleri izlemeleri için eğiterek kullanıcı başına performans sorunları yine de giderilebilir.

- Önbelleğe almayı destekleyen zengin Office istemcilerini (örneğin Outlook, Teams, OneDrive vb.) kullanın ve web tabanlı istemcilerden kaçının. Office istemcisini önbelleğe alma ve çevrimdışı erişim özellikleri, ağ tıkanıklığı ve gecikme süresinin etkisini önemli ölçüde azaltabilir.
- Microsoft 365 kiracınız _Sesli Konferans_ özelliğiyle yapılandırılmışsa, Teams kullanıcıları genel anahtarlı telefon ağı (PSTN) aracılığıyla toplantılara katılabilir. Daha fazla bilgi için bkz. [Office 365'de Sesli Konferans](/microsoftteams/audio-conferencing-in-office-365).
- Kullanıcılar ağ performansı sorunlarıyla karşılaşırsa sorun giderme için BT departmanlarına bildirmeli ve Microsoft 365 hizmetlerinde sorun olduğundan şüpheleniliyorsa Microsoft desteğine yükseltmelidir. Tüm sorunlar sınır ötesi ağ performansı nedeniyle kaynaklanmaz.

## <a name="optimizing-microsoft-teams-meetings-network-performance-for-users-in-china"></a>Çin'deki kullanıcılar için Microsoft Teams toplantıları ağ performansını iyileştirme

Küresel Microsoft 365 kiracısı olan ve Çin'de bulunan kuruluşlar için, Çin tabanlı kullanıcılar için Microsoft 365 istemci performansı, Çin İnternet mimarisine özgü faktörlerle karmaşık olabilir. Birçok şirket ve okul bu kılavuzu izleyerek iyi sonuçlar bildirdi. Ancak kapsam, BT ağ kurulumunun denetimi altında olan kullanıcı ağ konumlarıyla sınırlıdır; örneğin, ofis konumları veya VPN bağlantısı olan ev/mobil uç noktalar. Microsoft Teams çağrıları ve toplantıları genellikle ev ofisleri, mobil konumlar, yol ve kafe gibi dış konumlardan kullanılır. Aramalar ve toplantılar gerçek zamanlı medya trafiğine dayandığından, bu Teams deneyimleri ağ tıkanıklığı konusunda özellikle hassastır.

Sonuç olarak Microsoft, Teams'i taşımak için telekomünikasyon sağlayıcılarıyla işbirliği yaptı ve Çin'deki yerel ve genel İnternet bağlantıları ile Microsoft 365 küresel bulutundaki Teams ve Skype hizmetleri arasında daha yüksek kaliteli, tercihli bir ağ yolu kullanarak Çevrimiçi gerçek zamanlı medya trafiğini Skype Kurumsal. Bu özellik, paket kaybında on kat daha fazla iyileştirmeye ve kullanıcınızın deneyimini etkileyen diğer önemli ölçümlere neden olmuştur.

>[!IMPORTANT]
>Şu anda bu iyileştirmeler, Teams veya Microsoft Stream kullanarak büyük yayın veya "belediye binası" tarzı toplantılar gibi Microsoft Live Events toplantılarına katılmayı ele almamakta. Bu deneyim, yapımcı veya sunucu için normal bir Teams toplantısı olarak davrandığından, ağ geliştirmeleri canlı etkinlikler toplantısı sunan veya oluşturan kullanıcılara fayda sağlar.

### <a name="organization-network-best-practices-for-teams-meetings"></a>Teams toplantıları için kuruluş ağı en iyi yöntemleri

Sınır ötesi ağ tıkanıklığını önlemek için özel bir ağ uzantısını göz önünde bulundurmak için önceki kılavuzda bu ağ geliştirmelerinden nasıl yararlanabileceğinizi göz önünde bulundurmanız gerekir. Kuruluş ofisi ağları için iki genel seçenek vardır:

1. Yeni bir şey yapma. Sınır ötesi tıkanıklığı önlemek için özel ağ atlama ile ilgili önceki yönergeleri izlemeye devam edin. Teams gerçek zamanlı medya trafiği, daha önce olduğu gibi bu kurulumdan yararlanacaktır.
2. Bölünmüş/karma desen uygulayın.
   - Teams toplantıları ve gerçek zamanlı medya trafiğini çağırma dışında iyileştirme için bayrak eklenmiş tüm trafik için önceki kılavuzu kullanın.
   - Teams toplantısını yönlendirin ve genel İnternet üzerinden gerçek zamanlı medya trafiğini çağırın. Gerçek zamanlı medya ağ trafiğini tanımlamayla ilgili ayrıntılar için aşağıdaki bilgilere bakın.

Teams'in yüksek kaliteli bağlantıyı kullanan genel İnternet üzerinden gerçek zamanlı medya ses ve video trafiği göndermesi, trafiği özel bir ağ üzerinden göndermek için ücretsiz ve ödemeli olduğundan önemli ölçüde maliyet tasarrufuna neden olabilir. Kullanıcılar da SDWAN veya VPN istemcileri kullanıyorsa benzer ek avantajlar olabilir. Bazı kuruluşlar, genel bir uygulama olarak verilerinin daha fazla genel İnternet bağlantısından geçişini tercih edebilir.

Aynı seçenekler SDWAN veya VPN yapılandırmaları için de geçerli olabilir. Örneğin, bir kullanıcı Microsoft 365 trafiğini kurumsal ağa yönlendirmek için SDWAN veya VPN kullanıyor ve ardından sınır ötesi tıkanıklığı önlemek için bu ağın özel uzantısından yararlanılıyor. Kullanıcının SDWAN'ı veya VPN'i artık Teams toplantısını ve gerçek zamanlı trafiği VPN yönlendirmesinin dışında bırakacak şekilde yapılandırılabilir. Bu VPN yapılandırmasına bölünmüş tünel adı verilmektedir. Daha fazla bilgi için bkz. [vpn split tunneling for Office 365](/microsoft-365/enterprise/microsoft-365-vpn-implement-split-tunnel).

Ayrıca SDWAN'ınızı veya VPN'inizi Microsoft Teams gerçek zamanlı trafik de dahil olmak üzere tüm Microsoft 365 trafiği için kullanmaya devam edebilirsiniz. Microsoft'un SDWAN veya VPN çözümleri kullanımıyla ilgili bir önerisi yoktur.

### <a name="home-mobile-and-user-network-best-practices-for-teams-meetings"></a>Teams toplantıları için ev, mobil ve kullanıcı ağı için en iyi yöntemler

Çin'deki kullanıcılar bu iyileştirmelerden yalnızca Çin'deki genel internet hizmetine sabit hat veya mobil bağlantıyla bağlanarak yararlanabilir. Teams genel internet üzerindeki gerçek zamanlı medya ses ve video trafiği, gelişmiş bağlantı ve kaliteden doğrudan yararlanır.

Ancak, diğer Microsoft 365 hizmetlerinin ve sohbet veya dosyalar gibi Teams'deki diğer trafiğin verileri bu geliştirmelerden doğrudan yararlanmaz. Kuruluş ağı dışındaki kullanıcılar bu trafik için düşük ağ performansıyla karşılaşmaya devam edebilir. Bu makalede açıklandığı gibi, VPN veya SDWAN kullanarak bu etkileri azaltabilirsiniz. Kullanıcılarınızın ağ sorunlarını azaltmak için uygulama içi önbelleğe almayı destekleyen web istemcileri üzerinden zengin masaüstü istemcileri kullanmasını da sağlayabilirsiniz.

### <a name="identifying-teams-real-time-media-network-traffic"></a>Teams gerçek zamanlı medya ağ trafiğini belirleme

Bir ağ cihazı veya VPN/SDWAN kurulumu yapılandırmak için yalnızca Teams gerçek zamanlı medya ses ve video trafiğini dışlamanız gerekir. 11. kimlik için trafik ayrıntıları, [resmi Office 365 URL'leri ve IP adresi aralıkları](urls-and-ip-address-ranges.md#skype-for-business-online-and-microsoft-teams) listesinde bulunabilir. Diğer tüm ağ yapılandırmaları olduğu gibi kalmalıdır.

Microsoft, Microsoft 365 kullanıcı deneyimini ve istemcilerin performansını mümkün olan en geniş ağ mimarisi ve özellikleri üzerinde geliştirmek için sürekli çalışmaktadır. [Office 365 Networking Tech Community'yi ziyaret ederek](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking) bir konuşmayı başlatın veya bir konuşmaya katılın, kaynakları bulun ve özellik istekleri ve önerileri gönderin

## <a name="related-articles"></a>İlgili makaleler

[Genel bakış: Microsoft 365 için VPN bölünmüş tüneli](microsoft-365-vpn-split-tunnel.md)

[Microsoft 365 için VPN bölünmüş tüneli uygulama](microsoft-365-vpn-implement-split-tunnel.md)

[Microsoft 365 için yaygın VPN bölünmüş tünel senaryoları](microsoft-365-vpn-common-scenarios.md)

[VPN bölünmüş tüneli için Teams medya trafiğinin güvenliğini sağlama](microsoft-365-vpn-securing-teams.md)

[VPN ortamlarında Akış ve canlı etkinlikler için özel dikkat edilmesi gerekenler](microsoft-365-vpn-stream-and-live-events.md)

[Microsoft 365 Ağ Bağlantı İlkeleri](microsoft-365-network-connectivity-principles.md)

[Microsoft 365 ağ bağlantısını değerlendirme](assessing-network-connectivity.md)

[Microsoft 365 ağ ve performans ayarlama](network-planning-and-performance.md)

[Günümüzün benzersiz uzaktan çalışma senaryolarında modern güvenlik denetimleri elde etmek için güvenlik uzmanları ve BT için alternatif yollar (Microsoft Güvenlik Ekibi blogu)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Microsoft'ta VPN performansını geliştirme: otomatik bağlantılara izin vermek için Windows 10 VPN profillerini kullanma](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[VPN üzerinde çalıştırma: Microsoft uzak iş gücünü nasıl bağlı tutuyor?](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Microsoft küresel ağı](/azure/networking/microsoft-global-network)
