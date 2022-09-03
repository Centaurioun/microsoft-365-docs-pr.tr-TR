---
title: Uç Nokta için Microsoft Defender ile birlikte Office 365 için Microsoft Defender kullanma
f1.keywords:
- NOCSH
keywords: integrate, Microsoft Defender, Uç Nokta için Microsoft Defender
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 12/02/2021
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Cihazlarınıza yönelik tehditler ve e-posta içeriği hakkında daha ayrıntılı bilgi edinmek için Office 365 için Microsoft Defender Uç Nokta için Microsoft Defender birlikte kullanın.
ms.custom:
- seo-marvel-apr2020
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: be951f29924300bfa14c92df549c7959a995c7ef
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67598395"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender ile birlikte Office 365 için Microsoft Defender kullanma

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

[Office 365 için Microsoft Defender](defender-for-office-365.md) [Uç Nokta için Microsoft Defender](/windows/security/threat-protection) ile çalışacak şekilde yapılandırılabilir.

Office 365 için Microsoft Defender Uç Nokta için Microsoft Defender ile tümleştirmek, güvenlik operasyonları ekibinizin kullanıcıların cihazları risk altındaysa hızlı bir şekilde izlemenize ve harekete geçmenize yardımcı olabilir. Örneğin, tümleştirme etkinleştirildikten sonra güvenlik operasyonları ekibiniz algılanan bir e-posta iletisinden etkilenmiş olabilecek cihazları ve bu cihazlar için Uç Nokta için Microsoft Defender'de oluşturulan son uyarıları görebilir.

Aşağıdaki görüntüde **, Uç Nokta için Microsoft Defender** tümleştirme etkinleştirildiğinde Cihazlar sekmesinin nasıl göründüğü gösterilir:

:::image type="content" source="../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG" alt-text="Uyarı içeren cihazların listesi" lightbox="../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG":::

Bu örnekte, algılanan e-posta iletisinin alıcılarının dört cihazı olduğunu ve birinin uyarı içerdiğini görebilirsiniz. Bir cihazın bağlantısına tıklanması[, Microsoft 365 Defender portalında](/microsoft-365/security/defender/microsoft-365-defender) sayfasını açar.

> [!TIP]
> Microsoft 365 Defender portalı Microsoft Defender Güvenlik Merkezi yerini alır. [bkz. Microsoft 365 Defender'da Uç Nokta için Microsoft Defender](../defender/microsoft-365-security-center-mde.md).

## <a name="requirements"></a>Gereksinimler

- Kuruluşunuzun Office 365 için Microsoft Defender (veya Office 365 E5) ve Uç Nokta için Microsoft Defender olması gerekir.

- Microsoft 365'te genel yönetici veya güvenlik yöneticisi rolü atanmış olmalıdır. Daha fazla bilgi için bkz. [Microsoft 365 Defender portalında İzinler](permissions-microsoft-365-security-center.md).

- [Gezgin'e (veya gerçek zamanlı algılamalara)](threat-explorer.md) erişiminiz olmalıdır.

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Office 365 için Microsoft Defender Uç Nokta için Microsoft Defender ile tümleştirmek için

Office 365 için Microsoft Defender Uç Nokta için Microsoft Defender ile tümleştirme hem Uç Nokta için Defender'da hem de Office 365 için Defender ayarlanır.

1. Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com)) gidin ve oturum açın.

2. **Email & işbirliği** \> **Gezgini'ne** gidin.

3. **Gezgin** sayfasında, ekranın sağ üst köşesinde **MDE Ayarları'nı** seçin.

3. Görüntülenen **Uç Nokta için Microsoft Defender bağlantı** açılır penceresinde **, Uç Nokta için Microsoft Defender Bağlan** 'ı (![Aç/](../../media/scc-toggle-on.png)kapat) açın ve **kapat'ı** seçin.

   :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="MDE Bağlantısı sayfası" lightbox="../../media/explorer-mdeconnection-dialognew.png":::

4. Gezinti bölmesinde **Ayarlar'ı** seçin. **Ayarlar** sayfasında **Uç Noktalar'ı** seçin

5. Açılan **Uç Noktalar** sayfasında **Gelişmiş özellikler'i** seçin.

6. **Office 365 Tehdit Bilgileri bağlantısına** kadar aşağı kaydırın ve açın (![Açık.](../../media/scc-toggle-on.png)).

   İşiniz bittiğinde **Tercihleri kaydet'i** seçin.

## <a name="see-also"></a>Ayrıca bkz.

[Office 365'de tehdit araştırma ve yanıt özellikleri](office-365-ti.md)

[Office 365 için Microsoft Defender](defender-for-office-365.md)

[Uç Nokta için Microsoft Defender](/windows/security/threat-protection)
