---
title: Microsoft 365 Defender'ın Microsoft Sentinel ile tümleştirmesi
description: Microsoft Sentinel'i Microsoft 365 Defender olay ve olaylar için SIEM olarak kullanın.
keywords: olaylar, uyarılar, araştırma, analiz etme, yanıt, bağıntı, saldırı, makineler, cihazlar, kullanıcılar, kimlikler, kimlik, posta kutusu, e-posta, 365, Microsoft, m365
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
- M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 3ddf2e863b764cbf2109acda7a6318a98882f901
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480766"
---
# <a name="microsoft-365-defender-integration-with-microsoft-sentinel"></a>Microsoft 365 Defender'ın Microsoft Sentinel ile tümleştirmesi

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Microsoft Sentinel için Microsoft 365 Defender bağlayıcısı (önizleme), tüm Microsoft 365 Defender olay ve uyarı bilgilerini Microsoft Sentinel'e gönderir ve olayların eşitlenmiş kalmasını sağlar. 

Bağlayıcıyı ekledikten sonra, tüm ilişkili uyarıları, varlıkları ve Uç Nokta için Microsoft Defender alınan ilgili bilgileri içeren olayları&mdash;Microsoft 365 Defender, Kimlik için Microsoft Defender Office 365 için Microsoft Defender ve Microsoft Defender for Cloud Apps&mdash;, güvenlik bilgileri ve olay yönetimi (SIEM) verileri olarak Microsoft Sentinel'e akışla aktarılarak Microsoft Sentinel ile önceliklendirme ve olay yanıtı gerçekleştirme bağlamı sağlar. 

Microsoft Sentinel'de olaylar Microsoft 365 Defender ile çift yönlü olarak eşitlenmiş olarak kalır ve olay araştırma ve yanıt için Azure portal hem Microsoft 365 Defender portalının hem de Microsoft Sentinel'in avantajlarından yararlanmanızı sağlar.

Microsoft 365 Defender ile Microsoft Sentinel tümleştirmesine bu kısa genel bakışı izleyin (4 dakika).

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


Şöyle çalışır.

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Microsoft 365 Defender ve Microsoft Sentinel portalları için olay verilerinin akışı ve paylaşımı" lightbox="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png":::

## <a name="next-steps"></a>Sonraki adımlar

1. [Microsoft Sentinel ile Microsoft 365 Defender tümleştirmesi](/azure/sentinel/microsoft-365-defender-sentinel-integration) hakkında daha ayrıntılı bilgi edinin.
2. [Microsoft 365 Defender'dan Microsoft Sentinel'e veri bağlama](/azure/sentinel/connect-microsoft-365-defender).

## <a name="see-also"></a>Ayrıca bkz.

- [Microsoft 365 Defender'daki olaylara genel bakış](incidents-overview.md)
- [Microsoft Sentinel ile olayları araştırma](/azure/sentinel/tutorial-investigate-cases)
