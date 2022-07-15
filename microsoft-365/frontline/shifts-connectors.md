---
title: Bağlayıcıları kaydırıyor
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Vardiya bağlayıcıları ve vardiyaları iş gücü yönetim sisteminize bağlamak için bunları kullanma hakkında bilgi edinin.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: c211e066a1b5c6ad610c2f3be703d50be3ecf6af
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66824779"
---
# <a name="shifts-connectors"></a>Bağlayıcıları kaydırıyor

## <a name="overview"></a>Genel bakış

Vardiya bağlayıcıları, Microsoft Teams'deki zamanlama yönetim aracı olan Vardiyaları iş gücü yönetimi (WFM) sisteminizle tümleştirmenize olanak tanır. Bağlantı kurduktan sonra, ön cephe çalışanlarınız vardiyalar içinden WFM sisteminizde zamanlamalarını sorunsuz bir şekilde görüntüleyebilir ve yönetebilir.

WFM sisteminizi Teams'e bağlamak, ön cephe iş gücünüzün zamanlamaları daha etkili bir şekilde yönetmesini sağlar ve daha yüksek katılım ve üretkenlik için günlük süreçleri kolaylaştırır. Ön cephe çalışanlarınızın zamanlama, iletişim ve işbirliği ihtiyaçları için her yerden ve her cihazdan iş yapmak için tek bir yeri vardır.

Bu makalede, Shifts bağlayıcılarına ve bunların nasıl çalıştığına genel bir bakış sunun.

## <a name="how-shifts-connectors-work"></a>Shifts bağlayıcıları nasıl çalışır?

Bağlayıcılar zamanlama verilerini WFM sisteminizle Vardiyalar arasında eşitler ve kuruluşunuzun zamanlamalarını Teams'e getirir. Vardiyalar, ön cephe çalışanlarınızın zamanlama gereksinimleri için etkileşime geçtiği yerdir. WFM sisteminiz iş kuralları, uyumluluk ve zeka için kayıt sistemidir.

Zamanlamaların her zaman güncel olduğundan emin olmak için bağlayıcı aracılığıyla veri akışları. WFM sisteminizdeki zamanlamalar Vardiyalar ile eşitlenir. Vardiyalardaki zamanlamalarda yapılan değişiklikler de WFM sisteminizle gerçek zamanlı olarak eşitlenir. Kayıt sistemi olarak, veriler Vardiyalar'a kaydedilmeden önce tüm iş kuralları WFM sisteminiz tarafından zorlanır.

## <a name="managed-shifts-connectors"></a>Yönetilen Vardiyalar bağlayıcıları

Yönetilen Vardiyalar bağlayıcıları, iş ortaklarımızla işbirliği içinde geliştirilen bağlayıcılardır. Yönetilen bağlayıcılar bizim veya iş ortaklarımız tarafından barındırılır ve yönetilir. Yönetilen bağlayıcılarda yalnızca en az kurulum gereklidir.

### <a name="microsoft-teams-shifts-connector-for-blue-yonder"></a>Blue Yonder için Microsoft Teams Vardiyaları bağlayıcısı
<a name="blue_yonder"> </a>

Blue Yonder için Teams Shifts bağlayıcısı, Microsoft tarafından barındırılan ve yönetilen birinci taraf bir tekliftir. Bu bağlayıcı ile Zamanlamalarınızı yönetmek ve güncel tutmak için Vardiyaları Blue Yonder Workforce Management (Blue Yonder WFM) sürüm 2020.3, 2021.1 veya 2021.2 ile tümleştirebilirsiniz.  

> [!NOTE]
> Blue Yonder WFM sürüm 2020.3 veya 2021.1'iniz varsa, 2020.3.0.4 veya 2021.1.0.3 düzeltme ekini uygulayın. Bu düzeltme eki, kullanıcıların Vardiyalar'da kalıcı bir hata iletisi alması sorununu düzeltir. Ayrıca, kullanıcıların Vardiyalar'da kullanılabilirliklerini güncelleştirmelerini engelleyen bir sorunu da düzeltir.

:::image type="content" source="media/shifts-connector-blue-yonder.png" alt-text="Mobil cihazda Vardiyalar'da değiştirme isteğini, masaüstünde Teams'de onay istemeyi ve Blue Yonder WFM'da bir zamanlamayı gösteren ekran görüntüsü." lightbox="media/shifts-connector-blue-yonder.png":::

Ön cephe yöneticileri:

- Vardiyaları ve zamanlamaları Blue Yonder WFM yayımlayın ve Vardiyalar'da görüntüleyin.
- Blue Yonder WFM açık vardiyalar oluşturun, yönetin ve atayın ve bunları Vardiyalar'da görüntüleyin.
- Vardiyalar'da Mavi Yonder WFM oluşturulan açık vardiyaları atayın.
- Blue Yonder'da izin WFM oluşturma, düzenleme ve silme ve Vardiyalar'da görüntüleme.
- Hem Blue Yonder WFM hem de Shift'lerde çalışanlardan gelen zamanlama isteklerini görüntüleyin ve onaylayın.
- Blue Yonder WFM çalışan kullanılabilirliğini ayarlayın ve güncelleştirin ve Vardiyalar'da görüntüleyin.

Ön cephe çalışanları:

- Kendi vardiyalarını ve ekiplerinin vardiyalarını ve zamanlamalarını Vardiyalar'da görün.
- Vardiyalarda izin isteyin, vardiyaları açın ve vardiyaları değiştirin.
- Vardiyalar'da kullanılabilirliklerini ayarlayın.

Aşağıdaki eylemler şu anda desteklenmiyor:

- Vardiyalar'da vardiya ekleme, düzenleme, silme, kaydetme veya yayımlama.
- Vardiyalar'da izin ekleyin, düzenleyin, silin, kaydedin veya yayımlayın.
- Vardiyalar'da açık vardiyalar ekleyin, düzenleyin, silin, kaydedin veya yayımlayın.

Bir ön cephe yöneticisi veya çalışanı Vardiyalar'da bu eylemlerden herhangi birini yapmaya çalıştığında, eylemin desteklenmediğinden haberdar etmek için bir ileti alır.

#### <a name="example-scenario"></a>Örnek senaryo

Yönetici eden, Bağlayıcı aracılığıyla Teams'de Vardiyalar ile eşitlenen Blue Yonder WFM'da bir zamanlama yayımlar. Bir personel üyesi olan Alex, mobil cihazında Teams'de bildirim alır ve zamanlamasını ve atanan vardiyalarını görüntüler.

Alex'in biraz izin alması ve Vardiyalar'ı kullanarak bir gün izin istemesi gerekiyor. İstek, bağlayıcı aracılığıyla gerçek zamanlı olarak Blue Yonder WFM gönderilir. Mavi Yonder WFM, isteğin iş kurallarıyla uyumlu olmasını ve isteğin oluşturulmasını sağlar. Eden, isteği Blue Yonder WFM görüp onaylar ve onay Teams ile eşitlenir. (Eden ayrıca Vardiyalar'da isteği görebilir ve onaylayabilir). Alex, Teams'de isteğinin onaylandığı ve güncelleştirilmiş zamanlamasını görüntülediği bildirilir.

Alex bir iş arkadaşı ile vardiya değiştirmek istiyor. Vardiyalar'da Alex, Blue Yonder WFM iş kurallarına göre değiştirme için uygun olan tüm vardiyaların listesini görür. Alex, şu anda Gena'ya atanmış bir vardiya seçer. Gena, Mobil cihazlarında Teams'de bilgilendirilir ve değiştirme isteğini kabul eder. Eden, isteği Vardiyalar'da görür ve onaylar ve onay Blue Yonder WFM ile eşitlenir. (Eden, isteği Blue Yonder WFM' de de görebilir ve onaylayabilir). Alex ve Gena, Teams'de bilgilendirilir ve güncelleştirilmiş zamanlamalarını görüntüler.

#### <a name="set-up-a-connection"></a>Bağlantı kurma

Bağlayıcıyı kullanarak Shift'leri Blue Yonder WFM ile tümleştirmek yalnızca birkaç adımdan oluşur. Hızlı bir şekilde bağlantı kurmak için Microsoft 365 yönetim merkezi Shifts bağlayıcı sihirbazını kullanabilirsiniz. Sihirbaz, bağlayıcıyı seçtiğiniz ayarlara göre yapılandırıp bağlantıyı oluşturur. PowerShell kullanmayı tercih ederseniz, bağlanmak için kullanabileceğiniz PowerShell betikleri de sağlarız.

Adım adım yönergeler için bkz:

- [Shifts bağlayıcısı sihirbazını kullanarak Shifts'i Mavi Yonder'a bağlama Workforce Management](shifts-connector-wizard.md)
- [PowerShell kullanarak Vardiyaları Mavi Yonder'a bağlama Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)

Bağlantı kurulduktan sonra, istediğiniz zaman bağlantı ayarlarını güncelleştirmek ve değiştirmek için PowerShell'i kullanabilirsiniz. Bağlayıcının kendisine gelince, yükseltmeler veya bakım konusunda endişelenmeniz gerekmez. Biz hallederiz.

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>Microsoft Teams için Reflexis Shifts bağlayıcısı

Microsoft Teams için Reflexis Shifts bağlayıcısı Zebra tarafından barındırılır ve yönetilir. Bu bağlayıcı ile Zamanlamalarınızı yönetmek ve güncel tutmak için Vardiyaları Reflexis WFM sistemiyle tümleştirebilirsiniz.

Saha çalışanları Teams'deki Vardiyalar'da zamanlamalarına erişebilir ve istekleri Vardiyalardan Reflexis Workforce Scheduler'a (RWS) eşitlenir. RWS'de oluşturulan isteklerin ve vardiyaların durumu Teams'deki Vardiyalar ile eşitlenir.

:::image type="content" source="media/shifts-connector-reflexis.png" alt-text="Reflexis'te mobil cihazdaki vardiyaların ve zamanlamanın listesini gösteren ekran görüntüsü." lightbox="media/shifts-connector-reflexis.png":::

Ön cephe yöneticileri:

- Vardiyaları ve zamanlamaları Reflexis'te yayımlayın ve Vardiyalar'da görüntüleyin.
- Hem Reflexis hem de Shift'lerdeki vardiyaları düzenleyin.
- Hem Reflexis hem de Shift'lerde açık vardiyalar oluşturun, yönetin ve atayın.
- Hem Reflexis hem de Shift'lerde çalışanlardan gelen zamanlama isteklerini görüntüleyin ve onaylayın.

Ön cephe çalışanları:

- Kendi vardiyalarını ve ekiplerinin vardiyalarını ve zamanlamalarını Vardiyalar'da görün.
- Vardiyalarda izin isteyin, vardiyaları açın, vardiyaları değiştirin ve teklif edin.

Daha fazla bilgi edinmek için adresine https://connect.zebra.com/microsoft-connectorsgidin.

## <a name="related-articles"></a>İlgili makaleler

- [Vardiyalar uygulamasını yönetme](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
