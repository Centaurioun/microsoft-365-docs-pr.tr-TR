---
author: LanaChin
ms.author: v-lanachin
ms.date: ''
ms.topic: include
audience: admin
ms.service: microsoft-365-frontline
ms.openlocfilehash: 348370981c75fd0ca435b5c7f58a96f5790df11b
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68223468"
---
E-postada aldığınız işlem kimliğini kullanarak ayarladığınız bağlantının durumunu denetlemek için:

1. [Ortamınızı ayarlayın](#set-up-your-environment) (henüz ayarlamadıysanız).
1. Aşağıdaki komutu çalıştırın. Bu komut, bağlantı için ekip eşlemelerinin genel durumunu verir.

    ``` powershell
    Get-CsTeamsShiftsConnectionOperation -OperationId <YourOperationId>
    ```

Daha fazla bilgi için bkz. [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation).
