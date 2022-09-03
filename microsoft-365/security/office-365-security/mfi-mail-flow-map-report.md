---
title: Posta akışı haritası
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Yöneticiler, Bağlayıcılar üzerinden ve bağlayıcı kullanmadan kuruluşlarından gelen ve giden posta akışlarını görselleştirmek ve izlemek için Güvenlik & Uyumluluk Merkezi'ndeki Posta akışı panosunda Posta akışı haritasını kullanmayı öğrenebilir.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 36ab396e626f50adc2e5d420563fe100d579bbfc
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67597856"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>Güvenlik & Uyumluluk Merkezi'nde posta akışı haritası

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Güvenlik & Uyumluluk Merkezi'ndeki](https://protection.office.com) [Posta akışı panosundaki Posta akışı](mail-flow-insights-v2.md) **haritası**, postanın kuruluşunuzda nasıl aktığı hakkında içgörü sağlar. Desenleri öğrenmek, anomalileri tanımlamak ve oluşan sorunları düzeltmek için bu bilgileri kullanabilirsiniz.

:::image type="content" source="../../media/mfi-mail-flow-map-widget.png" alt-text="Güvenlik & Uyumluluk Merkezi'ndeki Posta akışı panosundaki Posta akışı eşleme pencere öğesi" lightbox="../../media/mfi-mail-flow-map-widget.png":::

Varsayılan olarak pencere öğesi, *Sankey* diyagramı olarak bilinen grafikte önceki güne ait posta akışı desenini gösterir. Sol ok Sol okunu ![kullanabilirsiniz.](../../media/scc-left-arrow.png) ve farklı günlere ait bilgileri göstermek için sağ ![ok Sağ ok](../../media/scc-right-arrow.png) tuşuna basın. Her farklı renk, farklı bir gelen veya giden bağlayıcı (veya bağlayıcı kullanmadan) üzerinden posta akışını temsil eder. Belirli bir rengin üzerine geldiğinizde, bu bağlayıcı türü için ileti sayısı görüntülenir.

## <a name="report-view-for-the-mail-flow-map"></a>Posta akışı haritası için rapor görünümü

**Posta akışı haritası** pencere öğesine tıkladığınızda **Posta akışı haritası** raporuna götürür.

Aşağıdaki grafikler rapor görünümünde kullanılabilir:

- **Şunun için verileri göster: Genel bakış**: Bu temelde pencere öğesinin daha büyük bir görünümüdür. Belirli bir rengin üzerine geldiğinizde, bu bağlayıcı türü için ileti sayısı görüntülenir.

    :::image type="content" source="../../media/mfi-mail-flow-map-report-overview.png" alt-text="Posta akışı eşleme raporundaki Genel Bakış görünümü" lightbox="../../media/mfi-mail-flow-map-report-overview.png":::

- **Şunun için verileri göster: Ayrıntı**: Bu görünüm bağlayıcılar ve hedef etki alanları hakkındaki ayrıntıları gösterir. En çok gönderen ve alıcı etki alanları listelenir ve geri kalanlar **Da Diğerleri'ne** konur. Belirli bir renk ve bölümün üzerine geldiğinizde ileti sayısı görüntülenir.

    :::image type="content" source="../../media/mfi-mail-flow-map-report-detail.png" alt-text="Posta akışı eşleme raporundaki Ayrıntı görünümü" lightbox="../../media/mfi-mail-flow-map-report-detail.png":::

Rapor görünümünde **Filtreler'e** tıklarsanız **Başlangıç tarihi** ve **Bitiş tarihi** içeren bir tarih aralığı belirtebilirsiniz.

Raporu belirli bir tarih aralığı için bir veya daha fazla alıcıya e-postayla göndermek için **İndirme iste'ye** tıklayın.

Varsa Posta akışı eşlemesinin altında ilgili içgörüler gösterilir (örneğin, [Olası posta döngüsünü düzeltme içgörüleri](mfi-mail-loop-insight.md).

## <a name="details-table-view-for-the-mail-flow-map"></a>Posta akışı eşlemesi için ayrıntılar tablosu görünümü

Rapor görünümünde **Ayrıntılar tablosunu görüntüle'ye** tıklarsanız aşağıdaki bilgiler gösterilir:

- **Tarih**
- **Kategori**
- **Bağlayıcı / Üçüncü taraf hizmet sağlayıcısı**
- **Gönderen/Alıcı etki alanı**
- **İleti sayısı**

Ayrıntılar tablosu görünümünde **Filtreler'e** tıklarsanız, **Başlangıç tarihi** ve **Bitiş tarihi** ile bir tarih aralığı belirtebilirsiniz.

Bir satır seçerseniz, açılır pencerede benzer ayrıntılar gösterilir:

:::image type="content" source="../../media/mfi-mail-flow-map-view-details-table-details.png" alt-text="Posta akışı haritasındaki ayrıntılar tablosundaki Ayrıntılar açılır öğesi" lightbox="../../media/mfi-mail-flow-map-view-details-table-details.png":::

Raporu belirli bir tarih aralığı için bir veya daha fazla alıcıya e-postayla göndermek için **İndirme iste'ye** tıklayın.

Raporlar görünümüne dönmek için **Raporu görüntüle'ye** tıklayın.

## <a name="see-also"></a>Ayrıca bkz.

Posta akışı panosundaki diğer içgörüler hakkında bilgi için [Bkz. Güvenlik & Uyumluluk Merkezi'ndeki Posta akışı içgörüleri](mail-flow-insights-v2.md).
