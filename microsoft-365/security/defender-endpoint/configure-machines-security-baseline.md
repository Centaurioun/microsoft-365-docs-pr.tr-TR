---
title: Uç Nokta için Microsoft Defender güvenlik temeline uyumluluğu artırma
description: Uç Nokta için Microsoft Defender güvenlik temeli, güvenlik denetimlerini en iyi korumayı sağlayacak şekilde ayarlar.
keywords: Intune yönetimi, Uç Nokta için Microsoft Defender, Microsoft Defender, Uç Nokta için Microsoft Defender ASR, güvenlik temeli
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
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 01833461638859ff1d4025851f0c8b0201e4eedb
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68201891"
---
# <a name="increase-compliance-to-the-microsoft-defender-for-endpoint-security-baseline"></a>Uç Nokta için Microsoft Defender güvenlik temeline uyumluluğu artırma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Güvenlik temelleri, güvenlik özelliklerinin hem güvenlik uzmanlarının hem de uzman Windows sistem yöneticilerinin yönergelerine göre yapılandırılmasını sağlar. Dağıtıldığında, Uç Nokta için Defender güvenlik temeli, en iyi korumayı sağlamak için Uç Nokta için Defender güvenlik denetimlerini ayarlar.

Güvenlik temellerini ve yapılandırma profillerini kullanarak Intune nasıl atandıklarını anlamak için [bu SSS bölümünü okuyun](/intune/security-baselines#q--a).

Güvenlik temellerine uyumluluk dağıtmadan ve izlemeden önce:

- [Cihazlarınızı Intune yönetimine kaydetme](configure-machines.md#enroll-devices-to-intune-management)
- [Gerekli izinlere sahip olduğunuzdan emin olun](configure-machines.md#obtain-required-permissions)

## <a name="compare-the-microsoft-defender-for-endpoint-and-the-windows-intune-security-baselines"></a>Uç Nokta için Microsoft Defender ve Windows Intune güvenlik temellerini karşılaştırma

Windows Intune güvenlik temeli, Windows çalıştıran cihazları güvenli bir şekilde yapılandırmak için tarayıcı ayarları, PowerShell ayarları ve Microsoft Defender Virüsten Koruma gibi bazı güvenlik özellikleri için ayarlar gibi kapsamlı bir dizi önerilen ayar sağlar. Buna karşılık, Uç Nokta için Defender temeli uç nokta algılama ve yanıt (EDR) ayarlarının yanı sıra Windows Intune güvenlik temelinde bulunan ayarlar da dahil olmak üzere Uç Nokta için Defender yığınındaki tüm güvenlik denetimlerini iyileştirici ayarlar sağlar. Her temel hakkında daha fazla bilgi için bkz:

- [Intune için Windows güvenlik temeli ayarları](/intune/security-baseline-settings-windows)
- [Intune için temel ayarları Uç Nokta için Microsoft Defender](/intune/security-baseline-settings-defender-atp)

İdeal olarak, Uç Nokta için Defender'a eklenen cihazlar her iki taban çizgisine de dağıtılır: Başlangıçta Windows'un güvenliğini sağlamak için Windows Intune güvenlik temeli ve ardından Uç Nokta için Defender güvenlik denetimlerini en iyi şekilde yapılandırmak için üst katmanda yer alan Uç Nokta için Defender güvenlik temeli. Riskler ve tehditlerle ilgili en son verilerden yararlanmak ve temeller geliştikçe çakışmaları en aza indirmek için, kullanıma sunuldukları anda her zaman temellerin en son sürümlerini tüm ürünlere uygulayın.

> [!NOTE]
> Uç Nokta için Defender güvenlik temeli fiziksel cihazlar için iyileştirilmiştir ve şu anda sanal makine (VM) veya VDI uç noktaları üzerinde kullanılması önerilmez. Bazı temel ayarlar, sanallaştırılmış ortamlardaki uzak etkileşimli oturumları etkileyebilir.

## <a name="monitor-compliance-to-the-defender-for-endpoint-security-baseline"></a>Uç Nokta için Defender güvenlik temeline uyumluluğu izleme

[Cihaz yapılandırma yönetimindeki](configure-machines.md) **Güvenlik temeli** kartı, Uç Nokta için Defender güvenlik temeli atanmış Windows 10 ve Windows 11 cihazlarda uyumlulukla ilgili genel bir bakış sağlar.

:::image type="content" source="images/secconmgmt_baseline_card.png" alt-text="Güvenlik temel kartı" lightbox="images/secconmgmt_baseline_card.png":::

*Uç Nokta için Defender güvenlik temeline uyumluluğu gösteren kart*

Her cihaza aşağıdaki durum türlerinden biri verilir:

- **Taban çizgisiyle eşleşir**: Cihaz ayarları temeldeki tüm ayarlarla eşleşir.
- **Taban çizgisiyle eşleşmiyor**: En az bir cihaz ayarı taban çizgisiyle eşleşmiyor.
- **Yanlış yapılandırılmış**: Cihazda en az bir temel ayar düzgün yapılandırılmamış ve çakışma, hata veya bekleme durumunda.
- **Uygulanamaz**: Cihazda en az bir temel ayar geçerli değildir.

Belirli cihazları gözden geçirmek için kartta **Güvenlik temelini yapılandır'ı** seçin. Bu sizi Intune cihaz yönetimine götürür. Buradan, cihazların adları ve **durumları için Cihaz durumu'nu** seçin.

> [!NOTE]
> Cihaz yapılandırma yönetimi sayfasında ve Intune genel bakış ekranlarında görüntülenen toplu verilerde tutarsızlıklarla karşılaşabilirsiniz.

## <a name="review-and-assign-the-microsoft-defender-for-endpoint-security-baseline"></a>Uç Nokta için Microsoft Defender güvenlik temelini gözden geçirin ve atayın

Cihaz yapılandırma yönetimi yalnızca özel olarak Uç Nokta için Microsoft Defender güvenlik temeli atanmış Windows 10 ve Windows 11 cihazların temel uyumluluğunu izler. Temeli rahatça gözden geçirebilir ve Intune cihaz yönetimindeki cihazlara atayabilirsiniz.

1. Intune cihaz yönetimine gitmek için **Güvenlik temeli kartında Güvenlik temelini** **yapılandır'ı** seçin. Taban çizgisi uyumluluğuna benzer bir genel bakış görüntülenir.

   > [!TIP]
   > Alternatif olarak, Tüm hizmetler > Intune > Cihaz güvenliği > **Güvenlik temelleri > Microsoft Defender ATP temeli'nden Microsoft Azure portal** Uç Nokta için Defender güvenlik temeline gidebilirsiniz.

2. Yeni bir profil oluşturun.

   :::image type="content" source="images/secconmgmt_baseline_intuneprofile1.png" alt-text="Intune'daki Uç Nokta için Microsoft Defender güvenlik temeli genel bakış sayfasındaki Profil oluştur sekmesi" lightbox="images/secconmgmt_baseline_intuneprofile1.png":::<br>
   *Intune güvenlik temeli Uç Nokta için Microsoft Defender genel bakış*

3. Profil oluşturma sırasında, temeldeki belirli ayarları gözden geçirebilir ve ayarlayabilirsiniz.

   :::image type="content" source="images/secconmgmt_baseline_intuneprofile2.png" alt-text="Intune profil oluşturma sırasında güvenlik temeli seçenekleri" lightbox="images/secconmgmt_baseline_intuneprofile2.png":::<br>
   *Intune profil oluşturma sırasında güvenlik temeli seçenekleri*

4. Profili uygun cihaz grubuna atayın.

   :::image type="content" source="images/secconmgmt_baseline_intuneprofile3.png" alt-text="Intune'de Güvenlik temel profilleri" lightbox="images/secconmgmt_baseline_intuneprofile3.png":::<br>
   *Intune güvenlik temeli profilini atama*

5. Profili oluşturarak kaydedin ve atanan cihaz grubuna dağıtın.

   :::image type="content" source="images/secconmgmt_baseline_intuneprofile4.png" alt-text="Intune güvenlik temeli atama" lightbox="images/secconmgmt_baseline_intuneprofile4.png":::<br>
   *Intune'de güvenlik temeli profili oluşturma*

> [!TIP]
> Intune üzerindeki güvenlik temelleri, cihazlarınızı kapsamlı bir şekilde güvenli hale getirmek ve korumak için kullanışlı bir yol sağlar. [Intune güvenlik temelleri hakkında daha fazla bilgi edinin](/intune/security-baselines).

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a>İlgili konular

- [Cihazlarınızı doğru yapılandırıldığından emin olun](configure-machines.md)
- [cihazları Uç Nokta için Microsoft Defender ekleme](configure-machines-onboarding.md)
- [ASR kuralı dağıtım ve algılamalarını iyileştirme](configure-machines-asr.md)
