---
title: Uç Nokta Saldırısı Bildirimleri
ms.reviewer: ''
description: Endpoint Attack Notifications, ağınıza yönelik en önemli tehditler için proaktif avcılık sağlar.
keywords: Endpoint Attack Notification, yönetilen tehdit avcılığı, yönetilen algılama ve yanıt (MDR) hizmeti, MTE, Microsoft Tehdit Uzmanları, uç nokta saldırı bildirimi, Defender Uzmanlarına Sorun, isteğe bağlı uzmanlar
search.product: Windows 10
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: vpattnaik
author: vpattnai
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 3ad9976614ee45b55b3c2570c1d3090c2259377e
ms.sourcegitcommit: 50da6f1f6ef2274c17ed9729e7ad84395b0a9be2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2022
ms.locfileid: "68506843"
---
# <a name="endpoint-attack-notifications"></a>Uç Nokta Saldırısı Bildirimleri

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> Bu, Uç Nokta için Microsoft Defender hizmetinizde tehdit avcılığı konularını kapsar. Ancak, hizmeti geçerli lisansınızın ötesinde keşfetmek ve tehditleri yalnızca uç noktalarda değil, aynı zamanda Office 365, bulut uygulamaları ve kimlik üzerinde proaktif olarak avlamak istiyorsanız [Microsoft Defender Uzmanlar'a](/microsoft-365/security/defender/defender-experts-for-hunting) bakın. 

Endpoint Attack Notifications (daha önce Microsoft Tehdit Uzmanları - Hedefli Saldırı Bildirimi olarak adlandırılıyordu), insan saldırgan saldırılar, uygulamalı klavye saldırıları veya siber casusluk gibi gelişmiş saldırılar da dahil olmak üzere ağınıza yönelik en önemli tehditler için proaktif avcılık sağlar. Bu bildirimler yeni bir uyarı olarak gösterilir. Yönetilen tehdit avcılığı hizmeti şunları içerir:

- Tehdit izleme ve analiz, işletme için bekleme süresini ve riski azaltma
- Hem bilinen hem de bilinmeyen saldırıları keşfetmek ve önceliklerini belirlemeye yönelik avcı tarafından eğitilmiş yapay zeka
- En önemli riskleri belirleme, SOC'ların zamanı ve enerjiyi en üst düzeye çıkarmasını sağlama
- Risk kapsamı ve hızlı SOC yanıtı sağlamak için hızla teslim edilebilecek kadar çok bağlam


![Uç Nokta Saldırısı Bildirimleri uyarısının ekran görüntüsü](../../media/defender-endpoint/endpoint-attack-notification-alert.png)

## <a name="apply-for-endpoint-attack-notifications"></a>Uç Nokta Saldırısı Bildirimleri için Uygula
Uç Nokta için Microsoft Defender müşterisiyseniz Endpoint Attack Notifications için başvurabilirsiniz. **Uygulanacak Ayarlar** \> **Uç Noktaları** \> **Genel** \> **Gelişmiş özellikler** \> **Uç Nokta Saldırısı Bildirimleri'ne** gidin. Kabul edildikten sonra Uç Nokta Saldırısı Bildirimleri'nin avantajlarından yararlanırsınız.

![365 Defender Portalında Uç Nokta Saldırısı Bildirimlerini etkinleştirme](../../media/defender-endpoint/enable-endpoint-attack-notifications.png)

## <a name="receive-endpoint-attack-notifications"></a>Uç Nokta Saldırısı bildirimlerini alma
Uç Nokta Saldırısı Bildirimleri, Ortamınızdaki şüpheli etkinliklere göre Microsoft'un yönetilen avcılık hizmeti tarafından el ile hazırlanmış uyarılardır. Bunlar birkaç ortam üzerinden görüntülenebilir:
- Microsoft 365 Defender portalındaki uyarılar kuyruğu
- [API'yi](../../security/defender-endpoint/get-alerts.md) kullanma
- Gelişmiş avcılıkta [DeviceAlertEvents](../../security/defender-endpoint/advanced-hunting-devicealertevents-table.md) tablosu
- E-posta [bildirimleri kuralı yapılandırıyorsanız e-postanız](../../security/defender-endpoint/configure-email-notifications.md)


Uç Nokta Saldırısı Bildirimleri şu şekilde tanımlanabilir:
- **Endpoint Attack Notification** adlı bir etiketiniz var
- **Uç Nokta için Microsoft Defender Microsoft Defender** \> **Uzmanlarından** oluşan bir hizmet kaynağına sahip olmanız

> [!NOTE]
> Uç Nokta Saldırısı Bildirimleri'ne kaydolduysanız ancak hizmetten herhangi bir uyarı görmüyorsanız, güçlü bir güvenlik duruşu olduğunu ve saldırılara daha az eğilimli olduğunuzu gösterir.

## <a name="create-an-email-notification-rule"></a>E-posta bildirim kuralı oluşturma
Bildirim alıcıları için e-posta bildirimleri göndermek için kurallar oluşturabilirsiniz. Ayrıntılar için bkz. E-posta bildirimi oluşturmak, düzenlemek, silmek veya sorunlarını gidermek için uyarı bildirimlerini [yapılandırma](configure-email-notifications.md) .


## <a name="next-steps"></a>Sonraki adımlar
- Doğrudan Uç Nokta için Microsoft Defender portalından Defender Uzmanlarına belirli uç nokta bildirimleriyle ilgili içgörüler hakkında soru sormak için [Bkz. Defender Uzmanlarına Sorun](../defender-endpoint/experts-on-demand.md).
- Uç noktalar, Office 365, bulut uygulamaları ve kimlik genelinde tehditleri proaktif olarak avlamak [için Microsoft Defender Uzmanlar'a](../defender/defender-experts-for-hunting.md) bakın.
