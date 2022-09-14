---
title: cihazları Uç Nokta için Microsoft Defender ekleme
description: Uç Nokta için Microsoft Defender ve ekleme oranını artırmak için Intune yönetilen cihazların ekleme işlemini izleyin.
keywords: ekleme, Intune yönetimi, Uç Nokta için Microsoft Defender, Microsoft Defender, Windows Defender, yapılandırma yönetimi
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 8a4a97e082e0f3b6d129e8c1bf86c6918de29b89
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67678613"
---
# <a name="get-devices-onboarded-to-microsoft-defender-for-endpoint"></a>cihazları Uç Nokta için Microsoft Defender ekleme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Eklenen her cihaz ek bir uç nokta algılama ve yanıt (EDR) sensörü ekler ve ağınızdaki ihlal etkinliğine göre görünürlüğü artırır. Ekleme ayrıca bir cihazın güvenlik açığı olan bileşenler ve güvenlik yapılandırma sorunları için denetlenebilmesini ve saldırılar sırasında kritik düzeltme eylemleri alabilmesini sağlar.

Cihazların ekleme işlemini izlemeden ve yönetmeden önce:

- [Cihazlarınızı Intune yönetimine kaydetme](configure-machines.md#enroll-devices-to-intune-management)
- [Gerekli izinlere sahip olduğunuzdan emin olun](configure-machines.md#obtain-required-permissions)

İstemcileri Uç Nokta için Microsoft Defender ile kolayca ekleme hakkında bilgi edinmek için bu videoyu izleyin.
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr?rel=0]

## <a name="discover-and-track-unprotected-devices"></a>Korumasız cihazları bulma ve izleme

**Ekleme** kartı, Uç Nokta için Defender'a eklenen Windows cihazlarının sayısını Intune yönetilen Windows cihazlarının toplam sayısıyla karşılaştırarak ekleme oranınıza üst düzey bir genel bakış sağlar.

:::image type="content" source="images/secconmgmt_onboarding_card.png" alt-text="Cihaz yapılandırma yönetimi Ekleme kartı" lightbox="images/secconmgmt_onboarding_card.png":::

*Intune yönetilen Windows cihazlarının toplam sayısıyla karşılaştırıldığında eklenen cihazları gösteren kart*

> [!NOTE]
> Configuration Manager, ekleme betiği veya Intune profilleri kullanmayan diğer ekleme yöntemlerini kullandıysanız veri tutarsızlıklarıyla karşılaşabilirsiniz. Bu tutarsızlıkları çözmek için Uç Nokta için Defender eklemesi için karşılık gelen bir Intune yapılandırma profili oluşturun ve bu profili cihazlarınıza atayın.

## <a name="onboard-more-devices-with-intune-profiles"></a>Intune profilleriyle daha fazla cihaz ekleme

Uç Nokta için Defender [, Windows cihazlarını eklemeye](onboard-configure.md) yönelik çeşitli kullanışlı seçenekler sağlar. Ancak Intune yönetilen cihazlarda, uç nokta için Defender algılayıcısını cihazları seçmek üzere rahatça dağıtmak ve bu cihazları etkin bir şekilde hizmete eklemek için Intune profillerinden yararlanabilirsiniz.

**Ekleme** kartından, Intune profil oluşturmak ve atamak için **Daha fazla cihaz** ekle'yi seçin. Bağlantı sizi Intune cihaz uyumluluk sayfasına götürür ve ekleme durumunuzla ilgili benzer bir genel bakış sağlar.

:::image type="content" source="images/secconmgmt_onboarding_1deviceconfprofile.png" alt-text="Intune cihaz yönetimindeki Uç Nokta için Microsoft Defender cihaz uyumluluğu sayfası" lightbox="images/secconmgmt_onboarding_1deviceconfprofile.png":::

*Intune cihaz yönetiminde cihaz uyumluluk sayfasını Uç Nokta için Microsoft Defender*

> [!TIP]
> Alternatif olarak, [Microsoft](https://portal.azure.com/) Defender **ATP'> Tüm hizmetler > Intune > Cihaz uyumluluğu bölümünden Microsoft Azure portal Uç Nokta için Defender ekleme uyumluluk** sayfasına gidebilirsiniz.

> [!NOTE]
> En güncel cihaz verilerini görüntülemek istiyorsanız **ATP algılayıcısı olmayan cihazlar listesi'ne** tıklayın.

Cihaz uyumluluk sayfasından, uç nokta için Defender algılayıcısının dağıtımı için özel olarak bir yapılandırma profili oluşturun ve bu profili eklemek istediğiniz cihazlara atayın. Bunu yapmak için şunları yapabilirsiniz:

- **ATP algılayıcısını önceden tanımlanmış bir cihaz yapılandırma profiliyle başlayacak şekilde yapılandırmak** için Cihaz yapılandırma profili oluştur'u seçin.
- Sıfırdan cihaz yapılandırma profilini oluşturun.

Daha fazla bilgi [için cihazları Uç Nokta için Defender'a eklemek için Intune cihaz yapılandırma profillerini kullanma hakkında bilgi edinin](/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile).

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a>İlgili konular

- [Cihazlarınızı doğru yapılandırıldığından emin olun](configure-machines.md)
- [Uç Nokta için Defender güvenlik temeline uyumluluğu artırma](configure-machines-security-baseline.md)
- [ASR kuralı dağıtım ve algılamalarını iyileştirme](configure-machines-asr.md)
