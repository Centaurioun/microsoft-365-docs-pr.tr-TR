---
title: Olay yanıtına öncelik tanımak için duyarlılık etiketlerini kullanın
description: Olaylara öncelik vermek ve olayları araştırmak için duyarlılık etiketlerini kullanmayı öğrenin
keywords: bilgi, koruma, veri, kayıp, önleme,etiketler, dlp, olay, araştırma, araştırma
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2 - EngageScoreSep2022
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 5dcc47dde921eb2e8c94fbb38b828bfc2f1c2d5b
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68646759"
---
# <a name="use-sensitivity-labels-to-prioritize-incident-response"></a>Olay yanıtına öncelik tanımak için duyarlılık etiketlerini kullanın

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Tipik bir gelişmiş kalıcı tehdit yaşam döngüsü, veri sızdırmayı içerir. Bir güvenlik olayında, şirket verilerinin ve bilgilerinin korunması için hassas dosyaların tehlikeye atılacağı araştırmalara öncelik verebilmek önemlidir.

Uç Nokta için Defender, duyarlılık etiketlerinin kullanılmasıyla güvenlik olaylarının önceliklendirilmesini çok daha basit hale getirmeye yardımcı olur. Duyarlılık etiketleri, gizli bilgiler gibi hassas bilgilere sahip cihazları içerebilecek olayları hızla tanımlar.

## <a name="investigate-incidents-that-involve-sensitive-data"></a>Hassas veriler içeren olayları araştırma

Olay araştırmasına öncelik vermek için veri duyarlılığı etiketlerini kullanmayı öğrenin.

> [!NOTE]
> Etiketler Windows 10, sürüm 1809 veya üzeri için algılandı ve Windows 11.

1. Microsoft 365 Defender portalında **Olaylar & uyarılar** \> **Olaylar'ı** seçin.

2. **Veri duyarlılığı** sütununu görmek için sağa kaydırın. Bu sütun, olaylarla ilgili cihazlarda gözlemlenen duyarlılık etiketlerini yansıtır ve hassas dosyaların olaydan etkilenip etkilenmeyebileceğini gösterir.

   :::image type="content" source="images/data-sensitivity-column.png" alt-text="Veri duyarlılığı sütunundaki Çok gizli seçeneği" lightbox="images/data-sensitivity-column.png":::

    **Ayrıca Veri duyarlılığına** göre filtreleyebilirsiniz

    :::image type="content" source="images/data-sensitivity-filter.png" alt-text="Veri duyarlılığı filtresi" lightbox="images/data-sensitivity-filter.png":::

3. Daha fazla araştırma yapmak için olay sayfasını açın.

   :::image type="content" source="images/incident-page.png" alt-text="Olay sayfası ayrıntıları" lightbox="images/incident-page.png":::

4. Duyarlılık etiketlerine sahip dosyaları depolayacak cihazları belirlemek için **Cihazlar** sekmesini seçin.

   :::image type="content" source="images/investigate-devices-tab.png" alt-text="Cihaz sekmesi" lightbox="images/investigate-devices-tab.png":::

5. Hassas verileri depolayan cihazları seçin ve hangi dosyaların etkilenebileceğini belirlemek için zaman çizelgesinde arama yapın ve ardından verilerin korunduğundan emin olmak için uygun eylemi gerçekleştirin.

   Veri duyarlılığı etiketlerini arayarak cihaz zaman çizelgesinde gösterilen olayları daraltabilirsiniz. Bunu yaptığınızda yalnızca etiket adı yazan dosyalarla ilişkili olaylar gösterilir.

   :::image type="content" source="images/machine-timeline-labels.png" alt-text="Etikete göre daraltılmış arama sonuçlarına sahip cihaz zaman çizelgesi" lightbox="images/machine-timeline-labels.png":::

> [!TIP]
> Bu veri noktaları gelişmiş avlanmada 'DeviceFileEvents' aracılığıyla da kullanıma sunulur ve gelişmiş sorguların ve zamanlama algılamanın duyarlılık etiketlerini ve dosya koruma durumunu dikkate almasını sağlar.
