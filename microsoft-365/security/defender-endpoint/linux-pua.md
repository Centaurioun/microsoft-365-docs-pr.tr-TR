---
title: Linux'ta Uç Nokta için Microsoft Defender ile istenmeyebilecek uygulamaları algılama ve engelleme
description: Linux'ta Uç Nokta için Microsoft Defender kullanarak İstenmeyebilecek Uygulamaları (PUA) algılayın ve engelleyin.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, linux, pua, pus
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 17977fd9ff6d90aa910e0fa4fef0aa489563a03a
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68224480"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-linux"></a>Linux'ta Uç Nokta için Microsoft Defender ile istenmeyebilecek uygulamaları algılama ve engelleme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Linux üzerinde Uç Nokta için Defender'daki istenmeyebilecek uygulama (PUA) koruma özelliği, ağınızdaki uç noktalarda PUA dosyalarını algılayabilir ve engelleyebilir.

Bu uygulamalar virüs, kötü amaçlı yazılım veya diğer tehdit türleri olarak kabul edilmez, ancak uç noktalarda performanslarını veya kullanımlarını olumsuz yönde etkileyen eylemler gerçekleştirebilir. PUA ayrıca kötü bir üne sahip olduğu düşünülen uygulamalara da başvurabilir.

Bu uygulamalar ağınıza kötü amaçlı yazılım bulaşma riskini artırabilir, kötü amaçlı yazılım bulaşmalarının tanımlanmasının zor olmasına neden olabilir ve uygulamaları temizlerken BT kaynaklarını boşa harcayabilir.

## <a name="how-it-works"></a>Nasıl çalışır?

Linux'ta Uç Nokta için Defender PUA dosyalarını algılayabilir ve raporlayabilir. Engelleme modunda yapılandırıldığında PUA dosyaları karantinaya taşınır.

Bir uç noktada PUA algılandığında, Linux'ta Uç Nokta için Defender tehdit geçmişinde bulaşmanın kaydını tutar. Geçmiş, Microsoft 365 Defender portalından veya komut satırı aracı aracılığıyla `mdatp` görselleştirilebilir. Tehdit adı "Uygulama" sözcüğünü içerir.

## <a name="configure-pua-protection"></a>PUA korumasını yapılandırma

Linux'ta Uç Nokta için Defender'da PUA koruması aşağıdaki yollardan biriyle yapılandırılabilir:

- **Kapalı**: PUA koruması devre dışı bırakıldı.
- **Denetim**: PUA dosyaları ürün günlüklerinde bildirilir ancak Microsoft 365 Defender raporlanmaz. Tehdit geçmişinde enfeksiyon kaydı depolanmaz ve ürün tarafından hiçbir işlem yapılmaz.
- **Engelle**: PUA dosyaları ürün günlüklerinde ve Microsoft 365 Defender bildirilir. Enfeksiyonun bir kaydı tehdit geçmişinde depolanır ve ürün tarafından eylem yapılır.

> [!WARNING]
> Varsayılan olarak, PUA koruması **Denetim** modunda yapılandırılır.

PUA dosyalarının işlenme şeklini komut satırından veya yönetim konsolundan yapılandırabilirsiniz.

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>PUA korumasını yapılandırmak için komut satırı aracını kullanın:

Terminal'de aşağıdaki komutu yürüterek PUA korumasını yapılandırın:

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>PUA korumasını yapılandırmak için yönetim konsolunu kullanın:

Kuruluşunuzda PUA korumasını Puppet veya Ansible gibi bir yönetim konsolundan, diğer ürün ayarlarının nasıl yapılandırıldığına benzer şekilde yapılandırabilirsiniz. Daha fazla bilgi [için, Linux'ta Uç Nokta için Defender tercihlerini ayarlama](linux-preferences.md) makalesinin [Tehdit türü ayarları](linux-preferences.md#threat-type-settings) bölümüne bakın.

## <a name="related-articles"></a>İlgili makaleler

- [Linux'ta Uç Nokta için Defender tercihlerini ayarlama](linux-preferences.md)
