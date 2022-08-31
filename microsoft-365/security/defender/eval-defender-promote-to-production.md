---
title: 7. Adım. Microsoft 365 Defender değerlendirme ortamınızı Üretim'e yükseltme
description: MDI, MDO, MDE ve Cloud Apps için Defender değerlendirmelerinizi Microsoft 365 Defender veya M365D'deki canlı ortamınıza yükseltmek için bu makaleyi kullanın.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
ms.topic: conceptual
ms.openlocfilehash: 018b8047ecce5dd4d41becb19ed779025715fe70
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479676"
---
# <a name="step-7-promote-your-microsoft-365-defender-evaluation-environment-to-production"></a>7. Adım. Microsoft 365 Defender değerlendirme ortamınızı üretim ortamına yükseltme

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Microsoft 365 Defender değerlendirme ortamınızı üretim ortamına yükseltmek için önce gerekli lisansı satın alın. [Değerlendirme ortamını oluşturma](eval-create-eval-environment.md) ve Office 365 E5 lisansını satın alma (Ücretsiz denemeyi başlat'ı seçmek yerine) içindeki adımları izleyin.

Ardından, tüm ek yapılandırmaları tamamlayın ve bunlar tam üretime ulaşana kadar pilot gruplarınızı genişletin.

## <a name="microsoft-defender-for-identity"></a>Kimlik için Microsoft Defender

Kimlik için Defender ek yapılandırma gerektirmez. Gerekli lisansları satın alıp algılayıcıyı tüm Active Directory etki alanı denetleyicilerinize ve Active Directory Federasyon Hizmetleri (AD FS) (AD FS) sunucularına yüklediğinizden emin olmanız yeterlidir.

## <a name="microsoft-defender-for-office-365"></a>Office 365 için Microsoft Defender

MDO başarıyla değerlendirildikten veya pilot olarak değerlendirildikten sonra tüm üretim ortamınıza yükseltilebilir.

1. Gerekli lisansları satın alıp sağlayın ve bunları üretim kullanıcılarınıza atayın.
2. Önerilen temel ilke yapılandırmalarını (Standart veya Katı) üretim e-posta etki alanınıza veya belirli kullanıcı gruplarına karşı yeniden çalıştırın.
3. İsteğe bağlı olarak, üretim e-posta etki alanınız veya kullanıcı gruplarınız için özel MDO ilkeleri oluşturun ve yapılandırın.  Ancak, atanan temel ilkelerin her zaman özel ilkelere göre öncelikli olacağını unutmayın.
4. Doğrudan EOP'ye çözümlenmesi için üretim e-posta etki alanınız için genel MX kaydını güncelleştirin.
5. Tüm üçüncü taraf SMTP ağ geçitlerinin yetkisini alın ve bu geçişle ilişkili EXO bağlayıcılarını devre dışı bırakın veya silin.

## <a name="microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender

Pilottan üretim ortamına Uç Nokta için Microsoft Defender değerlendirme ortamını yükseltmek için[, desteklenen araç ve yöntemlerden](../defender-endpoint/onboard-configure.md) herhangi birini kullanarak hizmete daha fazla uç nokta eklemeniz yeterlidir.

Uç Nokta için Microsoft Defender için daha fazla cihaz eklemek için aşağıdaki genel yönergeleri kullanın.

1. Cihazın [en düşük gereksinimleri](../defender-endpoint/minimum-requirements.md) karşıladığını doğrulayın.
2. Cihaza bağlı olarak, Uç Nokta için Defender portalının ekleme bölümünde sağlanan yapılandırma adımlarını izleyin.
3. Cihazlarınız için uygun yönetim aracını ve dağıtım yöntemini kullanın.
4. Cihazların düzgün şekilde eklendiğini ve hizmete bildirildiğini doğrulamak için bir algılama testi çalıştırın.

## <a name="microsoft-defender-for-cloud-apps"></a>Bulut Uygulamaları için Microsoft Defender

Microsoft Defender for Cloud Apps ek yapılandırma gerektirmez. Gerekli lisansları satın aldığınızdan emin olmanız yeterlidir. Dağıtımın kapsamını belirli kullanıcı gruplarına genişletdiyseniz, üretim ölçeğine ulaşana kadar bu grupların kapsamını artırın.
