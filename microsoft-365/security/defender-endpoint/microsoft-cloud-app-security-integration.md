---
title: Bulut Uygulamaları için Microsoft Defender tümleştirmesine genel bakış
ms.reviewer: ''
description: Uç Nokta için Microsoft Defender, tüm bulut uygulaması ağ etkinliklerini ileterek Cloud Apps için Defender ile tümleşir.
keywords: bulut, uygulama, ağ, görünürlük, kullanım
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
ms.topic: conceptual
ms.date: 10/18/2018
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 4a988a9d28ffdae2d9629413fa64d033eea263ca
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68231692"
---
# <a name="microsoft-defender-for-cloud-apps-in-defender-for-endpoint-overview"></a>Uç Nokta için Defender'da Microsoft Defender for Cloud Apps genel bakış

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Defender for Cloud Apps, bulut uygulamalarına erişimi denetlemenize ve sınırlamanıza olanak tanıyarak bulut uygulamaları ve hizmetlerinde görünürlük sağlarken, bulutta depolanan verilerde uyumluluk gereksinimlerini zorunlu tutmanızı sağlayan kapsamlı bir çözümdür. Daha fazla bilgi için bkz. [Cloud Apps için Defender](/cloud-app-security/what-is-cloud-app-security).

> [!NOTE]
> Bu özellik, Windows 10 sürüm 1809 veya üzeri ya da [Windows 11](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) çalıştıran cihazlarda Enterprise Mobility + Security için bir E5 lisansı ile kullanılabilir.

## <a name="microsoft-defender-for-endpoint-and-defender-for-cloud-apps-integration"></a>Uç Nokta için Microsoft Defender ve Cloud Apps için Defender tümleştirmesi

Cloud Apps için Defender bulma, kurumsal güvenlik duvarı ve ara sunuculardan bulut trafiği günlüklerinin ona iletilmesini kullanır. Uç Nokta için Microsoft Defender, tüm bulut uygulaması ağ etkinliklerini toplayıp ileterek Cloud Apps için Defender ile tümleştirilerek bulut uygulaması kullanımına benzersiz görünürlük sağlar. İzleme işlevi cihazda yerleşik olarak bulunur ve ağ etkinliğinin tam kapsamını sağlar.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4r4yQ]

Tümleştirme, mevcut Cloud Apps için Defender keşfinde aşağıdaki önemli iyileştirmeleri sağlar:

- Her yerde kullanılabilir - Ağ etkinliği doğrudan uç noktadan toplandığından, artık kurumsal güvenlik duvarı veya ara sunuculardan yönlendirilen trafiğe bağlı olmadığından cihazın bulunduğu her yerde, şirket ağında veya dışında kullanılabilir.

- Hazır çalışır, yapılandırma gerekmez - Bulut trafiği günlüklerinin Cloud Apps için Defender'a iletilmesi için güvenlik duvarı ve ara sunucu yapılandırması gerekir. Uç Nokta için Defender ve Cloud Apps için Defender tümleştirmesiyle yapılandırma gerekmez. Microsoft 365 Defender ayarlardan açın ve hazırsınız.

- Cihaz bağlamı - Bulut trafik günlüklerinin cihaz bağlamı yok. Uç Nokta için Defender ağ etkinliği, cihaz bağlamı (bulut uygulamasına erişen cihaz) ile bildirilir, böylece ağ etkinliğinin tam olarak nerede (cihaz) gerçekleştiğini ve bunu kimin (kullanıcı) gerçekleştirdiğini anlayabilirsiniz.

Bulut bulma hakkında daha fazla bilgi için bkz. [Bulunan uygulamalarla çalışma](/cloud-app-security/discovered-apps).

## <a name="related-topic"></a>İlgili konu

- [Bulut Uygulamaları için Microsoft Defender tümleştimesini yapılandırın](microsoft-cloud-app-security-config.md)
