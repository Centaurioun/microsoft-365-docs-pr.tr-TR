---
title: Microsoft 365 için yaygın VPN bölünmüş tünel senaryoları
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
- scotvorg
- Ent_O365
- Strat_O365_Enterprise
- remotework
f1.keywords:
- NOCSH
description: Microsoft 365 için yaygın VPN bölünmüş tünel senaryoları
ms.openlocfilehash: 7da7679a92c87a90a174ce05bd7e5db5458507af
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68195775"
---
# <a name="common-vpn-split-tunneling-scenarios-for-microsoft-365"></a>Microsoft 365 için yaygın VPN bölünmüş tünel senaryoları

>[!NOTE]
>Bu makale, uzak kullanıcılar için Microsoft 365 iyileştirmesini ele alan bir makale kümesinin parçasıdır.

>- Uzak kullanıcılar için Microsoft 365 bağlantısını iyileştirmek üzere VPN bölünmüş tünel kullanmaya genel bakış için bkz [. Genel Bakış: Microsoft 365 için VPN bölünmüş tünel oluşturma](microsoft-365-vpn-split-tunnel.md).
>- VPN bölünmüş tüneli uygulama hakkında ayrıntılı yönergeler için bkz. [Microsoft 365 için VPN bölünmüş tüneli uygulama](microsoft-365-vpn-implement-split-tunnel.md).
>- VPN bölünmüş tünel ortamlarında Teams medya trafiğinin güvenliğini sağlama yönergeleri için bkz. [VPN bölünmüş tüneli için Teams medya trafiğinin güvenliğini sağlama](microsoft-365-vpn-securing-teams.md).
>- VPN ortamlarında Stream ve canlı etkinlikleri yapılandırma hakkında bilgi için bkz. [VPN ortamlarında Akış ve canlı etkinlikler için dikkat edilmesi gereken özel noktalar](microsoft-365-vpn-stream-and-live-events.md).
>- Çin'deki kullanıcılar için Microsoft 365 dünya çapında kiracı performansını iyileştirme hakkında bilgi için bkz. [Çin kullanıcıları için Microsoft 365 performans iyileştirmesi](microsoft-365-networking-china.md).

Aşağıdaki listede, kurumsal ortamlarda görülen en yaygın VPN senaryolarını göreceksiniz. Müşterilerin çoğu geleneksel olarak model 1 'i (VPN Zorlamalı Tünel) çalıştırır. Bu bölüm, nispeten az çabayla ulaşılabilir olan ve ağ performansı ve kullanıcı deneyimi açısından muazzam avantajlara sahip olan **model 2'ye** hızlı ve güvenli bir şekilde geçiş gerçekleştirmenize yardımcı olur.

| Modeli | Açıklama |
| --- | --- |
| [1. VPN Zorlamalı Tüneli](#1-vpn-forced-tunnel) | Trafiğin %100'ü şirket içi, İnternet ve tüm O365/M365 dahil olmak üzere VPN tüneline gider |
| [2. Birkaç özel durumla VPN Zorlamalı Tüneli](#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions) | VPN tüneli varsayılan olarak kullanılır (VPN'ye giden varsayılan yol noktaları), doğrudan gitmelerine izin verilen birkaç, en önemli muafiyet senaryoları |
| [3. Geniş özel durumlarla VPN Zorlamalı Tüneli](#3-vpn-forced-tunnel-with-broad-exceptions) | VPN tüneli varsayılan olarak kullanılır (VPN'ye giden varsayılan yol noktaları), doğrudan gitmesine izin verilen geniş özel durumlar (tüm Microsoft 365, Tüm Salesforce, Tüm Yakınlaştırma gibi) |
| [4. VPN Seçmeli Tüneli](#4-vpn-selective-tunnel) | VPN tüneli yalnızca corpnet tabanlı hizmetler için kullanılır. Varsayılan yol (İnternet ve tüm İnternet tabanlı hizmetler) doğrudan gider. |
| [5. VPN yok](#5-no-vpn) | #2'nin bir varyasyonu. Eski VPN yerine tüm corpnet hizmetleri modern güvenlik yaklaşımları (Zscaler ZPA, Azure Active Directory (Azure AD) Proxy/MCAS vb.) aracılığıyla yayımlanır. |

## <a name="1-vpn-forced-tunnel"></a>1. VPN Zorlamalı Tüneli

Çoğu kurumsal müşteri için en yaygın başlangıç senaryosu. Zorlamalı VPN kullanılır; bu da uç noktanın şirket ağı içinde bulunup bulunmadığına bakılmaksızın trafiğin %100'ünün şirket ağına yönlendirildiği anlamına gelir. Microsoft 365 veya İnternet'e göz atma gibi tüm dış (İnternet) bağlı trafik, ara sunucular gibi şirket içi güvenlik ekipmanlarının dışına geri sabitlenir. Kullanıcıların neredeyse %100'ünün uzaktan çalıştığı mevcut iklimde, bu model VPN altyapısına yüksek yük getirir ve tüm kurumsal trafiğin performansını önemli ölçüde engeller ve bu nedenle kuruluşun kriz zamanında verimli bir şekilde çalışmasını engeller.

![VPN Zorlamalı Tünel modeli 1.](../media/vpn-split-tunneling/vpn-model-1.png)

## <a name="2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions"></a>2. Az sayıda güvenilen özel durumla VPN Zorlamalı Tüneli

Bir kuruluşun altında çalışması için önemli ölçüde daha verimlidir. Bu model, yüksek yük ve gecikme süresine duyarlı olan birkaç denetimli ve tanımlı uç noktanın VPN tünelini atlamasına ve doğrudan Microsoft 365 hizmetine gitmesine olanak tanır. Bu, boşaltılan hizmetlerin performansını önemli ölçüde artırır ve AYRıCA VPN altyapısı üzerindeki yükü azaltır, böylece kaynaklar için daha düşük çekişme ile çalışmasını gerektiren öğelerin çalışmasına izin verir. Bu makalenin, çok sayıda olumlu sonuçla hızlı bir şekilde basit, tanımlı eylemlerin gerçekleştirilmesini sağladığından geçişe yardımcı olmaya odaklandığı bu modeldir.

![Bölünmüş Tünel VPN modeli 2.](../media/vpn-split-tunneling/vpn-model-2.png)

## <a name="3-vpn-forced-tunnel-with-broad-exceptions"></a>3. Geniş özel durumlarla VPN Zorlamalı Tüneli

Model 2'nin kapsamını genişleter. Yalnızca küçük bir grup tanımlı uç noktayı doğrudan göndermek yerine, tüm trafiği doğrudan Microsoft 365 ve SalesForce gibi güvenilir hizmetlere gönderir. Bu, kurumsal VPN altyapısı üzerindeki yükü daha da azaltır ve tanımlanan hizmetlerin performansını artırır. Bu modelin uygulanabilirliğini değerlendirmek ve uygulamak daha uzun süreceğinden, model iki başarıyla uygulandıktan sonra daha sonraki bir tarihte yinelemeli olarak izleyebileceğiniz bir adımdır.

![Bölünmüş Tünel VPN modeli 3.](../media/vpn-split-tunneling/vpn-model-3.png)

## <a name="4-vpn-selective-tunnel"></a>4. VPN seçmeli Tüneli

Vpn tüneline yalnızca kurumsal IP adresine sahip olduğu belirlenen trafiğin gönderileceği üçüncü modeli tersine çevirir ve bu nedenle İnternet yolu diğer her şey için varsayılan yoldur. Bu model, bir kuruluşun bu modeli güvenli bir şekilde uygulayabilmesi için [Sıfır Güven](https://www.microsoft.com/security/zero-trust?rtc=1) yolunda iyi olmasını gerektirir. Bu modelin veya bazı varyasyonların, şirket ağından ve buluta daha fazla hizmet taşındığında büyük olasılıkla zaman içinde gerekli varsayılan değer haline geleceği belirtilmelidir.

Microsoft bu modeli dahili olarak kullanır. Microsoft'un VPN bölünmüş tünel uygulaması hakkında daha fazla bilgi için bkz [. Vpn üzerinde çalıştırma: Microsoft uzak iş gücünü nasıl bağlı tutuyor](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)?

![Bölünmüş Tünel VPN modeli 4.](../media/vpn-split-tunneling/vpn-model-4.png)

## <a name="5-no-vpn"></a>5. VPN yok

2 numaralı modelin daha gelişmiş bir sürümüdür, böylece tüm iç hizmetler modern bir güvenlik yaklaşımı veya Azure AD Proxy, Bulut Uygulamaları için Defender, Zscaler ZPA gibi SDWAN çözümü aracılığıyla yayımlanır.

![Bölünmüş Tünel VPN modeli 5.](../media/vpn-split-tunneling/vpn-model-5.png)

## <a name="related-articles"></a>İlgili makaleler

[Genel bakış: Microsoft 365 için VPN bölünmüş tüneli](microsoft-365-vpn-split-tunnel.md)

[Microsoft 365 için VPN bölünmüş tüneli uygulama](microsoft-365-vpn-implement-split-tunnel.md)

[VPN bölünmüş tüneli için Teams medya trafiğinin güvenliğini sağlama](microsoft-365-vpn-securing-teams.md)

[VPN ortamlarında Akış ve canlı etkinlikler için özel dikkat edilmesi gerekenler](microsoft-365-vpn-stream-and-live-events.md)

[Çin kullanıcıları için Microsoft 365 performans iyileştirmesi](microsoft-365-networking-china.md)

[Microsoft 365 Ağ Bağlantı İlkeleri](microsoft-365-network-connectivity-principles.md)

[Microsoft 365 ağ bağlantısını değerlendirme](assessing-network-connectivity.md)

[Microsoft 365 ağ ve performans ayarlama](network-planning-and-performance.md)

[Günümüzün benzersiz uzaktan çalışma senaryolarında modern güvenlik denetimleri elde etmek için güvenlik uzmanları ve BT için alternatif yollar (Microsoft Güvenlik Ekibi blogu)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Microsoft'ta VPN performansını geliştirme: otomatik bağlantılara izin vermek için Windows 10 VPN profillerini kullanma](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[VPN üzerinde çalıştırma: Microsoft uzak iş gücünü nasıl bağlı tutuyor?](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Microsoft küresel ağı](/azure/networking/microsoft-global-network)
