---
title: Microsoft 365 Defender'de avcılık için sorgu sonuçlarıyla kılavuzlu modda çalışma
description: Microsoft 365 Defender'de gelişmiş avcılık için sorgu sonuçlarını destekli modda kullanma ve özelleştirme
keywords: destekli mod, gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, özel algılamalar, şema, Kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.openlocfilehash: 3e125b8fef6c1c42f125f3a2744ce5c060293ac6
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68078183"
---
# <a name="work-with-query-results-in-guided-mode"></a>Sorgu sonuçlarıyla kılavuzlu modda çalışma
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

Kılavuzlu modu kullanarak avcılıkta, sorgunun sonuçları **Sonuçlar** sekmesinde görünür. 

[![Sonuçlar sekmesinin](../../media/guided-hunting/results-view.png) ekran görüntüsü ](../../media/guided-hunting/results-view.png#lightbox)

**Dışarı Aktar'ı** seçerek sonuçları csv dosyasına aktararak sonuçlar üzerinde daha fazla çalışabilirsiniz. Bu, CSV dosyasını kullanımınız için indirir.

Sonuçlar görünümünde diğer bilgileri görüntüleyebilirsiniz:
- Sonuç listesindeki kayıt sayısı (Ara düğmesinin yanında)
- Sorgu çalışma süresinin süresi
- Sorgunun kaynak kullanımı

## <a name="view-more-columns"></a>Diğer sütunları görüntüleme

Kolay görüntüleme için sonuçlara birkaç standart sütun eklenir. 

Daha fazla sütunu görüntülemek için:
1. Sonuç görünümünün sağ üst kısmında **Sütunları özelleştir'i** seçin.
 

2. Buradan, sonuçlar görünümüne eklenecek sütunları seçin ve gizlenecek sütunların seçimini kaldırın. 


[![Sonuçlar görünümüne](../../media/guided-hunting/results-view-customize-columns.png) ekleyebileceğiniz sütunların listesinin ekran görüntüsü ](../../media/guided-hunting/results-view-customize-columns-tb.png#lightbox)

3. Eklenen sütunlarla sonuçları görüntülemek için **Uygula'yı** seçin. Gerekirse kaydırma çubuklarını kullanın.


## <a name="see-also"></a>Ayrıca bkz.
- [Gelişmiş tehdit avcılığı kotaları ve kullanım parametreleri](advanced-hunting-limits.md)
- [Gelişmiş moda geçme](advanced-hunting-query-builder-details.md#switch-to-advanced-mode-after-building-a-query)
- [Sorgunuzu kılavuzlu modda daraltma](advanced-hunting-query-builder-details.md)