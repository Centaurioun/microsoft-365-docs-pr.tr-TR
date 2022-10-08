---
title: Microsoft 365 için ağ yol haritası
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 03/03/2022
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 ağını planlama, uygulama ve yönetme yol haritası.
ms.openlocfilehash: 868ec406522f9bd35e0087089d8fb8ce6b5c3e26
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68185281"
---
# <a name="networking-roadmap-for-microsoft-365"></a>Microsoft 365 için ağ yol haritası

Kuruluşlar için Microsoft 365 işbirliği ve üretkenlik bulut hizmetlerini, Microsoft Intune ve Microsoft Azure'ın birçok kimlik ve güvenlik hizmetini içerir. Bu bulut tabanlı hizmetlerin tümü, İnternet veya ayrılmış devreler üzerinden istemci cihazlardan gelen bağlantıların güvenliğine, performansına ve güvenilirliğine dayanır. Microsoft, bu hizmetleri barındırmak ve tüm dünyadaki müşterilerin kullanımına sunmak için performans ve tümleştirmeyi vurgulayan bir ağ altyapısı tasarlamıştır.

Microsoft 365 ekleme işleminin önemli bir parçası, ağ ve İnternet bağlantılarınızın iyileştirilmiş erişim için ayarlandığından emin olmaktır. Şirket içi ağınızı genel olarak dağıtılmış bir Hizmet Olarak Yazılım (SaaS) buluta erişecek şekilde yapılandırmak, şirket içi veri merkezlerine giden trafik ve merkezi İnternet bağlantısı için iyileştirilmiş geleneksel bir ağdan farklıdır.

Temel farklılıkları anlamak ve şirket içi kullanıcılarınız için en iyi performansı elde etmek üzere uç cihazlarınızı, istemci bilgisayarlarınızı ve şirket içi ağınızı değiştirmek için bu makaleleri kullanın.

## <a name="plan"></a>Plan

Ağ uygulamanızın planlama aşamasında:

- [Microsoft 365 ağlarının nasıl çalıştığını anlama](microsoft-365-networking-overview.md)
- [Ağ bağlantısı ilkeleri hakkında bilgi edinin](microsoft-365-network-connectivity-principles.md)
- [Geçerli ağ bağlantınızı değerlendirme](assessing-network-connectivity.md)
- [ExpressRoute'un kuruluşunuz için uygun olup olmadığını belirleme](network-planning-with-expressroute.md)
- [Ağ cihazlarınız için planlama](plan-for-network-devices.md)
- [Geçiş için ağınızı ayarlama](network-and-migration-planning.md)

## <a name="deploy"></a>Dağıtım

Ağ uygulamanızın dağıtım aşamasında:

- [Kurumsal ağınızın Microsoft 365 bağlantısı için iyileştirildiğinden emin olun](set-up-network-for-microsoft-365.md)
- [Kuruluşunuz için DNS etki alanlarını ekleme](../admin/setup/add-domain.md)
- [VPN bölünmüş tüneli kullanarak uzak çalışanlar için bağlantıyı iyileştirme](microsoft-365-vpn-split-tunnel.md)
- [Ağ performansını geliştirmek için CDN'yi yapılandırma](office-365-cdn-quickstart.md)
- [Microsoft 365 uç noktalarına bağlantınızı iyileştirme](microsoft-365-ip-web-service.md)
- Gerekirse [ExpressRoute'u yapılandırın](azure-expressroute.md)

## <a name="manage"></a>Yönetme

Ağ uygulamanızın yönetim aşamasında:

- [Microsoft 365 ağ bağlantısı test aracını kullanarak test etme ve iyileştirme](office-365-network-mac-perf-onboarding-tool.md)
- [Ağ cihazlarınızın en son Office 365 uç noktalarını kullandığından emin olun](microsoft-365-endpoints.md)
- [Ağ performansınızı izleme ve ayarlama](network-planning-and-performance.md)
- [Microsoft 365 bağlantınızı izleme](monitor-connectivity.md)

## <a name="network-equipment-vendors"></a>Ağ ekipmanı satıcıları

Ağ ekipmanı satıcısıysanız [Microsoft 365 Ağ İş Ortağı Programı](microsoft-365-networking-partner-program.md) katılın. Ürünlerinize ve çözümlerinize Microsoft 365 ağ bağlantısı ilkeleri oluşturmak için programa kaydolın.

## <a name="how-contoso-did-networking-for-microsoft-365"></a>Contoso Microsoft 365 için ağ iletişimi nasıl yaptı?

Kurgusal ama temsili çok uluslu bir işletme olan Contoso Corporation'ın microsoft 365 bulut hizmetleri için [ağ cihazlarını ve İnternet bağlantılarını nasıl iyileştirdiğini](contoso-networking.md) görün.

![The Contoso Corporation.](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Sonraki adım

[Microsoft 365 ağ bağlantısına genel bakış ile ağ](microsoft-365-networking-overview.md) planlamanızı başlatın.
