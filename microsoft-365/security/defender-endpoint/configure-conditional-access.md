---
title: Uç Nokta için Microsoft Defender'de Koşullu Erişimi Yapılandırma
description: Koşullu erişim uygulamak için Intune, Microsoft 365 Defender ve Azure'da gerçekleştirmeniz gereken adımlar hakkında bilgi edinin
keywords: koşullu erişim, koşullu, erişim, cihaz riski, risk düzeyi, tümleştirme, intune tümleştirmesi
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
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 5cf63f594d8e1d4b165ea435547d95786a12a0f4
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67703006"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender'de Koşullu Erişimi Yapılandırma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Bu bölüm, Koşullu Erişimi düzgün bir şekilde uygulamak için uygulamanız gereken tüm adımlarda size yol gösterir.

## <a name="before-you-begin"></a>Başlamadan önce

> [!WARNING]
> Kayıtlı Azure AD cihazların bu senaryoda desteklenmediğini unutmayın.</br>
> Yalnızca Intune kayıtlı cihazlar desteklenir.

Tüm cihazlarınızın Intune kayıtlı olduğundan emin olmanız gerekir. Cihazları Intune kaydetmek için aşağıdaki seçeneklerden herhangi birini kullanabilirsiniz:

- BT Yönetici: Otomatik kaydı etkinleştirme hakkında daha fazla bilgi için bkz. [Windows Kaydı](/intune/windows-enroll#enable-windows-10-automatic-enrollment)
- Son kullanıcı: Windows 10 ve Windows 11 cihazınızı Intune kaydetme hakkında daha fazla bilgi için bkz[. Windows 10 cihazınızı Intune](/intune/quickstart-enroll-windows-device)
- Son kullanıcı alternatifi: Azure AD etki alanına katılma hakkında daha fazla bilgi için bkz[. Nasıl yapılır: Azure AD katılma uygulamanızı planlama](/azure/active-directory/devices/azureadjoin-plan).

Microsoft 365 Defender, Intune portalı ve Azure AD portalında uygulamanız gereken adımlar vardır.

Bu portallara erişmek ve Koşullu erişim uygulamak için gerekli rolleri not almak önemlidir:

- **Microsoft 365 Defender** - Tümleştirmeyi açmak için portalda genel yönetici rolüyle oturum açmanız gerekir.
- **Intune** - Yönetim izinlerine sahip güvenlik yöneticisi haklarıyla portalda oturum açmanız gerekir.
- **Azure AD portalı** - Genel yönetici, güvenlik yöneticisi veya Koşullu Erişim yöneticisi olarak oturum açmanız gerekir.

> [!NOTE]
> Intune yönetilen ve Azure AD birleştirilmiş Windows 10 ve Windows 11 cihazları olan bir Microsoft Intune ortamına ihtiyacınız vardır.

Koşullu Erişimi etkinleştirmek için aşağıdaki adımları uygulayın:

- 1. Adım: Microsoft 365 Defender Microsoft Intune bağlantısını açma
- 2. Adım: Intune'de Uç Nokta için Defender tümleştirmesini açma
- 3. Adım: uyumluluk ilkesini Intune'de oluşturma
- 4. Adım: İlkeyi atama 
- 5. Adım: Azure AD Koşullu Erişim ilkesi oluşturma

### <a name="step-1-turn-on-the-microsoft-intune-connection"></a>1. Adım: Microsoft Intune bağlantısını açma

1. Gezinti bölmesinde **Ayarlar** \> **Uç Noktaları** \> **Genel** \> **Gelişmiş özellikler** \> **Microsoft Intune bağlantı'yı** seçin.
2. Microsoft Intune ayarını **Açık** olarak değiştirin.
3. **Tercihleri kaydet'e** tıklayın.

### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a>2. Adım: Intune'de Uç Nokta için Defender tümleştirmesini açma

1. [Azure portalda](https://portal.azure.com) oturum açın.
2. **Cihaz uyumluluğu** \> **Microsoft Defender ATP'yi** seçin.
3. **Connect Windows 10.0.15063+ cihazlarını Microsoft Defender Gelişmiş Tehdit Koruması** olarak **Açık** olarak ayarlayın.
4. **Kaydet**'e tıklayın.

### <a name="step-3-create-the-compliance-policy-in-intune"></a>3. Adım: uyumluluk ilkesini Intune'de oluşturma

1. [Azure portal](https://portal.azure.com) **Tüm hizmetler'i** seçin, **Intune** filtreleyin ve **Microsoft Intune'ı** seçin.
2. **Cihaz uyumluluk** \> **İlkeleri İlke** \> **oluştur'u** seçin.
3. **Ad** ve **Açıklama** girin.
4. **Platform'da** **Windows 10 ve üzerini** seçin.
5. **Cihaz Durumu** ayarlarında Cihazın **Cihaz Tehdit Düzeyi'nde veya altında olmasını gerektir'i** tercih ettiğiniz düzeye ayarlayın:

   - **Güvenli**: En güvenli düzeydir. Cihaz mevcut tehditlere sahip olamaz ve şirket kaynaklarına erişmeye devam edemez. Herhangi bir tehdit bulunursa cihaz uyumlu olmayan olarak değerlendirilir.
   - **Düşük**: Cihaz yalnızca düşük düzeyli tehditler varsa uyumludur. Orta veya yüksek tehdit düzeyine sahip cihazlar uyumlu değildir.
   - **Orta**: Cihazda bulunan tehditler düşük veya ortaysa cihaz uyumludur. Yüksek düzeydeki tehditler algılanırsa cihaz uyumlu olmayan olarak değerlendirilir.
   - **Yüksek**: Bu düzey en az güvenlidir ve tüm tehdit düzeylerine izin verir. Bu nedenle yüksek, orta veya düşük tehdit düzeylerine sahip cihazlar uyumlu olarak kabul edilir.

6. **Tamam'ı** ve **Oluştur'u** seçerek değişikliklerinizi kaydedin (ve ilkeyi oluşturun).

### <a name="step-4-assign-the-policy"></a>4. Adım: İlkeyi atama

1. [Azure portal](https://portal.azure.com) **Tüm hizmetler'i** seçin, **Intune** filtreleyin ve **Microsoft Intune'ı** seçin.
2. **Cihaz uyumluluk** \> **İlkeleri'ni** seçin> Uç Nokta için Microsoft Defender uyumluluk ilkenizi seçin.
3. **Ödevler'i** seçin.
4. İlkeyi atamak için Azure AD gruplarınızı dahil edin veya hariç tutun.
5. İlkeyi gruplara dağıtmak için **Kaydet'i** seçin. İlke tarafından hedeflenen kullanıcı cihazları uyumluluk açısından değerlendirilir.

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a>5. Adım: Azure AD Koşullu Erişim ilkesi oluşturma

1. [Azure portal](https://portal.azure.com) **Azure Active Directory** \> **Koşullu Erişim** \> **Yeni ilkesi'ni** açın.
2. İlke **Adı** girin ve **Kullanıcılar ve gruplar'ı** seçin. İlkeye gruplarınızı eklemek için Dahil Et veya Dışla seçeneklerini kullanın ve **Bitti'yi** seçin.
3. **Bulut uygulamaları'nı** seçin ve hangi uygulamaların korunacaklarını seçin. Örneğin, **Uygulama seç'i** seçin ve **sharepoint online ve Office 365 Exchange Online Office 365** **seçin.** Değişikliklerinizi kaydetmek için **Bitti'yi** seçin.

4. İlkeyi uygulamalara ve tarayıcılara uygulamak için **Koşullar** \> **İstemci uygulamaları'nı** seçin. Örneğin, **Evet'i** seçip **Tarayıcı** ve **Mobil uygulamalar ile masaüstü istemcilerini** etkinleştirin. Değişikliklerinizi kaydetmek için **Bitti'yi** seçin.

5. Cihaz uyumluluğuna göre Koşullu Erişim uygulamak için **İzin Ver'i** seçin. Örneğin Erişim **izni ver** \> **Cihazın uyumlu olarak işaretlenmesini gerektir'i** seçin. Değişikliklerinizi kaydetmek için **Seç'i** seçin.

6. değişikliklerinizi kaydetmek için **İlkeyi etkinleştir'i** ve ardından **Oluştur'u** seçin.

> [!NOTE]
> Cihaz Uyumluluğu ve Koşullu Erişim ilkelerini ayarlamak için Uç Nokta için Microsoft Defender uygulamasını Intune'daki Onaylı İstemci uygulaması ilkesiyle birlikte kullanabilirsiniz. Koşullu Erişim ayarlanırken Uç Nokta için Microsoft Defender uygulaması için dışlama gerekmez. Android & iOS'ta Uç Nokta için Microsoft Defender (Uygulama Kimliği - dd47d17a-3194-4d86-bfd5-c6ae6f5651e3) onaylı bir uygulama olmasa da, cihaz güvenlik duruşu bildirme iznine sahiptir. Bu izin, Koşullu Erişim'e uyumluluk bilgileri akışı sağlar.
> Bu değişikliğin 30 Eylül 2022'den itibaren geçerli olacağını lütfen unutmayın.

Daha fazla bilgi için bkz. [Intune'da Koşullu Erişim ile Uç Nokta için Microsoft Defender uyumluluğu zorlama](/intune/advanced-threat-protection).

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
