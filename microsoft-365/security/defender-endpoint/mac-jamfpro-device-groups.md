---
title: Jamf Pro'da cihaz gruplarını ayarlama
description: macOS'ta Uç Nokta için Microsoft Defender için Jamf Pro'da cihaz gruplarını ayarlamayı öğrenin
keywords: cihaz, grup, microsoft, defender, Uç Nokta için Microsoft Defender, mac, yükleme, dağıtma, kaldırma, intune, jamfpro, macos, catalina, mojave, high sierra
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 7f3006896ccebdb40f720671427dfe76b3d53025
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67687955"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a>Jamf Pro'da macOS cihaz gruplarında Uç Nokta için Microsoft Defender ayarlama

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Grup ilkesi kuruluş birimine (OU), Microsoft Endpoint Configuration Manager'ın cihaz koleksiyonuna ve Intune cihaz gruplarına benzer cihaz gruplarını ayarlayın.

1. **Statik Bilgisayar Grupları'na** gidin.

2. **Yeni**'yi seçin. 

   :::image type="content" source="images/jamf-pro-static-group.png" alt-text="Jamf Pro1 sayfası" lightbox="images/jamf-pro-static-group.png":::

3. Bir görünen ad girin ve **Kaydet'i** seçin.

   :::image type="content" source="images/jamfpro-machine-group.png" alt-text="Jamf Pro2 sayfası" lightbox="images/jamfpro-machine-group.png":::

4. Şimdi **Contoso'nun Makine Grubunu** **Statik Bilgisayar Grupları** altında görürsünüz.

   :::image type="content" source="images/contoso-machine-group.png" alt-text="Jamf Pro3 sayfası" lightbox="images/contoso-machine-group.png":::

## <a name="next-step"></a>Sonraki adım
- [Jamf Pro'da macOS ilkelerinde Uç Nokta için Microsoft Defender ayarlama](mac-jamfpro-policies.md)
