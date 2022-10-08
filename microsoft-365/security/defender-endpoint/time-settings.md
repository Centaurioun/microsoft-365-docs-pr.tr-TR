---
title: saat dilimi ayarlarını Microsoft 365 Defender
description: Microsoft 365 Defender saat dilimi ayarlarını yapılandırmak ve lisans bilgilerini görüntülemek için burada yer alan bilgileri kullanın.
keywords: ayarlar, Microsoft Defender, siber güvenlik tehdit bilgileri, Uç Nokta için Microsoft Defender, saat dilimi, utc, yerel saat, lisans
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
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 4d6dcb43ea34c253f97b6f5a3085470b460d3b1a
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68229646"
---
# <a name="microsoft-365-defender-time-zone-settings"></a>saat dilimi ayarlarını Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)


> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-settings-abovefoldlink)

**Saat dilimini** yapılandırmak ve lisans bilgilerini görüntülemek için Saat dilimi menüsünü kullanın.
:::image type="content" source="images/atp-time-zone.png" alt-text="Saat dilimi ayarları-1" lightbox="images/atp-time-zone.png":::

## <a name="time-zone-settings"></a>Saat dilimi ayarları

Algılanan ve gerçek siber saldırıların değerlendirilmesi ve analizinde zamanın yönü önemlidir.

Siberforensic araştırmalarda genellikle olay dizisini bir araya getirmek için zaman damgaları kullanılır. Sisteminizin doğru saat dilimi ayarlarını yansıtması önemlidir.

Uç Nokta için Microsoft Defender Eşgüdümlü Evrensel Saat (UTC) veya yerel saati görüntüleyebilir.

Geçerli saat dilimi ayarınız Uç Nokta için Microsoft Defender menüsünde gösterilir. Görüntülenen saat dilimini **Saat dilimi** menüsünde değiştirebilirsiniz.

:::image type="content" source="images/atp-time-zone-menu.png" alt-text="Saat dilimi ayarları-2" lightbox="images/atp-time-zone-menu.png":::

### <a name="utc-time-zone"></a>UTC saat dilimi

Uç Nokta için Microsoft Defender varsayılan olarak UTC saatini kullanır.

Uç Nokta için Microsoft Defender saat dilimini UTC olarak ayarlamak, tüm kullanıcılar için tüm sistem zaman damgalarını (uyarılar, olaylar ve diğerleri) UTC olarak görüntüler. Bu, dünyanın farklı yerlerinde çalışan güvenlik analistlerinin olayları araştırırken aynı zaman damgalarını kullanmasına yardımcı olabilir.

### <a name="local-time-zone"></a>Yerel saat dilimi

Uç Nokta için Microsoft Defender yerel saat dilimi ayarlarını kullanmasını seçebilirsiniz. Tüm uyarılar ve olaylar yerel saat diliminiz kullanılarak görüntülenir.

Yerel saat dilimi cihazınızın bölgesel ayarlarından alınır. Bölgesel ayarlarınızı değiştirirseniz, Uç Nokta için Microsoft Defender saat dilimi de değişir. Bu ayarın seçilmesi, Uç Nokta için Microsoft Defender'de görüntülenen zaman damgalarının tüm Uç Nokta için Microsoft Defender kullanıcılar için yerel saate hizalanacağı anlamına gelir. Farklı küresel konumlarda bulunan analistler artık bölgesel ayarlarına göre Uç Nokta için Microsoft Defender uyarılarını görecek.

Analistler tek bir konumda bulunuyorsa yerel saati kullanmayı seçmek yararlı olabilir. Bu durumda, yerel bir kullanıcı şüpheli bir e-posta bağlantısına tıkladığında olayları yerel saatle ilişkilendirmek daha kolay olabilir.

### <a name="set-the-time-zone"></a>Saat dilimini ayarlama

Uç Nokta için Microsoft Defender saat dilimi varsayılan olarak UTC olarak ayarlanır. Saat dilimini ayarlamak, tüm Uç Nokta için Microsoft Defender görünümlerin saatlerini de değiştirir.

Saat dilimini ayarlamak için:

1. **Saat dilimi** menüsüne tıklayın.
   :::image type="content" source="images/atp-time-zone.png" alt-text="Saat dilimi ayarları-3" lightbox="images/atp-time-zone.png":::
1. **Saat dilimi UTC** göstergesini seçin.
1. **Saat dilimi UTC'yi** veya yerel saat diliminizi (örneğin - 7:00) seçin.

### <a name="regional-settings"></a>Bölgesel ayarlar

Uç Nokta için Microsoft Defender için farklı tarih biçimleri uygulamak için Internet Explorer (IE) ve Microsoft Edge (Edge) için bölgesel ayarları kullanın. Google Chrome gibi başka bir tarayıcı kullanıyorsanız, bu tarayıcının saat ve tarih ayarlarını değiştirmek için gerekli adımları izleyin. 

#### <a name="internet-explorer-ie-and-microsoft-edge"></a>Internet Explorer (IE) ve Microsoft Edge

IE ve Microsoft Edge, Denetim masasının **Saatler, Dil ve Bölge** seçeneğinde yapılandırılan Bölge **ayarlarını kullanır**. 

#### <a name="known-issues-with-regional-formats"></a>Bölgesel biçimlerle ilgili bilinen sorunlar

##### <a name="date-and-time-formats"></a>Tarih ve saat biçimleri

Saat ve tarih biçimleriyle ilgili bazı bilinen sorunlar vardır. Bölgesel ayarlarınızı desteklenen biçimler dışında herhangi bir şekilde yapılandırdığınızda portal ayarlarınızı doğru şekilde yansıtmayabilir.

Aşağıdaki tarih ve saat biçimleri desteklenir:

- Tarih biçimi AA/gg/yyyy
- Tarih biçimi dd/AA/yyyy
- Saat biçimi ss:dd:ss (12 saat biçimi)

Aşağıdaki tarih ve saat biçimleri şu anda desteklenmiyor:

- Tarih biçimi yyyy-AA-gg
- Tarih biçimi dd-AAA-yy
- Tarih biçimi dd/AA/yy
- Tarih biçimi AA/gg/yy
- yy ile tarih biçimi. Sadece yyyy gösterecektir.
- Saat biçimi SS:dd:ss (24 saat biçimi)

##### <a name="decimal-symbol-used-in-numbers"></a>Sayılarda kullanılan ondalık simgesi

**Bölge** ayarlarındaki **Sayılar** biçim ayarlarında virgül seçili olsa bile kullanılan ondalık simgesi her zaman noktadır. Örneğin, 15,5K 15,5K olarak görüntülenir.
