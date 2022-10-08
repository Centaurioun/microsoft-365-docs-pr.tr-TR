---
author: LanaChin
ms.author: v-lanachin
ms.date: ''
ms.topic: include
audience: admin
ms.service: microsoft-365-frontline
ms.openlocfilehash: a411ff6608f09f7c5eff7f83dcc1dd3a98714378
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68223424"
---
> [!IMPORTANT]
> Bu adımları yalnızca bu makalenin önceki bölümlerindeki [Bağlantı ayarlarını değiştir](#change-connection-settings) bölümündeki betiği kullanarak veya [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance) cmdlet'ini kullanarak açık vardiyaları, açık vardiya isteklerini, değiştirme isteklerini veya izin isteklerini devre dışı bırakmayı seçtiyseniz izleyin. Bu adımın tamamlanması, Vardiyalar'daki özelliği gizler. Bu ikinci adım olmadan, kullanıcılar özelliği Vardiyalar'da görmeye devam eder ve kullanmaya çalışırlarsa "desteklenmeyen işlem" hata iletisini alır.

Vardiyalar'da açık vardiyaları, değiştirme isteklerini ve izin isteklerini gizlemek için, Graph API [zamanlama kaynak türünü](/graph/api/resources/schedule) kullanarak bir WFM örneğine eşlediğiniz her ekip için aşağıdaki parametreleri ```false``` olarak ayarlayın:

- Vardiyaları açma: ```openShiftsEnabled```
- Değiştirme istekleri:  ```swapShiftsRequestsEnabled```
- zaman aşımı istekleri: ```timeOffRequestsEnabled```

Vardiyalar'da açık vardiya isteklerini gizlemek için Vardiyalar'daki **Ayarlar'a** gidin ve **Vardiyaları aç** ayarını kapatın.
