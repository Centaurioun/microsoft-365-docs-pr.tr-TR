---
author: LanaChin
ms.author: v-lanachin
ms.date: ''
ms.topic: include
audience: admin
ms.service: microsoft-365-frontline
ms.openlocfilehash: 30186298f83ea1a1e1721b9dc31a77eb4af33975
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68223490"
---
Bağlantının hata ayrıntılarını gösteren bir rapor çalıştırabilirsiniz. Raporda başarılı ve başarısız olan ekip ve kullanıcı eşlemeleri listelenir. Ayrıca, bağlantıyla ilişkili hesaplarla ilgili sorunlar hakkında da bilgi sağlar.

1. [Ortamınızı ayarlayın](#set-up-your-environment) (henüz ayarlamadıysanız).
1. Bağlantı için hata raporlarının listesini alın.

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Belirli bir hata raporunu görüntülemek için aşağıdaki komutu çalıştırın:

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ErrorReportId <ErrorReportId>
    ```

Daha fazla bilgi için bkz. [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport).
