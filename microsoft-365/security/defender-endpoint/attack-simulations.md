---
title: Sanal saldırılar aracılığıyla Uç Nokta için Microsoft Defender deneyimi
description: Uç Nokta için Microsoft Defender ihlalleri nasıl algılayabileceğinizi, araştırabileceğini ve yanıt verebileceğini deneyimlemek için sağlanan saldırı senaryosu simülasyonlarını çalıştırın.
keywords: test, senaryo, saldırı, simülasyon, simülasyon, diy, Uç Nokta için Microsoft Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.openlocfilehash: 20ad6f155a0b9e5dbfc6ff00154f2d4012b80079
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2022
ms.locfileid: "67743382"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a>Sanal saldırılar aracılığıyla Uç Nokta için Microsoft Defender deneyimi 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-attacksimulations-abovefoldlink)

> [!TIP]
>
> - Uç Nokta için Microsoft Defender'deki en son geliştirmeler hakkında bilgi edinin: [Uç Nokta için Defender'daki yenilikler](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).
> - Uç Nokta için Defender, son MITRE değerlendirmesinde sektör lideri optik ve algılama özelliklerini göstermiştir. Okuma: [MITRE ATT&CK tabanlı değerlendirmeden alınan içgörüler](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

Hizmete birkaç cihazdan fazlasını eklemeden önce Uç Nokta için Defender'ı deneyimlemek isteyebilirsiniz. Bunu yapmak için, birkaç test cihazında denetimli saldırı simülasyonları çalıştırabilirsiniz. Sanal saldırıları çalıştırdıktan sonra Uç Nokta için Defender'ın kötü amaçlı etkinliği nasıl ortaya atdığını gözden geçirebilir ve verimli bir yanıta nasıl olanak sağladığını keşfedebilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

Sağlanan simülasyonlardan herhangi birini çalıştırmak için en az [bir yerleşik cihaza](onboard-configure.md) ihtiyacınız vardır.

Her saldırı senaryosuyla birlikte sağlanan kılavuz belgesini okuyun. Her belgede işletim sistemi ve uygulama gereksinimlerinin yanı sıra bir saldırı senaryosuna özgü ayrıntılı yönergeler bulunur.

## <a name="run-a-simulation"></a>Simülasyon çalıştırma

1. **Uç Nokta** \> **Değerlendirme & öğreticileri** \> **Öğreticiler & simülasyonları** bölümünde, kullanılabilir saldırı senaryolarından hangisinin benzetimini yapmak istediğinizi seçin:
   - **Senaryo 1: Belge arka kapı bırakma** - sosyal olarak tasarlanmış bir yem belgesinin teslimini simüle eder. Belge, saldırganlara denetim sağlayan özel olarak hazırlanmış bir arka kapı başlatır.
   - **Senaryo 2: Dosyasız saldırıda PowerShell betiği** - PowerShell'i kullanan, saldırı yüzeyini azaltmayı ve kötü amaçlı bellek etkinliğinin cihaz öğrenmesi algılamasını gösteren dosyasız bir saldırının benzetimini sağlar.
   - **Senaryo 3: Otomatik olay yanıtı - güvenlik olayı yanıt** kapasitenizi ölçeklendirmek için ihlal yapıtlarını otomatik olarak avlayan ve düzelten otomatik araştırmayı tetikler.

2. Seçtiğiniz senaryoyla birlikte sağlanan ilgili izlenecek yol belgesini indirin ve okuyun.

3. **Değerlendirme & öğreticileri Öğreticileri & simülasyonlar** \> bölümüne giderek simülasyon dosyasını indirin veya **simülasyon** betiğini kopyalayın. Dosyayı veya betiği test cihazına indirmeyi seçebilirsiniz, ancak zorunlu değildir.

4. Simülasyon dosyasını veya betiği, izlenecek yol belgesinde açıklandığı gibi test cihazında çalıştırın.

> [!NOTE]
> Simülasyon dosyaları veya betikler saldırı etkinliğini taklit eder ancak aslında zararsızdır ve test cihazına zarar vermez veya tehlikeye atmaz.
>
> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-attacksimulations-belowfoldlink)

## <a name="related-topics"></a>İlgili konular

- [Cihazları ekleme](onboard-configure.md)
- [Windows cihazlarını ekleme](configure-endpoints.md)
