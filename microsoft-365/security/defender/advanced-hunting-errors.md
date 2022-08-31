---
title: Microsoft 365 Defender için gelişmiş avcılık hatalarını işleme
description: Gelişmiş avcılık kullanılırken görüntülenen hataları anlama
keywords: gelişmiş avcılık, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema, kusto, zaman aşımı, kaynaklar, hatalar, bilinmeyen hata, sınırlar, kota, parametre, ayırma
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
ms.collection: m365-security-compliance
ms.topic: article
ms.openlocfilehash: 0839bd8c82defd79193c040c54c4b83afc7d24ce
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480094"
---
# <a name="handle-advanced-hunting-errors"></a>Gelişmiş tehdit avcılığı hatalarını işleme

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender
- Uç Nokta için Microsoft Defender


Gelişmiş tehdit avcılığı, söz dizimi hatalarını ve [sorguların önceden tanımlanmış kotalara ve kullanım parametrelerine](advanced-hunting-limits.md) her ulaşmasını bildiren hatalar görüntüler. Hataları düzeltme veya önleme hakkında ipuçları için aşağıdaki tabloya bakın.

| Hata türü | Neden | Çözüm | Hata iletisi örnekleri |
|--|--|--|--|
| Söz dizimi hataları | Sorgu, var olmayan işleçlere, sütunlara, işlevlere veya tablolara başvurular da dahil olmak üzere tanınmayan adlar içerir. | [Kusto işleçlerine ve işlevlerine](/azure/data-explorer/kusto/query/) yapılan başvuruların doğru olduğundan emin olun. Doğru gelişmiş avlanma sütunları, işlevleri ve tabloları için [şemayı](advanced-hunting-schema-tables.md) denetleyin. Tanınmaları için değişken dizelerini tırnak içine alın. Sorgularınızı yazarken IntelliSense'in otomatik tamamlama önerilerini kullanın. | `A recognition error occurred.` |
| Anlamsal hatalar | Sorgu geçerli işleç, sütun, işlev veya tablo adları kullanıyor olsa da yapısında ve sonuçta elde edilen mantıkta hatalar vardır. Bazı durumlarda gelişmiş avcılık, hataya neden olan belirli işleci tanımlar. | Sorgu yapısındaki hataları denetleyin. Rehberlik için [Kusto belgelerine](/azure/data-explorer/kusto/query/) bakın. Sorgularınızı yazarken IntelliSense'in otomatik tamamlama önerilerini kullanın. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| Zaman aşımı | Sorgu zaman [aşımına uğramadan önce yalnızca sınırlı bir süre](advanced-hunting-limits.md) içinde çalıştırılabilir. Karmaşık sorgular çalıştırılırken bu hata daha sık oluşabilir. | [Sorguyu iyileştirme](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| CPU azaltma | Aynı kiracıdaki sorgular, kiracı boyutuna göre ayrılan [CPU kaynaklarını](advanced-hunting-limits.md) aştı. | Hizmet her 15 dakikada bir ve her gün CPU kaynak kullanımını denetler ve kullanım ayrılan kotanın %10'unu aştıktan sonra uyarılar görüntüler. %100 kullanıma ulaşırsanız, hizmet sorguları sonraki günlük veya 15 dakikalık döngüye kadar engeller. [CPU kotalarına ulaşılmasını önlemek için sorgularınızı iyileştirme](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| Sonuç boyutu sınırı aşıldı  | Sorgu için sonuç kümesinin toplam boyutu boyut üst sınırını aştı. Sonuç kümesi 10.000 kayıt sınırındaki kesme işleminin kabul edilebilir bir boyuta indiremeyecek kadar büyük olması durumunda bu hata oluşabilir. Boyutlandırılabilir içeriğe sahip birden çok sütun içeren sonuçların bu hatadan etkilenme olasılığı daha yüksektir. | [Sorguyu iyileştirme](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| Aşırı kaynak tüketimi | Sorgu çok fazla miktarda kaynak tüketmiştir ve tamamlanması durdurulmuştur. Bazı durumlarda gelişmiş avcılık, iyileştirilmemiş belirli operatörü tanımlar. | [Sorguyu iyileştirme](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| Bilinmeyen hatalar | Bilinmeyen bir nedenden dolayı sorgu başarısız oldu. | Sorguyu yeniden çalıştırmayı deneyin. Sorgular bilinmeyen hatalar döndürmeye devam ederse portal üzerinden Microsoft'a başvurun. | `An unexpected error occurred during query execution. Please try again in a few minutes.`



## <a name="related-topics"></a>İlgili konular
- [Gelişmiş avcılık en iyi yöntemleri](advanced-hunting-best-practices.md)
- [Kotalar ve kullanım parametreleri](advanced-hunting-limits.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Kusto Sorgu Dili genel bakış](/azure/data-explorer/kusto/query/)