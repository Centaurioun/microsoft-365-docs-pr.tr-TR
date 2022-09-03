---
title: Uç Nokta için Microsoft Defender'de tehdit koruma raporu
description: Tehdit koruma raporunu kullanarak uyarı algılamalarını, kategorilerini ve önem derecesini izleme
keywords: uyarı algılama, kaynak, kategoriye göre uyarı, uyarı önem derecesi, uyarı sınıflandırması, belirleme
ms.service: microsoft-365-security
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
ms.subservice: mde
ms.openlocfilehash: 2e920be103f3008f7a3669d9d6913007cd5e9943
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67585410"
---
# <a name="threat-protection-report-in-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender'de tehdit koruma raporu

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

Tehdit koruması raporu, kuruluşunuzda oluşturulan uyarılar hakkında üst düzey bilgiler sağlar. Rapor, zaman içinde uyarıların algılama kaynaklarını, kategorilerini, önem derecelerini, durumlarını, sınıflandırmalarını ve belirlemelerini gösteren popüler bilgileri içerir.

Pano iki bölümde yapılandırılmıştır:

:::image type="content" source="images/threat-protection-reports.png" alt-text="Tehdit koruması raporu" lightbox="images/threat-protection-reports.png":::

Bölüm|Açıklama
---|---
1|Uyarı eğilimleri
2|Uyarı özeti

## <a name="alert-trends"></a>Uyarı eğilimleri
Varsayılan olarak, uyarı eğilimleri en son tam gün ile biten 30 günlük dönemdeki uyarı bilgilerini görüntüler. Kuruluşunuzda gerçekleşen eğilimlere daha iyi bir bakış açısı elde etmek için, gösterilen zaman aralığını ayarlayarak raporlama dönemine ince ayar yapabilirsiniz. Zaman aralığını ayarlamak için açılan seçeneklerden bir zaman aralığı seçin:

- 30 gün
- 3 ay
- 6 ay
- Özel

> [!NOTE]
> Bu filtreler yalnızca uyarı eğilimleri bölümüne uygulanır. Uyarı özeti bölümünü etkilemez.

## <a name="alert-summary"></a>Uyarı özeti

Uyarı eğilimleri popüler uyarı bilgilerini gösterirken, uyarı özetinde geçerli güne kadar kapsamı belirlenmiş uyarı bilgileri gösterilir.

 Uyarı özeti, ilgili filtrenin uygulandığı belirli bir uyarı kuyruğunda detaya gitmenizi sağlar. Örneğin, Algılama kaynakları kartında EDR çubuğuna tıklanması, yalnızca EDR algılamalarından oluşturulan uyarıları gösteren sonuçlarla birlikte uyarılar kuyruğunu size getirir.

> [!NOTE]
> Özet bölümüne yansıtılan verilerin kapsamı geçerli tarihten 180 gün öncesine kadar belirlenmiştir. Örneğin bugünün tarihi 5 Kasım 2019 ise, özet bölümündeki veriler 5 Mayıs 2019 ile 5 Kasım 2019 arasında başlayan sayıları yansıtır.
>
> Eğilimler bölümüne uygulanan filtre özet bölümüne uygulanmaz.

## <a name="alert-attributes"></a>Uyarı öznitelikleri

Rapor, aşağıdaki uyarı özniteliklerini görüntüleyen kartlardan oluşur:

- **Algılama kaynakları**: uyarıları tetikleme amacıyla Uç Nokta için Microsoft Defender tarafından kullanılan verileri sağlayan algılayıcılar ve algılama teknolojileri hakkındaki bilgileri gösterir.
- **Tehdit kategorileri**: Uyarıları tetikleyen tehdit veya saldırı etkinliği türlerini gösterir ve bu da güvenlik işlemleriniz için olası odak alanlarını gösterir.
- **Önem derecesi**: Tehditlerin kuruluşunuza yönelik toplu olası etkisini ve bunları ele almak için gereken yanıt düzeyini gösteren uyarıların önem derecesini gösterir.
- **Durum**: Uyarıların çözüm durumunu gösterir; el ile verilen uyarı yanıtlarınızın ve otomatik düzeltmenin verimliliğini gösterir (etkinleştirilirse).
- **Sınıflandırma & belirleme**: Çözüme göre uyarıları gerçek tehditler (doğru uyarılar) veya yanlış algılamalar (yanlış uyarılar) olarak sınıflandırmanız fark ederek nasıl sınıflandırdığınız gösterilir. Bu kartlar, bulunan gerçek tehdit türleri veya yanlış algılanan meşru etkinlikler gibi ek içgörüler sağlayarak çözümlenen uyarıların belirlenmesini de gösterir.

## <a name="filter-data"></a>Verileri filtreleme

Belirli özniteliklere sahip uyarıları dahil etmek veya hariç tutmak için sağlanan filtreleri kullanın.

> [!NOTE]
> Bu filtreler rapordaki **tüm** kartlar için geçerlidir.

Örneğin, yalnızca yüksek önem dereceli uyarılarla ilgili verileri göstermek için:

1. **Olaylar & uyarılar** \> **Uyarı** \> **Filtreleri > Önem Derecesi'nin** altında **Yüksek'i** seçin.
2. **Önem Derecesi** altındaki diğer tüm seçeneklerin seçimi kaldırıldığından emin olun.
3. **Uygula'yı** seçin.

## <a name="related-topic"></a>İlgili konu

- [Cihaz durumu ve uyumluluk raporu](machine-reports.md)
