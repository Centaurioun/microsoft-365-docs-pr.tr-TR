---
title: Mac'te Uç Nokta için Microsoft Defender lisans sorunlarını giderme
description: Mac'te Uç Nokta için Microsoft Defender lisans sorunlarını giderme.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, mac, performans
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
ms.openlocfilehash: 4188208bd6efed26c2c612629f57274d8328934c
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67692380"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a>macOS'ta Uç Nokta için Microsoft Defender lisans sorunlarını giderme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**

- [macOS](microsoft-defender-endpoint-mac.md)
 [Uç Nokta için Microsoft Defender Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
 [Uç Nokta için Microsoft Defender Plan 2'de](https://go.microsoft.com/fwlink/p/?linkid=2154037) Uç Nokta için Microsoft Defender
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[macOS ve](microsoft-defender-endpoint-mac.md) [El ile dağıtım](mac-install-manually.md) testi veya Kavram Kanıtı (PoC) üzerinde Uç Nokta için Microsoft Defender devam ederken aşağıdaki hatayı alabilirsiniz:

:::image type="content" source="images/no-license-found.png" alt-text="Lisans hatası" lightbox="images/no-license-found.png":::

**İleti:** 

Lisans bulunamadı

Kuruluşunuzun Microsoft 365 Kurumsal aboneliği için lisansı yok gibi görünüyor.

Yardım için yöneticinize başvurun.

**Neden:** 

Uç Nokta için Microsoft Defender macOS paketine dağıttınız ve/veya yüklediniz ("Yükleme paketini indir"), ancak yapılandırma betiğini çalıştırmamış olabilirsiniz ("Ekleme paketini indir"), veya kullanıcıya lisans atamamış olabilirsiniz.

MacOS aracısının Uç Nokta için Microsoft Defender güncel olmadığında da bu hatayla karşılaşabilirsiniz. 


**Çözüm:**

Burada belgelenen MicrosoftDefenderATPOnboardingMacOs.py yönergeleri izleyin: [İstemci yapılandırması](mac-install-manually.md#client-configuration)

macOS'ta Uç Nokta için Microsoft Defender güncel olmadığı senaryolar için aracıyı güncelleştirmeniz gerekir. 
