---
title: Uç Nokta için Microsoft Defender'de web'e gözatma güvenliğini izleme
description: Web'e gözatma güvenliğini izlemek için Uç Nokta için Microsoft Defender'de web korumasını kullanma
keywords: web koruması, web tehdit koruması, web'e göz atma, izleme, raporlar, kartlar, etki alanı listesi, güvenlik, kimlik avı, kötü amaçlı yazılım, yararlanma, web siteleri, ağ koruması, Edge, Internet Explorer, Chrome, Firefox, web tarayıcısı
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 1482ca9587c5e09c33b909029fd2697745768d3d
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67578476"
---
# <a name="monitor-web-browsing-security"></a>Web'e gözatma güvenliğini izleme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Web koruması, Microsoft 365 Defender portalındaki **Raporlar > Web koruması** altındaki raporlar aracılığıyla kuruluşunuzun web'e gözatma güvenliğini izlemenize olanak tanır. Rapor, web tehdit algılama istatistikleri sağlayan kartlar içerir.

- **Zaman içinde web tehdit koruması algılamaları** - Bu popüler kart, seçilen zaman aralığında türe göre algılanan web tehditlerinin sayısını görüntüler (Son 30 gün, Son 3 ay, Son 6 ay)

  :::image type="content" source="images/wtp-blocks-over-time.png" alt-text="Zaman içindeki web tehditleri koruma algılamalarını gösteren kart" lightbox="images/wtp-blocks-over-time.png":::

- **Web tehdit koruması özeti** - Bu kart, son 30 gün içindeki toplam web tehdit algılamalarını görüntüler ve farklı web tehditleri türleri arasında dağıtımı gösterir. Dilim seçildiğinde, kötü amaçlı veya istenmeyen web sitelerinde bulunan etki alanlarının listesi açılır.

  :::image type="content" source="images/wtp-summary.png" alt-text="Web tehditleri koruma özetini gösteren kart"  lightbox="images/wtp-summary.png":::

> [!NOTE]
> Bir bloğun kartlara veya etki alanı listesine yansıtılmış olması 12 saat kadar sürebilir.

## <a name="types-of-web-threats"></a>Web tehditleri türleri

Web koruması kötü amaçlı ve istenmeyen web sitelerini şu şekilde kategorilere ayırır:

- **Kimlik avı** - Kimlik sahtekarlığı yapılan web formları ve diğer kimlik avı mekanizmalarını içeren web siteleri, kullanıcıları kimlik bilgilerini ve diğer hassas bilgileri bölmeleri için kandırmak için tasarlanmıştır
- **Kötü amaçlı** - kötü amaçlı yazılım barındıran ve koddan yararlanan web siteleri
- **Özel gösterge** - URL'lerini veya etki alanlarını engelleme için [özel gösterge listenize eklediğiniz web](manage-indicators.md) siteleri

## <a name="view-the-domain-list"></a>Etki alanı listesini görüntüleme

**Etki Alanları** sayfasını açmak için **Web tehdit koruması özet** kartında belirli bir web tehdit kategorisi seçin. Bu sayfada söz konusu tehdit kategorisi altındaki etki alanlarının listesi görüntülenir. Sayfa her etki alanı için aşağıdaki bilgileri sağlar:

- **Erişim sayısı** - etki alanındaki URL'ler için istek sayısı
- **Bloklar** - isteklerin engellenme sayısı
- **Erişim eğilimi** - erişim denemesi sayısındaki değişiklik
- **Tehdit kategorisi** - web tehdidinin türü
- **Cihazlar** - Erişim denemesi olan cihaz sayısı

Bu etki alanındaki URL'lere erişmeyi denemiş cihazların listesini ve URL listesini görüntülemek için bir etki alanı seçin.

## <a name="related-topics"></a>İlgili konular

- [Web korumasına genel bakış](web-protection-overview.md)
- [Web içeriği filtreleme](web-content-filtering.md)
- [Web tehdit koruması](web-threat-protection.md)
- [Web tehditlerine yanıt verin](web-protection-response.md)
