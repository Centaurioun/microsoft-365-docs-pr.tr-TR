---
title: Teams için bekletme hakkında bilgi edinin
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- purview-compliance
- tier1
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Kuruluşunuz için Teams iletilerinin otomatik olarak tutulmasını veya silinmesini yönetebilmeniz için Microsoft Teams için geçerli olan Microsoft 365 bekletme ilkeleri hakkında bilgi edinin.
ms.openlocfilehash: 37e3546bb4b960f23c893ee401176471ad990eb4
ms.sourcegitcommit: 21548843708d80bc861f03ffae41457252492bb6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2022
ms.locfileid: "68794104"
---
# <a name="learn-about-retention-for-microsoft-teams"></a>Microsoft Teams için bekletme hakkında bilgi edinin

>*[Güvenlik & uyumluluğu için Microsoft 365 lisanslama kılavuzu](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Teams'de sohbetlerinizin veya iletilerinizin bir bekletme ilkesi tarafından silindiğini belirten bir ileti görüyorsanız bkz. [Bekletme ilkeleriyle ilgili Teams iletileri](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).
> 
> Bu sayfadaki bilgiler, bu bekletme ilkelerini yöneten BT yöneticilerine yöneliktir.

Bu makaledeki bilgiler, Microsoft Teams iletilerine özgü bilgiler içerdiğinden [Bekletme hakkında bilgi edinin'e](retention.md) eklenmiştir.

Diğer iş yükleri için bkz:

- [SharePoint ve OneDrive için bekletme hakkında bilgi edinin](retention-policies-sharepoint.md)
- [Yammer için bekletme hakkında bilgi edinin](retention-policies-yammer.md)
- [Exchange için bekletme hakkında bilgi edinin](retention-policies-exchange.md)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="whats-included-for-retention-and-deletion"></a>Saklama ve silmeye dahil olanlar

> [!NOTE]
> Bekletme ilkeleri [paylaşılan kanalları destekler](/MicrosoftTeams/shared-channels). Paylaşılan kanallar, saklama ayarlarını üst ekipten devralır.
> 
> Bekletme ilkeleri, [kendinizle sohbet](https://support.microsoft.com/office/start-a-chat-in-teams-0c71b32b-c050-4930-a887-5afbe742b3d8?storagetype=live#bkmk_chatwithself) özelliğiyle gönderilen iletileri de destekler.

Teams sohbetleri iletileri, kanal iletileri ve özel kanal iletileri Teams için bekletme ilkeleri kullanılarak silinebilir ve iletilerdeki metinlere ek olarak, uyumluluk nedeniyle aşağıdaki öğeler korunabilir: [Video klipleri](https://support.microsoft.com/office/record-a-video-clip-in-teams-0c57dae5-2974-4214-9c46-7a2136386f1c), eklenmiş resimler, tablolar, köprü metni bağlantıları, diğer Teams iletilerine ve dosyalarına bağlantılar ve [kart içeriği](/microsoftteams/platform/task-modules-and-cards/what-are-cards).

[Toplantılar ve çağrılar için meta veriler](/MicrosoftTeams/ediscovery-investigation#teams-metadata) içeren sistem tarafından oluşturulan iletiler olan yeni oluşturulan arama verileri kayıtları da desteklenir.

Bu sohbet iletileri ve özel kanal iletileri, konuşmadaki kişilerin tüm adlarını içerir ve kanal iletileri ekip adını ve ileti başlığını (varsa) içerir. 

Kod parçacıkları, Teams mobil istemcisinden kaydedilen sesli notlar, küçük resimler, duyuru görüntüleri ve ifade biçimindeki diğer kişilerden gelen tepkiler, Teams için bekletme ilkelerini kullandığınızda korunmaz.

Teams ile kullandığınız e-postalar ve dosyalar Teams için bekletme ilkelerine dahil değildir. Bu öğelerin kendi bekletme ilkeleri vardır.

## <a name="how-retention-works-with-microsoft-teams"></a>Bekletme Microsoft Teams ile nasıl çalışır?

Uyumluluk gereksinimlerinizin arka uç depolama ve işlemleri tarafından nasıl karşılandığını ve Şu anda Teams uygulamasında görünen iletiler yerine eBulma araçları tarafından doğrulanması gerektiğini anlamak için bu bölümü kullanın.

Teams'te sohbetlerden ve kanal iletilerinden verileri saklamak ve bu sohbetleri ve iletileri silmek için bekletme ilkesi kullanabilirsiniz. Arka planda Exchange posta kutuları, bu iletilerden kopyalanan verileri depolamak için kullanılır. Teams sohbetlerindeki veriler sohbete dahil edilen her kullanıcının posta kutusunda gizli bir klasörde depolanır ve Teams kanal iletileri için grup posta kutusundaki benzer bir gizli klasör kullanılır. Bu gizli klasörler, kullanıcılar veya yöneticiler tarafından doğrudan erişilebilir olacak şekilde tasarlanmamıştır, bunun yerine uyumluluk yöneticilerinin eBulma araçlarıyla arayabileceği verileri depolar.

Bu posta kutuları, RecipientTypeDetails özniteliklerine göre listelenir:

- **UserMailbox**: Bu posta kutuları, bulut tabanlı Teams kullanıcıları için ileti verilerini depolar.
- **MailUser**: Bu posta kutuları [, şirket içi Teams kullanıcıları](search-cloud-based-mailboxes-for-on-premises-users.md) için ileti verilerini depolar.
- **GroupMailbox**: Bu posta kutuları, Teams standart kanalları için ileti verilerini depolar.
- **SubstrateGroup**: Bu posta kutuları, Teams paylaşılan kanalları için ileti verilerini depolar.

Teams konferans odaları için kullanılan RoomMailbox gibi diğer posta kutusu türleri Teams saklama ilkeleri için desteklenmez.

Teams, tüm iletiler (sohbetler ve kanal iletileri) için birincil depolama alanı olarak Azure destekli bir sohbet hizmeti kullanır. Uyumluluk nedeniyle Teams iletilerini silmeniz gerekiyorsa, Teams için bekletme ilkeleri iletilerin oluşturulduğu zaman temelinde belirli bir süre sonra silinebilir. İletiler daha sonra hem uyumluluk işlemleri için depolandıkları Exchange posta kutularından hem de temel Alınan Azure destekli sohbet hizmeti tarafından kullanılan birincil depolama alanından kalıcı olarak silinir. Temel alınan mimari hakkında daha fazla bilgi için [Microsoft Teams'de güvenlik ve uyumluluk](/MicrosoftTeams/security-compliance-overview) ve özellikle [de Information Protection Mimarisi](/MicrosoftTeams/security-compliance-overview#information-protection-architecture) bölümüne bakın.

Teams sohbetlerinden ve kanal iletilerinden gelen bu veriler posta kutularında depolansa da **, Teams kanal iletileri** ve **Teams sohbetleri konumları** için bir bekletme ilkesi yapılandırmanız gerekir. Teams sohbetleri ve kanal iletileri, Exchange kullanıcısı veya grup posta kutuları için yapılandırılmış bekletme ilkelerine dahil değildir. Benzer şekilde, Teams için bekletme ilkeleri posta kutularında depolanan diğer e-posta öğelerini etkilemez.

Bir kullanıcı sohbete eklenirse, kendisiyle paylaşılan tüm iletilerin bir kopyası posta kutusuna gönderilir. Bu iletilerin oluşturulma tarihi yeni kullanıcı için değişmez ve tüm kullanıcılar için aynı kalır.

> [!NOTE]
> Bir kullanıcı Teams iletilerini koruyan etkin bir saklama ilkesine dahil edilirse ve bu ilkeye dahil edilen bir kullanıcının posta kutusunu silerseniz, posta kutusu Teams verilerini korumak için [etkin olmayan bir posta kutusuna](inactive-mailboxes-in-office-365.md) dönüştürülür. Bu Teams verilerini kullanıcı için saklamanız gerekmiyorsa, kullanıcı hesabını bekletme ilkesinden hariç tutun ve posta kutusunu silmeden önce [bu değişikliğin geçerli olmasını bekleyin](create-retention-policies.md#how-long-it-takes-for-retention-policies-to-take-effect) .

Sohbet ve kanal iletileri için bekletme ilkesi yapılandırıldıktan sonra, Exchange hizmetinden bir zamanlayıcı işi, bu Teams iletilerinin depolandığı gizli posta kutusu klasöründeki öğeleri düzenli aralıklarla değerlendirir. Zamanlayıcı işinin çalışması genellikle 1-7 gün sürer. Bu öğelerin saklama süreleri dolduğunda, kalıcı olarak silinmeden önce "geçici olarak silinen" öğeleri depolamak için her kullanıcı veya grup posta kutusunda bulunan başka bir gizli klasör olan SubstrateHolds klasörüne taşınırlar. 

İletiler en az 1 gün boyunca SubstrateHolds klasöründe kalır ve silinmeye uygunsa zamanlayıcı işi bir sonraki çalıştırılışında bunları kalıcı olarak siler.

> [!IMPORTANT]
> [İlk saklama ilkesi](retention.md#the-principles-of-retention-or-what-takes-precedence) nedeniyle ve Teams sohbeti ve kanal iletileri Exchange Online posta kutularında depolandığından, posta kutusu aynı konum, Dava Bekletme, gecikme bekletme ilkesinden etkileniyorsa veya posta kutusuna yasal veya araştırıcı nedenlerle eBulma ayrılığı uygulandığında SubstrateHolds klasöründen kalıcı silme işlemi her zaman askıya alınır.
>
> Posta kutusu geçerli bir ayrı tutmada yer alırken, silinen Teams sohbeti ve kanal iletileri artık Teams uygulamasında görünmez, ancak eBulma ile bulunabilir olmaya devam eder.

Sohbet ve kanal iletileri için bekletme ilkesi yapılandırıldıktan sonra, içeriğin izlediği yollar bekletme ilkesinin tutulup silineceği, yalnızca korunacak veya yalnızca silineceği durumlarına bağlıdır.

Bekletme ilkesi korunup silinecekse:

![Teams sohbeti ve kanal iletileri için bekletme akışı diyagramı.](../media/teamsretentionlifecycle.png)

Diyagramdaki iki yol için:

1. Bekletme süresi boyunca **bir sohbet veya kanal iletisi bir kullanıcı tarafından düzenlenir veya silinirse**, özgün ileti kopyalanır (düzenlenirse) veya SubstrateHolds klasörüne taşınır (silinirse). Bir kullanıcı Teams iletisini sildiğinde, ileti Teams uygulamasından kaybolsa da, ileti 21 gün boyunca SubstrateHolds klasörüne gitmez. İleti en az 1 gün boyunca SubstrateHolds klasöründe depolanır. Bekletme süresi dolduğunda, zamanlayıcı işi bir sonraki çalıştırıldığında (genellikle 1-7 gün arasında) ileti kalıcı olarak silinir.

2. **Bir sohbet veya kanal iletisi kullanıcı tarafından silinmezse** ve düzenleme sonrasında geçerli iletiler için, saklama süresi dolduktan sonra ileti SubstrateHolds klasörüne taşınır. Bu eylem genellikle bitiş tarihinden itibaren 1-7 gün arasında sürer. İleti SubstrateHolds klasöründe olduğunda, en az 1 gün boyunca orada depolanır ve zamanlayıcı işinin bir sonraki çalışmasında (genellikle 1-7 gün arasında) ileti kalıcı olarak silinir. 

> [!NOTE]
> Gizli klasörler de dahil olmak üzere posta kutularında depolanan iletiler eKeşif araçları tarafından aranabilir. İletiler SubstrateHolds klasöründen kalıcı olarak silinene kadar eBulma araçları tarafından aranabilir durumda kalır.

Saklama süresinin süresi dolduğunda ve bir iletiyi SubstrateHolds klasörüne taşıdığınızda, arka uç Azure sohbet hizmetine bir silme işlemi iletilir ve bu işlem aynı işlemi Teams istemci uygulamasına geçirir. Bu iletişim veya önbelleğe almadaki gecikmeler, kullanıcıların kısa bir süre boyunca bu iletileri Teams uygulamasında görmeye devam etmelerini açıklayabilir.

Azure sohbet hizmetinin bekletme ilkesi nedeniyle silme komutu aldığı bu senaryoda, Teams istemci uygulamasındaki ilgili ileti konuşmadaki tüm kullanıcılar için silinir. Bazen bu kullanıcıların bazıları başka bir kuruluştan olabileceği, daha uzun saklama süresine sahip bir bekletme ilkesine sahip olabileceği veya kendilerine hiçbir bekletme ilkesi atanmadığı için bu [davranış beklenmedik görünebilir](/microsoftteams/troubleshoot/teams-im-presence/messages-unexpectedly-deleted-retention-policy) . Bu kullanıcılar için, iletilerin kopyaları posta kutularında depolanmaya devam eder ve iletiler başka bir bekletme ilkesi tarafından kalıcı olarak silinene kadar eBulma için aranabilir durumda kalır.

> [!IMPORTANT]
> Teams uygulamasında görünen iletiler, uyumluluk gereksinimleri için tutulup tutulmadıklarını veya kalıcı olarak silindiklerinin doğru bir yansıması değildir.

Bekletme ilkesi yalnızca saklama veya yalnızca silme olduğunda, içeriğin yolları saklama ve silme çeşitlemeleridir.

### <a name="content-paths-for-retain-only-retention-policy"></a>Yalnızca saklama bekletme ilkesi için içerik yolları

1. Bekletme süresi boyunca **bir sohbet veya kanal iletisi bir kullanıcı tarafından düzenlenir veya silinirse**: Özgün ileti kopyalanır (düzenlenirse) veya SubstrateHolds klasörüne taşınır (silinirse). Bir kullanıcı Teams iletisini sildiğinde, ileti Teams uygulamasından kaybolsa da, ileti 21 gün boyunca SubstrateHolds klasörüne gitmez. İleti en az 1 gün boyunca SubstrateHolds klasöründe depolanır. Bekletme ilkesi sonsuza kadar korunacak şekilde yapılandırılmışsa, öğe orada kalır. Bekletme ilkesinin bekletme süresi için bir bitiş tarihi varsa ve süresi dolarsa, zamanlayıcı işi bir sonraki çalıştırıldığında (genellikle 1-7 gün arasında) ileti kalıcı olarak silinir.

2. **Sohbet veya kanal iletisi bir kullanıcı tarafından değiştirilmez veya silinmezse** ve bekletme süresi boyunca düzenlemeden sonra geçerli iletiler için: Bekletme süresinden önce ve sonra hiçbir şey olmaz; ileti özgün konumunda kalır.

### <a name="content-paths-for-delete-only-retention-policy"></a>Yalnızca silme bekletme ilkesi için içerik yolları

1. **Sohbet veya kanal iletisi** saklama süresi boyunca bir kullanıcı tarafından düzenlenir veya silinirse: Özgün ileti kopyalanır (düzenlenirse) veya SubstrateHolds klasörüne taşınır (silinirse).  Bir kullanıcı Teams iletisini sildiğinde, ileti Teams uygulamasından kaybolsa da, ileti 21 gün boyunca SubstrateHolds klasörüne gitmez. İleti en az 1 gün boyunca SubstrateHolds klasöründe depolanır ve zamanlayıcı işinin bir sonraki çalışmasında (genellikle 1-7 gün arasında) kalıcı olarak silinir.

2. Bekletme süresi boyunca **bir sohbet veya kanal iletisi kullanıcı tarafından silinmezse**: Saklama süresinin sonunda ileti SubstrateHolds klasörüne taşınır. Bu eylem genellikle bitiş tarihinden itibaren 1-7 gün arasında sürer. İleti en az 1 gün boyunca orada tutulur ve zamanlayıcı işi bir sonraki çalıştırıldığında (genellikle 1-7 gün arasında) kalıcı olarak silinir.

#### <a name="example-flows-and-timings-for-retention-policies"></a>Bekletme ilkeleri için örnek akışlar ve zamanlamalar

Önceki bölümlerde açıklanan işlemlerin ve zamanlamaların aşağıdaki yapılandırmalara sahip bekletme ilkelerine nasıl uygulandığını görmek için aşağıdaki örnekleri kullanın:

- [Örnek 1: 7 yıl boyunca yalnızca saklama](#example-1-retain-only-for-7-years)
- [Örnek 2: 30 gün boyunca saklama ve ardından silme](#example-2-retain-for-30-days-and-then-delete)
- [Örnek 3: 1 gün sonra yalnızca silme](#example-3-delete-only-after-1-day)

Kalıcı silmeye başvuran tüm örneklerde saklama [ilkeleri](retention.md#the-principles-of-retention-or-what-takes-precedence) nedeniyle, iletinin öğeyi tutmak için başka bir bekletme ilkesine tabi olması veya eBulma saklamaya tabi olması durumunda bu eylem askıya alınır.

##### <a name="example-1-retain-only-for-7-years"></a>Örnek 1: 7 yıl boyunca yalnızca saklama

1. günde, kullanıcı bir sohbet veya kanal iletisi oluşturur.

5. günde kullanıcı bu iletiyi düzenler.

30. günde kullanıcı geçerli iletiyi siler.

Bekletme sonuçları:

- Özgün ileti için:
    - 5. günde, ileti SubstrateHolds klasörüne kopyalanır ve burada eBulma araçlarıyla 1. günden itibaren en az 7 yıl boyunca (saklama süresi) aranabilir.

- Geçerli (düzenlenmiş) ileti için:
    - 30. günde, ileti artık Teams uygulamasında görüntülenmez ve 21 gün sonra SubstrateHolds klasörüne taşınır ve 1. günden itibaren en az 7 yıl boyunca eBulma araçlarıyla aranabilir olmaya devam eder (saklama süresi).

Kullanıcı belirtilen saklama süresinden sonra geçerli iletiyi silmişse, saklama süresi yerine 21 gün sonra da SubstrateHolds klasörüne taşınır. Ancak artık saklama süresinin dolması durumunda ileti en az 1 gün sonra ve genellikle 1-7 gün içinde kalıcı olarak silinir.

##### <a name="example-2-retain-for-30-days-and-then-delete"></a>Örnek 2: 30 gün boyunca saklama ve ardından silme

1. günde, kullanıcı bir sohbet veya kanal iletisi oluşturur.

10. günde kullanıcı bu iletiyi düzenler.

Kullanıcı başka düzenlemeler yapmaz ve iletiyi silmez.

Bekletme sonuçları:

- Özgün ileti için:
    - 10. günde, ileti SubstrateHolds klasörüne kopyalanır ve burada eBulma araçlarıyla aranabilir.
    - Saklama süresinin sonunda (1. günden itibaren 30 gün), ileti genellikle en az 1 gün sonra 1-7 gün içinde kalıcı olarak silinir ve ardından eBulma aramalarıyla döndürülemez.

- Geçerli (düzenlenmiş) ileti için:
    - Saklama süresinin sonunda (1. günden itibaren 30 gün), ileti genellikle 1-7 gün içinde SubstrateHolds klasörüne taşınır ve burada eBulma araçlarıyla aranabilir.
    - İleti daha sonra genellikle en az 1 gün sonra 1-7 gün içinde kalıcı olarak silinir ve ardından eBulma aramalarıyla döndürülemez.

##### <a name="example-3-delete-only-after-1-day"></a>Örnek 3: 1 gün sonra yalnızca silme

> [!NOTE]
> Bu yapılandırmanın kısa bir günlük süresi ve 1-7 günlük bir süre içinde çalışan bekletme işlemleri nedeniyle, bu bölümde tipik zaman aralıkları içinde yer alan örnek zamanlamalar gösterilir.

1. günde, kullanıcı bir sohbet veya kanal iletisi oluşturur.

Kullanıcı iletiyi düzenlemez veya silmezse örnek bekletme sonucu:

- 5. gün (genellikle 2. günde saklama süresinin başlamasından 1-7 gün sonra):
    - İleti SubstrateHolds klasörüne taşınır ve eBulma araçlarıyla aranabileceği en az 1 gün boyunca orada kalır.

- 9. gün (genellikle SubstrateHolds klasöründe en az 1 gün sonra 1-7 gün):
    - İleti kalıcı olarak silinir ve eBulma aramalarıyla döndürülemez.

Bu örnekte gösterildiği gibi, yalnızca bir gün sonra iletileri silmek için bir bekletme ilkesi yapılandırabilirsiniz ancak hizmet, uyumlu bir silme işlemi sağlamak için birden çok işlemden geçer. Sonuç olarak, 1 gün sonra gerçekleştirilen silme eylemi, eBulma aramalarında artık döndürülmemesi için iletinin kalıcı olarak silinmesi 16 gün sürebilir.

## <a name="skype-for-business-and-teams-interop-chats"></a>Skype Kurumsal ve Teams birlikte çalışma sohbetleri

Teams'e Skype Kurumsal bir sohbet geldiğinde, teams sohbet yazışmasında bir iletiye dönüşür ve uygun posta kutusuna gönderilir. Teams bekletme ilkeleri, Teams yazışmasından gelen bu iletilere uygulanır. 

Ancak, konuşma geçmişi Skype Kurumsal için ve Skype Kurumsal istemci tarafından geçmişin bir posta kutusuna kaydedildiğini gösterirse, bu sohbet verileri teams saklama ilkesi tarafından işlenmez. Bu içerik için Skype Kurumsal için yapılandırılmış bir bekletme ilkesi kullanın.

## <a name="messages-and-external-users"></a>İletiler ve dış kullanıcılar

Kuruluşunuzun barındırtığı bir toplantıya veya sohbete dış kullanıcılar dahil edildiğinde:

- Dış kullanıcı kiracınızda bir konuk hesabı kullanarak katılırsa, tüm Teams iletileri hem kullanıcılarınızın posta kutusunda hem de konuk hesabına verilen gölge posta kutusunda depolanır. Ancak, saklama ilkeleri, konumun tamamı için bir bekletme ilkesine dahil olarak bildirilse de (bazen "kuruluş genelinde ilke" olarak da bilinir) gölge posta kutuları için desteklenmez.

- Dış kullanıcı başka bir Microsoft 365 kuruluşundan bir hesap kullanarak katılırsa, bekletme ilkeleriniz bu kullanıcının başka bir kiracıdaki posta kutusunda depolandığından iletileri silemez. Ancak aynı toplantı veya sohbet için bekletme ilkeleriniz kullanıcılarınız için iletileri silebilir.

## <a name="when-a-user-leaves-the-organization"></a>Kullanıcı kuruluştan ayrıldığında 

Exchange Online'de posta kutusu olan bir kullanıcı kuruluşunuzdan ayrılırsa ve Microsoft 365 hesabı silinirse, bekletmeye tabi olan sohbet iletileri etkin olmayan bir posta kutusunda depolanır. Sohbet iletileri, posta kutusu devre dışı bırakılmadan önce kullanıcıya yerleştirilen bekletme ilkesine tabi kalır ve içerik eBulma aramasında kullanılabilir. Daha fazla bilgi için bkz [. Etkin olmayan posta kutuları hakkında bilgi edinin](inactive-mailboxes-in-office-365.md). 

Kullanıcı Teams'de herhangi bir dosya depoladıysa SharePoint ve OneDrive için [eşdeğer bölüme](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) bakın.

## <a name="configuration-guidance"></a>Yapılandırma kılavuzu

Microsoft 365'te saklamayı yapılandırmaya yeni başladıysanız bkz. [Veri yaşam döngüsü yönetimini kullanmaya başlama](get-started-with-data-lifecycle-management.md).

Teams için bir bekletme ilkesi yapılandırmaya hazırsanız bkz. [Bekletme ilkeleri oluşturma ve yapılandırma](create-retention-policies.md).
