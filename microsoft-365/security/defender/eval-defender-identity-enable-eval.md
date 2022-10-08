---
title: Kimlik için Microsoft Defender için değerlendirme ortamını etkinleştirme
description: Algılayıcıyı yapılandırmaya & yükleyerek ve diğer bilgisayarlardaki yerel yöneticileri bularak Microsoft 365 Defender deneme laboratuvarında veya pilot ortamda Kimlik için Microsoft Defender ayarlayın.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
- tier1
ms.topic: conceptual
ms.openlocfilehash: e549c9c080e420f0b9aaf9fb18ac6552d7385a7f
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68059294"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-identity"></a>Kimlik için Microsoft Defender için değerlendirme ortamını etkinleştirme

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Bu makale, Kimlik için Microsoft Defender için değerlendirme ortamını ayarlama işleminin [2. adımıdır](eval-defender-identity-overview.md). Bu işlem hakkında daha fazla bilgi için [genel bakış makalesine](eval-defender-identity-overview.md) bakın.

Kimlik için Microsoft Defender ortamınızı ayarlamak için aşağıdaki adımları kullanın. 

:::image type="content" source="../../media/defender/m365-defender-identity-eval-enable-steps.png" alt-text="Microsoft Defender değerlendirme ortamında Kimlik için Microsoft Defender etkinleştirme adımları" lightbox="../../media/defender/m365-defender-identity-eval-enable-steps.png":::

- [1. Adım. Kimlik için Defender Örneğini ayarlama](#step-1-set-up-the-defender-for-identity-instance)
- [2. Adım. Algılayıcıyı yükleme ve yapılandırma](#step-2-install-and-configure-the-sensor)
- [3. Adım. Algılayıcı ile makinelerde olay günlüğü ve ara sunucu ayarlarını yapılandırma](#step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor)
- [4. Adım. Kimlik için Defender'ın diğer bilgisayarlardaki yerel yöneticileri tanımlamasına izin ver](#step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers)

## <a name="step-1-set-up-the-defender-for-identity-instance"></a>Adım 1. Kimlik için Defender Örneğini ayarlama

Örneğinizi oluşturmak ve ardından bu örneği Active Directory ortamınıza bağlamak için Kimlik için Defender portalında oturum açın. 

|  Adım | Açıklama     |Daha fazla bilgi  |
|---------|---------|---------|
|1     | Kimlik için Defender örneğini oluşturma        | [Hızlı Başlangıç: Kimlik için Microsoft Defender örneğinizi oluşturma](/defender-for-identity/install-step1)        |
|2     | Kimlik için Defender örneğini Active Directory ormanınıza bağlama   | [Hızlı Başlangıç: Active Directory Ormanınıza bağlanma](/defender-for-identity/install-step2)  |

## <a name="step-2-install-and-configure-the-sensor"></a>Adım 2. Algılayıcıyı yükleme ve yapılandırma

Ardından, şirket içi ortamınızdaki etki alanı denetleyicilerinde ve AD FS sunucularında Kimlik için Defender algılayıcısını indirin, yükleyin ve yapılandırın.

|  Adım | Açıklama     |Daha fazla bilgi  |
|---------|---------|---------|
|1     | Kaç Kimlik için Microsoft Defender algılayıcıya ihtiyacınız olduğunu belirleyin.        | [Kimlik için Microsoft Defender için kapasite planlama](/defender-for-identity/capacity-planning)   |
|2     | Algılayıcı kurulum paketini indirme  |  [Hızlı Başlangıç: Kimlik için Microsoft Defender algılayıcı kurulum paketini indirme](/defender-for-identity/install-step3)   |
|3     | Kimlik için Defender algılayıcısını yükleme    |  [Hızlı Başlangıç: Kimlik için Microsoft Defender algılayıcısını yükleme](/defender-for-identity/install-step4)       |
|4     | Algılayıcıyı yapılandırma       |  [Kimlik için Microsoft Defender algılayıcı ayarlarını yapılandırma](/defender-for-identity/install-step5)   |

## <a name="step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor"></a>Adım 3. Algılayıcı ile makinelerde olay günlüğü ve ara sunucu ayarlarını yapılandırma

Algılayıcıyı yüklediğiniz makinelerde algılama özelliklerini etkinleştirmek ve geliştirmek için Windows olay günlüğü toplama ve İnternet proxy ayarlarını yapılandırın.

|  Adım | Açıklama     |Daha fazla bilgi  |
|---------|---------|---------|
|1     | Windows olay günlüğü koleksiyonunu yapılandırma         | [Windows Olay koleksiyonunu yapılandırma](/defender-for-identity/configure-windows-event-collection)        |
|2     | İnternet proxy ayarlarını yapılandırma        | [Kimlik için Microsoft Defender Algılayıcınız için uç nokta ara sunucusu ve İnternet bağlantı ayarlarını yapılandırma](/defender-for-identity/configure-proxy)        |

## <a name="step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers"></a>Adım 4. Kimlik için Defender'ın diğer bilgisayarlardaki yerel yöneticileri tanımlamasına izin ver

Kimlik için Microsoft Defender yanal hareket yolu algılama, belirli makinelerdeki yerel yöneticileri tanımlayan sorgulara dayanır. Bu sorgular, Kimlik için Defender Hizmeti hesabı kullanılarak SAM-R protokolüyle gerçekleştirilir. 

Windows istemcilerinin ve sunucularının Kimlik için Defender hesabınızın SAM-R gerçekleştirmesine izin vermesini sağlamak için, Ağ erişim ilkesinde listelenen yapılandırılmış hesaplara ek olarak Kimlik için Defender hizmet hesabını eklemek için grup ilkesi bir değişiklik yapılmalıdır. **Etki alanı denetleyicileri dışındaki** tüm bilgisayarlara grup ilkeleri uyguladığıdan emin olun.

Bunun nasıl yapılacağını açıklayan yönergeler için bkz[. SAM'ye uzaktan çağrı yapmak için Kimlik için Microsoft Defender yapılandırma](/defender-for-identity/install-step8-samr). 

## <a name="next-steps"></a>Sonraki adımlar

Adım 3 /3: [Pilot Kimlik için Microsoft Defender](eval-defender-identity-pilot.md)

[Değerlendirme Kimlik için Microsoft Defender](eval-defender-identity-overview.md) için genel bakışa dönün

[Değerlendirme ve pilot Microsoft 365 Defender](eval-overview.md) genel bakışa dönün
