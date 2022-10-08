---
title: Microsoft 365 ile karma çalışma için altyapınızı ayarlama
author: dansimp
f1.keywords:
- NOCSH
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: high
ms.collection:
- highpri
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-overview
- M365initiative-coredeploy
ms.custom: seo-marvel-jun2020
keywords: evden çalışma, evden çalışma, hibrit, uzaktan çalışan, hibrit iş, uzak çalışanlar, hibrit bağlantı, uzaktan erişim, uzaktan erişim, uzaktan çalışma, telework, teleworking, mobil iş, uzak iş, her yerden çalışma, esnek çalışma alanı
description: Hibrit çalışanlarınızın şirket içi ve Microsoft 365 kaynaklarına güvenli bir şekilde erişebilmesi için altyapı katmanlarında ilerleyin.
ms.openlocfilehash: b79c0096139633a2ff151adce71f69aea9780b6b
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67986960"
---
# <a name="set-up-your-infrastructure-for-hybrid-work-with-microsoft-365"></a>Microsoft 365 ile karma çalışma için altyapınızı ayarlama

Çalışanınızın üretkenliğini ve işbirliğini güvenli hale getirmek ve iyileştirmek için, yerinde ve uzak çalışanların kuruluşunuzun şirket içi ve bulut tabanlı bilgilerine, araçlarına ve kaynaklarına kolayca ve güvenli bir şekilde erişmesine izin vermeniz gerekir. Bu çözüm, çalışanlarınızın nerede olurlarsa olsunlar en iyi işlerini yapmalarını sağlayan temel altyapı katmanlarının dağıtımında adım adım ilerler.

Karma çalışanlar yerinde veya uzaktan konumların bir birleşiminde çalışabilir. Çalışanların geleneksel bir ofisten uzak çalışmasına izin vermek birçok kuruluşun şunları sağlaması açısından önemlidir:

- Yeniden taşınmak istemeyen veya esnek bir çalışma ortamı gerektiren çalışanları işe alma ve tutma.
- Çalışanların işe gidişlerini azaltın, işçileri üretken olmaya ve iş dışındaki stres azaltıcı etkinliklere daha fazla zaman bırakın.
- Ofis alanından tasarruf edin.

Microsoft 365, hibrit çalışanlarınızı yerinde veya uzaktan çalışma konusunda güçlendiren özelliklere sahiptir.

![Microsoft 365 ile hibrit çalışanlarınızı güçlendirin.](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)

> [!NOTE]
> Microsoft 365'i yeni kullanıyorsanız [bu kaynaklara](https://www.microsoft.com/microsoft-365) bakın.

Dağıtım işlemine genel bir bakış için bu videoyu izleyin.
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4F1af]

Hibrit çalışan üretkenliğini sağlamak için yerinde ve bulut tabanlı altyapıyı yöneten BT uzmanları için bu çözüm şu temel özellikleri sağlar:

- Bağlı

  Dünyanın her yerinden ve herhangi bir zamanda çalışanlarınız şunlara erişebilir:

  - Microsoft 365 aboneliğinizdeki bulut tabanlı hizmetler ve veriler.

  - Şirket içi uygulama veri merkezleri tarafından sunulanlar gibi kuruluş kaynakları.

- Güvenli

  Oturum açma işlemleri, Microsoft 365'in çok faktörlü kimlik doğrulaması (MFA) ve yerleşik güvenlik özellikleri ile güvenlik altına alınır ve kötü amaçlı yazılımlara, kötü amaçlı saldırılara ve veri kaybına karşı Windows 11 veya 10 koruma sağlar.

- Yönetilen

  Hibrit çalışanınızın cihazları güvenlik ayarları, izin verilen uygulamalar ve sistem durumuyla uyumluluk gerektirmek için buluttan yönetilebilir.

- İşbirliğine dayalı ve üretken

  Hibrit çalışanlarınız, şirket içi kadar üretken olabilir ve bunlarla son derece işbirliğine dayalı olabilir:

  - Teams ile çevrimiçi toplantılar ve sohbet oturumları.

  - SharePoint ve OneDrive ile genel erişilebilirlik ve gerçek zamanlı işbirliği ile bulut tabanlı dosya depolama için paylaşılan çalışma alanları.

  - İşi bölmek ve işleri halletmek için paylaşılan görevler ve iş akışları.

Sorunsuz bir oturum açma deneyimi için şirket içi Active Directory Domain Services (AD DS) kullanıcı hesaplarınız Azure Active Directory (Azure AD) ile eşitlenmelidir. Windows 11 veya 10 cihazınızı korumak için Intune'a kayıtlı olmaları gerekir. Altyapının üst düzey bir görünümü aşağıdadır.

![Microsoft 365 ile karma çalışanlar için temel altyapı.](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

Karma çalışanlarınız için Microsoft 365'in özelliklerini etkinleştirmek için bu Microsoft 365 özelliklerini kullanın.

|Yetenek veya özellik|Açıklama|Lisanslama|
|---|---|---|
|Güvenlik varsayılanlarıyla zorunlu kılınan MFA|Oturum açma işlemleri için ikinci bir kimlik doğrulaması biçimi gerektirerek güvenliği aşılmış kimliklere ve cihazlara karşı koruma sağlayın. Güvenlik varsayılanları tüm kullanıcı hesapları için MFA gerektirir.|Microsoft 365 E3 veya E5|
|Koşullu Erişim ile zorunlu kılınan MFA|Koşullu Erişim ilkeleriyle oturum açma özelliklerini temel alarak MFA gerektirme.|Microsoft 365 E3 veya E5|
|Risk tabanlı Koşullu Erişim ile zorunlu kılınan MFA|Azure AD Kimlik Koruması ile kullanıcının oturum açma riskine bağlı olarak MFA gerektirir.|Azure AD Premium P2 lisansları olan Microsoft 365 E5 veya E3|
|parola sıfırlamayı (SSPR) Self-Service|Kullanıcılarınızın parolalarını veya hesaplarını sıfırlamasına veya kilidini açmasına izin verin.|Microsoft 365 E3 veya E5|
|Azure AD Uygulama Ara Sunucusu|İntranet sunucularında barındırılan web tabanlı uygulamalar için güvenli uzaktan erişim sağlayın.|Ayrı ücretli Azure aboneliği gerektirir|
|Azure Noktadan Siteye VPN|Azure sanal ağı üzerinden uzak çalışanın cihazından intranetinize güvenli bir bağlantı oluşturun.|Ayrı ücretli Azure aboneliği gerektirir|
|Windows 365|Kişisel ve yönetilmeyen cihazlarını yalnızca Windows 365 Bulut bilgisayarlarıyla kullanabilen uzak çalışanları destekleyin.|Ayrı ücretli Azure aboneliği gerektirir|
|Uzak Masaüstü |Çalışanların intranetinizdeki Windows tabanlı bilgisayarlara bağlanmasına izin verin.|Microsoft 365 E3 veya E5|
|Uzak Masaüstü Hizmetleri Ağ Geçidi|İletişimleri şifreleyin ve RDS konaklarının doğrudan İnternet'e açık olmasını engelleyin.|Ayrı Windows Server lisansları gerektirir|
|Microsoft Intune|Cihazları ve uygulamaları yönetme.|Microsoft 365 E3 veya E5|
|Yapılandırma Yöneticisi|Cihazlarınızda yazılım yüklemelerini, güncelleştirmelerini ve ayarlarını yönetme|Ayrı Configuration Manager lisansları gerektirir|
|Uç Nokta Analizi|Windows istemcilerinizin güncelleştirmeye hazır olup olmadığını belirleyin.|Ayrı Configuration Manager lisansları gerektirir|
|Windows Autopilot|Yeni Windows 11 veya 10 cihazı üretken kullanım için ayarlayın ve önceden yapılandırın.|Microsoft 365 E3 veya E5|
|Microsoft Teams, Exchange Online, SharePoint Online ve OneDrive, Microsoft 365 Uygulamaları, Microsoft Power Platform ve Yammer|Oluşturma, iletişim kurma ve işbirliği yapma.|Microsoft 365 E3 veya E5|
||||

Güvenlik ve uyumluluk ölçütleri için bkz. [Uzak çalışanlar için güvenlik ve uyumluluk dağıtma](empower-people-to-work-remotely-security-compliance.md).

<a name="poster"></a> Bu çözümün 2 sayfalık özeti için [Hibrit çalışanları güçlendirme posteri'ne](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pdf) bakın.

[![Hibrit çalışan posterini güçlendirin.](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pdf)

## <a name="provide-hybrid-working-for-all-of-your-workers"></a>Tüm çalışanlarınız için karma çalışma sağlayın

Bu cihazlarla tüm çalışanlarınızın her yerden üretken kalmasını sağlayabilirsiniz:

- Surface dizüstü bilgisayar ve Windows 11 veya 10 gibi microsoft 365 bulut uygulamalarına ve hizmetlerine doğrudan web üzerinden erişme özelliklerine, güvenliğine ve performansına sahip modern bir cihaz.

- Microsoft 365 bulut uygulamalarına ve hizmetlerine bir [Windows 365 Bulut PC](empower-people-to-work-remotely-remote-access.md#deploy-windows-365-to-provide-remote-access-for-remote-workers-using-personal-devices) aracılığıyla dolaylı olarak erişebilen, eski dizüstü bilgisayarlar veya evden kullanılan masaüstleri de dahil olmak üzere tüm cihazlar. Bu seçenek yüksek performans, güçlü güvenlik ve basitleştirilmiş BT yönetimi sağlar.

## <a name="next-steps"></a>Sonraki adımlar

Kuruluşunuzun sunucularına ve bulut hizmetlerine erişimin güvenliğini sağlamak ve iyileştirmek ve karma çalışanınızın üretkenliğini en üst düzeye çıkarmak için bu adımları kullanın.

1. [MFA ile oturum açma güvenliğini artırma](empower-people-to-work-remotely-secure-sign-in.md)
2. [Şirket içi uygulama ve hizmetlere uzaktan erişim sağlama](empower-people-to-work-remotely-remote-access.md)
3. [Güvenlik ve uyumluluk hizmetlerini dağıtma](empower-people-to-work-remotely-security-compliance.md)
4. [Cihazlarınız, bilgisayarlarınız ve diğer uç noktalarınız için uç nokta yönetimi dağıtma](empower-people-to-work-remotely-manage-endpoints.md)
5. [Karma çalışan üretkenliği uygulamalarını ve hizmetlerini dağıtma](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [Çalışanlarınızı eğitin ve kullanım geri bildirimlerini ele alın](empower-people-to-work-remotely-train-monitor-usage.md)

[![Microsoft 365 ile karma çalışma için altyapınızı ayarlama adımları.](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)

Kurgusal ama temsili çok uluslu bir kuruluşun hibrit çalışma için altyapısını nasıl ayarlamış olduğunu görmek için bkz. [Contoso'nun COVID-19 yanıtı ve karma çalışma altyapısı](contoso-remote-onsite-work.md).
