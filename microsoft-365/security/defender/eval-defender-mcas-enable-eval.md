---
title: Microsoft Defender for Cloud Apps için değerlendirme ortamını etkinleştirme
description: Office 365 için Microsoft Defender içinde Bulut Uygulamaları için Defender mimarisini öğrenin ve Microsoft 365 Defender ürünleri arasındaki etkileşimleri anlayın.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 0c9f4687cf36d4db5f22cd6e1b95f55eebc84cf9
ms.sourcegitcommit: 61b22df76e0f81e5ef11c587b129287886151c79
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2022
ms.locfileid: "66749934"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Apps için değerlendirme ortamını etkinleştirme

**Şunlar için geçerlidir:**

- Microsoft 365 Defender

Bu makale, Microsoft Defender for Cloud Apps için değerlendirme ortamını ayarlama işleminin [2. Adımıdır](eval-defender-mcas-overview.md). Bu işlem hakkında daha fazla bilgi için [genel bakış makalesine](eval-defender-mcas-overview.md) bakın.

Bu makale, Bulut Uygulamaları için Defender portalına erişme ve bulut uygulaması trafik verilerini toplamak için gerekli tümleştirmeyi yapılandırma işleminde size yol gösterir.

Ortamınızda kullanılan bulut uygulamalarını bulmak için aşağıdaki yöntemlerden birini veya ikisini birden uygulayabilirsiniz:

- Uç Nokta için Microsoft Defender ile tümleştirerek Cloud Discovery ile hızla çalışmaya başlayın. Bu yerel tümleştirme, ağınızdaki ve ağınızdaki Windows 10 ve Windows 11 cihazlarınızda bulut trafiğiyle ilgili verileri hemen toplamaya başlamanızı sağlar.
- Ağınıza bağlı tüm cihazlar tarafından erişilen tüm bulut uygulamalarını bulmak için, güvenlik duvarlarınıza ve diğer proxy'lerinize Cloud Apps için Defender günlük toplayıcısını dağıtın. Bu dağıtım uç noktalarınızdan veri toplamaya yardımcı olur ve analiz için Bulut Uygulamaları için Defender'a gönderir. Cloud Apps için Defender, daha da fazla özellik için bazı üçüncü taraf proxy'lerle yerel olarak tümleşir.

Bu makale her iki yöntem için de rehberlik içerir.

Microsoft Defender for Cloud Apps ayarlamak için aşağıdaki adımları kullanın.

:::image type="content" source="../../media/defender/m365-defender-mcas-eval-enable-steps.png" alt-text="Microsoft Defender değerlendirme ortamında Microsoft Microsoft Defender for Cloud Apps etkinleştirme adımları" lightbox="../../media/defender/m365-defender-mcas-eval-enable-steps.png":::

- [1. Adım. Cloud Apps için Defender portalına bağlanma](#step-1)
- [2. Adım. Uç Nokta için Microsoft Defender ile tümleştirme](#step-2)
- [3. Adım. Güvenlik duvarlarınızda ve diğer proxy'lerde Cloud Apps için Defender günlük toplayıcısını dağıtma](#step-3)
- [4. Adım. Kuruluşunuzda hangi uygulamaların kullanıldığını görmek için Cloud Discovery panosunu görüntüleyin](#step-4)

<a name="step-1"></a>

## <a name="step-1-connect-to-the-defender-for-cloud-apps-portal"></a>Adım 1. Cloud Apps için Defender portalına bağlanma

Lisanslama işlemini doğrulamak ve Cloud Apps için Defender portalına bağlanmak için bkz[. Hızlı Başlangıç: Microsoft Defender for Cloud Apps kullanmaya başlama](/cloud-app-security/getting-started-with-cloud-app-security).

Portala hemen bağlanamıyorsanız IP adresini güvenlik duvarınızın izin verilenler listesine eklemeniz gerekebilir. Bkz. [Cloud Apps için Defender için temel kurulum](/cloud-app-security/general-setup).

Sorun yaşamaya devam ediyorsanız [Ağ gereksinimleri'ne](/cloud-app-security/network-requirements) bakın.

<a name="step-2"></a>

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a>Adım 2. Uç Nokta için Microsoft Defender ile tümleştirme

Microsoft Defender for Cloud Apps Uç Nokta için Microsoft Defender ile yerel olarak tümleşir. Tümleştirme, Cloud Discovery'nin kullanıma alınmasını kolaylaştırır, Cloud Discovery özelliklerini kurumsal ağınızın ötesine genişletir ve cihaz tabanlı araştırmayı etkinleştirir. Bu tümleştirme, BT tarafından yönetilen Windows 10 ve Windows 11 cihazlardan erişilen bulut uygulamalarını ve hizmetlerini gösterir.

Uç Nokta için Microsoft Defender zaten ayarladıysanız, Cloud Apps için Defender ile tümleştirmeyi yapılandırmak, Microsoft 365 Defender bir geçiş düğmesidir. Tümleştirme açıldıktan sonra Cloud Apps için Defender portalına dönebilir ve Cloud Discovery Panosu'nda zengin verileri görüntüleyebilirsiniz.

Bu görevleri gerçekleştirmek için bkz. [Microsoft Defender for Cloud Apps ile tümleştirme Uç Nokta için Microsoft Defender](/cloud-app-security/mde-integration).

<a name="step-3"></a>

## <a name="step-3-deploy-the-defender-for-cloud-apps-log-collector-on-your-firewalls-and-other-proxies"></a>Adım 3. Güvenlik duvarlarınızda ve diğer proxy'lerde Cloud Apps için Defender günlük toplayıcısını dağıtma

Ağınıza bağlı tüm cihazların kapsamı için, uç noktalarınızdan veri toplamak ve analiz için Cloud Apps için Defender'a göndermek üzere güvenlik duvarlarınızda ve diğer proxy'lerde Cloud Apps için Defender günlük toplayıcısını dağıtın.

Aşağıdaki Güvenli Web Ağ Geçitlerinden (SWG) birini kullanıyorsanız, Bulut Uygulamaları için Defender sorunsuz dağıtım ve tümleştirme sağlar:

- Zscaler
- iboss
- Corrata
- Menlo Güvenliği

Bu ağ cihazlarıyla tümleştirme hakkında daha fazla bilgi için bkz. [Cloud Discovery'yi ayarlama](/cloud-app-security/set-up-cloud-discovery).

<a name="step-4"></a>

## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a>Adım 4. Kuruluşunuzda hangi uygulamaların kullanıldığını görmek için Cloud Discovery panosunu görüntüleyin

Cloud Discovery panosu, bulut uygulamalarının kuruluşunuzda nasıl kullanıldığı hakkında daha fazla içgörü sağlamak üzere tasarlanmıştır. Ne tür uygulamaların kullanıldığına, açık uyarılarınıza ve kuruluşunuzdaki uygulamaların risk düzeylerine bir bakışta genel bakış sağlar.

Cloud Discovery panosunu kullanmaya başlamak için bkz. [Bulunan uygulamalarla çalışma](/cloud-app-security/discovered-apps).

## <a name="next-steps"></a>Sonraki adımlar

Adım 3 /3: [Pilot Microsoft Defender for Cloud Apps](eval-defender-mcas-pilot.md)

[Değerlendirme Microsoft Defender for Cloud Apps](eval-defender-mcas-overview.md) için genel bakışa dönün

[Değerlendirme ve pilot Microsoft 365 Defender](eval-overview.md) genel bakışa dönün
