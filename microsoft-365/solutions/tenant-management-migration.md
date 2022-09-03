---
title: Adım 4. Kurumsal kiracılar için Microsoft 365 kiracılarınız için geçiş
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Microsoft 365 kiracılarınız için Windows cihazlarınızı, Office istemci uygulamalarınızı ve Office sunucularınızı geçirin.
ms.openlocfilehash: 4ab57aa0ca1a3abae7d7d189be0a11824e5b2511
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67585058"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a>Adım 4. Kurumsal kiracılar için Microsoft 365 kiracılarınız için geçiş

Çoğu kuruluş, işletim sistemlerinin, istemci yazılımının ve sunucu yazılımının birden çok sürümünü içeren heterojen bir ortama sahiptir. Kuruluş için Microsoft 365, BT altyapınızın temel bileşenlerinin en güvenli sürümlerini içerir. Ayrıca bulut teknolojilerinden yararlanmak için tasarlanmış üretkenlik özellikleri de içerir.

Kurumsal tümleşik ürün paketi için Microsoft 365'in iş değerini en üst düzeye çıkarmak için, bu sürümleri geçirmek üzere bir strateji planlamaya ve uygulamaya başlayın:

| Kaynak | Hedef |
|:-------|:-----|
| Windows 7 ve Windows 8.1 | Windows 10 Enterprise |
| Çalışanlarınızın cihazlarına yüklenmiş Office istemci ürünleri | Microsoft 365 Kurumsal Uygulamaları |
| Şirket içi sunuculara yüklenen Office sunucusu ürünleri | Microsoft 365'teki eşdeğer bulut tabanlı hizmetleri |
|  |  |

## <a name="migrating-to-windows-10"></a>Windows 10 geçiş

Her Kurumsal için Microsoft 365 lisansı, Windows 10 Enterprise için bir lisans içerir. Windows 7 veya Windows 8.1 çalıştıran cihazlarınızı geçirmek için yerinde yükseltme yapabilirsiniz. Windows 7 desteği *14 Ocak 2020'de* sona erdi. 

Yerinde yükseltmenin ötesinde Windows 10 Enterprise yüklemenin ek yöntemleri için bkz. [Windows 10 dağıtım senaryoları](/windows/deployment/windows-10-deployment-scenarios). Ayrıca [Windows 10 dağıtımını](/windows/deployment/planning/) kendiniz de planlayabilirsiniz.

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a>Kurumlar için Microsoft 365 Uygulamaları geçiş

Kuruluş için Microsoft 365, Microsoft bulutundan yüklenen ve güncelleştirilen Office istemci ürünlerinin (Word, PowerPoint, Excel ve Outlook) bir sürümü olan Kurumlar için Microsoft 365 Uygulamaları içerir. Daha fazla bilgi için bkz. [Kurumlar için Microsoft 365 Uygulamaları hakkında](/deployoffice/about-microsoft-365-apps).

Bilgisayarlarınızı Office 2019 veya daha eski sürümler için güncel tutmak yerine aşağıdaki adımları izleyin:

1. Kullanıcılarınız için bir Microsoft 365 lisansı alın ve atayın.
2. Bilgisayarlarında Office 2013 veya Office 2016'yi kaldırın.
3. Kurumlar için Microsoft 365 Uygulamaları tek tek veya BT dağıtımı sırasında yükleyin. Daha fazla bilgi için bkz[. Microsoft 365 Uygulamaları için dağıtım kılavuzu](/deployoffice/deployment-guide-microsoft-365-apps).

Kurumlar için Microsoft 365 Uygulamaları hem güvenlik güncelleştirmelerini hem de yeni özellik güncelleştirmelerini otomatik olarak yükler ve gelişmiş güvenlik ve üretkenlik için Microsoft 365'teki bulut tabanlı hizmetlerden yararlanabilir.

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a>Şirket içi sunucuları ve verileri Microsoft 365'e geçirme

Kuruluş için Microsoft 365, Web tarayıcıları ve Outlook istemcisi gibi Office sunucu yazılımının şirket içi sürümleriyle aynı araçlardan bazılarını kullanan Office sunucu hizmetlerinin bulut tabanlı sürümlerini içerir. Bu bulut tabanlı hizmetler, güvenlik ve yeni özellikler için otomatik olarak güncelleştirilir. Geçişten sonra, BT departmanınız şirket içi sunucuları korumak ve güncelleştirmek için gereken süreden tasarruf edebilir.

Belirli Microsoft 365 iş yükleri için kullanıcıları ve verileri geçirme hakkında bilgi için aşağıdaki kaynakları kullanın:

- [Posta kutularını şirket içi Exchange Server Exchange Online taşıma](/exchange/hybrid-deployment/move-mailboxes)
- [SharePoint verilerini SharePoint Server'dan SharePoint Online'a geçirme](/sharepointmigration/migrate-to-sharepoint-online)
- [çevrimiçi Skype Kurumsal Microsoft Teams'e geçirme](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a>Kuruluşunuzun tamamına geçiş

Kuruluşunuzun tamamını Kuruluş için Microsoft 365'teki ürün ve hizmetlere taşıma hakkında daha iyi bir resim edinmek için şu geçiş posterini indirin:

[![Microsoft 365'e Geçiş posterini gösteren resim.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

Bu iki sayfalık poster, mevcut altyapınızın envanterini oluşturmanın hızlı bir yoludur. Kuruluş için Microsoft 365'te bir ürüne veya hizmete geçiş konusunda rehberlik almak için bunu kullanın. Windows ve Office ürünlerinin yanı sıra cihaz yönetimi, kimlik ve tehdit koruması, bilgi koruması ve uyumluluk gibi diğer altyapı ve güvenlik öğelerini gösterir.

## <a name="results-of-step-4"></a>4. Adımın Sonuçları

Microsoft 365 kiracınız için geçiş için şunları belirlediniz:

- Windows 7 veya Windows 8.1 çalıştıran cihazlar ve bunları Windows 10 Enterprise güncelleştirme planı.
- Office istemci uygulamalarını çalıştıran cihazlar ve bunları kuruluş için Microsoft 365 uygulamalarına güncelleştirme planı.
- Hangi şirket içi Office sunucu hizmetlerinin Microsoft 365 eşdeğerlerine ve bunları ve verilerini geçirme planına geçirilmesi gerekir.

Burada, şirket içi sunucuların geçişi tamamlanmış bir kiracı örneği verilmiştir.

![Şirket içi sunucuların geçişi tamamlanmış bir kiracı örneği.](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

Bu çizimde kuruluş şunları içerir:

- Şirket içi Exchange Server posta kutuları Exchange Online geçirildi.
- Şirket içi SharePoint Server siteleri ve verileri Microsoft 365'te SharePoint'e geçirildi.

## <a name="ongoing-maintenance-for-migration"></a>Geçiş için devam eden bakım

Sürekli olarak şunları yapmanız gerekebilir:

- Exchange posta kutusu geçişinizin durumuna bağlı olarak, kuruluşunuza Exchange Online geçişini yapmaya devam edin.
- Şirket içi SharePoint site geçişinizin durumuna bağlı olarak, Microsoft 365'te SharePoint'e geçişi kuruluşunuza aktarmaya devam edin.

## <a name="next-step"></a>Sonraki adım

[![5. Adım. Cihaz ve uygulama yönetimini dağıtma.](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)

[Cihaz ve uygulama yönetimini](tenant-management-device-management.md) dağıtmak için cihaz ve uygulama yönetimi ile devam edin.