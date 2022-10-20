---
title: İlk Görüşte Uç Nokta için Microsoft Defender Bloğu (BAFS) tanıtımı
description: İlk Bakışta Engelle'nin saniyeler içinde yeni kötü amaçlı yazılımları nasıl algılayıp engellediğini gösteren bir tanıtım.
keywords: Uç Nokta için Microsoft Defender, bulut tabanlı koruma, kötü amaçlı yazılımları algılama, kötü amaçlı yazılımları engelleme, tanıtım
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
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 0f9bb664fbbbb6a9791ec20c41bf5a2cda874fb5
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68643349"
---
# <a name="block-at-first-sight-bafs-demonstration"></a>İlk Bakışta Engelle (BAFS) gösterimi

İlk Bakışta Engelle, Microsoft Defender Virüsten Koruma'nın yeni kötü amaçlı yazılımları saniyeler içinde algılamak ve engellemek için bir yol sağlayan bulut tabanlı koruma özelliğidir. Sahte bir kötü amaçlı yazılım dosyası indirerek beklendiği gibi çalıştığını test edebilirsiniz.

## <a name="scenario-requirements-and-setup"></a>Senaryo gereksinimleri ve kurulumu

- Windows 10 Yıldönümü güncelleştirmesi (1607) veya üzeri
- Bulut koruması etkinleştirildi
- Bu ayarı ve diğerlerini etkinleştirmek için [PowerShell betiğini indirip kullanabilirsiniz](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings/)

  > [!NOTE]
  > Tarayıcınızın bu dosyayı birkaç saniye içinde kaydetmesini istemesini görmeniz gerekir.

### <a name="test-bafs"></a>BAFS'i test edin

1. Aşağıdaki **Yeni dosya oluştur ve indir'e** tıklayın.
1. Tarayıcının dosyayı taradığı ve ardından bir virüsten koruma engelleme bildiriminin izlediğini görmeniz gerekir.
1. [Yeni dosya & indirin!](https://demowdtestground.blob.core.windows.net/samples/ztp_xzXLX_s1H8MsxK2SRlsjmzaH62cOZEaqtstGsOw/wdtestfile.exe?sv=2015-07-08&sr=b&sig=7JNcGzAYWEinuWKNmjoC6tDmEjGZMQj8rAEF9HIzJdE%3D&se=2022-09-30T18%3A29%3A28Z&sp=r)

## <a name="see-also"></a>Ayrıca bkz.

[İlk Bakışta Engelle](configure-block-at-first-sight-microsoft-defender-antivirus.md)

[Uç Nokta için Microsoft Defender - tanıtım senaryoları](defender-endpoint-demonstrations.md)
