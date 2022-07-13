---
title: İlke sırasını İş için Microsoft Defender anlama
description: İş için Defender ile şirket cihazlarınızı korumaya yönelik siber güvenlik ilkeleriyle öncelik sırası hakkında bilgi edinin.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 361a1a08569f24c83498fddeb0e4c2b9bd8c5d02
ms.sourcegitcommit: fa90763559239c4c46c5e848939126763879d8e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2022
ms.locfileid: "66770887"
---
# <a name="understand-policy-order-in-microsoft-defender-for-business"></a>İlke sırasını İş için Microsoft Defender anlama

## <a name="policy-order-in-defender-for-business"></a>İş için Defender'da ilke sırası

İş için Defender, çalışanlarınızın kullandığı cihazların korunduğundan emin olmak için önceden tanımlanmış ilkeler içerir. Güvenlik ekibiniz de yeni ilkeler ekleyebilir. Örneğin, bazı cihazlara belirli ayarları ve diğer cihazlara farklı ayarları uygulamak istediğinizi varsayalım. Bunu yapmak için yeni nesil koruma ilkeleri veya güvenlik duvarı ilkeleri gibi ilkeler ekleyebilirsiniz.

İlkeler eklendikçe bir öncelik sırası atandığını fark edeceksiniz. Tanımladığınız ilkelerin öncelik sırasını düzenleyebilirsiniz, ancak varsayılan ilkeler için öncelik sırasını değiştiremezsiniz. Örneğin, Windows istemci cihazlarınız için üç yeni nesil koruma ilkeniz olduğunu varsayalım. Bu durumda, varsayılan ilkeniz öncelik olarak 3 numaradır. İlkelerinizin 1 ve 2 numaralı sırasını değiştirebilirsiniz, ancak varsayılan ilke listenizde 3 numarada kalır. 

**Birden çok ilke hakkında hatırlamanız gereken önemli şey, cihazların yalnızca ilk uygulanan ilkeyi almasıdır.** Önceki üç yeni nesil ilke örneğimize bakarak, üç ilkenin de hedeflediği cihazlarınız olduğunu varsayalım. Bu durumda, bu cihazlar ilke numarası 1'i alır, ancak 2 ve 3 numaralı ilkeleri almaz. 


## <a name="key-points-to-remember-about-policy-order"></a>İlke sırası hakkında hatırlanması gereken önemli noktalar

- İlkelere öncelik sırası atanır.
- Cihazlar yalnızca ilk uygulanan ilkeyi alır.
- İlkelerin öncelik sırasını değiştirebilirsiniz.
- Varsayılan ilkelere en düşük öncelik sırası verilir.

## <a name="next-steps"></a>Sonraki adımlar

- [İş için Defender'ı kullanmaya başlama](mdb-get-started.md)
- [Cihazları yönetme](mdb-manage-devices.md)
- [İş için Defender'da olayları görüntüleme ve yönetme](mdb-view-manage-incidents.md)
- [İş için Defender'da tehditlere yanıt verme ve tehditleri azaltma](mdb-respond-mitigate-threats.md)
- [İşlem merkezindeki düzeltme eylemlerini gözden geçirme](mdb-review-remediation-actions.md)