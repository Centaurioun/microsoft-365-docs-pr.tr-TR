---
title: Uç Nokta için Microsoft Defender'de web tehditlerine yanıt verme
description: Kötü amaçlı ve istenmeyen web siteleriyle ilgili uyarılara yanıt verin. Web tehdit korumasının son kullanıcıları web tarayıcıları ve Windows bildirimleri aracılığıyla nasıl bilgilendirenleri anlama
keywords: web koruması, web tehdit koruması, web'e göz atma, uyarılar, yanıt, güvenlik, kimlik avı, kötü amaçlı yazılım, kötüye kullanma, Web siteleri, ağ koruması, Edge, Internet Explorer, Chrome, Firefox, web tarayıcısı, bildirimler, son kullanıcılar, Windows bildirimleri, engelleme sayfası,
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
ms.openlocfilehash: 4d1489d217c9537c344b7cca6efbcd4a43aa28b8
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67583406"
---
# <a name="respond-to-web-threats"></a>Web tehditlerine yanıt verin

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Uç Nokta için Microsoft Defender'da web koruması, özel gösterge listenizdeki kötü amaçlı web siteleri ve web siteleriyle ilgili uyarıları verimli bir şekilde araştırmanıza ve yanıtlamanıza olanak tanır.

## <a name="view-web-threat-alerts"></a>Web tehdit uyarılarını görüntüleme

Uç Nokta için Microsoft Defender, kötü amaçlı veya şüpheli web etkinliği için aşağıdaki [uyarıları](manage-alerts.md) oluşturur:

- **Ağ koruması tarafından engellenen şüpheli bağlantı**: Bu uyarı, kötü amaçlı bir web sitesine veya özel gösterge listenizdeki bir web sitesine erişme girişimi *blok* modunda ağ koruması tarafından *durdurulduğunda* oluşturulur
- **Ağ koruması tarafından algılanan şüpheli bağlantı**: Bu uyarı, kötü amaçlı bir web sitesine veya özel gösterge listenizdeki bir web sitesine erişme girişimi *yalnızca denetim* modunda ağ koruması tarafından algılandığında oluşturulur

Her uyarı aşağıdaki bilgileri sağlar:

- Engellenen web sitesine erişmeye çalışılmış cihaz
- Web isteği göndermek için kullanılan uygulama veya program
- Özel gösterge listesindeki kötü amaçlı URL veya URL
- Yanıtlayanlar için önerilen eylemler

:::image type="content" source="images/wtp-alert.png" alt-text="Web tehdit korumasıyla ilgili uyarı" lightbox="images/wtp-alert.png":::

> [!NOTE]
> Uyarı hacmini azaltmak için Uç Nokta için Microsoft Defender her gün aynı cihazdaki aynı etki alanı için web tehdit algılamalarını tek bir uyarıda birleştirir. Yalnızca bir uyarı oluşturulur ve [web koruma raporuna](web-protection-monitoring.md) sayılır.

## <a name="inspect-website-details"></a>Web sitesi ayrıntılarını inceleme

Uyarıda web sitesinin URL'sini veya etki alanını seçerek daha ayrıntılı bilgi edinebilirsiniz. Bu, belirli bir URL veya etki alanı hakkında aşağıdakiler gibi çeşitli bilgiler içeren bir sayfa açar:

- Web sitesine erişmeye çalışan cihazlar
- Web sitesiyle ilgili olaylar ve uyarılar
- Web sitesinin kuruluşunuzdaki etkinliklerde ne sıklıkta görüldüğü

  :::image type="content" source="images/wtp-website-details.png" alt-text="Etki alanı veya URL varlık ayrıntıları sayfası" lightbox="images/wtp-website-details.png":::

[URL veya etki alanı varlık sayfaları hakkında daha fazla bilgi edinin](investigate-domain.md)

## <a name="inspect-the-device"></a>Cihazı inceleme

Engellenen BIR URL'ye erişmeye çalıştığınız cihazı da de kontrol edebilirsiniz. Uyarı sayfasında cihazın adını seçtiğinizde cihaz hakkında kapsamlı bilgiler içeren bir sayfa açılır.

[Cihaz varlık sayfaları hakkında daha fazla bilgi edinin](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a>Son kullanıcılar için web tarayıcısı ve Windows bildirimleri

Uç Nokta için Microsoft Defender web koruması sayesinde, son kullanıcılarınızın Microsoft Edge veya diğer tarayıcıları kullanarak kötü amaçlı veya istenmeyen web sitelerini ziyaret etmelerini engeller. Engelleme [ağ koruması](network-protection.md) tarafından gerçekleştirildiğinden, web tarayıcısından genel bir hata görürler. Ayrıca Windows'tan bir bildirim de görürler.

:::image type="content" source="images/wtp-browser-blocking-page.png" alt-text="403 hatasını gösteren Microsoft Edge ve Windows bildirimi" lightbox="images/wtp-browser-blocking-page.png":::

*Microsoft Edge'de web tehdidi engellendi*

:::image type="content" source="images/wtp-chrome-browser-blocking-page.png" alt-text="Güvenli bağlantı uyarısı gösteren Chrome web tarayıcısı ve Windows bildirimi" lightbox="images/wtp-chrome-browser-blocking-page.png":::
*Chrome'da engellenen web tehdidi*

## <a name="related-topics"></a>İlgili konular

- [Web korumasına genel bakış](web-protection-overview.md)
- [Web içeriği filtreleme](web-content-filtering.md)
- [Web tehdit koruması](web-threat-protection.md)
- [Web güvenliğini izleyin](web-protection-monitoring.md)
