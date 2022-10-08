---
title: Toplu şikayet düzeyi değerleri
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- m365-security
description: Yöneticiler, Exchange Online Protection (EOP) içinde kullanılan toplu şikayet düzeyi (BCL) değerleri hakkında bilgi edinebilir.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 1e7da11302109a17d9a80c466aa1ed338a0cc6ae
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68066772"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>EOP'de toplu şikayet düzeyi (BCL)

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online posta kutusu olmayan Exchange Online veya tek başına Exchange Online Protection (EOP) kuruluşlarında posta kutuları olan Microsoft 365 kuruluşlarında EOP, toplu postacılardan gelen iletilere toplu şikayet düzeyi (BCL) atar. BCL, iletiye bir X üst bilgisinde eklenir ve iletileri istenmeyen posta olarak tanımlamak için kullanılan [istenmeyen posta güvenilirlik düzeyine (SCL)](spam-confidence-levels.md) benzer. Daha yüksek bir BCL, toplu iletinin şikayet oluşturma olasılığının daha yüksek olduğunu gösterir (ve bu nedenle istenmeyen posta olma olasılığı daha yüksektir). Microsoft, toplu postayı tanımlamak ve uygun BCL'yi belirlemek için hem iç hem de üçüncü taraf kaynakları kullanır.

Toplu posta gönderenler, gönderme düzenleri, içerik oluşturma ve alıcı alma uygulamalarında farklılık gösterir. İyi bir toplu posta gönderenler, abonelerine ilgili içeriğe sahip istenen iletileri gönderir. Bu iletiler, alıcılardan birkaç şikayet oluşturur. Diğer toplu posta gönderenler istenmeyen postalara benzeyen ve alıcılardan birçok şikayet oluşturan istenmeyen iletiler gönderir. Toplu postacıdan gelen iletiler toplu posta veya gri posta olarak bilinir.

 İstenmeyen posta filtreleme, iletileri BCL eşiğine (varsayılan değer veya belirttiğiniz değer) göre **Toplu e-posta** olarak işaretler ve iletide belirtilen eylemi uygular (varsayılan eylem, iletiyi alıcının Gereksiz Email klasörüne teslim etmektir). Daha fazla bilgi için bkz. [İstenmeyen posta önleme ilkelerini yapılandırma](configure-your-spam-filter-policies.md) ve [Gereksiz e-posta ile toplu e-posta arasındaki fark nedir?](what-s-the-difference-between-junk-email-and-bulk-email.md)

BCL eşikleri aşağıdaki tabloda açıklanmıştır.

|Bcl|Açıklama|
|:---:|---|
|0|İleti toplu gönderenden değil.|
|1, 2, 3|İleti, birkaç şikayet oluşturan toplu gönderenden geliyor.|
|4, 5, 6, 7<sup>\*</sup>|İleti, karışık sayıda şikayet oluşturan toplu bir gönderenden geliyor.|
|8, 9|İleti, çok sayıda şikayet oluşturan toplu bir gönderenden geliyor.|

<sup>\*</sup> Bu, istenmeyen posta önleme ilkelerinde kullanılan varsayılan eşik değeridir.
