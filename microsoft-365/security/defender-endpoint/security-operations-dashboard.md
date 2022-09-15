---
title: Microsoft Defender Güvenlik Merkezi Güvenlik işlemleri panosu
description: Panoyu kullanarak risk altındaki cihazları belirleyin, hizmetin durumunu izleyin ve cihazlar ve uyarılar hakkındaki istatistikleri ve bilgileri görün.
keywords: pano, uyarılar, yeni, devam ediyor, çözüldü, risk, risk altındaki cihazlar, bulaşmalar, raporlama, istatistikler, grafikler, grafikler, sistem durumu, etkin kötü amaçlı yazılım algılamaları, tehdit kategorisi, kategoriler, parola çalan, fidye yazılımı, yararlanma, tehdit, düşük önem düzeyi, etkin kötü amaçlı yazılım
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
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: be52ed0d0c4ac2d2388f4d8dd3009e56ee6dbcab
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67693983"
---
# <a name="microsoft-defender-security-center-security-operations-dashboard"></a>Microsoft Defender Güvenlik Merkezi Güvenlik işlemleri panosu

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-secopsdashboard-abovefoldlink)

**Güvenlik işlemleri panosu**, uç nokta algılama ve yanıt özelliklerinin ortaya çıktığı yerdir. Algılamaların nerede görüldüğüne yönelik üst düzey bir genel bakış sağlar ve yanıt eylemlerinin nerede gerekli olduğunu vurgular.

Panoda aşağıdakilerin anlık görüntüsü görüntülenir:

- Etkin uyarılar
- Risk altındaki cihazlar
- Algılayıcı durumu
- Hizmet durumu
- Günlük cihaz raporlama
- Etkin otomatik araştırmalar
- Otomatik araştırma istatistikleri
- Risk altındaki kullanıcılar
- Şüpheli etkinlikler

:::image type="content" source="images/atp-sec-ops-dashboard.png" alt-text="Güvenlik işlemleri panosu" lightbox="images/atp-sec-ops-dashboard.png":::

Göründükleri bağlamı anlamanıza yardımcı olmak için ağınızda şüpheli etkinliklerin olup olmadığını, nerede ve ne zaman gerçekleştiğini hızla belirlemek için uyarıları ve cihazları araştırabilir ve araştırabilirsiniz.

**Güvenlik işlemleri panosunda**, bir cihazdaki önemli olayların veya davranışların tanımlanmasını kolaylaştırmak için toplu olaylar görürsünüz. Ayrıntılı olaylara ve düşük düzeyli göstergelere de detaya gidebilirsiniz.

Ayrıca kuruluşunuzun genel sistem durumu hakkında görsel ipuçları veren tıklanabilir kutucuklara sahiptir. Her kutucuk, ilgili genel bakışın ayrıntılı bir görünümünü açar.

## <a name="active-alerts"></a>Etkin uyarılar

Ağınızdaki son 30 günün genel etkin uyarı sayısını kutucuktan görüntüleyebilirsiniz. Uyarılar **Yeni** ve **Devam Ediyor** olarak gruplandırılır.

:::image type="content" source="images/active-alerts-tile.png" alt-text="Etkin uyarılar sayfası" lightbox="images/active-alerts-tile.png":::

Her grup, ilgili uyarı önem derecelerine göre daha fazla alt kategoriye ayrılır. Bu kategori kuyruğunun (**Yeni** veya **Devam Ediyor**) sıralanmış görünümünü görmek için her uyarı halkasının içindeki uyarı sayısına tıklayın.

Daha fazla bilgi için bkz. [Uyarılara genel bakış](alerts-queue.md).

Her satır bir uyarı önem derecesi kategorisi ve uyarının kısa bir açıklamasını içerir. Ayrıntılı görünümünü görmek için bir uyarıya tıklayabilirsiniz. Daha fazla bilgi için bkz[. Uç Nokta için Microsoft Defender uyarıları](investigate-alerts.md) araştırma ve [Uyarılara genel bakış](alerts-queue.md).

## <a name="devices-at-risk"></a>Risk altındaki cihazlar

Bu kutucuk, en fazla etkin uyarıya sahip cihazların listesini gösterir. Her cihaz için toplam uyarı sayısı, cihaz adının yanındaki bir daire içinde gösterilir ve ardından kutucuğun en ucundaki önem derecelerine göre daha fazla kategorilere ayrılmıştır (etiketini görmek için her önem derecesi çubuğunun üzerine gelin).

:::image type="content" source="images/devices-at-risk-tile.png" alt-text="Risk altındaki cihazlar sayfası" lightbox="images/devices-at-risk-tile.png":::

Bu cihazla ilgili ayrıntıları görmek için cihazın adına tıklayın. Daha fazla bilgi için bkz[. Uç Nokta için Microsoft Defender Cihazlar listesinde cihazları araştırma](investigate-machines.md).

Ayrıca, etkin uyarı sayısına göre sıralanmış olarak doğrudan **Cihazlar listesine** gitmek için kutucuğun üst kısmındaki **Cihazlar listesine** de tıklayabilirsiniz. Daha fazla bilgi için bkz[. Uç Nokta için Microsoft Defender Cihazlar listesinde cihazları araştırma](investigate-machines.md).

## <a name="devices-with-sensor-issues"></a>Algılayıcı sorunları olan cihazlar

**Algılayıcı sorunları olan cihazlar** kutucuğu, tek tek cihazın Uç Nokta için Microsoft Defender hizmetine algılayıcı verileri sağlayabilme özelliği hakkında bilgi sağlar. Kaç cihazın dikkat gerektirdiğini bildirir ve sorunlu cihazları belirlemenize yardımcı olur.

:::image type="content" source="images/atp-tile-sensor-health.png" alt-text="Algılayıcı sorunları olan cihazlar kutucuğu" lightbox="images/atp-tile-sensor-health.png":::

Hizmete düzgün rapor vermeyen cihazların sayısı hakkında bilgi sağlayan iki durum göstergesi vardır:

- **Yanlış yapılandırılmış**: Bu cihazlar algılayıcı verilerini kısmen Uç Nokta için Microsoft Defender hizmetine bildiriyor olabilir ve düzeltilmesi gereken yapılandırma hataları olabilir.
- **Etkin değil**: Geçen ay yedi günden uzun bir süre boyunca Uç Nokta için Microsoft Defender hizmetine raporlamayı durduran cihazlar.

Gruplardan herhangi birine tıkladığınızda, tercihinize göre filtrelenmiş cihazlar listesine yönlendirilirsiniz. Daha fazla bilgi için bkz. [Algılayıcı durumunu denetleme](check-sensor-status.md) ve [Cihazları araştırma](investigate-machines.md).

## <a name="service-health"></a>Hizmet durumu

**Hizmet durumu** kutucuğu, hizmetin etkin olup olmadığını veya sorun olup olmadığını size bildirir.

:::image type="content" source="images/status-tile.png" alt-text="Hizmet durumu sayfası" lightbox="images/status-tile.png":::

Hizmet durumu hakkında daha fazla bilgi için bkz. [Uç Nokta için Microsoft Defender hizmet durumunu denetleme](service-status.md).

## <a name="daily-devices-reporting"></a>Günlük cihaz raporlama

**Günlük cihazlar raporlama** kutucuğu, son 30 gün içinde günlük rapor veren cihaz sayısını temsil eden bir çubuk grafik gösterir. Her gün rapor eden cihazların tam sayısını görmek için grafiğin üzerindeki tek tek çubukların üzerine gelin.

:::image type="content" source="images/atp-daily-devices-reporting.png" alt-text="Günlük cihazlar raporlama kutucuğu" lightbox="images/atp-daily-devices-reporting.png":::

## <a name="active-automated-investigations"></a>Etkin otomatik araştırmalar

Ağınızdaki son 30 günün toplam otomatik araştırma sayısını **Etkin otomatik araştırma kutucuğundan** görüntüleyebilirsiniz. Araştırmalar **Beklemede eylemi**, **Cihaz bekleniyor** ve **Çalışıyor** olarak gruplandırılır.

:::image type="content" source="images/atp-active-investigations-tile.png" alt-text="Etkin otomatik araştırma" lightbox="images/atp-active-investigations-tile.png":::

## <a name="automated-investigations-statistics"></a>Otomatik araştırma istatistikleri

Bu kutucuk, son yedi gün içindeki otomatik araştırmalarla ilgili istatistikleri gösterir. Tamamlanan araştırma sayısını, başarıyla düzeltilen araştırma sayısını, araştırmanın başlatılması için gereken ortalama bekleme süresini, bir uyarıyı düzeltmek için gereken ortalama süreyi, araştırılan uyarı sayısını ve tipik bir el ile araştırmadan kaydedilen otomasyon saat sayısını gösterir. 

:::image type="content" source="images/atp-automated-investigations-statistics.png" alt-text="Otomatik araştırma istatistikleri" lightbox="images/atp-automated-investigations-statistics.png":::

**Otomatik araştırmalara**, **Düzeltilen araştırmalara** ve **araştırılan uyarılar'a** tıklayarak uygun kategoriye göre filtrelenmiş **Araştırma sayfasına** gidebilirsiniz. Bu, bağlam içinde araştırmaların ayrıntılı dökümünü görmenizi sağlar.

## <a name="users-at-risk"></a>Risk altındaki kullanıcılar

Kutucuk, en etkin uyarılara ve yüksek, orta veya düşük uyarılarda görülen uyarı sayısına sahip kullanıcı hesaplarının listesini gösterir. 

:::image type="content" source="images/atp-users-at-risk.png" alt-text="Risk altındaki kullanıcılar sayfası" lightbox="images/atp-users-at-risk.png":::

Kullanıcı hesabıyla ilgili ayrıntıları görmek için kullanıcı hesabına tıklayın. Daha fazla bilgi için bkz [. Kullanıcı hesabını araştırma](investigate-user.md).

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-secopsdashboard-belowfoldlink)

## <a name="related-topics"></a>İlgili konular

- [Uç Nokta için Microsoft Defender portalını anlama](use.md)
- [Portala genel bakış](portal-overview.md)
- [Microsoft Defender Güvenlik Açığı Yönetimi panosunu görüntüleme](tvm-dashboard-insights.md)
- [Tehdit analizi panosunu görüntüleme ve önerilen risk azaltma eylemlerini gerçekleştirme](threat-analytics.md)
