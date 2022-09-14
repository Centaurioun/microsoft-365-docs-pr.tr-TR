---
title: Microsoft 365 Ağ Bağlantısı Konum Hizmetleri
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/06/2021
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: admindeeplinkMAC
description: Microsoft 365 Ağ Bağlantısı Konum Hizmetleri
ms.openlocfilehash: 68569be7de9924ada4c2323d00630cdf084525e4
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67670807"
---
# <a name="microsoft-365-network-connectivity-location-services"></a>Microsoft 365 Ağ Bağlantısı Konum Hizmetleri

<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 yönetim merkezi</a> artık Microsoft 365 kiracınızdan toplanan canlı performans ölçümleri olan **Ağ İçgörüleri ve performans önerilerini** gösterir. Bu ölçümler yalnızca kiracınızdaki yönetici kullanıcılar tarafından görüntülenebilir. Kurumsal ağ bağlantısı, İnternet'e bir ağ çıkış konumu üzerinden ofis konumu başına tasarlanmıştır. Microsoft 365 istemci bağlantısı bu yolu ve ardından İnternet üzerinden Microsoft hizmeti ön kapı sunucularına kullanır. Ofis konumlarını belirlemek, bu ağ içgörülerini gösterebilmek için önemlidir.

## <a name="location-in-network-measurements"></a>Ağ ölçümlerindeki konum

Kuruluşun yöneticisi, konumun bu özellik tarafından kullanılan ağ ölçümlerine eklenmesini tercih edebilir. Bu, her ofisin bulunduğu şehrin otomatik olarak bulunmasını sağlar. Konum bilgileri kesin değildir ve 300m olarak belirsizdir ve şehre göre kategorilere ayrılmıştır. Konum bir Windows cihazında yakalandığında, cihaz araç **tepsisinde Bir Kullanımda Konum** simgesi gösterir. Yöneticiler bu simgenin görünümünü kullanıcılara bildirmek isteyebilir. Bu işlemle birlikte konum, bir kişinin veya cihazın konumu değil kuruluş ofisi konumu olarak değerlendirilir. Ağ içgörüleri, bulunan bu ofis konumu şehirlerinde gösterilebilir. Önerilerde daha yüksek doğruluk istiyorsanız, belirli ofis konumu adreslerini girebilirsiniz. Bunun yerine ağ içgörüleri bu konumlara toplanır. Office konumları 300 metreden daha yakın bir şekilde toplanamaz.

## <a name="location-in-the-microsoft-365-admin-center"></a>Microsoft 365 Yönetici Merkezi'ndeki konum

<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 yönetim merkezi</a> Bing harita denetimleri, kuruluş ofisi konumlarının nerede olduğunu göstermek için kullanılır. Denetimler ayrıca seçilen bir ofis konumu için ağ çevre topolojisini gösterir. Bir yönetici office konumları için belirli adres ayrıntıları eklediğinde, veri girişini kolaylaştırmak için adres önermek için Bing Haritalar de kullanılır.

## <a name="terms-of-use"></a>Kullanım Koşulları

Coğrafi kodlar da dahil olmak üzere Bing Haritalar aracılığıyla sağlanan tüm içerikler yalnızca içeriğin sağlandığı ürün içinde kullanılabilir. Müşterinin <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Bing Haritalar</a> tarafından desteklenen Microsoft 365 yönetim merkezi Konum Hizmetleri özelliğini kullanması, adresinde ve [Microsoft Gizlilik Bildirimi'nde](https://go.microsoft.com/fwlink/?LinkID=248686)<https://go.microsoft.com/?linkid=9710837> bulunan _Bing Haritalar End-User Kullanım Koşullarına_ tabidir.

Bing Haritalar aracılığıyla sağlanan bu özellik **TomTom** tarafından da desteklenir. TomTom'un ürün ve hizmetleri hakkında daha fazla bilgi adresinde [https://www.tomtom.com/legal](https://www.tomtom.com/legal)bulunabilir.

## <a name="related-topics"></a>İlgili konular

[Microsoft 365 Yönetici Merkezi'nde ağ bağlantısı](office-365-network-mac-perf-overview.md)

[Microsoft 365 ağ performansı içgörüleri](office-365-network-mac-perf-insights.md)

[Microsoft 365 ağ değerlendirmesi](office-365-network-mac-perf-score.md)

[Microsoft 365 yönetim merkezi Microsoft 365 bağlantı testi](office-365-network-mac-perf-onboarding-tool.md)
