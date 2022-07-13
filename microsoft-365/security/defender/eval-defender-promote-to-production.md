---
title: 7. Adım. Microsoft 365 Defender değerlendirme ortamınızı Üretim'e yükseltme
description: MDI, MDO, MDE ve Cloud Apps için Defender değerlendirmelerinizi Microsoft 365 Defender veya M365D'deki canlı ortamınıza yükseltmek için bu makaleyi kullanın.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 769a70177ada62b4dbb505a8363fe3bdbfc4a59a
ms.sourcegitcommit: 61b22df76e0f81e5ef11c587b129287886151c79
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2022
ms.locfileid: "66748747"
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
