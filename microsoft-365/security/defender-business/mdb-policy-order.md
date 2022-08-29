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
ms.date: 08/11/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 4d3f2f7a04891fdf3e08f06d6744894e18e944dd
ms.sourcegitcommit: 9b10e56b9e83f3a80757fa6108bebd1d80cf4178
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2022
ms.locfileid: "67320360"
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