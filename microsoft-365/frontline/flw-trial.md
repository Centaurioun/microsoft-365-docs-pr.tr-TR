---
title: Teams'de Ön Cephe Deneme sürümünü yönetme
author: daisyfell
ms.author: daisyfeller
ms.reviewer: samanro
manager: pamgreen
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Kuruluşunuz için ön cephe çalışanları için 90 günlük Teams denemesi ayarlamayı öğrenin.
ms.localizationpriority: high
ms.collection:
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 311d0a5b1204f022a993bbef24ea4bc1edda324c
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66824764"
---
# <a name="manage-the-frontline-trial-in-teams"></a>Teams'de Ön Cephe Deneme sürümünü yönetme

> [!NOTE]
> Bu deneme deneyimi çok yakında sunulacaktır. Microsoft 365 Yönetici [merkezinizdeki İleti merkezinde](https://go.microsoft.com/fwlink/p/?linkid=2070717) bir ileti arayarak bunun kuruluşunuz tarafından ne zaman kullanılabilir olduğunu de kontrol edebilirsiniz.

Microsoft Teams Ön Cephe Deneme deneyimi, kuruluşunuzdaki Teams'de bulunan kullanıcıların, diğer üyeler Azure Active Directory'de (Azure AD) olduğu sürece ön cephe ekiplerinin tamamı için bir Teams deneyimi başlatmasına olanak tanır. [AllowSelfServicePurchase PowerShell modülünü](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell) kullanarak kuruluşunuzdaki kullanıcılar için bu özelliği devre dışı bırakabilirsiniz.

## <a name="what-services-are-included"></a>Hangi hizmetler dahil edilir?

Deneme sürümü, aşağıdaki özel durumlar dışında [Microsoft 365 F3 lisansındaki](https://www.microsoft.com/microsoft-365/enterprise/f3) her şeyi içerir:

- Ön Cephe Denemesi, Exchange Bilgi Noktası yerine Exchange Foundation'ı içerir. Bu değişiklik nedeniyle kullanıcılarda diğer Teams işlevleri eksik olabilir.

## <a name="eligibility"></a>Uygunluk

> [!NOTE]
> kuruluşunuzun deneme pilotunun bir parçası olup olmadığını denetlemek için Microsoft 365 Yönetici [merkezinizdeki İleti merkezinde](https://go.microsoft.com/fwlink/p/?linkid=2070717) bir duyuru arayabilirsiniz. Kullanıcıların denemeyi başlatması veya deneme sürümüne katılması için kuruluşunuzun deneme pilotunun bir parçası olması gerekir. Bu teklif GCC, GCC High, DoD veya EDU müşterileri için kullanılamaz.

Ön Cephe Deneme sürümü, deneme başına en fazla 300 kullanıcıyı barındırabilir.

Kullanıcılar aşağıdakiler durumunda ekipleri için ön cephe denemesi başlatabilir:

- Teams'e erişim sağlayan etkin bir lisansa sahip olmanız gerekir.
- Daha önce ön çalışan denemesi başlatmadım.

> [!IMPORTANT]
> Deneme sürümünü başlatan kullanıcı deneme süresi sona ermeden kuruluşunuzdan ayrılırsa, yönetici olarak denemeyi izlemeniz, bu özelliklerden kimin yararlanacağını görmek için ekiple iletişim kurmanız ve ücretli lisansa yükseltmeniz gereken kullanıcılara karar vermeniz gerekir.

Kullanıcılar yönetilen bir Azure Active Directory etki alanı e-posta adresleri varsa ön çalışan deneme sürümüne katılabilir.

Kullanıcılar daha önce bir deneme sürümü başlattıysa ancak başka bir deneme başlatamıyorsa katılabilir.

> [!NOTE]
> Teams'e mevcut erişimi olmayan kullanıcılar yalnızca ekip oluşturma sırasında deneme ekibine eklenebilir. Mevcut Teams kullanıcıları, ekip oluşturulduktan sonra da deneme sürümüne eklenebilir.

## <a name="set-up-the-trial"></a>Deneme sürümünü ayarlama

Uygun kullanıcılar, Teams'deki Görevler uygulamasında masaüstünden veya [web uygulamasından](https://teams.microsoft.com/_#/apps/com.microsoft.teamspace.tab.planner/sections/mytasks) oturum açarak Ön Cephe Denemesi başlatabilir. Şu anda mobil cihazlardan Ön Cephe Deneme sürümü başlatmak desteklenmez. Bir deneme başlatıldığında, ekibin tamamına otomatik olarak Ön Cephe Deneme lisansı atanır. Teams'e erişim sağlayan mevcut ücretli lisansları olan kullanıcılara da deneme lisansları atanır, ancak deneme süresi boyunca mevcut lisanslarının işlevselliğini korur ve deneme süresi sona erdikten sonra mevcut ücretli lisanslarını korurlar. Deneme sürümünü başlatan kullanıcı, deneme süresi boyunca e-posta bildirimleri alır.

## <a name="manage-the-frontline-trials-experience"></a>Ön cephe deneme deneyimini yönetme

Yöneticiler, **AllowSelfServicePurchase** PowerShell modülünü kullanarak son kullanıcıların kuruluşlarında Ön Cephe Deneme sürümünü başlatmasını engelleyebilir. Bu yalnızca deneme lisansları içindir. [AllowSelfServicePurchase PowerShell modülünü kullanmayı öğrenin](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell).

### <a name="manage-teams-for-users-who-have-the-frontline-trial-license"></a>Ön Cephe Deneme lisansına sahip kullanıcılar için Teams'i yönetme

Ön Cephe Deneme lisansına sahip kullanıcıları, normal ücretli lisansı olan kullanıcıları yönettiğiniz gibi yönetebilirsiniz. Daha fazla bilgi için bkz. [Kuruluşunuz için Teams ayarlarını yönetme](/microsoftteams/manage-teams-overview).

### <a name="remove-a-trial-license"></a>Deneme lisansını kaldırma

Ön Cephe Deneme lisansını PowerShell veya Microsoft 365 yönetim merkezi aracılığıyla kaldırabilirsiniz.

[PowerShell ile kaldırmayı öğrenin](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).

[Yönetim merkezinde kaldırmayı öğrenin](/microsoft-365/admin/add-users/delete-a-user).

## <a name="upgrade-users-from-frontline-trial"></a>Frontline Deneme Sürümünden kullanıcıları yükseltme

Kullanıcılar, deneme süresi sona erdiğinde lisans istemek için size ulaşabilir. Kullanıcılarınızı yükseltmek için yönetici ayrıcalıklarına sahip olmanız gerekir.

### <a name="when-to-upgrade"></a>Yükseltme zamanları

90 günlük deneme sürümünün sonuna doğru, ücretli lisansa kimlerin devam etmesi gerektiğini görmek için kullanıcılarınıza bakmanız gerekir. Kullanıcıların deneyimlerinde herhangi bir kesinti yaşanmasını önlemek için Ön Cephe Deneme aboneliğinin süresi dolmadan önce bunu yaptığınızdan emin olun.

> [!IMPORTANT]
> Ön Cephe Deneme lisansı sona erer ve kullanıcıya Teams içeren bir lisans hemen atanmazsa Teams'e erişimi kaybeder. 30 gün sonra verileri (dosyalar, iletiler ve daha fazlası) silinir. Kullanıcı Azure Active Directory'de hala var. 30 günlük süre içinde Teams işlevselliğini etkinleştirmek için kullanıcıya yeni bir lisans atanırsa, Teams'deki tüm içeriği mevcut olmaya devam eder.

### <a name="choose-an-upgrade-path"></a>Yükseltme yolu seçme

> [!TIP]
> Ön Cephe Deneme sürümü [Microsoft 365 F3 lisansına](https://www.microsoft.com/microsoft-365/enterprise/f3) dayanır.

Kuruluşunuzun şu anda sahip olduğu aboneliklere bağlı olarak, Ön Cephe Deneme sürümünden ücretli lisansa yükseltmenin üç yolu vardır:

- **Mevcut bir Microsoft 365 aboneliğini yükseltin.** Kuruluşunuzun Teams içermeyen diğer Office ürünlerine abonelikleri varsa bu seçeneği kullanın. Daha fazla bilgi için bkz. [Farklı bir plana yükseltme](/microsoft-365/commerce/subscriptions/upgrade-to-different-plan). Mevcut aboneliğin etkin kullanıcılarını görmek için Microsoft 365 yönetim merkezi **Kullanıcılar >** [Etkin kullanıcılar'a](https://go.microsoft.com/fwlink/p/?linkid=834822) gidin.

- **Mevcut bir Microsoft 365 aboneliğine kullanıcı ekleyin.** Kuruluşunuzun ön cephe ekibinizi kapsayacak kadar ücretli Teams lisansı yoksa bu seçeneği kullanın. Daha fazla bilgi için bkz. [Lisans satın alma veya kaldırma](/microsoft-365/commerce/licenses/buy-licenses). Zaten yeterli kullanılabilir lisansı olan mevcut bir aboneliğe kullanıcı eklemek için bkz. [Kullanıcıları farklı bir aboneliğe taşıma](/microsoft-365/commerce/subscriptions/move-users-different-subscription). Mevcut aboneliğin etkin kullanıcılarını görmek için Microsoft 365 yönetim merkezi **Kullanıcılar >** [Etkin kullanıcılar'a](https://go.microsoft.com/fwlink/p/?linkid=834822) gidin.

- **Yeni bir Microsoft 365 aboneliği satın alın.** Kuruluşunuzun Office ürünlerine yönelik aboneliği yoksa veya kuruluşunuz ön cephe kullanıcılarını kapsayacak şekilde mevcut aboneliklerinden farklı bir abonelik satın almak istiyorsa bu seçeneği kullanın. Daha fazla bilgi için bkz. [Ön cephe çalışanları için Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise/frontline).

Hangi Microsoft 365 aboneliğine yükseltebileceğinizden emin değilseniz bkz. [Ön cephe çalışanları için Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise/frontline). Abonelik seçerken ek yardıma ihtiyacınız varsa veya kuruluşunuzun 300'den fazla lisansa ihtiyacı varsa [Microsoft iş ortağınıza veya Microsoft](https://www.microsoft.com/solution-providers/home) hesabı temsilcinize başvurun.

### <a name="assign-paid-licenses"></a>Ücretli lisans atama

Yeni edinilen lisanslarınızı atamak için bkz. [Kullanıcılara lisans atama](/microsoft-365/admin/manage/assign-licenses-to-users).  

Yeni lisansları atadıktan sonra Teams Exploratory lisanslarının atamasını kaldırın. Daha fazla bilgi için bkz. [Kullanıcılardan lisans atamalarını kaldırma](/microsoft-365/admin/manage/remove-licenses-from-users).

## <a name="faq"></a>SSS

**Deneme süresi ne kadardır?** <br>
Ön Cephe Denemesi 90 gün sürer.

**Yöneticiler 90 günlük Ön Cephe Denemesi deneyiminin sonunda ne yapmalı?** <br>
90 günlük deneme sürümünün sonunda, ücretli lisansa kimlerin devam etmesi gerektiğini görmek için kullanıcılarınıza bakmanız gerekir. Ardından [kullanıcılarınızı yükseltmeniz](#upgrade-users-from-frontline-trial) gerekir.

**Deneme sürümünü başlatan kullanıcı kuruluşunuzdan ayrılırsa ne olur?** <br>
Yönetici olarak 90 günlük süre boyunca deneme sürümünü izlemeniz ve deneme süresi sona erdiğinde ihtiyacı olan kullanıcılar için ücretli lisanslara yükseltmeniz gerekir.

**Veri saklama ilkesi nedir?** <br>
[Microsoft 365 abonelik bilgilerinden](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?) veri saklama hakkında bilgi edinebilirsiniz.

**Bir kullanıcı Ön Cephe Deneme sürümünü başlatırken bir hatayla karşılaşırsa ne olur?** <br>
Kuruluşunuzun, deneme sürümünü başlatan kullanıcının ve deneme sürümüne eklenen kullanıcıların [uygunluk ölçütlerini](#eligibility) karşıladığından emin olun.