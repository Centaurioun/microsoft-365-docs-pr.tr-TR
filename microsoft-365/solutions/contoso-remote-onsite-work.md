---
title: Contoso'nun COVID-19 yanıtı ve hibrit çalışma desteği
author: dansimp
f1.keywords:
- NOCSH
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso Corporation'ın COVID-19 pandemisine nasıl yanıt verdiğini ve hibrit çalışma için yazılım yükleme ve güncelleştirme altyapısını nasıl hazırladığını anlayın.
ms.openlocfilehash: 557d9b7bbfab2ea6db65fb1e033b190436590346
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67730495"
---
# <a name="contosos-covid-19-response-and-support-for-hybrid-work"></a>Contoso'nun COVID-19 yanıtı ve hibrit çalışma desteği

Contoso, şirket içi kaynaklarına Paris'in merkezindeki merkezi bir VPN sunucusu aracılığıyla erişen uzak çalışanlarını her zaman desteklemişti. Contoso tüm uzak çalışanlara yönetilen bir dizüstü bilgisayar vermişti. Şirket içi çalışanların masaüstü bilgisayar ve dizüstü bilgisayarlarının bir karışımı vardı.

## <a name="contosos-response-to-covid-19"></a>Contoso'nun COVID-19'a yanıtı

COVID-19 pandemisinin başlamasıyla birlikte, aniden temel çalışanlar hariç tüm çalışanlar uzaktan çalışanlardı. Contoso, iş gücünü evden çalışmaya kaydırarak ve şirket içi kaynaklara uzaktan erişim ve Microsoft 365 bulut hizmetlerini kullanarak çevrimiçi olarak birincil etkinliklerini yürüterek yanıt verdi.

Contoso'nun, zaten uzak olan iş gücünün %25'ini desteklemek için Paris merkez ofisinde uzaktan erişim VPN sunucuları vardı, ancak iş gücünün %90'ını desteklemek için uzaktan erişim kapasitesinin ölçeğini büyütmek için hızla taşındı. Contoso, uzak çalışanların Contoso intranetine erişim için bölgesel olarak yakın bir giriş noktası kullanması için her uydu ofiste uzaktan erişim VPN sunucuları dağıttı.

Contoso ayrıca bölünmüş tünel için dizüstü bilgisayarlara, tabletlere ve akıllı telefonlara yüklenen VPN istemcilerinin yapılandırmasını da güncelleştirerek İyileştirme Office 365 uç noktalarına yönelik trafiğin VPN bağlantısını atlayıp doğrudan İnternet üzerinden gönderilmesini sağlar. Daha fazla bilgi için bkz. [VPN bölünmüş tünel kullanarak uzak kullanıcılar için Office 365 bağlantısını iyileştirme](../enterprise/microsoft-365-vpn-split-tunnel.md).

Burada, Paris genel merkezine ve uydu ofislerinin her birine yüklenmiş VPN cihazlarıyla elde edilen yapılandırma yer alır. 

![Contoso'nun VPN altyapısı.](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

Yüklü VPN istemcisine sahip bir uzak çalışan, bölgesel olarak en yakın ofisi bulmak için DNS kullanır ve burada yüklü OLAN VPN cihazına bağlanır. Bölünmüş tünel sayesinde Microsoft 365 İyileştirme uç noktalarına giden trafik doğrudan bölgesel olarak en yakın Microsoft 365 ağ konumuna gönderilir. Diğer tüm trafik VPN bağlantısı üzerinden VPN cihazına gönderilir.

## <a name="contosos-support-for-hybrid-work"></a>Contoso'nun karma çalışma desteği

Bölgesel kilitlemeler sırasında çoğunlukla uzak çalışanları desteklemek için ilk değişiklikler yapıldıktan sonra Contoso, bir çalışanın şu durumlarda olabileceği karma çalışmayı desteklemek için altyapı değişiklikleri yaptı:

- Her zaman uzak.
- Her zaman yerinde.
- Yerinde ve uzak bir kombinasyon.

Microsoft 365 kimlik, güvenlik ve uyumluluk özellikleri, Sıfır Güven ve kullanıcının konumuna ve cihazına bakılmaksızın çalışacak şekilde tasarlanmıştır. Daha fazla bilgi için bkz. [Sıfır Güven](https://www.microsoft.com/security/business/zero-trust).

Ancak, yüklenecek yazılım şirket içinden veya İnternet kaynağından gelebileceğinden, yazılımın yeni yüklemelerini ve güncelleştirmelerini yönetmek cihazın konumuna bağlıdır. Contoso BT mimarları yeni yüklemelerini tasarladı ve altyapıyı çalışan yerine cihazın konumuna göre güncelleştirdi.

İki tür cihaz belirlediler: şirket içi ve dolaşıma ayrılmış.

### <a name="dedicated-on-premises"></a>Ayrılmış şirket içi

Ayrılmış şirket içi cihaz, Contoso intranet'inden hiçbir zaman ayrılmayan ve vpn istemcisi yüklü olmayan bir masaüstü veya sunucu bilgisayarıdır. Bu şirket içi cihazlar Windows 10, Kurumlar için Microsoft 365 Uygulamaları ve Edge tarayıcısı yüklemeleri ve güncelleştirmeleri için Microsoft Endpoint Configuration Manager ve dağıtım noktalarını kullanmaya devam eder.

### <a name="roaming"></a>Dolaşım

Bir dolaşım cihazı Contoso intranet'inden ayrılabilir ve birçok ofis çalışanına ve tüm uzak çalışanlara ve Contoso VPN istemcisi yüklü akıllı telefonlar ve tabletler gibi kuruluşa ait diğer cihazlara verilen dizüstü bilgisayarları içerir. 

Bu cihazlar herhangi bir zamanda İnternet'e bağlanabileceğinden, Windows 10, Kurumlar için Microsoft 365 Uygulamaları ve Edge yüklemeleri ve güncelleştirmeleri için Intune veya diğer bulut tabanlı hizmetleri kullanır. Mevcut şirket içi Configuration Manager dağıtım noktalarını kullanmaz.

Bu, dolaşım cihazı için bazı yüklemelerin ve güncelleştirmelerin şirket içinde ve intranete bağlıyken İnternet üzerinden gerçekleştirileceği anlamına gelir. Ancak Contoso BT mimarları, özellikle uzak çalışanların çoğu intranete nadiren bağlı olduğunda, yapılandırmanın basitliğinin intranet bant genişliğinin İnternet'e iyileştirilmesinden daha önemli olduğuna karar verdi.

Sonuçta elde edilen altyapı aşağıdadır.

![Contoso'nun altyapısı yüklenir ve güncelleştirilir.](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

Yükleme ve güncelleştirme davranışı, cihazların bilgisayar hesapları şu gruplardan birinin üyesi yapılarak belirlenir:

- OnPremDevices

  Cihazdaki Configuration Manager istemcisi, yüklemeler ve güncelleştirmeler için dağıtım noktalarını kullanır.

- RoamingDevices

  Intune ve cihazdaki diğer ayarlar, yüklemeler ve güncelleştirmeler için Microsoft 365 ağının kullanımını belirtir.

## <a name="new-onboarding-process"></a>Yeni ekleme işlemi

Yeni bir çalışana veya veri merkezinde yeni bir sunucuya verilen yeni bir ayrılmış şirket içi cihaz için, çalışan oturum açtığında, cihazın OnPremDevices grubundaki üyeliğine bağlı olarak Configuration Manager istemcisi Windows 10 için en son güncelleştirmeleri indirip yükler. şirket içi Configuration Manager dağıtım noktalarından Kurumlar için Microsoft 365 Uygulamaları ve Edge. Tamamlandığında, ayrılmış şirket içi cihaz kullanıma hazırdır ve devam eden güncelleştirmeler için bu dağıtım noktalarını kullanır.

Yeni bir çalışana verilen yeni bir uzak cihaz için, çalışan oturum açtığında, RoamingDevices grubu üyeliğine bağlı olarak cihaz Intune bulut hizmetiyle ve diğer hizmetlerle iletişim kurar ve Windows 10, Kurumlar için Microsoft 365 Uygulamaları ve Edge için en son güncelleştirmeleri indirir ve yükler. Tamamlandığında, uzak cihaz kullanıma hazırdır ve şirket içi kaynaklara erişim için yüklü VPN istemcisini ve devam eden güncelleştirmeler için Microsoft 365 ağını kullanır.

## <a name="next-step"></a>Sonraki adım

Kuruluşunuzda [karma çalışma için altyapınızı ayarlayın](empower-people-to-work-remotely.md).
