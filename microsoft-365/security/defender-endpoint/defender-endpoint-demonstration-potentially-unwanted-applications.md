---
title: İstenmeyebilecek uygulamalar (PUA) gösterimini Uç Nokta için Microsoft Defender
description: İstenmeyebilecek Uygulamalar (PUA) koruma özelliğinin PUA'ların uç noktalara indirilmesini ve yüklenmesini nasıl belirleyip engelleyebileceğini gösteren tanıtım.
keywords: Uç Nokta için Microsoft Defender, istenmeyebilecek uygulamalar, (PUA), zararlı uygulama koruması, gösterim
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: evaluation
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
- demo
ms.topic: article
ms.subservice: mde
ms.date: 10/21/2022
ms.openlocfilehash: b8212717d21f7509195ab5b276ccffc443b760c3
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68732701"
---
# <a name="potentially-unwanted-applications-pua-demonstration"></a>İstenmeyebilecek uygulamalar (PUA) gösterimi

Microsoft Defender Virüsten Koruma'daki İstenmeyebilecek Uygulamalar (PUA) koruma özelliği, PUA'ların ağınızdaki uç noktaları indirip yüklemesini tanımlayıp engelleyebilir. Bu uygulamalar virüs, kötü amaçlı yazılım veya diğer tehdit türleri olarak kabul edilmez, ancak uç noktalarda performanslarını veya kullanımlarını olumsuz yönde etkileyen eylemler gerçekleştirebilir.

## <a name="scenario-requirements-and-setup"></a>Senaryo gereksinimleri ve kurulumu

- Windows 10, Windows 11

- PUA korumasını etkinleştirin. Daha fazla bilgi için [İstenmeyebilecek Uygulamaları Algılama ve Engelleme](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) makalesine bakın.
- Ayrıca bu ayarı ve diğerlerini etkinleştirmek için [PowerShell betiğini indirip kullanabilirsiniz](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings/) .

## <a name="scenario"></a>Senaryo

1. Git [http://www.amtso.org/feature-settings-check-potentially-unwanted-applications/](http://www.amtso.org/feature-settings-check-potentially-unwanted-applications/)
2. "İstenmeyebilecek Uygulama 'test' dosyasını indirin" bağlantısına tıklayın
3. Dosya indirildikten sonra otomatik olarak engellenir ve çalıştırılması engellenir.

## <a name="see-also"></a>Ayrıca bkz.

[Olası İstenmeyen Uygulamaları tespit edin ve engelleyin](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)

[Uç Nokta için Microsoft Defender - tanıtım senaryoları](defender-endpoint-demonstrations.md)
