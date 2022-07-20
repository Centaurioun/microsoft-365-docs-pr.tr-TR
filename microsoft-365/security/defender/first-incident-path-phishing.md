---
title: Kimlik avı e-posta saldırısı örneği
description: Bir kimlik avı saldırısının örnek analizinde ilerleyin.
keywords: olaylar, uyarılar, araştırma, bağıntı, saldırı, makineler, cihazlar, kullanıcılar, kimlik, kimlik, posta kutusu, e-posta, 365, Microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
- M365-security-compliance
- m365solution-firstincident
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: dcf620cfaeb1d33665538d16d080e72745b96e42
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2022
ms.locfileid: "66892928"
---
# <a name="example-of-a-phishing-email-attack"></a>Kimlik avı e-posta saldırısı örneği

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Microsoft 365 Defender, e-postayla gönderilen kötü amaçlı ekleri algılamaya yardımcı olabilir. [Office 365 Güvenlik ve Uyumluluk Merkezi](https://protection.office.com/) Microsoft 365 Defender ile tümleştirdiğinden, güvenlik analistleri e-posta ekleri gibi Office 365 gelen tehditleri görebilir.

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
