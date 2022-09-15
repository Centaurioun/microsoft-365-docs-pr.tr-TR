---
title: VPN bölünmüş tüneli için Teams medya trafiğinin güvenliğini sağlama
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 3/3/2022
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
f1.keywords:
- NOCSH
description: VPN bölünmüş tüneli için Teams medya trafiğinin güvenliğini sağlama
ms.openlocfilehash: eb06696b35df6ddb923c6b1e9ae97abf01dccabe
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67701158"
---
# <a name="securing-teams-media-traffic-for-vpn-split-tunneling"></a>VPN bölünmüş tüneli için Teams medya trafiğinin güvenliğini sağlama

>[!NOTE]
>Bu makale, uzak kullanıcılar için Microsoft 365 iyileştirmesini ele alan bir makale kümesinin parçasıdır.

>- Uzak kullanıcılar için Microsoft 365 bağlantısını iyileştirmek üzere VPN bölünmüş tünel kullanmaya genel bakış için bkz [. Genel Bakış: Microsoft 365 için VPN bölünmüş tünel oluşturma](microsoft-365-vpn-split-tunnel.md).
>- VPN bölünmüş tüneli uygulama hakkında ayrıntılı yönergeler için bkz. [Microsoft 365 için VPN bölünmüş tüneli uygulama](microsoft-365-vpn-implement-split-tunnel.md).
>- VPN bölünmüş tünel senaryolarının ayrıntılı listesi için bkz. [Microsoft 365 için yaygın VPN bölünmüş tünel senaryoları](microsoft-365-vpn-common-scenarios.md).
>- VPN ortamlarında Stream ve canlı etkinlikleri yapılandırma hakkında bilgi için bkz. [VPN ortamlarında Akış ve canlı etkinlikler için dikkat edilmesi gereken özel noktalar](microsoft-365-vpn-stream-and-live-events.md).
>- Çin'deki kullanıcılar için Microsoft 365 dünya çapında kiracı performansını iyileştirme hakkında bilgi için bkz. [Çin kullanıcıları için Microsoft 365 performans iyileştirmesi](microsoft-365-networking-china.md).

Bazı Microsoft Teams yöneticileri, bölünmüş tünel modeli kullanarak arama akışlarının Teams'de nasıl çalıştığı ve bağlantıların güvenliğinin nasıl sağlandığı hakkında ayrıntılı bilgi gerektirebilir.

## <a name="configuration"></a>Yapılandırma

Hem çağrılar hem de toplantılar için, yönlendirme tablosunda gerekli Ip alt ağlarını iyileştirme rota tablosunda doğru şekilde yer aldığı sürece, Teams belirli bir hedef için hangi yerel arabirimin kullanması gerektiğini belirlemek için [GetBestRoute](/windows/win32/api/iphlpapi/nf-iphlpapi-getbestroute) işlevini çağırdığında, yukarıda listelenen Microsoft IP bloklarındaki Microsoft hedefleri için yerel arabirim döndürülür.

Bazı VPN istemci yazılımları, URL'ye göre yönlendirme düzenlemesine izin verir. Ancak, Teams medya trafiğinin kendisiyle ilişkilendirilmiş BIR URL'si yoktur, bu nedenle bu trafik için yönlendirme denetiminin IP alt ağları kullanılarak yapılması gerekir.

Teams istemci yapılandırmasıyla ilgili olmayan bazı senaryolarda, medya trafiği doğru rotalar olsa bile VPN tünelinden geçmeye devam eder. Bu senaryoyla karşılaşırsanız Teams IP alt ağlarının veya bağlantı noktalarının VPN kullanmasını engellemek için bir güvenlik duvarı kuralı kullanmanız yeterli olacaktır.

>[!IMPORTANT]
>Teams medya trafiğinin tüm VPN senaryolarında istenen yöntemle yönlendirildiğinden emin olmak için lütfen kullanıcıların Microsoft Teams istemci sürümü **1.3.00.13565** veya üzerini çalıştırdığından emin olun. Bu sürüm, istemcinin kullanılabilir ağ yollarını algılama şekliyle ilgili iyileştirmeler içerir.

Sinyal trafiği HTTPS üzerinden gerçekleştirilir ve medya trafiği kadar gecikme süresine duyarlı değildir ve URL/IP verilerinde **İzin Ver** olarak işaretlenir ve bu nedenle isterseniz VPN istemcisi üzerinden güvenli bir şekilde yönlendirilebilir.

>[!NOTE]
>Microsoft Edge **96 ve üzeri** , eşler arası trafik için VPN bölünmüş tünel oluşturmayı da destekler. Bu, müşterilerin örneğin Edge'de Teams web istemcileri için VPN bölünmüş tünel avantajından yararlanabileceği anlamına gelir. Edge'de çalışan web siteleri için ayarlamak isteyen müşteriler, Edge [WebRtcRespectOsRoutingTableEnabled](/deployedge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) ilkesini devre dışı bırakmanın ek adımlarını uygulayarak bunu gerçekleştirebilir.

### <a name="security"></a>Güvenlik

Bölünmüş tünellerden kaçınmanın yaygın bağımsız değişkenlerinden biri, bunun daha az güvenli olmasıdır; örneğin VPN tünelinden gitmeyen tüm trafik, VPN tüneline uygulanan şifreleme şemasından yararlanmaz ve bu nedenle daha az güvenlidir.

Bunun ana karşı bağımsız değişkeni, medya trafiğinin RTP trafiğine gizlilik, kimlik doğrulaması ve yeniden yürütme saldırısı koruması sağlayan bir Real-Time Aktarım Protokolü (RTP) profili olan Güvenli Real-Time Aktarım Protokolü ( _SRTP_) aracılığıyla şifrelendiğidir. SRTP'nin kendisi, TLS güvenli sinyal kanalı aracılığıyla değiştirilen rastgele oluşturulmuş bir oturum anahtarına dayanır. Bu [güvenlik kılavuzunda bu](/skypeforbusiness/optimizing-your-network/security-guide-for-skype-for-business-online) konu ayrıntılı olarak ele alınmıştır, ancak asıl ilgi alanı medya şifrelemesi bölümüdür.

Medya trafiği, güvenli bir rastgele sayı oluşturucu tarafından oluşturulan bir oturum anahtarı kullanan ve sinyal veren TLS kanalı kullanılarak değiştirilen SRTP kullanılarak şifrelenir. Ayrıca, Mediation Sunucusu ile iç sonraki atlama arasında her iki yönde akan medya da SRTP kullanılarak şifrelenir.

Skype Kurumsal Online, _NAT Çevresindeki Geçişleri Kullanarak Geçişler (TURN) üzerinden medya geçişlerine_ güvenli erişim için kullanıcı adı/parolalar oluşturur. Medya geçişleri, kullanıcı adını/parolayı TLS güvenli bir SIP kanalı üzerinden değiştirir. İstemciyi şirket ağına bağlamak için bir VPN tüneli kullanılsa da, hizmete ulaşmak için şirket ağından ayrıldığında trafiğin yine de SRTP biçiminde akması gerektiğini belirtmek gerekir.

Teams'in _NAT (STUN)_ amplifikasyon saldırıları için ses veya Oturum Geçişi Yardımcı Programları gibi yaygın güvenlik sorunlarını nasıl azaltacağıyla ilgili bilgiler [5.1 Uygulayıcılar için GüvenlikLe İlgili Dikkat Edilmesi Gerekenler](/openspecs/office_protocols/ms-ice2/69525351-8c68-4864-b8a6-04bfbc87785c) bölümünde bulunabilir.

Ayrıca, uzaktan çalışma senaryolarındaki modern güvenlik denetimleri hakkında bilgi edinmek [için güvenlik uzmanlarının ve BT'nin günümüzün benzersiz uzaktan çalışma senaryolarında modern güvenlik denetimlerine ulaşmanın alternatif yolları (Microsoft Güvenlik Ekibi blogu) makalesini](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) de okuyabilirsiniz.

### <a name="testing"></a>Test

İlke gerçekleştikten sonra Beklendiği gibi çalıştığını onaylamanız gerekir. Yolun yerel İnternet bağlantısını kullanacak şekilde doğru şekilde ayarlandığını test etmenin birden çok yolu vardır:

- Yukarıdaki gibi izleme yolları da dahil olmak üzere bağlantı testlerini sizin için çalıştıracak [Microsoft 365 bağlantı testini](https://aka.ms/netonboard) çalıştırın. Ayrıca ek içgörüler sağlaması gereken vpn testlerini de bu araçlara ekliyoruz.

- Bölünmüş tünel kapsamındaki bir uç noktaya yönelik basit bir **tracert** , alınan yolu göstermelidir, örneğin:

  ```powershell
  tracert worldaz.tr.teams.microsoft.com
  ```

  Ardından yerel ISS aracılığıyla bu uç noktaya giden ve bölünmüş tünel için yapılandırdığımız Teams aralıklarındaki bir IP'ye çözümlenmesi gereken bir yol görmeniz gerekir.

- Wireshark gibi bir araç kullanarak ağ yakalaması yapın. Arama sırasında UDP'ye filtre uygularsanız Teams **İyileştirme** aralığında trafiğin bir IP'ye aktığını görmeniz gerekir. Bu trafik için VPN tüneli kullanılıyorsa, medya trafiği izlemede görünmez.

## <a name="additional-support-logs"></a>Ek destek günlükleri

Sorun gidermek için daha fazla veriye ihtiyacınız varsa veya Microsoft desteğinden yardım istiyorsanız, aşağıdaki bilgileri almak çözüm bulma işlemini hızlandırmanıza olanak sağlamalıdır. Microsoft desteğinin **TSS Windows CMD tabanlı evrensel Sorun Giderme Betik araç takımı** , ilgili günlükleri basit bir şekilde toplamanıza yardımcı olabilir. Araç ve kullanım yönergeleri adresinde <https://aka.ms/TssTools>bulunabilir.

## <a name="related-articles"></a>İlgili makaleler

[Genel bakış: Microsoft 365 için VPN bölünmüş tüneli](microsoft-365-vpn-split-tunnel.md)

[Microsoft 365 için VPN bölünmüş tüneli uygulama](microsoft-365-vpn-implement-split-tunnel.md)

[Microsoft 365 için yaygın VPN bölünmüş tünel senaryoları](microsoft-365-vpn-common-scenarios.md)

[VPN ortamlarında Akış ve canlı etkinlikler için özel dikkat edilmesi gerekenler](microsoft-365-vpn-stream-and-live-events.md)

[Çin kullanıcıları için Microsoft 365 performans iyileştirmesi](microsoft-365-networking-china.md)

[Microsoft 365 Ağ Bağlantı İlkeleri](microsoft-365-network-connectivity-principles.md)

[Microsoft 365 ağ bağlantısını değerlendirme](assessing-network-connectivity.md)

[Microsoft 365 ağ ve performans ayarlama](network-planning-and-performance.md)

[Günümüzün benzersiz uzaktan çalışma senaryolarında modern güvenlik denetimleri elde etmek için güvenlik uzmanları ve BT için alternatif yollar (Microsoft Güvenlik Ekibi blogu)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Microsoft'ta VPN performansını geliştirme: otomatik bağlantılara izin vermek için Windows 10 VPN profillerini kullanma](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[VPN üzerinde çalıştırma: Microsoft uzak iş gücünü nasıl bağlı tutuyor?](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Microsoft küresel ağı](/azure/networking/microsoft-global-network)
