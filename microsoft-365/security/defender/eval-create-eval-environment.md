---
title: Daha fazla siber güvenlik ve XDR için Microsoft 365 Defender Değerlendirme Ortamı oluşturma
description: Değerlendirdiğiniz Microsoft 365 Defender XDR'ye nelerin dahil olduğunu öğrenin ve deneme lisanslarını etkinleştirerek Microsoft 365 Defender deneme laboratuvarınızı veya pilot ortamınızı başlatın. XDR siber güvenlik yolculuğunuza buradan başlayın ve bu testi üretime nasıl alacağınızı öğrenin.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 05/19/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: fb097532fe809fa1b1ec4c29a9a489bcb4ea2871
ms.sourcegitcommit: 61b22df76e0f81e5ef11c587b129287886151c79
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2022
ms.locfileid: "66747977"
---
# <a name="step-1-create-the-microsoft-365-defender-evaluation-environment-for-greater-cyber-security"></a>Adım 1. Daha fazla siber güvenlik için Microsoft 365 Defender Değerlendirme Ortamı oluşturma

Bu Microsoft Defender XDR çözümü hakkında bilgi edinebilir ve bu serinin geri kalanında dağıtılan adımlarda derleyebilirsiniz:

- [Ortamı oluşturma](eval-create-eval-environment.md)
- Bu Microsoft XDR'nin her teknolojisini ayarlama veya öğrenme
    - [Kimlik için Microsoft Defender](eval-defender-identity-overview.md)
    - [Office için Microsoft Defender](eval-defender-office-365-overview.md)
    - [Uç Nokta için Microsoft Defender](eval-defender-endpoint-overview.md)
    - [Bulut Uygulamaları için Microsoft Defender](eval-defender-mcas-overview.md)
- [Bu XDR'yi kullanarak araştırma ve yanıtlama](eval-defender-investigate-respond.md)
- [Deneme ortamını üretime yükseltme](eval-defender-promote-to-production.md)
- [Genel Bakış'a geri dön](eval-overview.md)

Bu serideki adımlar, Microsoft 365 Defender XDR'nin arkasındaki kavramları öğrenmekten derlemeye ve değerlendirme ortamını canlı üretim ortamına almaya kadar uçtan uca çalışır.

Değerlendirmede bu sonraki adımı gerçekleştirmenin iki yaygın yolu vardır. Bu seride zaten bir üretim Microsoft 365 kiracınız olduğu varsayılır ve *geçerli ortamdaki* Microsoft 365 Defender değerlendirmek için E5 deneme lisanslarını etkinleştirir. Yerinde değerlendirme, değerlendirme döneminden sonra lisans satın alma işlemiyle tüm güvenlik yöntemlerini korumanıza olanak sağlar.

İkincisi, değerlendirme amacıyla [Microsoft 365 Defender deneme laboratuvarı ortamınızı ayarlamaktır](setup-m365deval.md). Test sırasında işletmeden çok fazla gerçek sinyal almayabileceğini unutmayın.

## <a name="you-will-need-to-activate-e5-trial-licenses-to-evaluate-microsoft-365-defender"></a>Microsoft 365 Defender değerlendirmek için E5 deneme lisanslarını etkinleştirmeniz gerekir

1. Mevcut Microsoft 365 kiracı yönetim portalınızda oturum açın.
2. Gezinti menüsünden **Hizmetleri Satın Al'ı** seçin.
3. aşağı kaydırarak Office 365 bölümüne gelin ve lisans Office 365 E5 altındaki **Ayrıntılar** düğmesini seçin.

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="Microsoft 365 Defender portalındaki Ayrıntılar düğmesi" lightbox="../../media/mdo-eval/2_mdo-eval-license-details.png":::

4. **Ücretsiz denemeyi başlat** bağlantısını seçin.

   :::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="Microsoft 365 Defender portalındaki Ücretsiz denemeyi başlat düğmesi" lightbox="../../media/mdo-eval/3-m365-purchase-button.png":::

5. İsteğinizi onaylayın ve **Şimdi deneyin** düğmesine tıklayın.

   :::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="Microsoft 365 Defender portalındaki Şimdi Dene düğmesi" lightbox="../../media/mdo-eval/4_mdo-trial-order.png":::

## <a name="go-to-the-next-step"></a>Sonraki adıma gitme

[Kimlik için Microsoft 365'i etkinleştirmeyi öğrenin](eval-defender-identity-overview.md)

Veya [Değerlendirme ve pilot Microsoft 365 Defender](eval-overview.md) için Genel Bakış'a geri dönün
