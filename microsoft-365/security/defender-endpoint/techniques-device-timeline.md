---
title: Cihaz zaman çizelgesindeki teknikler
description: Uç Nokta için Microsoft Defender'de cihaz zaman çizelgesini anlama
keywords: cihaz zaman çizelgesi, uç nokta, MITRE, MITRE ATT&CK, teknikler, taktikler
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 27bc68c1226f3b036b7cd1b043b993c97f93fda1
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68636288"
---
# <a name="techniques-in-the-device-timeline"></a>Cihaz zaman çizelgesindeki teknikler

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)

Belirli bir cihazda gerçekleşen olayları analiz ederek bir araştırmada daha fazla içgörü elde edebilirsiniz. İlk olarak, [Cihazlar listesinden ilgilendiğim](machines-view-overview.md) cihazı seçin. Cihaz sayfasında, cihazda gerçekleşen tüm olayları görüntülemek için **Zaman Çizelgesi** sekmesini seçebilirsiniz.

## <a name="understand-techniques-in-the-timeline"></a>Zaman çizelgesindeki teknikleri anlama

> [!IMPORTANT]
> Bazı bilgiler, genel önizlemede kullanıma sunulan ve ticari olarak yayınlanmadan önce önemli ölçüde değiştirilebilen önceden yayımlanmış bir ürün özelliğiyle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

Uç Nokta için Microsoft Defender'de **Teknikler**, olay zaman çizelgesinde ek bir veri türüdür. Teknikler [, MITRE ATT&CK](https://attack.mitre.org/) teknikleri veya alt teknikleriyle ilişkili etkinlikler hakkında daha fazla içgörü sağlar.

Bu özellik, analistlerin bir cihazda gözlemlenen etkinlikleri anlamasına yardımcı olarak araştırma deneyimini basitleştirir. Analistler daha fazla araştırma yapmaya karar verebilir.

Genel önizleme için Teknikler varsayılan olarak kullanılabilir ve cihazın zaman çizelgesi görüntülendiğinde olaylarla birlikte gösterilir.

:::image type="content" source="images/device-timeline-2.png" alt-text="Cihaz zaman çizelgesindeki Teknikler" lightbox="images/device-timeline-2.png":::

Teknikler kalın metinle vurgulanır ve solda mavi bir simgeyle gösterilir. Karşılık gelen MITRE ATT&CK kimliği ve teknik adı da Ek bilgiler altında etiketler olarak görünür.

Teknikler için Arama ve Dışarı Aktarma seçenekleri de sağlanır.

## <a name="investigate-using-the-side-pane"></a>Yan bölmeyi kullanarak araştırma

İlgili yan bölmesini açmak için bir Teknik seçin. Burada ilgili ATT&CK teknikleri, taktikler ve açıklamalar gibi ek bilgileri ve içgörüleri görebilirsiniz.

İlgili ATT&CK tekniği sayfasını açmak için ilgili *Saldırı tekniğini* seçin. Bu sayfa hakkında daha fazla bilgi bulabilirsiniz.

Sağ tarafta mavi bir simge gördüğünüzde varlığın ayrıntılarını kopyalayabilirsiniz. Örneğin, ilgili bir dosyanın SHA1 dosyasını kopyalamak için mavi sayfa simgesini seçin.

:::image type="content" source="images/techniques-side-pane-clickable.png" alt-text="Varlık ayrıntılarını kopyalamak için" lightbox="images/techniques-side-pane-clickable.png":::

Komut satırları için de aynısını yapabilirsiniz.

:::image type="content" source="images/techniques-side-pane-command.png" alt-text="Komut satırını kopyalama seçeneği" lightbox="images/techniques-side-pane-command.png":::

## <a name="investigate-related-events"></a>İlgili olayları araştırma

Seçili Teknikle ilgili olayları bulmak için [gelişmiş avcılığı](advanced-hunting-overview.md) kullanmak **için İlgili olayları avla'yı** seçin. Bu, Technique ile ilgili olayları bulmak için bir sorgu içeren gelişmiş tehdit avcılığı sayfasına yol açar.

:::image type="content" source="images/techniques-hunt-for-related-events.png" alt-text="İlgili olayları avla seçeneği" lightbox="images/techniques-hunt-for-related-events.png":::

> [!NOTE]
> Teknik yan bölmesindeki **İlişkili olayları ara** düğmesini kullanarak sorgulama, tanımlanan teknikle ilgili tüm olayları görüntüler, ancak sorgu sonuçlarına Tekniğin kendisini içermez.

## <a name="customize-your-device-timeline"></a>Cihaz zaman çizelgenizi özelleştirme

Cihaz zaman çizelgesinin sağ üst tarafında, zaman çizelgesindeki olay ve teknik sayısını sınırlamak için bir tarih aralığı seçebilirsiniz.

Hangi sütunların kullanıma açık olduğunu özelleştirebilirsiniz. Bayrak eklenmiş olayları veri türüne veya olay grubuna göre de filtreleyebilirsiniz.

### <a name="choose-columns-to-expose"></a>Kullanıma açık sütunları seçme

Sütunları seç düğmesini seçerek zaman çizelgesinde hangi **sütunların gösterileceğini seçebilirsiniz** .

:::image type="content" source="images/filter-customize-columns.png" alt-text="Sütunları özelleştirebileceğiniz bölme" lightbox="images/filter-customize-columns.png":::


Buradan hangi bilgilerin dahil olacağını seçebilirsiniz.

### <a name="filter-to-view-techniques-or-events-only"></a>Yalnızca teknikleri veya olayları görüntülemek için filtreleyin

Yalnızca olayları veya teknikleri görüntülemek için cihaz zaman çizelgesinden **Filtreler'i** seçin ve görüntülemek için tercih ettiğiniz Veri türünü seçin.

:::image type="content" source="images/device-timeline-filters.png" alt-text="Filtreler bölmesi" lightbox="images/device-timeline-filters.png":::

## <a name="see-also"></a>Ayrıca bkz.

- [Cihazlar listesini görüntüleme ve düzenleme](machines-view-overview.md)
- [cihaz zaman çizelgesi olay bayraklarını Uç Nokta için Microsoft Defender](device-timeline-event-flag.md)
