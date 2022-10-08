---
author: LanaChin
ms.author: v-lanachin
ms.date: ''
ms.topic: include
audience: admin
ms.service: microsoft-365-frontline
ms.openlocfilehash: ec11ee0ed02d05da683caeb025e52522444d8215
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68223446"
---
> [!NOTE]
> Her iki bağlantı için de Microsoft 365 sistem hesabı aynı olmalıdır. Değilse, "Bu belirlenen aktör profilinin ekip sahipliği ayrıcalıkları yok" hata iletisini alırsınız.

Bir ekibin eşlemesini bir bağlantıdan kaldırmak ve başka bir bağlantıyla eşlemek istiyorsanız:

1. [Ortamınızı ayarlayın](#set-up-your-environment) (henüz ayarlamadıysanız).
1. Bağlantı için tüm ekip eşlemelerinin listesini görüntüleyin.

    ```powershell
    Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Bağlantıdan bir ekip eşlemesini kaldırın.

    ```powershell
    Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId>
    ```

1. Ekibi başka bir bağlantıyla eşleyin.

    ```powershell
    New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId> -WfmTeamId <SiteId> -TimeZone <TimeZone>
    ```

Daha fazla bilgi için bkz. [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap), [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap) ve [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap).
