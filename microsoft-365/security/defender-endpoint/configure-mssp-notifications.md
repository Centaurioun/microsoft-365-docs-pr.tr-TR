---
title: MSSP'lere gönderilen uyarı bildirimlerini yapılandırma
description: MSSP'lere gönderilen uyarı bildirimlerini yapılandırma
keywords: yönetilen güvenlik hizmeti sağlayıcısı, mssp, yapılandırma, tümleştirme
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 81f2d696ba1f66316a2623539cee841f35e267bd
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68638510"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a>MSSP'lere gönderilen uyarı bildirimlerini yapılandırma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)

> [!NOTE]
> Bu adım, MSSP müşterisi veya MSSP tarafından yapılabilir. MSSP müşterisi adına bunu yapılandırmak için MSSP'lere uygun izinler verilmelidir.

Portala erişim verildikten sonra, kiracıyla ilişkili uyarılar oluşturulduğunda ve koşullar ayarlandığında e-postaların MSSP'lere gönderilmesi için uyarı bildirim kuralları oluşturulabilir.

Daha fazla bilgi için bkz. [Uyarı bildirimleri için kurallar oluşturma](configure-email-notifications.md#create-rules-for-alert-notifications).

Bu onay kutuları işaretlenmelidir:

- **Kuruluş adını ekle** - Müşteri adı e-posta bildirimlerine eklenir
- **Kiracıya özgü portal bağlantısını ekle** - Uyarı bağlantısı URL'si, hedef kiracı portalına doğrudan erişime izin veren kiracıya özgü parametreye (tid=target_tenant_id) sahip olur

## <a name="related-topics"></a>İlgili konular

- [Portala MSSP erişimi ver](grant-mssp-access.md)
- [MSSP müşteri portalına erişin](access-mssp-portal.md)
- [Müşteri kiracı uyarılarını getir](fetch-alerts-mssp.md)
