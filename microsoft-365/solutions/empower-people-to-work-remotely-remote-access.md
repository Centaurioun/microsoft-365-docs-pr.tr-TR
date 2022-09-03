---
title: Adım 2. Şirket içi uygulama ve hizmetlere uzaktan erişim sağlama
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Microsoft 365 bulut hizmetlerine erişimi iyileştirirken uzak çalışanlarınızın şirket içi kaynaklara erişebildiğinden emin olun.
ms.openlocfilehash: 2c159bd375a6944f47f2f9bde853348f7866e5bb
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67577926"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a>Adım 2. Şirket içi uygulama ve hizmetlere uzaktan erişim sağlama

Kuruluşunuz, genellikle ağınızın kenarında VPN sunucuları ve kullanıcılarınızın cihazlarında yüklü VPN istemcileri olan bir uzaktan erişim VPN çözümü kullanıyorsa, kullanıcılarınız şirket içi uygulamalara ve sunuculara erişmek için uzaktan erişim VPN bağlantılarını kullanabilir. Ancak Microsoft 365 bulut tabanlı hizmetlere yönelik trafiği iyileştirmeniz gerekebilir.

Kullanıcılarınız VPN çözümü kullanmıyorsa, tüm uygulamalarınızın web tabanlı olup olmadığına bağlı olarak erişim sağlamak için Azure Active Directory (Azure AD) Uygulama Ara Sunucusu ve Azure Noktadan Siteye (P2S) VPN kullanabilirsiniz.

Uzaktan erişim için birincil yapılandırmalar şunlardır:

- Zaten bir uzaktan erişim VPN çözümü kullanıyorsunuz.
- Uzaktan erişim VPN çözümü kullanmıyor ve uzak çalışanlarınızın kişisel bilgisayarlarını kullanmasını istiyorsunuz.
- Uzaktan erişim VPN çözümü kullanmıyorsanız, karma kimliğiniz var ve yalnızca şirket içi web tabanlı uygulamalara uzaktan erişime ihtiyacınız var.
- Uzaktan erişim VPN çözümü kullanmıyorsanız ve bazıları web tabanlı olmayan şirket içi uygulamalara erişmeniz gerekir.

Bu makalede ele alınan uzaktan erişim yapılandırma seçenekleri için bu akış çizelgesine bakın.

:::image type="content" source="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-flowchart.png" alt-text="Uzaktan erişim yapılandırma akış çizelgesi." lightbox="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-flowchart.png":::

Uzaktan erişim bağlantılarıyla, kullanıcılarınızı şirket içi bilgisayara bağlamak için [Uzak Masaüstü'nü](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) de kullanabilirsiniz. Örneğin, uzak çalışan, Windows, iOS veya Android cihazından ofisindeki bilgisayara bağlanmak için Uzak Masaüstü'nü kullanabilir. Uzaktan bağlandıktan sonra, önünde oturuyormuş gibi kullanabilirler.

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a>Microsoft 365 bulut hizmetlerine uzaktan erişim VPN istemcileri için performansı iyileştirme

Uzak çalışanlarınız kuruluş ağınıza uzaktan erişim elde etmek için geleneksel bir VPN istemcisi kullanıyorsa, VPN istemcisinin bölünmüş tünel desteğine sahip olduğunu doğrulayın.

Bölünmüş tünel olmadan, tüm uzaktan çalışma trafiğiniz VPN bağlantısı üzerinden gönderilir; burada kuruluşunuzun uç cihazlarına iletilmesi, işlenmesi ve ardından İnternet'e gönderilmesi gerekir.

:::image type="content" source="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png" alt-text="Tünel oluşturmadan VPN istemcilerinden gelen ağ trafiği." lightbox="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png":::

Microsoft 365 trafiğinin kuruluşunuz üzerinden dolaylı bir yol alması gerekir. Bu, VPN istemcisinin fiziksel konumundan uzak bir Microsoft ağ giriş noktasına iletilebilir. Bu dolaylı yol ağ trafiğine gecikme ekler ve genel performansı azaltır.

Bölünmüş tünel ile VPN istemcinizi, belirli trafik türlerinin kuruluş ağına VPN bağlantısı üzerinden gönderilmesini dışlamak üzere yapılandırabilirsiniz.

Microsoft 365 bulut kaynaklarına erişimi iyileştirmek için bölünmüş tünel VPN istemcilerinizi VPN bağlantısı üzerinden **En İyi Duruma Getir** kategorisi Microsoft 365 uç noktalarına trafiği hariç tutacak şekilde yapılandırın. Daha fazla bilgi için bkz. [uç nokta kategorilerini Office 365](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories). Kategori uç noktalarını iyileştirme [listesine](../enterprise/urls-and-ip-address-ranges.md) bakın.

Microsoft 365 bulut uygulamalarına giden trafiğin çoğunun VPN bağlantısını atladığı sonuçta elde edilen trafik akışı aşağıdadır.

:::image type="content" source="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png" alt-text="Tünel ile VPN istemcilerinden gelen ağ trafiği." lightbox="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png":::

Bu, VPN istemcisinin önemli Microsoft 365 bulut hizmeti trafiğini doğrudan İnternet üzerinden ve Microsoft ağına en yakın giriş noktasına gönderip almasını sağlar.

Daha fazla bilgi ve kılavuz için bkz[. VPN bölünmüş tünel kullanarak uzak kullanıcılar için Office 365 bağlantısını iyileştirme](../enterprise/microsoft-365-vpn-split-tunnel.md).

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a>Tüm uygulamalarınız web uygulamaları olduğunda ve karma kimliğiniz varsa uzaktan erişimi dağıtma

Uzak çalışanlarınız geleneksel bir VPN istemcisi kullanmıyorsa ve şirket içi kullanıcı hesaplarınız ve gruplarınız Azure AD ile eşitlenmişse, şirket içi sunucularda barındırılan web tabanlı uygulamalar için güvenli uzaktan erişim sağlamak için Azure AD Uygulama Ara Sunucusu kullanabilirsiniz. Web tabanlı uygulamalar SharePoint Server sitelerini, Outlook Web Access sunucularını veya diğer web tabanlı iş kolu uygulamalarını içerir.

Azure AD Uygulama Ara Sunucusu bileşenleri aşağıdadır.

:::image type="content" source="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png" alt-text="Azure AD Uygulama Ara Sunucusu bileşenleri." lightbox="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png":::

Daha fazla bilgi için bu [Azure AD Uygulama Ara Sunucusu genel bakışına](/azure/active-directory/manage-apps/application-proxy) bakın.

> [!NOTE]
> Azure AD Uygulama Ara Sunucusu bir Microsoft 365 aboneliğine dahil değildir. Ayrı bir Azure aboneliğiyle kullanım için ödemeniz gerekir.

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a>Tüm uygulamalarınız web uygulamaları olmadığında uzaktan erişimi dağıtma

Uzak çalışanlarınız geleneksel bir VPN istemcisi kullanmıyorsa ve web tabanlı olmayan uygulamalarınız varsa, Azure Noktadan Siteye (P2S) VPN kullanabilirsiniz.

P2S VPN bağlantısı, uzak çalışanın cihazından bir Azure sanal ağı üzerinden kuruluş ağınıza güvenli bir bağlantı oluşturur.

:::image type="content" source="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png" alt-text="Azure P2S VPN bileşenleri." lightbox="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png":::

Daha fazla bilgi için bkz. [P2S VPN'e genel bakış](/azure/vpn-gateway/point-to-site-about).

> [!NOTE]
> Azure P2S VPN, Microsoft 365 aboneliğine dahil değildir. Ayrı bir Azure aboneliğiyle kullanım için ödemeniz gerekir.

## <a name="deploy-windows-365-to-provide-remote-access-for-remote-workers-using-personal-devices"></a>Kişisel cihazları kullanarak uzak çalışanlar için uzaktan erişim sağlamak için Windows 365 dağıtma

Yalnızca kişisel ve yönetilmeyen cihazlarını kullanabilen uzak çalışanları desteklemek için Windows 365 kullanarak kullanıcılarınızın evden kullanması için sanal masaüstleri oluşturun ve ayırın. Şirket içi ağ bağlantısı (OPNC) ile Windows 365 Bulut bilgisayarları, kuruluşunuzun ağına bağlı bilgisayarlar gibi davranabilir.

:::image type="content" source="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-windows-365.png" alt-text="Windows 365 bileşenleri." lightbox="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-windows-365.png":::

Daha fazla bilgi için bu [Windows 365 genel bakışına](/windows-365/overview) bakın.

> [!NOTE]
> Windows 365 bir Microsoft 365 aboneliğine dahil değildir. Ayrı bir abonelikle kullanım için ödemeniz gerekir.

## <a name="protect-your-remote-desktop-services-connections-with-the-remote-desktop-services-gateway"></a>Uzak Masaüstü Hizmetleri Ağ Geçidi ile Uzak Masaüstü Hizmetleri bağlantılarınızı koruma

Çalışanların şirket içi ağınızdaki Windows tabanlı bilgisayarlara bağlanmasına izin vermek için Uzak Masaüstü Hizmetleri (RDS) kullanıyorsanız uç ağınızda bir Microsoft Uzak Masaüstü Services ağ geçidi kullanmanız gerekir. Ağ geçidi, trafiği şifrelemek için Aktarım Katmanı Güvenliği'ni (TLS) kullanır ve RDS barındıran şirket içi bilgisayarın doğrudan İnternet'e açık olmasını önler.

:::image type="content" source="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-remote-desktop.png" alt-text="Uzak Masaüstü Hizmetleri Ağ Geçidi ile Uzak Masaüstü Hizmetleri bağlantıları." lightbox="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-remote-desktop.png":::

Daha fazla bilgi için [bu makaleye](https://www.microsoft.com/security/blog/2020/04/16/security-guidance-remote-desktop-adoption/) bakın.

## <a name="admin-technical-resources-for-remote-access"></a>Uzaktan erişim için teknik kaynakları Yönetici

- [Altyapınızdaki yükü azaltmak & uzak personel için Office 365 trafiğini hızla iyileştirme](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)
- [VPN bölünmüş tünel kullanarak uzak kullanıcılar için Office 365 bağlantısını iyileştirme](../enterprise/microsoft-365-vpn-split-tunnel.md)

## <a name="results-of-step-2"></a>2. Adımın Sonuçları

Uzak çalışanlarınız için uzaktan erişim çözümü dağıtıldıktan sonra:

| Uzaktan erişim yapılandırması | Sonuç -ları |
|:-------|:-----|
| Uzaktan erişim VPN çözümü var | Uzaktan erişim VPN istemcinizi bölünmüş tünel ve Microsoft 365 uç noktalarının İyileştir kategorisi için yapılandırmışsınız. |
| Uzaktan erişim VPN çözümü yoktur ve yalnızca şirket içi web tabanlı uygulamalara uzaktan erişime ihtiyacınız vardır | Azure Uygulaması Proxy'yi yapılandırmışsınız. |
| Uzaktan erişim VPN çözümü yok ve bazıları web tabanlı olmayan şirket içi uygulamalara erişmeniz gerekiyor | Azure P2S VPN'yi yapılandırmışsınız. |
| Uzaktan çalışanlar kişisel cihazlarını evden kullanıyor | Windows 365 yapılandırmışsınız. |
| Uzak çalışanlar şirket içi sistemlere RDS bağlantıları kullanıyor | Uç ağınıza bir Uzak Masaüstü Hizmetleri ağ geçidi dağıttınız. |
|||

## <a name="next-step"></a>Sonraki adım

[![3. Adım: Microsoft 365 güvenlik ve uyumluluk hizmetlerini dağıtma.](../media/empower-people-to-work-remotely/remote-workers-step-grid-3.png)](empower-people-to-work-remotely-security-compliance.md)

Uygulamalarınızı, verilerinizi ve cihazlarınızı korumak için Microsoft 365 güvenlik ve uyumluluk hizmetlerini dağıtmak için [3. Adımla](empower-people-to-work-remotely-security-compliance.md) devam edin.
