---
title: Sağlık kuruluşları için Microsoft 365'i kullanmaya başlama
author: samanro
ms.author: samanro
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-frontline
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-overview
- m365-frontline
- m365solution-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.reviewer: ''
description: Microsoft 365 ve Microsoft Teams'deki teletıp özellikleri ve bunları sağlık kuruluşunuzda nasıl uygulayabileceğiniz hakkında bilgi edinin.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 01bd5b5c9386869e78b23da81d6e7cc48ecc16c8
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66824696"
---
# <a name="get-started-with-microsoft-365-for-healthcare-organizations"></a>Sağlık kuruluşları için Microsoft 365'i kullanmaya başlama

Microsoft 365 ve Microsoft Teams, hastaneler ve diğer Sağlık kuruluşları için yararlı olan bir dizi teletıp özelliği sunar. Teams özellikleri, aşağıdakilerle hastanelere yardımcı olmak için geliştiriliyor:

- Sanal randevular ve Elektronik Sağlık Kaydı (EHR) tümleştirmesi
- Teams ilke paketleri
- Güvenli mesajlaşma
- Teams şablonları
- Bakım koordinasyonu ve işbirliği

> [!NOTE]
> Bu işlev, Sağlık hizmetleri için Microsoft Bulut'un da bir parçasıdır. Azure, Dynamics 365 ve Microsoft 365'in özelliklerini [Sağlık için Microsoft Bulut'ta](/industry/healthcare) bir araya getiren bu çözümü kullanma hakkında daha fazla bilgi edinin.

Teams'de sağlık ekibi işbirliğini geliştirmek için sağlık koleksiyonunu kullanma hakkında daha fazla bilgi edinmek için aşağıdaki videoyu izleyin.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hqan]

Sağlık kuruluşunuzdan en iyi şekilde yararlanmak için öncelikle Microsoft 365 ve Microsoft Teams'in günlük etkinliklerinizde size yardımcı olabilecek senaryoları seçer ve ardından Teams ortamınızı bu senaryoları destekleyecek doğru temel bilgiler, ekipler ve uygulamalarla hazırladığınızdan emin olursunuz.

1. Uygulamak istediğiniz [senaryolarınızı seçin](#scenarios-for-healthcare).
2. [Microsoft 365'i ayarlama](flw-setup-microsoft-365.md) - Microsoft 365'in temel öğelerini, Microsoft Teams'i ve ihtiyacınız olan diğer hizmetleri ayarlayın.
3. [Hizmetleri ve uygulamaları yapılandırma](flw-setup-microsoft-365.md#step-5-configure-apps-for-your-scenario) - İşletmeniz için ihtiyacınız olan kanallar ve uygulamalar da dahil olmak üzere ihtiyacınız olan ekipleri hızla ayarlamak için ekip şablonlarını kullanın. Senaryolarınızı desteklemek için gerektiğinde Microsoft'un diğer uygulamalarını ekleyin.

## <a name="scenarios-for-healthcare"></a>Sağlık için senaryolar

Sağlık kuruluşları için aşağıdaki senaryolar kullanılabilir:

| Senaryo | Açıklama | Gereksinimler |
| -------- | -------- | -------- |
| [Elektronik Sağlık Kaydı (EHR) tümleştirmesi ile sanal randevular](#virtual-appointments-and-electronic-healthcare-record-ehr-integration) | Hastalarla sanal randevu zamanlama, yönetme ve yürütme. Bu senaryo, Teams'i ve Cerner veya Epic platformunu sanal randevuları destekleyecek şekilde bağlar. | Healthcare için Microsoft Cloud'a etkin abonelik veya Microsoft Teams EHR bağlayıcısı aboneliği tek başına teklifi. <br> Kullanıcıların Teams toplantılarını* içeren uygun bir Microsoft 365 veya Office 365 lisansına sahip olması gerekir. <br> Kuruluşların Cerner sürümü Kasım 2018 veya üzeri ya da Epic sürümü Kasım 2018 veya üzeri olmalıdır. <br>[Cerner EHR](ehr-admin-cerner.md#before-you-begin) ve [Epic EHR](ehr-admin-epic.md#before-you-begin) gereksinimlerinin ayrıntıları |
| [Microsoft Bookings ve Bookings uygulamasıyla sanal randevular](#virtual-appointments-and-electronic-healthcare-record-ehr-integration) | Hastalarla sanal randevu zamanlama, yönetme ve yürütme. Bu senaryo, sanal randevuları desteklemek için Microsoft Bookings dayanır. | Microsoft Bookings kuruluş için açık olmalıdır. <br> Bookings uygulamasının tüm kullanıcıları ve toplantılara katılan tüm personel, Teams Toplantısı zamanlamasını destekleyen bir lisansa sahip olmalıdır*. <br>[Bookings gereksinimlerinin ayrıntıları](/microsoftteams/bookings-app-admin#prerequisites-to-use-the-bookings-app-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)|
| [Bakım koordinasyonu ve işbirliği](#care-coordination-and-collaboration) | Klinisyenler ve personel zamanlamalar, belgeler, görevler vb. üzerinde dahili olarak işbirliği yapabilir.| Kullanıcıların uygun lisansa* sahip olması gerekir. |

*Office 365 A3, A5, E3, E5, F1, F3, Microsoft 365 A3, A5, E3 ve E5, İş Standardı desteklenir. Genel Teams lisanslama hakkında daha fazla bilgi için bkz. [Teams'e kullanıcı erişimini yönetme](/microsoftteams/user-access).

Alternatif olarak, Ön cephe çalışanları için Microsoft 365'e yönelik [Kurumsal iletişimler](flw-corp-comms.md) veya [Refah ve katılım](flw-wellbeing-engagement.md) gibi diğer [senaryolar](flw-choose-scenarios.md) arasından seçim yapabilirsiniz.

Ayrıca Microsoft Teams'in sağlık kuruluşunuz için çalışmasına yardımcı olan bu özelliklerden yararlanın:

| Özellik | Açıklama | Gereksinimler |
| -------- | -------- | -------- |
| [Teams ilke paketleri](#teams-policy-packages)| Klinik çalışanlarının, bilgi çalışanlarının ve hasta odası cihazlarının Teams işlevselliğine uygun erişime sahip olduğundan emin olun.| Kullanıcıların uygun lisansa* sahip olması gerekir. |
| [Güvenli mesajlaşma](#secure-messaging) | Acil iletilere daha hızlı dikkat edin ve iletinin alınıp okunduğuna güvenin. | Kullanıcıların uygun lisansa* sahip olması gerekir.  |
| [Teams şablonları](#teams-templates-for-healthcare-organizations) | Bir koğuş, pod veya departman içinde veya hastane içindeki birden çok koğuş, pod ve departman arasında iletişim ve işbirliği için önceden yüklenmiş ayarlar, kanallar ve önceden yüklenmiş uygulamalar içeren önceden tanımlanmış bir şablon içeren ekipler oluşturun. | Kullanıcıların uygun lisansa* sahip olması gerekir.  |

## <a name="virtual-appointments-and-electronic-healthcare-record-ehr-integration"></a>Sanal randevular ve Elektronik Sağlık Kaydı (EHR) tümleştirmesi

Hastalarla sanal randevular zamanlamak, yönetmek ve yürütmek için Teams'deki toplantı platformunun tamamını kullanın.

- Kuruluşunuz elektronik sistem durumu kayıtlarını veya EHR'yi zaten kullanıyorsa, daha sorunsuz bir deneyim için Teams'i tümleştirebilirsiniz. Teams Elektronik Sağlık Kaydı (EHR) bağlayıcısı, klinisyenlerin doğrudan EHR sisteminden Teams'deki başka bir sağlayıcıyla sanal hasta randevusu veya danışmanlığı başlatmasını kolaylaştırır. Daha fazla bilgi edinmek için bkz. [Teams ile sanal randevular - Cerner EHR ile tümleştirme](ehr-admin-cerner.md) ve [Teams ile sanal randevular - Epic EHR ile tümleştirme](ehr-admin-epic.md).
- Desteklenen bir EHR kullanmıyorsanız Teams'de Microsoft Bookings ve Bookings uygulamasını kullanabilirsiniz. Daha fazla bilgi için bkz. [Teams ile sanal randevular ve Bookings uygulaması](bookings-virtual-visits.md).

![Microsoft Teams ile sanal randevular.](media/virtual-visits-teams.png)

## <a name="teams-policy-packages"></a>Teams ilke paketleri

Teams'de farklı rollerin neler yapabileceğini tanımlamak için Teams ilke paketlerini uygulayın. Örneğin, ilkeleri belirtin:

- Kayıtlı hemşireler gibi klinik çalışanlar, sohbet, arama, vardiya yönetimi ve toplantılara tam erişim elde edebilmeleri için hemşireleri, doktorları ve sosyal çalışanları ücretlendirilir.
- BT personeli, bilişim personeli, finans personeli ve uyumluluk görevlileri gibi sağlık kuruluşunuzdaki bilgi çalışanları sohbet, arama ve toplantılara tam erişime sahip olabilir.
- Hasta odası cihazlarının ayarlarını kontrol etmek için hasta odaları.

Daha fazla bilgi edinmek için bkz. [Sağlık hizmetleri için Teams ilke paketleri](/microsoftteams/policy-packages-healthcare?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json).

## <a name="secure-messaging"></a>Güvenli mesajlaşma

Güvenli mesajlaşma, çeşitli yeni özellikler de dahil olmak üzere sağlık ekiplerinde işbirliğini destekler:

- İletiyi gönderen, iletisi için özel bir öncelik ayarlayabilir, bu nedenle alıcı iletiyi okuyana kadar sürekli olarak bilgilendirilir.
- İletiyi gönderen bir okundu bilgisi isteyebilir, bu nedenle gönderdiği bir ileti ileti alıcısı tarafından okunduğunda bildirim alır.

Bu özellikler birlikte acil iletilere daha hızlı dikkat ve iletinin alınıp okunduğuna güven sağlar. Bu özellikleri kullanan yeni sağlık ekipleri hasta bazında oluşturulabilir. Bu özellikler ilke tabanlıdır ve kişilere veya Teams'in tamamına atanabilir.

Daha fazla bilgi edinmek için bkz. [Sağlık kuruluşları için Güvenli Microsoft Mesajlaşma ilkelerini kullanmaya başlama](messaging-policies-hc.md).

Ayrıca güvenli mesajlaşma ile ilgili olarak Healthcare kuruluşları tarafından federasyona sahip diğer kiracıların olması ve daha zengin kiracılar arası iletişime olanak sağlamasıdır. (Bkz. [Microsoft Teams'de dış toplantıları ve sohbeti yönetme](/microsoftteams/manage-external-access)).

## <a name="teams-templates-for-healthcare-organizations"></a>Sağlık kuruluşları için Teams şablonları

Ekipler, sağlık kuruluşları için özel olarak tasarlanmış şablonlar içerir ve bu da personelin hasta bakımı veya operasyonel ihtiyaçları üzerinde iletişim kurması ve işbirliği yapması için ekipler oluşturmayı kolaylaştırır. Daha fazla bilgi için bkz. [Sağlık ekibi şablonlarını kullanma](/microsoftteams/expand-teams-across-your-org/healthcare/healthcare-templates-admin-console?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json).

## <a name="care-coordination-and-collaboration"></a>Bakım koordinasyonu ve işbirliği

Bakımı koordine etmek ve Teams ile işbirliği yapmak için sağlık ekibinizi bir araya getirin.

![Sağlık: Teams'de sağlık ekibinizle işbirliği yapın.](media/teams-healthcare-collaborate-in-teams.png)

Teams; hekimlerin, klinisyenlerin, hemşirelerin ve diğer personelin Teams'deki dahil edilen işbirliği özellikleriyle verimli bir şekilde işbirliği yapmasına olanak tanır, örneğin:

- Sağlık ekipleriniz ve bilgi çalışanlarınız için ekipler ve kanallar ayarlayın. Bilgi kaynaklarını sabitleyebilecekleri sekmelerden ek yardımla, çalışmalarını yapılandırmanın bir yolu olarak sekmelerle kanalları kullanın.
- Sohbet edin, mesaj gönderin ve iletişim kurun. Ekibiniz, dikkate ihtiyacı olan farklı hastalar hakkında kalıcı konuşmalar yapabilir.
- Sağlık ekibinin üyelerini arayın ve toplantılar. Teams ses, video, ekran paylaşımı, kayıt ve transkripsiyon özelliklerinin gücüyle tek tek toplantılar ayarlayın veya günlük toplantıları yönetmek için kanal toplantılarını kullanın.
- Dosyaları ve belgeleri depolayın ve paylaşın. Sağlık ekibiniz, Office belgeleri üzerinde çalışan ve işbirliği yapan tek bir sanallaştırılmış ekibin parçasıdır.

Ayrıca ekibiniz Teams'deki uygulamaları kullanarak şunları da yapabilir:

- Listeler uygulamasıyla listeleri paylaşma ve bilgileri izleme
- Görevler uygulamasıyla görevleri izleme ve izleme
- Onaylar uygulamasıyla onayları kolaylaştırma
- Vardiyalar uygulamasıyla zamanlama oluşturma, yönetme ve paylaşma

### <a name="share-lists-and-track-information-with-the-lists-app"></a>Listeler uygulamasıyla listeleri paylaşma ve bilgileri izleme

Teams'deki Listeler uygulaması, ekiplerin bilgileri izlemesine ve çalışmayı düzenlemesine yardımcı olur. Uygulama tüm Teams kullanıcıları için önceden yüklenmiştir ve her ekipte ve kanalda bir sekme olarak kullanılabilir. Listeler sıfırdan, önceden tanımlanmış şablonlardan veya verileri Excel'e aktararak oluşturulabilir.

Sağlık ekipleri başlamak için Hastalar şablonunu kullanabilir. Hastaların ihtiyaçlarını ve durumunu izlemek için listeler oluşturabilirler. Teams'te liste oluşturmak için Excel elektronik tablolarındaki mevcut hasta verileri getirilebilir. Bu listeler, bakımı koordine etmek için yuvarlama ve hasta izleme gibi senaryolar için kullanılabilir.

Örneğin, ücret hemşiresi bir ekipte tüm sağlık ekibi üyelerini içeren bir hasta listesi oluşturur. Turlar sırasında sağlık ekibi Teams'e mobil cihazlarından erişir ve ekipteki herkesin eşitlenmiş durumda kalmak için görüntüleyebileceği hasta bilgilerini listedeki hasta bilgilerini güncelleştirir. Sağlık ekibinin önemli sağlık performansı ölçümlerini tartışmak ve değerlendirmek için toplandığı yuvarlama oturumlarında, hastanın taburcu olmak için doğru kayma yolunda olduğundan emin olmak için bu bilgileri Teams'i kullanarak büyük bir ekran ekranında paylaşabilirler. yerinde olmayan sistem durumu ekibi üyeleri uzaktan katılabilir.

Hasta yuvarlama için ayarlanmış örnek bir liste aşağıda verilmişti.

:::image type="content" source="media/lists-patients-example.png" alt-text="Hasta yuvarlama için örnek listenin ekran görüntüsü.":::

Daha fazla bilgi edinmek için bkz. [Teams'de kuruluşunuz için Listeler uygulamasını yönetme](/microsoftteams/manage-lists-app?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json).

### <a name="track-and-monitor-tasks-with-the-tasks-app"></a>Görevler uygulamasıyla görevleri izleme ve izleme

Tüm sağlık ekibinize yönelik öğeleri izlemek için Teams'deki [Görevler'i](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) kullanın. Sağlık ekibiniz, Teams çalıştıran herhangi bir cihazdan istediğiniz zaman görev oluşturabilir, atayabilir ve zamanlayabilir, görevleri kategorilere ayırabilir ve durumu güncelleştirebilir. BT uzmanları ve yöneticileri de kuruluşunuz için belirli ekiplere görev yayımlayabilir. Örneğin, yeni güvenlik protokolleri için bir dizi görev veya hastanede kullanılacak yeni bir giriş adımı yayımlayabilirsiniz.

Daha fazla bilgi için bkz. [Microsoft Teams'de kuruluşunuz için Görevler uygulamasını yönetme](/microsoftteams/manage-tasks-app?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)

### <a name="streamline-approvals-with-the-approvals-app"></a>Onaylar uygulamasıyla onayları kolaylaştırma

Ekibinizle tüm isteklerinizi ve süreçlerinizi kolaylaştırmak için [Onaylar'ı](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) kullanın. Ekip çalışması için onayları doğrudan merkezinizden oluşturun, yönetin ve paylaşın. Bir onay akışını sohbet gönderdiğiniz yerden, kanal konuşmasında veya Onaylar uygulamasının kendisinden başlatın. Bir onay türü seçin, ayrıntıları ekleyin, dosya ekleyin ve onaylayanları seçin. Gönderildikten sonra onaylayanlara bildirim gönderilir ve isteği gözden geçirip üzerinde işlem yapabilir.

Kuruluşunuz için Onaylar uygulamasına izin verebilir ve bunu ekiplerinize ekleyebilirsiniz. Daha fazla bilgi için bkz. [Onaylar uygulamasını yönetme](/microsoftteams/approval-admin?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json).

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-frontline-worker-integration"></a>Vardiyalar uygulaması ve Ön Cephe Çalışanı tümleştirmesi ile zamanlama oluşturma, yönetme ve paylaşma

Ekipler Vardiyalar uygulaması ve Ön Cephe Çalışanı ile tümleşir ve vardiya personeli özelliklerini ve daha fazlasını koordine etmek için kullanılabilir. Örneğin, Vardiyalar'da Hemşire yöneticileri personeli için zamanlamalar ayarlayabilir ve eşgüdümlü olarak ayarlayabilir ve hemşireler zamanlamaları denetleyebilir ve vardiyaları değiştirebilir.

Daha fazla bilgi için bkz. [Microsoft Teams'de kuruluşunuz için Vardiyalar uygulamasını yönetme](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json).

## <a name="help-your-clinical-and-information-workers-get-going-with-teams"></a>Klinik çalışanlarınızın ve bilgi çalışanlarınızın Teams ile çalışmaya başlamalarını sağlama

Kuruluşunuzdaki tüm kullanıcıların Teams'i kullanmaya alışmalarına yardımcı olmak için kullanabileceğiniz birçok kaynak vardır:

- Kuruluşunuzun Teams yolculuğuna yeni başlıyorsanız veya Teams'i kuruluşunuzun daha fazla alanına genişletiyorsanız Teams'i dağıtma hakkında öneriler için Teams [benimseme merkezini](https://adoption.microsoft.com/microsoft-teams/) ziyaret edin.
- Kullanıcılarınız için yalnızca yapması gereken görevleri kapsayacak özel [öğrenme yolları](https://adoption.microsoft.com/microsoft-365-learning-pathways/) ayarlamayı göz önünde bulundurun.
- Teams [destek sitesindeki Teams'de](https://support.microsoft.com/teams) [hızlı eğitim videoları](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7) da dahil olmak üzere temel görevleri gerçekleştirme konusunda kullanıcılarınız için yardım ve eğitim alın. Bu site ayrıca [Listeler](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db), [Görevler](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070), [Onaylar, Bookings ve Vardiyalar](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) dahil olmak üzere Teams uygulamaları [](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)için yardım ve [eğitime sahiptir](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821).
