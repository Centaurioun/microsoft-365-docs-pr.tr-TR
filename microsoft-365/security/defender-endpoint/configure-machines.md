---
title: Cihazlarınızı doğru yapılandırıldığından emin olun
description: Tehditlere karşı genel dayanıklılığı artırmak ve saldırıları algılama ve yanıtlama yeteneğinizi geliştirmek için cihazları düzgün bir şekilde yapılandırın.
keywords: ekleme, Intune yönetimi, Uç Nokta için Microsoft Defender, Microsoft Defender, Windows Defender, saldırı yüzeyini azaltma, ASR, güvenlik temeli
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
- tier2
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 6ca8123f75e9bed18a6383b96ab74094b62c9f9f
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68167329"
---
# <a name="ensure-your-devices-are-configured-properly"></a>Cihazlarınızı doğru yapılandırıldığından emin olun

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Düzgün yapılandırılmış cihazlarla tehditlere karşı genel dayanıklılığı artırabilir ve saldırıları algılama ve yanıtlama yeteneğinizi geliştirebilirsiniz. Güvenlik yapılandırma yönetimi, cihazlarınızın şunlardan emin olmasını sağlar:

- Uç Nokta için Microsoft Defender ekleme
- Uç Nokta için Defender güvenlik temeli yapılandırmasını karşılama veya aşma
- Stratejik saldırı yüzeyi risk azaltmaları var

Cihaz **yapılandırma yönetimi** sayfasını açmak için gezinti menüsünden Yapılandırma yönetimi'ne tıklayın.

:::image type="content" source="images/secconmgmt_main.png" alt-text="Güvenlik yapılandırma yönetimi sayfası" lightbox="images/secconmgmt_main.png":::

*Cihaz yapılandırma yönetimi sayfası*

Yapılandırma durumunu kuruluş düzeyinde izleyebilir ve Microsoft Intune ve <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalındaki</a> cihaz yönetimi sayfalarına doğrudan, ayrıntılı bağlantılar aracılığıyla kötü ekleme kapsamı, uyumluluk sorunları ve kötü iyileştirilmiş saldırı yüzeyi risk azaltmalarına yanıt olarak hızla eyleme geçebilirsiniz.

Bunu yaparken şu avantajlardan yararlanabilirsiniz:

- Cihazlarınızdaki olayların kapsamlı görünürlüğü
- Ham olayları işlemeye ve ihlal etkinliğini ve tehdit göstergelerini tanımlamaya yönelik güçlü tehdit bilgileri ve güçlü cihaz öğrenme teknolojileri
- Kötü amaçlı implantların yüklenmesini, sistem dosyalarının ve işlemlerinin ele geçirilmesi, veri sızdırma ve diğer tehdit etkinliklerinin etkili bir şekilde durdurulması için yapılandırılmış tam bir güvenlik özellikleri yığını
- Tehdit etkinliğine karşı stratejik savunmaları en üst düzeye çıkarırken üretkenlik üzerindeki etkiyi de en aza indiren iyileştirilmiş saldırı yüzeyi risk azaltmaları

## <a name="enroll-devices-to-intune-management"></a>Cihazları Intune yönetimine kaydetme

Cihaz yapılandırma yönetimi, kuruluşunuzdaki cihazların envanterini ve temel güvenlik yapılandırmasını oluşturmak için Intune cihaz yönetimiyle yakından çalışır. Intune yönetilen Windows cihazlarında yapılandırma sorunlarını izleyebilir ve yönetebilirsiniz.

Cihazlarınızın düzgün yapılandırıldığından emin olmadan önce bunları Intune yönetimine kaydedin. Intune kaydı güçlüdür ve Windows cihazları için çeşitli kayıt seçeneklerine sahiptir. Intune kayıt seçenekleri hakkında daha fazla bilgi [için Windows cihazları için kaydı ayarlama](/intune/windows-enroll) hakkında bilgi edinin.

> [!NOTE]
> Windows cihazlarını Intune kaydetmek için yöneticilere zaten lisans atanmış olmalıdır. [Cihaz kaydı için lisans atama hakkında bilgi edinin](/intune/licenses-assign).

> [!TIP]
> Intune aracılığıyla cihaz yönetimini iyileştirmek [için Intune Uç Nokta için Defender'a bağlayın](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).

## <a name="obtain-required-permissions"></a>Gerekli izinleri alma

Varsayılan olarak, yalnızca Azure AD'de Genel Yönetici veya Intune Hizmet Yöneticisi rolü atanmış kullanıcılar cihazları ekleme ve güvenlik temelini dağıtma için gereken cihaz yapılandırma profillerini yönetebilir ve atayabilir.

Size başka roller atanmışsa gerekli izinlere sahip olduğunuzdan emin olun:

- Cihaz yapılandırmalarına yönelik tam izinler
- Güvenlik temellerine yönelik tam izinler
- Cihaz uyumluluk ilkelerine yönelik okuma izinleri
- Kuruluşa yönelik okuma izinleri

:::image type="content" source="images/secconmgmt_intune_permissions.png" alt-text="Intune'da gerekli izinler" lightbox="images/secconmgmt_intune_permissions.png":::

*Intune cihaz yapılandırma izinleri*

> [!TIP]
> Intune izin atama hakkında daha fazla bilgi edinmek için [özel roller oluşturma hakkında bilgi edinin](/intune/create-custom-role#to-create-a-custom-role).

## <a name="in-this-section"></a>Bu bölümde

Konu|Açıklama
:---|:---
[Uç Nokta için Defender'a eklenen cihazları alma](configure-machines-onboarding.md)|Intune yönetilen cihazların ekleme durumunu izleyin ve Intune aracılığıyla daha fazla cihaz ekleme. 
[Uç Nokta için Defender güvenlik temeline uyumluluğu artırma](configure-machines-security-baseline.md)|Temel uyumluluğu ve uyumsuzluğu izleyin. Güvenlik temelini daha Intune yönetilen cihazlara dağıtın.
[ASR kuralı dağıtım ve algılamalarını iyileştirme](configure-machines-asr.md)|<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalındaki</a> etki analizi araçlarını kullanarak kural dağıtımını ve ince ayar algılamalarını gözden geçirin.

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
