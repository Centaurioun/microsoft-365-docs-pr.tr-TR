---
title: İstenmeyen posta güvenilirlik düzeyi
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
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- m365-security
ms.custom:
- seo-marvel-apr2020
description: Yöneticiler, Exchange Online Protection (EOP) içindeki iletilere uygulanan istenmeyen posta güvenilirlik düzeyi (SCL) hakkında bilgi edinebilir.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 52287e2e264cd8b6281bc7b0f85b315cc0047494
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68082581"
---
# <a name="spam-confidence-level-scl-in-eop"></a>EOP'de istenmeyen posta güvenilirlik düzeyi (SCL)

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

posta kutuları Exchange Online olmayan Exchange Online veya tek başına Exchange Online Protection (EOP) kuruluşlarında posta kutuları olan Microsoft 365 kuruluşlarında, gelen iletiler EOP'de istenmeyen posta filtrelemeden geçer ve bir istenmeyen posta puanı atanır. Bu puan, X üst bilgisindeki iletiye eklenen tek bir istenmeyen posta güvenilirlik düzeyine (SCL) eşlenir. Daha yüksek bir SCL, iletinin istenmeyen posta olma olasılığının daha yüksek olduğunu gösterir. EOP, ileti üzerinde SCL'yi temel alarak işlem uygular.

SCL'nin anlamı ve iletilerde gerçekleştirilen varsayılan eylemler aşağıdaki tabloda açıklanmıştır. İstenmeyen posta filtreleme kararına göre iletilerde gerçekleştirebileceğiniz eylemler hakkında daha fazla bilgi için bkz. [EOP'de istenmeyen posta önleme ilkelerini yapılandırma](configure-your-spam-filter-policies.md).

|Scl|Tanım|Varsayılan eylem|
|:---:|---|---|
|-1|İleti istenmeyen posta filtrelemeyi atladı. Örneğin, ileti güvenilir bir gönderenden, güvenilir bir alıcıya gönderildi veya IP İzin Ver Listesi'nde bir e-posta kaynak sunucusundan geliyor. Daha fazla bilgi için bkz. [EOP'de güvenilir gönderen listeleri oluşturma](create-safe-sender-lists-in-office-365.md).|İletiyi alıcıların gelen kutusuna teslim edin.|
|0, 1|İstenmeyen posta filtreleme, iletinin istenmeyen posta olmadığını belirledi.|İletiyi alıcıların gelen kutusuna teslim edin.|
|5, 6|İstenmeyen posta filtrelemesi iletiyi **İstenmeyen Posta** olarak işaretledi|İletiyi alıcıların Önemsiz Email klasörüne teslim edin.|
|9|İstenmeyen posta filtrelemesi iletiyi **Yüksek güvenilirlikli istenmeyen posta** olarak işaretledi|İletiyi alıcıların Önemsiz Email klasörüne teslim edin.|

SCL 2, 3, 4, 7 ve 8'in istenmeyen posta filtrelemesi tarafından kullanılmadığını fark edeceksiniz.

İletilerde SCL'yi damgalama amacıyla posta akışı kurallarını (taşıma kuralları olarak da bilinir) kullanabilirsiniz. SCL'yi ayarlamak için bir posta akışı kuralı kullanırsanız, 5 veya 6 değerleri **İstenmeyen Posta** için istenmeyen posta filtreleme eylemini tetikler ve 7, 8 veya 9 değerleri **yüksek güvenilirlikli istenmeyen posta** için istenmeyen posta filtreleme eylemini tetikler. Daha fazla bilgi için bkz. [İletilerde istenmeyen posta güvenilirlik düzeyini (SCL) ayarlamak için posta akışı kurallarını kullanma](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).

SCL'ye benzer şekilde, toplu şikayet düzeyi (BCL) hatalı toplu e-postayı ( _gri posta_ olarak da bilinir) tanımlar. Daha yüksek bir BCL, toplu posta iletisinin şikayet oluşturma olasılığının daha yüksek olduğunu gösterir (ve bu nedenle istenmeyen posta olma olasılığı daha yüksektir). İstenmeyen posta önleme ilkelerinde BCL eşiğini yapılandırabilirsiniz. Daha fazla bilgi için bkz. [EOP'de istenmeyen posta önleme ilkelerini yapılandırma](configure-your-spam-filter-policies.md), [EOP'de toplu şikayet düzeyi (BCL)](bulk-complaint-level-values.md) ve [Gereksiz e-posta ile toplu e-posta arasındaki fark nedir?](what-s-the-difference-between-junk-email-and-bulk-email.md).

****

![LinkedIn Learning kısa simgesi.](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Microsoft 365'i yeni mi kullanıyorsunuz?** LinkedIn Learning tarafından size getirilen **Microsoft 365 yöneticileri ve BT uzmanları** için ücretsiz video kurslarını keşfedin.
