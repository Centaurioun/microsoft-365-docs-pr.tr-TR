---
title: Olası posta döngüsü içgörüsünü düzeltme
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.collection: m365-security
ms.localizationpriority: medium
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Yöneticiler, kuruluşlarındaki posta döngülerini tanımlamak ve düzeltmek için Güvenlik & Uyumluluk Merkezi'ndeki Posta akışı panosundaki Olası posta döngüsünü düzeltme içgörülerini kullanmayı öğrenebilir.
ms.subservice: mdo
ms.service: microsoft-365-security
search.appverid: met150
ms.openlocfilehash: 93c623f56e9a4a7bc5dc1ee362f3e9135e3d634a
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68091773"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Güvenlik & Uyumluluk Merkezi'nde olası posta döngüsü içgörülerini düzeltme

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Posta döngüleri hatalıdır çünkü:

- Sistem kaynaklarını boşa harcarlar.
- Kuruluşunuzun posta hacmi kotasını tüketir.
- Özgün ileti gönderenlerine kafa karıştırıcı teslim dışı raporlar (NDR'ler veya geri dönen iletiler olarak da bilinir) gönderirler.

[Güvenlik & Uyumluluk Merkezi'ndeki](https://protection.office.com) [Posta akışı panosunun](mail-flow-insights-v2.md) **Sizin için önerilir** alanında yer alan **Olası posta döngüsü** içgörülerini düzeltme, kuruluşunuzda bir posta döngüsü algılandığında size bildirir.

Bu içgörü yalnızca koşul algılandıktan sonra görünür (posta döngüleriniz yoksa içgörüleri görmezsiniz).

:::image type="content" source="../../media/mfi-fix-possible-mail-loop.png" alt-text="Posta akışı panosunun Sizin için önerilen alanındaki Yavaş posta akışı kurallarını düzeltme içgörüleri" lightbox="../../media/mfi-fix-possible-mail-loop.png":::

Pencere öğesinde **Ayrıntıları görüntüle'ye** tıkladığınızda, daha fazla bilgi içeren bir açılır pencere görüntülenir:

- **Etki alanı**
- **İleti sayısı: Döngüden** etkilenen **iletilerin bir** örneğinin [ileti izleme](message-trace-scc.md) sonuçlarını görmek için Örnek iletileri görüntüle'ye tıklayabilirsiniz.
- **Etki alanı türü**" Örneğin, Yetkili veya Yetkili Değil.
- **MX kaydı**: Etki alanı için MX kaydının ana bilgisayar (**Posta sunucusu**) ve **Öncelik** değerleri.
- **Döngü nedeni** ve **Düzeltme**: En yaygın posta döngüsü senaryolarını belirleyecek ve döngünün düzeltilmesi için önerilen eylemleri sağlayacağız.

:::image type="content" source="../../media/mfi-fix-possible-mail-loop-details.png" alt-text="Olası posta döngüsünü düzelt içgörüsünde Ayrıntıları görüntüle'ye tıkladıktan sonra görüntülenen Ayrıntılar açılır öğesi" lightbox="../../media/mfi-fix-possible-mail-loop-details.png":::

## <a name="see-also"></a>Ayrıca bkz.

Posta akışı panosundaki diğer içgörüler hakkında bilgi için [Bkz. Güvenlik & Uyumluluk Merkezi'ndeki Posta akışı içgörüleri](mail-flow-insights-v2.md).
