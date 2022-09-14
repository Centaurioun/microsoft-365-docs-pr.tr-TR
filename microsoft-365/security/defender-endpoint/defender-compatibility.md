---
title: Uç Nokta için Defender ile virüsten koruma çözümü uyumluluğu
description: Uç Nokta için Microsoft Defender ile Windows Defender nasıl çalıştığı hakkında bilgi edinin. Ayrıca bir üçüncü taraf kötü amaçlı yazılımdan koruma istemcisi kullanıldığında Uç Nokta için Defender'ın nasıl çalıştığını da öğrenin.
keywords: windows defender uyumluluğu, defender, Uç Nokta için Microsoft Defender, uç nokta için defender, virüsten koruma, mde
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.date: 05/06/2021
ms.subservice: mde
ms.openlocfilehash: 2fcab2ab95623b8d2a7d551b697765bc317d2e42
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67679811"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender ile virüsten koruma çözümü uyumluluğu

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-defendercompat-abovefoldlink)

Uç Nokta için Microsoft Defender aracısı, dosya tarama gibi bazı özellikler için Microsoft Defender Virüsten Koruma'ya bağlıdır.

> [!IMPORTANT]
> Uç Nokta için Defender, Microsoft Defender Virüsten Koruma Dışlamaları ayarlarına bağlı değildir.

Microsoft Defender Virüsten Koruma etkin kötü amaçlı yazılımdan koruma olsun veya olmasın Uç Nokta için Defender cihazlarında Güvenlik bilgileri güncelleştirmelerini yapılandırmanız gerekir. Daha fazla bilgi için bkz [. Microsoft Defender Virüsten Koruma güncelleştirmelerini yönetme ve temelleri uygulama](manage-updates-baselines-microsoft-defender-antivirus.md).

Eklenen bir cihaz üçüncü taraf kötü amaçlı yazılımdan koruma istemcisi tarafından korunuyorsa, söz konusu uç noktadaki Microsoft Defender Virüsten Koruma pasif moda girer.

Microsoft Defender Virüsten Koruma güncelleştirmeleri almaya devam eder ve *mspeng.exe* işlemi çalışan bir hizmet olarak listelenir. Ancak tarama gerçekleştirmez ve çalışan üçüncü taraf kötü amaçlı yazılımdan koruma istemcisinin yerini almaz.

Microsoft Defender Virüsten Koruma arabirimi devre dışı bırakılır. Cihazdaki kullanıcılar, isteğe bağlı taramalar gerçekleştirmek veya çoğu seçeneği yapılandırmak için Microsoft Defender Virüsten Koruma'yi kullanamaz.

Daha fazla bilgi için Bkz. [Microsoft Defender Virüsten Koruma ve Uç Nokta için Defender uyumluluk konusu](microsoft-defender-antivirus-compatibility.md).
