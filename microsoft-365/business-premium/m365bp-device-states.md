---
title: Cihaz durumları
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: İş için Microsoft 365'teki Yönetici giriş Yönetici Cihaz eylemleri listesinde yer alan çeşitli cihaz durumları hakkında bilgi edinin.
ms.openlocfilehash: 07024ea6f4e37e32716c8af3e56f4481104ed975
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66862033"
---
# <a name="device-states-in-microsoft-365-for-business"></a>İş için Microsoft 365'teki cihaz durumları

Bu makale Microsoft 365 İş Ekstra için geçerlidir.

> [!NOTE]
> İş için Microsoft Defender, 1 Mart 2022'de başlayarak Microsoft 365 İş Ekstra müşterilerine dağıtılıyor. Bu teklif, cihazlar için ek güvenlik özellikleri sağlar. [İş için Defender hakkında daha fazla bilgi edinin](../security/defender-business/mdb-overview.md).

**Cihaz eylemleri** listesindeki (Yönetim giriş sayfası \> **Cihaz eylemleri**) cihazlar aşağıdaki durumlarda olabilir.
  
![In the Device actions list, you can see the Devices states.](./../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|**Durum**|**Açıklama**|
|:-----|:-----|
|Intune tarafından yönetilen  |Microsoft 365 İş Ekstra tarafından yönetilir.  |
|Devre dışı bırakma bekliyor  |Microsoft 365 İş Ekstra, şirket verilerini cihazdan kaldırmaya hazırlanıyor.  |
|Devre dışı bırakma sürüyor  |Microsoft 365 İş Ekstra şu anda cihazdan şirket verilerini kaldırıyor.  |
|Devre dışı bırakma başarısız  | Şirket verilerini kaldırma işlemi başarısız oldu.  |
|Devre dışı bırakma iptal edildi  |Devre dışı bırakma eylemi iptal edildi.  |
|Temizleme işlemi beklemede  |Fabrika sıfırlamasının başlatılması bekleniyor.  |
|Temizleme işlemi sürüyor  |Fabrika sıfırlaması gönderildi.  |
|Temizleme başarısız oldu  |Fabrika sıfırlaması yapılamaz.  |
|Silme iptal edildi  |Fabrika silme işlemi iptal edildi.  |
|Uygun olmayan durumda  |Bir eylem beklemede (veya devam ediyor) ancak cihaz 30 günden fazla süreyle iade edilmemiştir.  |
|Silme bekliyor  |Silme eylemi bekliyor.  |
|Bulundu  |Microsoft 365 İş Ekstra cihazı algılamıştır.  |
   

## <a name="see-also"></a>Ayrıca bkz.

[İş için Microsoft 365 planlarının güvenliğini sağlamaya yönelik en iyi yöntemler](../admin/security-and-compliance/secure-your-business-data.md)