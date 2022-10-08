---
title: Posta akışı panosunda kabul edilen olmayan etki alanı raporu
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.collection: m365-security
ms.localizationpriority: medium
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Yöneticiler, Microsoft 365'te gönderenin etki alanının yapılandırılmadığı şirket içi kuruluşunuzdan gelen iletileri izlemek için Güvenlik & Uyumluluk Merkezi'ndeki Posta akışı panosunda Kabul edilen olmayan etki alanı raporunu kullanmayı öğrenebilir.
ms.subservice: mdo
ms.service: microsoft-365-security
search.appverid: met150
ms.openlocfilehash: 4073014a3266891832a1b0b18cea40df71b80b6d
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68083967"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>Güvenlik & Uyumluluk Merkezi'nde kabul edilen olmayan etki alanı raporu

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Güvenlik & Uyumluluk Merkezi'ndeki](https://protection.office.com) [Posta akışı panosundaki](mail-flow-insights-v2.md) **Kabul edilen olmayan etki alanı** raporu, gönderenin etki alanının Microsoft 365 kuruluşunuzda kabul edilen bir etki alanı olarak yapılandırılmadığı şirket içi e-posta kuruluşunuzdan gelen iletiler hakkında bilgi görüntüler.

Microsoft 365, bu iletilerin amacının kötü amaçlı olduğunu kanıtlayan verilerimiz varsa bu iletileri kısıtlayabilir. Bu nedenle, neler olduğunu anlamanız ve sorunu çözmeniz önemlidir.

:::image type="content" source="../../media/mfi-non-accepted-domain-report-widget.png" alt-text="Güvenlik & Uyumluluk Merkezi'ndeki Posta akışı panosundaki Kabul edilen olmayan etki alanı pencere öğesi" lightbox="../../media/mfi-non-accepted-domain-report-widget.png":::

## <a name="report-view-for-the-non-accepted-domain-report"></a>Kabul edilen olmayan etki alanı raporu için rapor görünümü

**Kabul edilen olmayan etki alanı** pencere öğesindeki grafiğe tıkladığınızda **kabul edilen etki alanı raporuna** yönlendirilirsiniz.

Varsayılan olarak, etkilenen tüm bağlayıcılar için etkinlik gösterilir. **Verileri göster'e** tıklarsanız açılan listeden belirli bir bağlayıcı seçebilirsiniz.

Grafikteki bir veri noktasının (gün) üzerine geldiğinizde bağlayıcının toplam ileti sayısını görürsünüz.

:::image type="content" source="../../media/mfi-non-accepted-domain-report-overview-view.png" alt-text="Kabul edilen etki alanı raporundaki Rapor görünümü" lightbox="../../media/mfi-non-accepted-domain-report-overview-view.png":::

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>Kabul edilen olmayan etki alanı raporu için ayrıntılar tablosu görünümü

Rapor görünümünde **Ayrıntılar tablosunu görüntüle'ye** tıklarsanız aşağıdaki bilgiler gösterilir:

- **Tarih**
- **Gelen bağlayıcı adı**
- **Gönderen etki alanı**
- **İleti sayısı**
- **Örnek iletiler**: Etkilenen iletilerin bir örneğinin ileti kimlikleri.

Ayrıntılar tablosu görünümünde **Filtreler'e** tıklarsanız, **Başlangıç tarihi** ve **Bitiş tarihi** ile bir tarih aralığı belirtebilirsiniz.

Raporu belirli bir tarih aralığı için bir veya daha fazla alıcıya e-postayla göndermek için **İndirme iste'ye** tıklayın.

Tabloda bir satır seçtiğinizde, aşağıdaki bilgileri içeren bir açılır öğe görüntülenir:

- **Tarih**
- **Gelen bağlayıcı adı**
- **Gönderen etki alanı**
- **İleti sayısı**
- **Örnek iletiler**: Etkilenen **iletilerin bir örneğinin** [ileti izleme](message-trace-scc.md) sonuçlarını görmek için Örnek iletileri görüntüle'ye tıklayabilirsiniz.

:::image type="content" source="../../media/mfi-non-accepted-domain-report-details-flyout.png" alt-text="Kabul edilen etki alanı raporundaki Ayrıntılar tablosu görünümünde bir satır seçtikten sonra Ayrıntılar açılır öğesi" lightbox="../../media/mfi-non-accepted-domain-report-details-flyout.png":::

Raporlar görünümüne dönmek için **Raporu görüntüle'ye** tıklayın.

## <a name="related-topics"></a>İlgili konular

Posta akışı panosundaki diğer içgörüler hakkında bilgi için [Bkz. Güvenlik & Uyumluluk Merkezi'ndeki Posta akışı içgörüleri](mail-flow-insights-v2.md).
