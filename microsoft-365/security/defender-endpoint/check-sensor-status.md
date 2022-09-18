---
title: Algılayıcının sistem durumunu Uç Nokta için Microsoft Defender
description: Hangilerinin yanlış yapılandırıldığı, etkin olmadığını veya algılayıcı verilerini raporlamadığı belirlemek için cihazlarda algılayıcının durumunu denetleyin.
keywords: algılayıcı, algılayıcı durumu, yanlış yapılandırılmış, etkin değil, algılayıcı verileri yok, algılayıcı verileri, iletişim bozukluğu, iletişim
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/24/2018
search.appverid: met150
ms.openlocfilehash: 353dad94d14ccfd807a946161d3879815526899d
ms.sourcegitcommit: 2dedd0f594b817779e034afa6c4418def2382a22
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2022
ms.locfileid: "67799098"
---
# <a name="check-sensor-health-state-at-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender algılayıcı durumunu denetleme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-checksensor-abovefoldlink)

**Algılayıcı sorunları olan cihazlar** kutucuğu, tek bir cihazın algılayıcı verileri sağlama ve Uç Nokta için Defender hizmetiyle iletişim kurma özelliği hakkında bilgi sağlar. Kaç cihazın dikkat gerektirdiğini bildirir ve sorunlu cihazları belirlemenize ve bilinen sorunları düzeltmek için işlem yapmanıza yardımcı olur.

Kutucukta hizmete düzgün raporlama yapmayan cihazların sayısı hakkında bilgi sağlayan iki durum göstergesi vardır:

- **Yanlış yapılandırılmış** - Bu cihazlar algılayıcı verilerini kısmen Uç Nokta için Defender hizmetine bildiriyor olabilir ve düzeltilmesi gereken yapılandırma hataları olabilir.
- **Etkin değil** - Son ay içinde yedi günden fazla süreyle Uç Nokta için Defender hizmetine raporlamayı durduran cihazlar.

Gruplardan herhangi birine tıkladığınızda, tercihinize göre filtrelenmiş **Cihazlar listesine** yönlendirilirsiniz.

:::image type="content" source="images/atp-devices-with-sensor-issues-tile.png" alt-text="Algılayıcı sorunları olan cihazlar kutucuğu" lightbox="images/atp-devices-with-sensor-issues-tile.png":::

**Cihazlar listesinde**, sistem durumu listesini aşağıdaki duruma göre filtreleyebilirsiniz:

- **Etkin** - Uç Nokta için Defender hizmetine etkin olarak raporlama yapan cihazlar.
- **Yanlış yapılandırılmış** - Bu cihazlar algılayıcı verilerini kısmen Uç Nokta için Defender hizmetine bildiriyor olabilir ancak düzeltilmesi gereken yapılandırma hataları olabilir. Yanlış yapılandırılmış cihazlarda aşağıdaki sorunlardan biri veya bir birleşimi olabilir:
  - **Algılayıcı verileri yok** - Cihazlar algılayıcı verilerini göndermeyi durdurdu. Cihazdan sınırlı uyarılar tetiklenebilir.
  - **İletişim bozukluğu** - Cihazla iletişim kurma yeteneği bozuk. Ayrıntılı analiz için dosya gönderme, dosyaları engelleme, cihazı ağdan yalıtma ve cihazla iletişim gerektiren diğer eylemler çalışmayabilir.
- **Etkin değil** - Uç Nokta için Defender hizmetine raporlamayı durduran cihazlar.

Dışarı **Aktarma** özelliğini kullanarak listenin tamamını CSV biçiminde de indirebilirsiniz. Filtreler hakkında daha fazla bilgi için bkz. [Cihazlar listesini görüntüleme ve düzenleme](machines-view-overview.md).

> [!NOTE]
> Filtrelenmemiş verileri görüntülemek için listeyi CSV biçiminde dışarı aktarın. CSV dosyası, görünümde uygulanan filtrelemelerden bağımsız olarak kuruluştaki tüm cihazları içerir ve kuruluşunuzun ne kadar büyük olduğuna bağlı olarak indirilmesi önemli ölçüde zaman alabilir.

:::image type="content" source="images/atp-devices-list-page.png" alt-text="Cihaz listesi sayfasındaki Dışarı Aktar sekmesi" lightbox="images/atp-devices-list-page.png":::

Yanlış yapılandırılmış veya etkin olmayan bir cihaza tıkladığınızda cihaz ayrıntılarını görüntüleyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

- [Uç Nokta için Defender'da iyi durumda olmayan algılayıcıları düzeltme](fix-unhealthy-sensors.md)
- [İstemci çözümleyicisine genel bakış](overview-client-analyzer.md)
- [İstemci çözümleyicisini indirin ve çalıştırın](download-client-analyzer.md)
- [İstemci çözümleyicisini Windows’da çalıştırın](run-analyzer-windows.md)
- [İstemci çözümleyicisini macOS veya Linux'ta çalıştırın](run-analyzer-macos-linux.md)
- [Windows'da gelişmiş sorun giderme için veri toplama](data-collection-analyzer.md)
