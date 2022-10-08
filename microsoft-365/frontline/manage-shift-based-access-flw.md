---
title: Teams'de ön cephe çalışanları için vardiya tabanlı erişimi yönetme
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Kuruluşunuzdaki ön hat çalışanları için Teams'de vardiya tabanlı erişimi yönetmeyi öğrenin.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: bcbf2a52e14b2a382581612c026589df4612e374
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68068797"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Teams'de ön cephe çalışanları için vardiya tabanlı erişimi yönetme

## <a name="overview"></a>Genel bakış

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Microsoft Teams'de iletişim durumu, kullanıcının diğer kullanıcılar için geçerli kullanılabilirliğini ve durumunu gösterir. Ön cephe çalışanlarının varlığı genellikle diğer personele göre daha az tahmin edilebilirdir, çalışma saatleri genellikle her gün aynı değildir. Yönetici olarak, Teams'i kuruluşunuzdaki ön cephe çalışanlarının vardiyalı veya vardiya dışında ne zaman olduklarını belirtmeleri için vardiya tabanlı bir durum kümesi gösterecek şekilde yapılandırabilirsiniz.

Bu vardiya tabanlı iletişim durumu Düz&mdash;![yeşil onay işareti, Vardiyada'yı gösterir.](media/flw-presence-on-shift.png) **Vardiyada**, ![x ile gri daire, Vardiya kapalı'yı gösterir.](media/flw-presence-off-shift.png) **Vardiya dışında**, ![Düz kırmızı daire, Meşgul **Meşgul'ün**&mdash;](media/flw-presence-busy.png) Teams'deki [varsayılan iletişim durumu kümesinden](/microsoftteams/presence-admins) ayrı olduğunu gösterir. Bu iki iletişim durumu kümesiyle, kuruluşunuzdaki kişiler için rollerine göre farklı deneyimler yapılandırabilirsiniz.

Vardiya tabanlı erişim sayesinde, ön cephe çalışanları vardiya dışındayken Teams'e erişimi yönetebilirsiniz. Örneğin, Teams'i ön cephe çalışanlarının zamanlanmış bir vardiyada değilken Teams'i kullanabilmeleri için kabul etmesi gereken bir ileti görüntüleyecek şekilde ayarlayabilirsiniz.  

## <a name="scenario"></a>Senaryo

Burada, kuruluşunuzun vardiya tabanlı erişimi nasıl yönetebileceğine yönelik bir örnek verilmiştır.

Kuruluşunuzda, yöneticilerinin zamanladığı ve onayladığı bir vardiyada çalıştıkları saatler için ödeme yapılması gereken ön çalışanlar var. Teams uygulamasının kullanılması da dahil olmak üzere zamanlanmış bir vardiya dışında çalışmak için harcanan zaman için bu kişilere ödeme yapılmamalıdır. "Vardiya dışındayken Teams'de zamanınız ödenebilir saatlere doğru sayılmaz" ifadesini içeren özel bir ileti ayarlarsınız. Bu ileti, ön çalışanlar vardiya dışındayken Teams'e erişmeye çalıştığında görüntülenir. Teams'i kullanmayı tercih ederlerse, bu kez ödeme yapılmayacağını anlayarak **Kabul ediyorum'a** tıklarlar.

Ayrıca kuruluşunuzda maaşlı ve vardiyalı çalışmayan bilgi çalışanlarınız da vardır. Bilgi çalışanlarınızı Teams'deki varsayılan iletişim durumu durumlarını kullanacak şekilde yapılandırırken, ön cephe çalışanlarınızın vardiya tabanlı iletişim durumunu sağlarsınız.

## <a name="shift-based-presence-states"></a>Vardiya tabanlı iletişim durumu

Vardiya tabanlı iletişim durumu burada belirtilmiştir.

|Uygulama yapılandırıldı |Kullanıcı yapılandırıldı  |Daha fazla bilgi  |
|---------|---------|---------|
|![Düz yeşil onay işareti, Vardiyada'yı gösterir.](media/flw-presence-on-shift.png) Vardiyalı     |         |Vardiyanın başlangıcında otomatik olarak ayarlama         |
|![x ile gri daire, Kapalı vardiyasını gösterir](media/flw-presence-off-shift.png) Vardiya dışı     |         |Vardiyanın sonunda otomatik olarak ayarlama         |
|![Düz kırmızı daire, Meşgul'e işaret eder.](media/flw-presence-busy.png) Meşgul      | ![Düz kırmızı daire, Meşgul'i gösterir](media/flw-presence-busy.png) Meşgul         |Otomatik olarak ayarlayın. Ön hat çalışanı vardiyadayken el ile de ayarlanabilir.|

## <a name="off-shift-access-to-teams"></a>Teams'e vardiya dışı erişim

Bu özellik, ön hat çalışanları vardiya dışındayken Teams'e erişimi yönetmenize olanak tanır. Teams'i vardiya dışındayken Teams'e erişen ön cephe çalışanlarına ileti görüntüleyecek şekilde ayarlayabilirsiniz. Ön cephe çalışanlarının, Teams'i kullanabilmeleri için önce iletiyi **kabul ediyorum'a** tıklamaları gerekir.

Varsayılan iletiyi kullanabilir, önceden tanımlanmış bir dizi ileti arasından seçim yapabilir veya istediğiniz metni görüntülemek için iletiyi özelleştirebilirsiniz. Varsayılan ileti şu şekildedir:

![Varsayılan iletinin ekran görüntüsü.](media/shifts-presence-message.png)

Ayrıca ileti görüntülendiğinde sıklığı ayarlayabilir ve ilk vardiyanın başlamasıyla son vardiyanın sona ermesi ile Teams'e erişimin kısıtlanma süresi arasında bir yetkisiz kullanım süresi ayarlayabilirsiniz.

## <a name="manage-shift-based-access"></a>Vardiya tabanlı erişimi yönetme

Yönetici olarak, kuruluşunuzdaki ön cephe çalışanlarının vardiya tabanlı iletişim durumunu denetlemek için ilkeleri kullanırsınız. Aşağıdaki PowerShell cmdlet'lerini kullanarak bu ilkeleri yönetirsiniz:

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

Yeni bir ilke oluşturmak için New-CsTeamsShiftsPolicy cmdlet'ini kullanın, istediğiniz ilke ayarlarını yapın ve ilkeyi kullanıcılara atamak için Grant-CsTeamsShiftsPolicy cmdlet'ini kullanın.

Aşağıda bazı örnekler verilmiştir. Aralarından seçim yapabileceğiniz önceden tanımlanmış vardiya dışı iletilerin listesi de dahil olmak üzere her ilke ayarı ve parametresi hakkında ayrıntılı bilgi için bkz. [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-1"></a>Örnek 1

Bu örnekte, Vardiya Dışı Teams Erişimi Varsayılan İletisi adlı yeni bir ilke oluşturacağız. Bu ilkede vardiya tabanlı iletişim durumu açıktır ve bu ilkeye atanan bir kullanıcı vardiya dışındaYken Teams'e her eriştiğinde varsayılan ileti görüntülenir. Kullanıcı, iletiyi kabul ederse vardiya dışındaYken Teams'i kullanabilir ve ilk vardiyanın başlamasıyla son vardiyanın sona ermesi ile erişimin kısıtlandığı zaman arasındaki yetkisiz kullanım süresi 10 dakikadır.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Görüntülemek istediğiniz iletiyi ayarlamak için **ShiftNoticeMessageType** parametresini kullanın. Bu parametre için aralarından seçim yapabileceğiniz önceden tanımlanmış iletilerin listesini görmek için bkz. [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-2"></a>Örnek 2 

Bu örnekte, Vardiya Dışı Teams Erişimi Özel İletisi adlı yeni bir ilke oluşturacağız. Bu ilkede vardiya tabanlı iletişim durumu açıktır ve vardiya dışındayken bu ilkeye atanan bir kullanıcı Teams'e her eriştiğinde özel bir ileti görüntülenir. Kullanıcı, iletiyi kabul ederse vardiya dışındayken Teams'i kullanabilir ve ilk vardiyanın başlamasıyla son vardiyanın sona ermesi ile erişimin kısıtlandığı zaman arasındaki yetkisiz kullanım süresi 15 dakikadır.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Görüntülemek istediğiniz iletiyi ayarlamak için **ShiftNoticeMessageType** parametresini kullanın. Daha fazla bilgi için bkz. [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-3"></a>Örnek 3

Bu örnekte, Vardiya Dışı Teams Erişim İletisi1 adlı yeni bir ilke oluşturacağız. Bu ilkede vardiya tabanlı iletişim durumu açıktır ve bu ilkeye atanan bir kullanıcı vardiya dışındaYken Teams'e her eriştiğinde aşağıdaki önceden tanımlanmış ileti görüntülenir.

  "İşvereniniz, çalışma saatleri dışında muaf olmayan veya saatlik çalışanlar tarafından ağ, uygulama, sistem veya araçlarının kullanımını yetkilendirmez veya onaylamaz. Kabul ederek, vardiya dışındaYken Teams kullanımınızın yetkilendirilmediğini ve telafi edilmeyeceğini kabul etmiş olursunuz." 

Kullanıcı, iletiyi kabul ederse vardiya dışındayken Teams'i kullanabilir ve ilk vardiyanın başlamasıyla son vardiyanın sona ermesi ile erişimin kısıtlandığı zaman arasındaki yetkisiz kullanım süresi üç dakikadır.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Görüntülemek istediğiniz iletiyi ayarlamak için **ShiftNoticeMessageType** parametresini kullanın. Bu parametre için aralarından seçim yapabileceğiniz önceden tanımlanmış iletilerin listesini görmek için bkz. [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-4"></a>Örnek 4

Bu örnekte, remy@contoso.com adlı bir kullanıcıya Vardiya Dışı Teams Erişimi Özel İletisi adlı bir ilke atarız.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>İlgili konular

- [Teams'de kuruluşunuz için Vardiyalar uygulamasını yönetme](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
- [Teams PowerShell'e genel bakış](/microsoftteams/teams-powershell-overview)