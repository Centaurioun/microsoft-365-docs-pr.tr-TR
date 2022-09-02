---
title: Uç Nokta için Microsoft Defender'da olayları araştırma
description: Bir olayı araştırmanıza yardımcı olmak için ilişkili uyarıları görme, olayı yönetme ve uyarı meta verilerini görme
keywords: araştırma, olay, uyarılar, meta veriler, risk, algılama kaynağı, etkilenen cihazlar, desenler, bağıntı
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 76e944b809317b7783c30251407ba0ef310c7751
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67521345"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender'da olayları araştırma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Ağınızı etkileyen olayları araştırın, ne anlama geldiğini anlayın ve bunları çözmek için kanıtları harmanlayın.

Bir olayı araştırdığınızda şunları görürsünüz:

- Olay ayrıntıları
- Olay açıklamaları ve eylemleri
- Sekmeler (uyarılar, cihazlar, araştırmalar, kanıt, grafik)

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUV]

## <a name="analyze-incident-details"></a>Olay ayrıntılarını analiz etme

**Olay bölmesini** görmek için bir olaya tıklayın. Olay ayrıntılarını ve ilgili bilgileri (uyarılar, cihazlar, araştırmalar, kanıt, grafik) görmek için **Olay sayfasını aç'ı** seçin.

:::image type="content" source="images/atp-incident-details.png" alt-text="Bir olayın ayrıntıları" lightbox="images/atp-incident-details.png":::

### <a name="alerts"></a>Uyarılar

Uyarıları araştırabilir ve bir olayda bunların nasıl birbirine bağlandığını görebilirsiniz. Uyarılar, aşağıdaki nedenlere göre olaylar halinde gruplandırılır:

- Otomatik araştırma - Otomatik araştırma, özgün uyarıyı araştırırken bağlantılı uyarıyı tetikledi
- Dosya özellikleri - Uyarıyla ilişkili dosyalar benzer özelliklere sahiptir
- El ile ilişkilendirme - Bir kullanıcı uyarıları el ile bağladı
- Yakın zaman - Uyarılar belirli bir zaman çerçevesi içinde aynı cihazda tetiklendi
- Aynı dosya - Uyarıyla ilişkilendirilmiş dosyalar tamamen aynıdır
- Aynı URL - Uyarıyı tetikleyen URL tamamen aynıdır

:::image type="content" source="images/atp-incidents-alerts-reason.png" alt-text="Uyarıların bu olayda birbirine bağlanma nedenlerini gösteren olay ayrıntıları sayfasının bulunduğu Uyarılar sekmesi" lightbox="images/atp-incidents-alerts-reason.png":::

Ayrıca bir uyarıyı yönetebilir ve uyarı meta verilerini diğer bilgilerle birlikte görebilirsiniz. Daha fazla bilgi için bkz [. Uyarıları araştırma](investigate-alerts.md).

### <a name="devices"></a>Aygıtları

Ayrıca belirli bir olayın parçası olan veya ilgili cihazları da araştırabilirsiniz. Daha fazla bilgi için bkz [. Cihazları araştırma](investigate-machines.md).

:::image type="content" source="images/atp-incident-device-tab.png" alt-text="Olay ayrıntıları sayfasındaki Cihazlar sekmesi" lightbox="images/atp-incident-device-tab.png":::

### <a name="investigations"></a>Sondajları

Olay **uyarılarına** yanıt olarak sistem tarafından başlatılan tüm otomatik araştırmaları görmek için Araştırmalar'ı seçin.

:::image type="content" source="images/atp-incident-investigations-tab.png" alt-text="Olay ayrıntıları sayfasındaki araştırma sekmesi" lightbox="images/atp-incident-investigations-tab.png":::

## <a name="going-through-the-evidence"></a>Kanıtları gözden geçirerek

Uç Nokta için Microsoft Defender, uyarılardaki tüm olayların desteklenen olaylarını ve şüpheli varlıkları otomatik olarak araştırır ve size otomatik yanıt ve önemli dosyalar, işlemler, hizmetler ve daha fazlası hakkında bilgi sağlar.

Analiz edilen varlıkların her biri virüslü, düzeltilmiş veya şüpheli olarak işaretlenir.

:::image type="content" source="images/atp-incident-evidence-tab.png" alt-text="Olay ayrıntıları sayfasındaki Kanıt sekmesi" lightbox="images/atp-incident-evidence-tab.png":::

## <a name="visualizing-associated-cybersecurity-threats"></a>İlgili siber güvenlik tehditlerini görselleştirme

Uç Nokta için Microsoft Defender, çeşitli veri noktalarından gelen desenleri ve bağıntıları görebilmeniz için tehdit bilgilerini bir olay halinde toplar. Bu tür bağıntıları olay grafı üzerinden görüntüleyebilirsiniz.

### <a name="incident-graph"></a>Olay grafiği

**Graph**, siber güvenlik saldırısının hikayesini anlatır. Örneğin, giriş noktasının ne olduğunu, hangi cihazda güvenliğin ihlal veya etkinliğin gözlemlendiği gösterilir. Vb.

:::image type="content" source="images/atp-incident-graph-tab.png" alt-text="Olay grafiği" lightbox="images/atp-incident-graph-tab.png":::

Olay grafiğindeki dairelere tıklayarak kötü amaçlı dosyaların ayrıntılarını, ilişkili dosya algılamalarını, dünya çapında kaç örnek bulunduğunu, kuruluşunuzda gözlemlenip gözlemlenmediğini, varsa kaç örnek olduğunu görüntüleyebilirsiniz.

:::image type="content" source="images/atp-incident-graph-details.png" alt-text="Olay ayrıntıları sayfası" lightbox="images/atp-incident-graph-details.png":::

## <a name="related-topics"></a>İlgili konular

- [Olay sırası](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Uç Nokta için Microsoft Defender'da olayları araştırma](/microsoft-365/security/defender-endpoint/investigate-incidents)
- [Uç Nokta için Microsoft Defender olaylarını yönetme](/microsoft-365/security/defender-endpoint/manage-incidents)
