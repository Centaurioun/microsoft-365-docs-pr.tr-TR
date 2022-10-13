---
title: Vardiya yönetimi için zamanlama sahiplerini yönetme
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
description: Zamanlama yönetimi için vardiya sahiplerini yönetmeyi öğrenin. Ekip üyesinin iznini zamanlama sahibine yükseltmek için bir ilke ayarlayabilirsiniz.
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
- microsoftcloud-healthcare
- microsoftcloud-retail
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 57676d0f1f037c1c780d0a6f7f0611dc79ab5a7e
ms.sourcegitcommit: 04e517c7e00323b5c33d8ea937115725cf2cfd4d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2022
ms.locfileid: "68564992"
---
# <a name="schedule-owner-for-shift-management"></a>Vardiya yönetimi için Sahibi Zamanla

## <a name="overview"></a>Genel bakış

Zamanlama Sahibi özelliği, çalışanı ekip sahibi yapmadan zamanlamaları yönetebilmeleri için ekip üyesinin izinlerini yükseltmenize olanak tanır. Zamanlama Sahibi izinleriyle, bir çalışan ekip kanallarını güncelleştirme, düzenleme veya silme gibi diğer ekip özelliklerini değiştiremeden takımının zamanlamasını yönetebilir.

Zamanlama sahibi izinlerine sahip bir kullanıcı ne yapabilir?

- Ekiplerinin vardiya atamalarını yönetmek için zamanlamalar oluşturun, düzenleyin ve yayımlayın.
- Vardiya değiştirme ve açık vardiya alma istekleri de dahil olmak üzere vardiya isteklerini görüntüleyin ve onaylayın.
- Ekip için belirli özellikleri etkinleştirmek için Vardiyalar'da ayarları yönetin.
- Çalışan bordrolarını işlemek için ekiplerinin zaman çizelgesini görüntüleyin ve değiştirin.

## <a name="why-schedule-owner"></a>Neden Sahibi Zamanla?

Zamanlama Sahibi özelliği olmadan, günlük iş işlevleri kesintiye uğrayabilir. Ekip sahibi ekibin çalıştırılmasına yardımcı olsa da, günlük zamanlamadan sorumlu kişi olmayabilir. Bu durumda, yalnızca zamanlama yönetimi sorumluluğunun başka bir ekip üyesine aktarılması, ekip içindeki günlük işlemleri kolaylaştırır ve aynı erişim ayrıcalıklarına sahip iki ekip üyesinin karışıklığını ortadan kaldırır.

## <a name="scenario"></a>Senaryo

Burada, kuruluşunuzun Sahip Zamanlama özelliğini nasıl kullanabileceğine ilişkin bir örnek verilmiş.

Departman yöneticilerinin doğrudan mağaza yöneticisine raporladığı büyük bir kuruluşta çalışıyorsunuz. Mağaza yöneticisi şirketinizde daha fazla yetkiye sahiptir ve Vardiyalar'da ekip sahibidir. Öte yandan departman yöneticileri vardiyalara yalnızca ekip üyesi olarak eklenir. Mağaza yöneticileri departman yöneticilerinden daha fazla kıdemli olsa da, departman yöneticilerinin ekip çalışanlarının günlük zamanlamasını işlemesi daha mantıklıdır.

*Zamanlama Sahibi olmadan*, departman yöneticilerine ekip sahibiyle tam olarak aynı ayrıcalıklar verilmelidir. Son zamanlarda, departman yöneticileri bilgileri başka bir yere taşıyor ve kanalların adını değiştiriyor ve bu durum mağaza yöneticisinin çalışmalarında karmaşıklıklara neden oldu. Mağaza yöneticisi, departman yöneticilerinin zamanlamalarını düzenleyebilmelerini istiyor, ancak Vardiyalar dışında ekipte başka bir şeyi değiştirebilmelerini istemiyor.

*Zamanlama Sahibi ile*, departman yöneticilerine diğer ekip sahibi ayrıcalıkları olmadan zamanlama ayrıcalıkları verilebilir.

## <a name="manage-schedule-ownership"></a>Zamanlama sahipliğini yönetme

Bir yönetici olarak, kuruluşunuzda yönetim sahipliğini zamanlamak için ilkeleri kullanırsınız. Aşağıdaki PowerShell cmdlet'lerini kullanarak bu ilkeleri yönetirsiniz:

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy?view=teams-ps)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy?view=teams-ps)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy?view=teams-ps)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy?view=teams-ps)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy?view=teams-ps)

### <a name="example-1"></a>Örnek 1

Burada, Zamanlama Sahibi özelliğinin açık olduğu ScheduleOwnerPolicy adlı yeni bir ilke oluşturacağız.

```powershell
New-CsTeamsShiftsPolicy –Identity ScheduleOwnerPolicy  -EnableScheduleOwnerPermissions $true -AccessType UnrestrictedAccess_TeamsApp
```

### <a name="example-2"></a>Örnek 2

Bu örnekte, remy@contoso.com adlı bir kullanıcıya ScheduleOwnerPolicy adlı bir ilke atarız.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName ScheduleOwnerPolicy
```

## <a name="related-articles"></a>İlgili makaleler

- [Teams'de kuruluşunuz için Vardiyalar uygulamasını yönetme](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)