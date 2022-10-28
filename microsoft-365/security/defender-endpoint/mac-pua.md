---
title: Mac'te Uç Nokta için Microsoft Defender ile istenmeyebilecek uygulamaları algılama ve engelleme
description: macOS üzerinde Uç Nokta için Microsoft Defender kullanarak İstenmeyebilecek Uygulamaları (PUA) algılayın ve engelleyin.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, mac, pua, pus, catalina, big sur, monterey, ventura, mac için mde
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
ms.openlocfilehash: 6469537490dfafff5aa3ea62874e4293fe810547
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2022
ms.locfileid: "68769039"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-macos"></a>macOS'ta Uç Nokta için Microsoft Defender ile istenmeyebilecek uygulamaları algılama ve engelleme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

macOS'taki Uç Nokta için Microsoft Defender'daki istenmeyebilecek uygulama (PUA) koruma özelliği, ağınızdaki uç noktalarda PUA dosyalarını algılayabilir ve engelleyebilir.

Bu uygulamalar virüs, kötü amaçlı yazılım veya diğer tehdit türleri olarak kabul edilmez, ancak uç noktalarda performanslarını veya kullanımlarını olumsuz yönde etkileyen eylemler gerçekleştirebilir. PUA ayrıca kötü bir üne sahip olduğu düşünülen uygulamalara da başvurabilir.

Bu uygulamalar ağınıza kötü amaçlı yazılım bulaşma riskini artırabilir, kötü amaçlı yazılım bulaşmalarının tanımlanmasının zor olmasına neden olabilir ve uygulamaları temizlerken BT kaynaklarını boşa harcayabilir.

## <a name="how-it-works"></a>Nasıl çalışır?

macOS'ta Uç Nokta için Microsoft Defender PUA dosyalarını algılayabilir ve raporlayabilir. Engelleme modunda yapılandırıldığında PUA dosyaları karantinaya taşınır.

Bir uç noktada PUA algılandığında, bildirimler devre dışı bırakılmadığı sürece macOS'ta Uç Nokta için Microsoft Defender kullanıcıya bir bildirim sunar. Tehdit adı "Uygulama" sözcüğünü içerir.

## <a name="configure-pua-protection"></a>PUA korumasını yapılandırma

macOS'ta Uç Nokta için Microsoft Defender PUA koruması aşağıdaki yollardan biriyle yapılandırılabilir:

- **Kapalı**: PUA koruması devre dışı bırakıldı.
- **Denetim**: PUA dosyaları ürün günlüklerinde bildirilir, ancak Microsoft 365 Defender portalda raporlanmaz. Kullanıcıya bildirim sunulmaz ve ürün tarafından hiçbir işlem yapılmaz.
- **Engelle**: PUA dosyaları ürün günlüklerinde ve Microsoft 365 Defender portalında bildirilir. Kullanıcıya bir bildirim sunulur ve ürün tarafından işlem yapılır.

> [!WARNING]
> Varsayılan olarak, PUA koruması **Denetim** modunda yapılandırılır.

PUA dosyalarının işlenme şeklini komut satırından veya yönetim konsolundan yapılandırabilirsiniz.

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>PUA korumasını yapılandırmak için komut satırı aracını kullanın:

Terminal'de aşağıdaki komutu yürüterek PUA korumasını yapılandırın:

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>PUA korumasını yapılandırmak için yönetim konsolunu kullanın:

Kuruluşunuzda, JAMF veya Intune gibi bir yönetim konsolundan PUA korumasını, diğer ürün ayarlarının nasıl yapılandırıldığına benzer şekilde yapılandırabilirsiniz. Daha fazla bilgi [için macOS'ta Uç Nokta için Microsoft Defender için tercihleri ayarlama](mac-preferences.md) konusunun [Tehdit türü ayarları](mac-preferences.md#threat-type-settings) bölümüne bakın.

## <a name="related-topics"></a>İlgili konular

- [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
