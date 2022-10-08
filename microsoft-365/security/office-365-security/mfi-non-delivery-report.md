---
title: Posta akışı panosunda teslim edilmedi raporu
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
description: Yöneticiler, kuruluşunuzdaki gönderenlerden gelen teslim dışı raporlarda (NDR'ler veya geri dönen iletiler olarak da bilinir) en sık karşılaşılan hata kodlarını izlemek için Güvenlik & Uyumluluk Merkezi'ndeki Posta akışı panosundaki Teslim edilmedi ayrıntıları raporunu kullanmayı öğrenebilir.
ms.subservice: mdo
ms.service: microsoft-365-security
search.appverid: met150
ms.openlocfilehash: 6c2069a0896fc77191602b9df8b6c24cc2bdb007
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68091795"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>Güvenlik & Uyumluluk Merkezi'nde teslim edilmedi raporu

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Güvenlik & Uyumluluk Merkezi'ndeki](https://protection.office.com) [Posta akışı panosundaki](mail-flow-insights-v2.md) **Teslim edilmedi raporu**, kuruluşunuzdaki kullanıcılar için teslim edilmedi raporlarında (NDR'ler veya geri dönen iletiler olarak da bilinir) en çok karşılaşılan hata kodlarını gösterir. Bu rapor, e-posta teslim sorunlarını giderebilmeniz için NDR'lerin ayrıntılarını gösterir.

:::image type="content" source="../../media/mfi-non-delivery-report-widget.png" alt-text="Güvenlik & Uyumluluk Merkezi'ndeki Posta akışı panosundaki Teslim edilmedi raporu pencere öğesi" lightbox="../../media/mfi-non-delivery-report-widget.png":::

## <a name="report-view-for-the-non-delivery-report"></a>Teslim edilmedi raporu için rapor görünümü

**Teslim edilmedi raporu** pencere öğesine tıkladığınızda **teslim edilmedi raporu** açılır.

Varsayılan olarak, tüm hata kodları için etkinlik gösterilir. **Verileri göster'e** tıklarsanız açılan listeden belirli bir hata kodunu seçebilirsiniz.

Grafikte belirli bir günde belirli bir rengin (hata kodu) üzerine geldiğinizde hatanın toplam ileti sayısını görürsünüz.

:::image type="content" source="../../media/mfi-non-delivery-report-overview-view.png" alt-text="Kabul edilen etki alanı raporundaki Rapor görünümü" lightbox="../../media/mfi-non-delivery-report-overview-view.png":::

## <a name="details-table-view-for-the-non-delivery-report"></a>Teslim edilmedi raporu için ayrıntılar tablosu görünümü

Rapor görünümünde **Ayrıntılar tablosunu görüntüle'ye** tıklarsanız aşağıdaki bilgiler gösterilir:

- **Tarih**
- **Teslim edilemez rapor kodu**
- **Sayısı**
- **Örnek iletiler**: Etkilenen iletilerin bir örneğinin ileti kimlikleri.

Ayrıntılar tablosu görünümünde **Filtreler'e** tıklarsanız, **Başlangıç tarihi** ve **Bitiş tarihi** ile bir tarih aralığı belirtebilirsiniz.

Raporu belirli bir tarih aralığı için bir veya daha fazla alıcıya e-postayla göndermek için **İndirme iste'ye** tıklayın.

Tabloda bir satır seçtiğinizde, aşağıdaki bilgileri içeren bir açılır öğe görüntülenir:

- **Tarih**
- **Teslim edilmedi rapor kodu**: Belirli bir hata kodunun nedenleri ve çözümleri hakkında daha fazla bilgi için bağlantıya tıklayabilirsiniz.
- **Sayısı**
- **Örnek iletiler**: Etkilenen **iletilerin bir örneğinin** [ileti izleme](message-trace-scc.md) sonuçlarını görmek için Örnek iletileri görüntüle'ye tıklayabilirsiniz.

:::image type="content" source="../../media/mfi-non-delivery-report-details-flyout.png" alt-text="Teslim edilmedi raporundaki Ayrıntılar tablosu görünümünde bir satır seçtikten sonra Ayrıntılar açılır öğesi" lightbox="../../media/mfi-non-delivery-report-details-flyout.png":::

## <a name="related-topics"></a>İlgili konular

Posta akışı panosundaki diğer içgörüler hakkında bilgi için [Bkz. Güvenlik & Uyumluluk Merkezi'ndeki Posta akışı içgörüleri](mail-flow-insights-v2.md).
