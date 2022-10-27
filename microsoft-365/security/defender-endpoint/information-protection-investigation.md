---
title: Verilerinizi korumak ve güvenlik olayı yanıtını önceliklendirmek için Uç Nokta için Microsoft Defender duyarlılık etiketlerini kullanın
description: Veri tuvaletleri, dlp ve güvenlik olayları içeren olayları korumak, önceliklendirmek ve araştırmak için Uç Nokta için Defender duyarlılık etiketlerini kullanmayı öğrenin.
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
- ContentEngagementFY23
- tier2 - EngageScoreSep2022
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: cdb1d9eb306fd472690cc756fdbe0a1b412d7ab8
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68729951"
---
# <a name="microsoft-defender-for-endpoint-sensitivity-labels-protect-and-prioritize-incident-response"></a>Uç Nokta için Microsoft Defender duyarlılık etiketleri olay yanıtlarını korur ve önceliklendirir

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Tipik bir gelişmiş kalıcı tehdit yaşam döngüsü (veya APT), verilerin kuruluştan *alındığı* nokta olan veri sızdırmayı içerir. Bu gibi durumlarda duyarlılık etiketleri, hangi verilerin korunacak en yüksek öncelikli olduğunu yazarak güvenlik işlemlerinin nereden başlayacağını söyleyebilir.

Uç Nokta için Defender, duyarlılık etiketlerinin kullanılmasıyla güvenlik olaylarının önceliklerinin daha basit hale getirilmesine yardımcı olur. Örneğin duyarlılık etiketleri, hassas bilgileri olan cihazları (gizli bilgiler gibi) içerebilecek olayları hızla tanımlar.

Uç Nokta için Defender'da duyarlılık etiketlerini şu şekilde kullanabilirsiniz.

## <a name="investigate-incidents-that-involve-sensitive-data-on-devices-with-defender-for-endpoint"></a>Uç Nokta için Defender ile cihazlarda hassas veriler içeren olayları araştırma

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

## <a name="related-information-about-sensitivity-labels"></a>Duyarlılık etiketleri hakkında ilgili bilgiler

- [Office 365'da duyarlılık etiketleri hakkında bilgi edinin](../../compliance/sensitivity-labels.md)
- [E-postanın veya Office'in içine duyarlılık etiketi uygulamayı öğrenin](https://support.microsoft.com/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
- [Veri Kaybı Önleme uygularken duyarlılık etiketlerini koşul olarak kullanmayı öğrenin](../../compliance/dlp-sensitivity-label-as-condition.md)