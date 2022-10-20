---
title: Microsoft 365 hizmetlerinde IPv6 desteği
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 06/02/2022
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c08786fb-298e-437c-8222-dab7625fc815
description: 'Özet: Microsoft 365 bileşenlerinde ve Microsoft 365 kamu tekliflerinde IPv6 desteğini açıklar.'
ms.openlocfilehash: ace89b7f49eb5535dd49119358c1936d8a6b638a
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68623974"
---
# <a name="ipv6-support-in-microsoft-365-services"></a>Microsoft 365 hizmetlerinde IPv6 desteği

Kurumsal ağlar, hizmet sağlayıcıları ve cihazlar arasında IPv6'nın giderek daha fazla benimsenmesi ve desteklenmesiyle birlikte, birçok müşteri kullanıcılarının IPv6 istemcilerinden ve IPv6 ağlarından Microsoft 365 hizmetlerine erişmeye devam edip edemediğini merak ediyor. Microsoft 365 hizmetleri hem IPv6 çift yığından hem de yalnızca IPv6 cihazlarından başarıyla kullanılabilir (Yalnızca IPv6 cihazlar için DNS64 veya NAT64 gibi çeviri teknolojileri gerekir). Aslında, tüketicilerden IPv6'nın daha iyi benimsenmesini sağlayan büyük kuruluşlara kadar artan sayıda müşterimiz var. Çoğu müşteri için, IPv4 dijital manzaralarından tamamen kaybolmaz, bu nedenle herhangi bir Microsoft 365 özelliği veya hizmeti için IPv6 gerektirmeyi veya IPv4 önceliklerini kaldırmayı planlamıyoruz.

Microsoft 365 ile ilgili temel önceliklerimizden biri, herhangi bir konumdan, herhangi bir cihazdan İnternet üzerinden sorunsuz müşteri ve kullanıcı deneyimleri sağlamaktır. Buna, çift yığın yapılandırmasında IPv6 kullanan müşteri cihazlarından Microsoft 365'e erişimin yanı sıra yalnızca IPv6 istemci dağıtımlarına geçiş dahildir. Çoğu durumda, Microsoft 365 ağ bağlantısı ilkeleri, Microsoft 365 [URL'leri ve IP adresi aralıkları ve Microsoft 365](urls-and-ip-address-ranges.md) [ağ planlama en iyi yöntemlerinde](network-and-migration-planning.md#best-practices-for-network-planning-and-improving-migration-performance-for-office-365) açıklandığı gibi [Microsoft 365'e](microsoft-365-network-connectivity-principles.md) bağlanmaya yönelik standart bir İnternet tabanlı modeli izlediğinizde, IPv6 geçişleri kullanıcı deneyiminizi kesintiye uğratmaz.

Birçok Microsoft 365 hizmeti bugün yerel IPv6 desteği sağlamaktadır ve doğrudan IPv6 çift yığın ve yalnızca IPv6 istemcilerinden erişilebilir. Microsoft 365 ayrıca müşteriler ve ağ çözümü sağlayıcıları tarafından IPv4 İnternet kaynaklarına bağlanmak için yaygın olarak kullanılan geleneksel IPv6 ile IPv4 çeviri teknolojilerine (temel 64 proxy'ler veya DNS64/NAT64 gibi) erişim sağlar.

Tüm SaaS hizmetlerinde ve genel olarak İnternet'te olduğu gibi, yerel olarak IPv6'nın kapsamı Microsoft 365 arabirimlerini, özelliklerini ve API'lerini etkinleştirerek sürekli olarak ve doğrudan müşteri eylemi veya denetimi olmadan genişler. Ağlarınızda Microsoft 365'e ve İnternet'e erişmesi gereken IPv6 veya yalnızca IPv6 hizmetleri çalıştırıyorsanız, daha fazla ağ yeniden yapılandırması olmadan Microsoft 365'e uçtan uca IPv6 bağlantısı sağlamak için DNS64/NAT64 gibi dinamik IPv6/IPv4 geçiş mekanizmaları eklemeniz önerilir.

Microsoft 365 hizmetlerinin çoğu son kullanıcılar ve BT yöneticileri için tamamen şeffaf bir şekilde IPv6 özellikleriyle etkinleştirilmiştir veya etkinleştirilecektir. Bazı Microsoft 365 senaryolarında (anonim gelen e-posta gibi) IPv6 ile birlikte kullanılmak üzere özel gereksinimler ve dikkat edilmesi gerekenler vardır. Senaryoya özgü IPv6 gereksinimleri ve dikkat edilmesi gerekenler hakkında daha fazla bilgi için lütfen Microsoft hesabı ekibinize veya Microsoft desteğine başvurun.

İşte geri dönmek için kullanabileceğiniz kısa bir bağlantı: [https://aka.ms/o365ip6](https://aka.ms/o365ip6)

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft 365 Ağ Bağlantısına Genel Bakış](microsoft-365-networking-overview.md)

[Office 365 uç noktalarını yönetme](managing-office-365-endpoints.md)

[Office 365 URL'leri ve IP adresi aralıkları](urls-and-ip-address-ranges.md)

[Office 365 IP Adresi ve URL Web hizmeti](microsoft-365-ip-web-service.md)

[Microsoft 365 ağ bağlantısını değerlendirme](assessing-network-connectivity.md)

[Microsoft 365 için ağ planlama ve performans ayarlama](network-planning-and-performance.md)

[Temelleri ve performans geçmişini kullanarak performans ayarlamayı Office 365](performance-tuning-using-baselines-and-history.md)

[Office 365 için performans sorunlarını giderme planı](performance-troubleshooting-plan.md)

[İçerik Teslim Ağları](content-delivery-networks.md)

[Microsoft 365 bağlantı testi](https://aka.ms/netonboard)

[Microsoft hızlı ve güvenilir küresel ağını nasıl oluşturur?](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Office 365 Ağ blogu](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)
