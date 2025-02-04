---
title: Otomasyon dosyası yüklemelerini yönetin
description: İçerik analizini etkinleştirin ve analiz için gönderilecek dosya uzantısını ve e-posta eki uzantılarını yapılandırın
keywords: otomasyon, dosya, karşıya yüklemeler, içerik, analiz, dosya, uzantı, e-posta, ek
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
- tier2
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 7369ce07cd05ac994d77abc5e76df1a4d95ca41a
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68620283"
---
# <a name="manage-automation-file-uploads"></a>Otomasyon dosyası yüklemelerini yönetin

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

Otomatik araştırmada ek inceleme için belirli dosyaların ve e-posta eklerinin otomatik olarak buluta yüklenebilmesi için içerik analizi özelliğini etkinleştirin.

Dosya uzantısı adlarını ve e-posta eki uzantısı adlarını belirterek dosyaları ve e-posta eklerini tanımlayın.

Örneğin, dosya veya ek uzantısı adları olarak *exe* ve *bat* eklerseniz, otomatik araştırma sırasında ek inceleme için bu uzantılara sahip tüm dosyalar veya ekler otomatik olarak buluta gönderilir.

## <a name="add-file-extension-names-and-attachment-extension-names"></a>Dosya uzantısı adları ve ek uzantısı adları ekleyin.

1. Gezinti bölmesinde **Ayarlar** \> Uç Noktaları **Kuralları Otomasyon** \> **yüklemeleri'ni** \> seçin.

2. İçerik analizi ayarını **Açık** ve **Kapalı arasında değiştirin**.

3. Aşağıdaki uzantı adlarını yapılandırın ve uzantı adlarını virgülle ayırın:
   - **Dosya uzantısı adları** - E-posta ekleri dışındaki şüpheli dosyalar ek inceleme için gönderilir

## <a name="related-topics"></a>İlgili konular

- [Otomasyon klasörü dışlamalarını yönetin](manage-automation-folder-exclusions.md)
