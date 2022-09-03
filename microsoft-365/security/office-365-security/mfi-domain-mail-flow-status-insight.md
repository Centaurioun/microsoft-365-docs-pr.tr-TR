---
title: Posta akışı panosundaki en iyi etki alanı posta akışı durumu içgörüleri
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
description: Yöneticiler, MX kayıtlarıyla ilgili posta akışı sorunlarını gidermek için Güvenlik & Uyumluluk Merkezi'ndeki Posta akışı panosundaki En iyi etki alanı posta akışı durumu içgörülerini kullanmayı öğrenebilir.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 525a424babac6d7be1da0abf73a61da723857e8e
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67599615"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Güvenlik & Uyumluluk Merkezi'ndeki en iyi etki alanı posta akışı durumu içgörüleri

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Güvenlik & Uyumluluk Merkezi'ndeki](https://protection.office.com) [Posta akışı panosundaki](mail-flow-insights-v2.md) **En iyi etki alanı posta akışı durumu** içgörüleri, kuruluşunuzun geçerli posta akışı durumunu verir.

Bu içgörü ***, posta akışı*** sorunları yaşayan etki alanlarını belirlemenize ve gidermenize yardımcı olur. Örneğin, etki alanının süresi dolduğundan veya etki alanının MX kaydı yanlış olduğundan etki alanı dış e-posta alamıyor.

:::image type="content" source="../../media/mfi-top-domain-mail-flow-status-widget.png" alt-text="Güvenlik & Uyumluluk Merkezi'ndeki Posta akışı panosundaki En iyi etki alanı akışı durumu pencere öğesi" lightbox="../../media/mfi-top-domain-mail-flow-status-widget.png":::

Pencere öğesinde **Ayrıntıları görüntüle'ye** tıkladığınızda, her **etki alanının durumuyla** ilgili daha fazla ayrıntı gösteren bir Etki alanı durumu açılır öğesi görüntülenir:

- **Etki alanı**
- **Önceki MX kaydı**
- **Geçerli MX kaydı**
- **alma durumunu Email**
- **Etki alanı durumu**: Yeşil onay işareti geçerli MX kaydının (pencere öğesine tıkladığınızda) kayıtta sahip olduğumuz değerle eşleşdiğini ve etki alanının son iki saat içinde e-posta aldığını gösterir.

  Kırmızı X, MX kaydının değiştirildiğini ve etki alanının son 6 saat içinde e-posta almadığını gösterir. Bu, etki alanınızın süresinin dolduğunu veya MX kaydının yanlış güncelleştirildiğini gösterir. Etki alanının süresinin dolduğunu veya etki alanının MX kaydının yanlış olup olmadığını görmek için etki alanı kayıt şirketinize veya DNS barındırma hizmetinize danışın.

Daha fazla etki alanı için aynı bilgileri görmek için **Daha fazla görüntüle'ye** tıklayabilirsiniz.

:::image type="content" source="../../media/mfi-top-domain-mail-flow-status-view-details.png" alt-text="Üst etki alanı posta akışı durumu içgörüsünde Ayrıntılar açılır öğesi" lightbox="../../media/mfi-top-domain-mail-flow-status-view-details.png":::

## <a name="see-also"></a>Ayrıca bkz.

Posta akışı panosundaki diğer içgörüler hakkında bilgi için [Bkz. Güvenlik & Uyumluluk Merkezi'ndeki Posta akışı içgörüleri](mail-flow-insights-v2.md).
