---
author: LanaChin
ms.author: v-lanachin
ms.date: ''
ms.topic: include
audience: admin
ms.service: microsoft-365-frontline
ms.openlocfilehash: beabbc18474a4454fbcfa448b76898de8af14c1b
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68223512"
---
Bağlantı ayarlarını değiştirmek için bu betiği kullanın. Değiştirebileceğiniz ayarlar arasında WFM hizmet hesabınız ve parolanız, Microsoft 365 sistem hesabınız, ekip eşlemeleri ve eşitleme ayarları yer alır.

Eşitleme ayarları eşitleme sıklığını (dakika cinsinden) ve WFM sisteminizle Vardiyalar arasında eşitlenen zamanlama verilerini içerir. Zamanlama verileri aşağıdaki parametrelerde tanımlanır. [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector) komutunu çalıştırarak görüntüleyebilirsiniz.

- **enabledConnectorScenarios** parametresi, WFM sisteminizden Shifts ile eşitlenen verileri tanımlar. Seçenekler şunlardır: `Shift`, `SwapRequest`, `UserShiftPreferences``OpenShift`, , `OpenShiftRequest`, `TimeOff`, `TimeOffRequest`.
- **enabledWfiScenarios** parametresi, Vardiyalar'dan WFM sisteminize eşitlenen verileri tanımlar. Seçenekler : `SwapRequest`, `OpenShiftRequest`, `TimeOffRequest`, `UserShiftPreferences`.

    > [!NOTE]
    > Vardiyalar ve WFM sisteminiz arasında açık vardiyaları eşitlememeyi, vardiya isteklerini açmamayı, değiştirme isteklerini veya izin isteklerini değiştirmemeyi seçerseniz, Vardiyalar'da özelliği gizlemek için yapmanız gereken başka bir adım vardır. Bu betiği çalıştırdıktan sonra, bu makalenin devamında [Açık vardiyaları devre dışı bırakma, vardiya isteklerini açma, değiştirme istekleri ve izin istekleri](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) bölümündeki adımları izlediğinize emin olun.

> [!IMPORTANT]
> Değiştirmek istemediğiniz ayarlar için, betik tarafından istendiğinde özgün ayarları yeniden girmeniz gerekir.
