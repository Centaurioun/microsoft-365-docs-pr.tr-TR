---
title: Uç nokta algılama ve yanıt özelliklerine genel bakış
ms.reviewer: ''
description: Uç Nokta için Microsoft Defender'deki uç nokta algılama ve yanıt özellikleri hakkında bilgi edinin
keywords: Uç Nokta için Microsoft Defender, uç nokta algılama ve yanıt, yanıt, algılama, siber güvenlik, koruma
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
ms.openlocfilehash: c964b8def27e13c93a4742cccdce03e02ae777b0
ms.sourcegitcommit: 2dedd0f594b817779e034afa6c4418def2382a22
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2022
ms.locfileid: "67797182"
---
# <a name="overview-of-endpoint-detection-and-response"></a>Uç nokta algılama ve yanıta genel bakış

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Plan 1 ve 2](defender-endpoint-plan-1-2.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Uç Nokta için Defender'daki uç nokta algılama ve yanıt özellikleri, neredeyse gerçek zamanlı ve eyleme dönüştürülebilir gelişmiş saldırı algılamaları sağlar. Güvenlik analistleri uyarıların önceliklerini etkili bir şekilde belirleyebilir, ihlal kapsamının tamamını görebilir ve tehditleri düzeltmek için yanıt eylemleri gerçekleştirebilir.

Bir tehdit algılandığında, analistin araştırması için sistemde uyarılar oluşturulur. Aynı saldırı tekniklerine sahip veya aynı saldırgana atfedilen uyarılar _olay_ adı verilen bir varlıkta toplanır. Uyarıları bu şekilde toplama, analistlerin tehditleri topluca araştırmasını ve yanıtlamasını kolaylaştırır.

> [!NOTE]
> Uç Nokta için Defender algılama, belirli bir uç noktada gerçekleşen her işlemi veya etkinliği kaydeden bir denetim veya günlüğe kaydetme çözümü olarak tasarlanmamıştır. Algılayıcımızın dahili bir azaltma mekanizması vardır, bu nedenle aynı olayların tekrarlanma oranının yüksek olması günlükleri sular altında tutmaz.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4o1j5]

> [!IMPORTANT]
> [Uç Nokta Planı 1](defender-endpoint-plan-1.md) ve [İş için Microsoft Defender](../defender-business/mdb-overview.md) için Defender yalnızca aşağıdaki el ile yanıt eylemlerini içerir:
> - Antivirüs taraması başlat
> - Cihazı yalıtma
> - Dosyayı durdurma ve karantinaya al
> - Bir dosyayı engellemek veya dosyaya izin vermek için gösterge ekleme

"İhlal varsay" düşünce yapısından ilham alan Uç Nokta için Defender, davranışsal siber telemetri verilerini sürekli olarak toplar. Buna işlem bilgileri, ağ etkinlikleri, çekirdek ve bellek yöneticisine yönelik derin optik, kullanıcı oturum açma etkinlikleri, kayıt defteri ve dosya sistemi değişiklikleri ve diğerleri dahildir. Bilgiler altı ay boyunca depolanır ve analistin saldırının başlangıcına kadar zamanda geriye gitmesine olanak tanır. Analist daha sonra çeşitli görünümlerde özetleyebilir ve birden çok vektör aracılığıyla bir araştırmaya yaklaşabilir.

Yanıt özellikleri, etkilenen varlıklar üzerinde hareket ederek tehditleri hemen düzeltme gücü sağlar.

## <a name="related-topics"></a>İlgili konular

- [Olay sırası](view-incidents-queue.md)
- [Uyarı sırası](alerts-queue.md)
- [Cihazlar listesi](machines-view-overview.md)
