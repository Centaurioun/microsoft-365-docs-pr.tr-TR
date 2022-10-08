---
title: Kimlik avı e-posta saldırısı örneği
description: Bir kimlik avı saldırısının örnek analizinde ilerleyin.
keywords: olaylar, uyarılar, araştırma, bağıntı, saldırı, makineler, cihazlar, kullanıcılar, kimlik, kimlik, posta kutusu, e-posta, 365, Microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-firstincident
- highpri
- tier1
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bb7476a4608d7d89fa522529914a0f075311b8cd
ms.sourcegitcommit: 99b174a8d431092b3cf7d650593248671297fd91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68297870"
---
# <a name="example-of-a-phishing-email-attack"></a>Kimlik avı e-posta saldırısı örneği

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Microsoft 365 Defender, e-posta yoluyla gönderilen kötü amaçlı eklerin tespit edilmesine yardımcı olabilir ve güvenlik analistleri, e-posta ekleri gibi Office 365 gelen tehditler hakkında görünürlüğe sahip olabilir.

Örneğin, bir analiste çok aşamalı bir olay atanmıştır.
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-incident.png" alt-text="Çok aşamalı bir olay" lightbox="../../media/first-incident-path-phishing/first-incident-phishing-incident.png":::

Olayın **Uyarılar** sekmesinde, Office 365 için Defender ve Microsoft Defender for Cloud Apps uyarıları görüntülenir. Analist, e-posta iletileri uyarılarını seçerek Office 365 için Defender uyarılarında detaya gidebilir. Uyarının ayrıntıları yan bölmede görüntülenir.

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png" alt-text="E-posta uyarısı" lightbox="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png":::
 
Aşağı kaydırarak, etkilenen kötü amaçlı dosyaları ve kullanıcıyı gösteren daha fazla bilgi görüntülenir.

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-impact.png" alt-text="E-posta uyarısının kullanıcı ve dosya etkisi" lightbox="../../media/first-incident-path-phishing/first-incident-phishing-impact.png":::
  
**Uyarı sayfasını aç'ı** seçtiğinizde, bağlantıyı seçerek çeşitli bilgilerin daha ayrıntılı olarak görüntülenebileceği belirli bir uyarıya yönlendirilirsiniz. Gerçek e-posta iletisi, panelin alt kısmındaki **Gezgin'de iletileri görüntüle'yi** seçerek görüntülenebilir.
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png" alt-text="Uyarının ayrıntıları" lightbox="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png"::: 

Bu, analisti e-posta Konusu, Alıcı, Gönderen ve diğer bilgilerin görüntülendiği Tehdit Yönetimi sayfasına götürür. **Özel Eylemler** altındaki **ZAP**, analiste Sıfır saatlik otomatik temizleme özelliğinin uygulandığını bildirir. ZAP, kuruluş genelindeki posta kutularındaki kötü amaçlı ve istenmeyen posta iletilerini otomatik olarak algılar ve kaldırır. Daha fazla bilgi için bkz. [Exchange Online'da Sıfır saat otomatik temizleme (ZAP).](../office-365-security/zero-hour-auto-purge.md)

**Eylemler** seçilerek belirli iletilerde başka eylemler yapılabilir. 
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-actions.png" alt-text="E-posta iletilerinde gerçekleştirilebilecek diğer eylemler" lightbox="../../media/first-incident-path-phishing/first-incident-phishing-actions.png"::: 

## <a name="next-step"></a>Sonraki adım

[Kimlik tabanlı saldırı](first-incident-path-identity.md) araştırma yoluna bakın.

## <a name="see-also"></a>Ayrıca bkz.

- [Olaylara genel bakış](incidents-overview.md)
- [Olayları araştırın](investigate-incidents.md)
- [Olayları yönetin](manage-incidents.md)
