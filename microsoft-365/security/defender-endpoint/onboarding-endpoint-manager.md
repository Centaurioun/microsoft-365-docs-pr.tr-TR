---
title: Microsoft Endpoint Manager aracılığı ile katılım
description: Microsoft Endpoint Manager kullanarak Uç Nokta için Microsoft Defender eklemeyi öğrenin
keywords: ekleme, yapılandırma, dağıtma, dağıtım, uç nokta yöneticisi, Uç Nokta için Microsoft Defender, koleksiyon oluşturma, uç nokta algılama yanıtı, yeni nesil koruma, saldırı yüzeyi azaltma, microsoft endpoint manager
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-endpointprotect
- m365solution-scenario
- highpri
- tier1
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 596488f105e2b7be1c6047a37cca7a2fbc297c79
ms.sourcegitcommit: 04e517c7e00323b5c33d8ea937115725cf2cfd4d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2022
ms.locfileid: "68564027"
---
# <a name="onboarding-using-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager aracılığı ile katılım

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Bu makale Dağıtım kılavuzunun bir parçasıdır ve örnek ekleme yöntemi olarak görev yapar.

[Planlama](deployment-strategy.md) konusunda, cihazları hizmete eklemek için çeşitli yöntemler sağlanmıştır. Bu konu, bulutta yerel mimariyi kapsar.

:::image type="content" source="images/cloud-native-architecture.png" alt-text="Buluta özel mimari" lightbox="images/cloud-native-architecture.png":::
*Ortam mimarileri diyagramı*

Uç Nokta için Defender çeşitli uç noktaların ve araçların eklenip eklenmediğini desteklese de, bu makale bunları kapsamaz. Desteklenen diğer dağıtım araçlarını ve yöntemlerini kullanarak genel ekleme hakkında bilgi için bkz. [Eklemeye genel bakış](onboarding.md).

[Microsoft Endpoint Manager](/mem/endpoint-manager-overview), çeşitli hizmetleri bir hale getiren bir çözüm platformudur. [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) ve [Microsoft Endpoint Configuration Manager](/mem/configmgr) içerir.

Bu konu, kullanıcılara şu konuda yol gösterir:

- 1. Adım: Microsoft Endpoint Manager'da (MEM) yapılandırmaları atamak üzere bir grup oluşturarak cihazları hizmete ekleme
- 2. Adım: Microsoft Endpoint Manager kullanarak Uç Nokta için Defender özelliklerini yapılandırma

Bu ekleme kılavuzu, Microsoft Endpoint Manager kullanırken uygulamanız gereken aşağıdaki temel adımlarda size yol gösterecektir:

- [Hedef cihazları veya kullanıcıları tanımlama](#identify-target-devices-or-users)
  - Azure Active Directory grubu oluşturma (Kullanıcı veya Cihaz)
- [Yapılandırma Profili Oluşturma](#step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities)
  - Microsoft Endpoint Manager'da her özellik için ayrı bir ilke oluşturma konusunda size yol göstereceğiz.

## <a name="resources"></a>Kaynaklar

İşlemin geri kalanında ihtiyacınız olan bağlantılar şunlardır:

- [MEM portalı](https://aka.ms/memac)
- [Microsoft 365 Defender](https://security.microsoft.com)
- [Intune Güvenlik temelleri](/mem/intune/protect/security-baseline-settings-defender-atp#microsoft-defender)

Microsoft Endpoint Manager hakkında daha fazla bilgi için şu kaynaklara göz atın:

- [Microsoft Endpoint Manager sayfası](/mem/)
- [Intune ve ConfigMgr yakınsama hakkında blog gönderisi](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace/)
- [MEM'de giriş videosu](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace)

## <a name="step-1-onboard-devices-by-creating-a-group-in-mem-to-assign-configurations-on"></a>1. Adım: MEM'de yapılandırmaları atamak için bir grup oluşturarak cihazları ekleme

### <a name="identify-target-devices-or-users"></a>Hedef cihazları veya kullanıcıları tanımlama

Bu bölümde yapılandırmalarınızı atamak için bir test grubu oluşturacağız.

> [!NOTE]
> Intune, cihazları ve kullanıcıları yönetmek için Azure Active Directory (Azure AD) gruplarını kullanır. Intune yöneticisi olarak, grupları kuruluş gereksinimlerinize uyacak şekilde ayarlayabilirsiniz.
>
> Daha fazla bilgi için bkz. [Kullanıcıları ve cihazları düzenlemek için grup ekleme](/mem/intune/fundamentals/groups-add).

### <a name="create-a-group"></a>Grup oluşturma

1. MEM portalını açın.

2. **Yeni Grup > Gruplar'a** tıklayın.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/66f724598d9c3319cba27f79dd4617a4.png" alt-text="Microsoft Endpoint Manager portalı1" lightbox="images/66f724598d9c3319cba27f79dd4617a4.png":::

3. Ayrıntıları girin ve yeni bir grup oluşturun.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/b1e0206d675ad07db218b63cd9b9abc3.png" alt-text="Microsoft Endpoint Manager portalı2" lightbox="images/b1e0206d675ad07db218b63cd9b9abc3.png":::

4. Test kullanıcınızı veya cihazınızı ekleyin.

5. **Gruplar > Tüm gruplar** bölmesinde yeni grubunuzu açın.

6. **Üyeler > Üye ekle'yi** seçin.

7. Test kullanıcınızı veya cihazınızı bulun ve seçin.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/149cbfdf221cdbde8159d0ab72644cd0.png" alt-text="Microsoft Endpoint Manager portalı3" lightbox="images/149cbfdf221cdbde8159d0ab72644cd0.png":::

8. Test grubunuzun artık test etmek için bir üyesi var.

## <a name="step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities"></a>2. Adım: Uç Nokta için Microsoft Defender özelliklerini yapılandırmak için yapılandırma ilkeleri oluşturma

Aşağıdaki bölümde, bir dizi yapılandırma ilkesi oluşturacaksınız.

İlk olarak, Uç Nokta için Defender'a hangi kullanıcı veya cihaz gruplarının eklendiğini seçen bir yapılandırma ilkesidir:

- [Uç nokta algılama ve yanıt](#endpoint-detection-and-response)

Ardından birkaç farklı tür uç nokta güvenlik ilkesi oluşturarak devam edebilirsiniz:

- [Yeni nesil koruma](#next-generation-protection)
- [Saldırı yüzeyini azaltma](#attack-surface-reduction---attack-surface-reduction-rules)

### <a name="endpoint-detection-and-response"></a>Uç nokta algılama ve yanıt

1. MEM portalını açın.

2. **Uç nokta güvenliği > Uç nokta algılama ve yanıtı'na** gidin. **Profil Oluştur'a** tıklayın.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/58dcd48811147feb4ddc17212b7fe840.png" alt-text="Microsoft Endpoint Manager portalı4" lightbox="images/58dcd48811147feb4ddc17212b7fe840.png":::

3. **Platform'un altında Windows 10 ve Daha Sonra, Profil - Uç nokta algılama ve yanıt > Oluştur'u seçin**.

4. Bir ad ve açıklama girip  **İleri'yi** seçin.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/a5b2d23bdd50b160fef4afd25dda28d4.png" alt-text="Microsoft Endpoint Manager portalı5" lightbox="images/a5b2d23bdd50b160fef4afd25dda28d4.png":::

5. Ayarları gerektiği gibi seçin ve ardından  **İleri'yi** seçin.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/cea7e288b5d42a9baf1aef0754ade910.png" alt-text="Microsoft Endpoint Manager portalı6" lightbox="images/cea7e288b5d42a9baf1aef0754ade910.png":::

    > [!NOTE]
    > Bu örnekte, Uç Nokta için Defender zaten Intune ile tümleştirildiği için bu otomatik olarak doldurulur. Tümleştirme hakkında daha fazla bilgi için bkz[. Intune'de Uç Nokta için Microsoft Defender etkinleştirme](/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp).
    >
    > Aşağıdaki görüntü, Uç Nokta için Microsoft Defender Intune ile tümLEŞTIRİlMEDİĞİnde göreceğiniz bir örnektir:
    >
    > :::image type="content" source="images/2466460812371ffae2d19a10c347d6f4.png" alt-text="Microsoft Endpoint Manager portalı7" lightbox="images/2466460812371ffae2d19a10c347d6f4.png":::

6. Gerekirse kapsam etiketleri ekleyin ve  **İleri'yi** seçin.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ef844f52ec2c0d737ce793f68b5e8408.png" alt-text="Microsoft Endpoint Manager portalı8" lightbox="images/ef844f52ec2c0d737ce793f68b5e8408.png":::

7. **Eklenecek grupları seç'e** tıklayarak test grubu ekleyin ve grubunuzu seçin, ardından **İleri'yi** seçin.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/fc3525e20752da026ec9f46ab4fec64f.png" alt-text="Microsoft Endpoint Manager portalı9" lightbox="images/fc3525e20752da026ec9f46ab4fec64f.png":::

8. Gözden geçirin ve kabul edin, ardından  **Oluştur'u** seçin.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/289172dbd7bd34d55d24810d9d4d8158.png" alt-text="Microsoft Endpoint Manager portalı10" lightbox="images/289172dbd7bd34d55d24810d9d4d8158.png":::

9. Tamamlanmış ilkenizi görüntüleyebilirsiniz.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/5a568b6878be8243ea2b9d82d41ed297.png" alt-text="Microsoft Endpoint Manager portalı11" lightbox="images/5a568b6878be8243ea2b9d82d41ed297.png":::

### <a name="next-generation-protection"></a>Yeni nesil koruma

1. MEM portalını açın.

2. **İlke Oluşturma > Virüsten Koruma > Uç nokta güvenliği'ne** gidin.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/6b728d6e0d71108d768e368b416ff8ba.png" alt-text="Microsoft Endpoint Manager portalı12" lightbox="images/6b728d6e0d71108d768e368b416ff8ba.png":::

3. **Platform - Windows 10 ve Üzeri - Windows ve Profil - Microsoft Defender Virüsten Koruma > Oluştur'u** seçin.

4. Ad ve açıklama girin, ardından  **İleri'yi** seçin.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/a7d738dd4509d65407b7d12beaa3e917.png" alt-text="Microsoft Endpoint Manager portalı13" lightbox="images/a7d738dd4509d65407b7d12beaa3e917.png":::

5. **Yapılandırma ayarları sayfasında**: Microsoft Defender Virüsten Koruma (Bulut Koruması, Dışlamalar, Real-Time Koruması ve Düzeltme) için ihtiyacınız olan yapılandırmaları ayarlayın.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/3840b1576d6f79a1d72eb14760ef5e8c.png" alt-text="Microsoft Endpoint Manager portalı14" lightbox="images/3840b1576d6f79a1d72eb14760ef5e8c.png":::

6. Gerekirse kapsam etiketleri ekleyin ve  **İleri'yi** seçin.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/2055e4f9b9141525c0eb681e7ba19381.png" alt-text="Microsoft Endpoint Manager portalı15" lightbox="images/2055e4f9b9141525c0eb681e7ba19381.png":::

7. Dahil etmek istediğiniz grupları seçin, test grubunuz için atayın ve  **ardından İleri'yi** seçin.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/48318a51adee06bff3908e8ad4944dc9.png" alt-text="Microsoft Endpoint Manager portalı16" lightbox="images/48318a51adee06bff3908e8ad4944dc9.png":::

8. Gözden geçirin ve oluşturun, ardından  **Oluştur'u** seçin.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/dfdadab79112d61bd3693d957084b0ec.png" alt-text="Microsoft Endpoint Manager portalı17" lightbox="images/dfdadab79112d61bd3693d957084b0ec.png":::

9. Oluşturduğunuz yapılandırma ilkesini görürsünüz.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/38180219e632d6e4ec7bd25a46398da8.png" alt-text="Microsoft Endpoint Manager portalı18" lightbox="images/38180219e632d6e4ec7bd25a46398da8.png":::

### <a name="attack-surface-reduction---attack-surface-reduction-rules"></a>Saldırı Yüzeyi Azaltma - Saldırı yüzeyi azaltma kuralları

1. MEM portalını açın.

2. **Uç nokta güvenliği > Saldırı yüzeyi azaltma** bölümüne gidin.

3. **İlke Oluştur'u** seçin.

4. **Oluştur > Platform - Windows 10 ve Üzeri - Profil - Saldırı yüzeyi azaltma kurallarını** seçin.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/522d9bb4288dc9c1a957392b51384fdd.png" alt-text="Microsoft Endpoint Manager portalı19" lightbox="images/522d9bb4288dc9c1a957392b51384fdd.png":::

5. Bir ad ve açıklama girip  **İleri'yi** seçin.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png" alt-text="Microsoft Endpoint Manager portalı20" lightbox="images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png":::

6. **Yapılandırma ayarları sayfasında**: Saldırı yüzeyi azaltma kuralları için ihtiyacınız olan yapılandırmaları ayarlayın ve **İleri'yi** seçin.

    > [!NOTE]
    > Tüm Saldırı yüzeyi azaltma kurallarını Denetim olarak yapılandıracağız.
    >
    > Daha fazla bilgi için bkz [. Saldırı yüzeyi azaltma kuralları](attack-surface-reduction.md).

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/dd0c00efe615a64a4a368f54257777d0.png" alt-text="Microsoft Endpoint Manager portalı21" lightbox="images/dd0c00efe615a64a4a368f54257777d0.png":::

7. Kapsam Etiketlerini gerektiği gibi ekleyin ve  **İleri'yi** seçin.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/6daa8d347c98fe94a0d9c22797ff6f28.png" alt-text="Microsoft Endpoint Manager portalı22" lightbox="images/6daa8d347c98fe94a0d9c22797ff6f28.png":::

8. Eklenecek ve test grubuna atanacak grupları seçin ve ardından  **İleri'yi** seçin.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/45cefc8e4e474321b4d47b4626346597.png" alt-text="Microsoft Endpoint Manager portalı23" lightbox="images/45cefc8e4e474321b4d47b4626346597.png":::

9. Ayrıntıları gözden geçirin ve  **Oluştur'u** seçin.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/2c2e87c5fedc87eba17be0cdeffdb17f.png" alt-text="Microsoft Endpoint Manager portalı24" lightbox="images/2c2e87c5fedc87eba17be0cdeffdb17f.png":::

10. İlkeyi görüntüleyin.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/7a631d17cc42500dacad4e995823ffef.png" alt-text="Microsoft Endpoint Manager portalı25" lightbox="images/7a631d17cc42500dacad4e995823ffef.png":::

### <a name="attack-surface-reduction---web-protection"></a>Saldırı Yüzeyini Azaltma - Web Koruması

1. MEM portalını açın.

2. **Uç nokta güvenliği > Saldırı yüzeyi azaltma** bölümüne gidin.

3. **İlke Oluştur'u** seçin.

4. **Windows 10 ve Daha Sonra - Web koruması > Oluştur'u** seçin.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png" alt-text="Microsoft Endpoint Manager portalı26" lightbox="images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png":::

5. Bir ad ve açıklama girip  **İleri'yi** seçin.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/5be573a60cd4fa56a86a6668b62dd808.png" alt-text="Microsoft Endpoint Manager portalı27" lightbox="images/5be573a60cd4fa56a86a6668b62dd808.png":::

6. **Yapılandırma ayarları sayfasında**: Web Koruması için gereken yapılandırmaları ayarlayın ve **İleri'yi** seçin.

    > [!NOTE]
    > Web Korumasını Engelle olarak yapılandırıyoruz.
    >
    > Daha fazla bilgi için bkz. [Web Koruması](web-protection-overview.md).

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/6104aa33a56fab750cf30ecabef9f5b6.png" alt-text="Microsoft Endpoint Manager portalı28" lightbox="images/6104aa33a56fab750cf30ecabef9f5b6.png":::

7. **Kapsam Etiketlerini gerekli > İleri'ye** ekleyin.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/6daa8d347c98fe94a0d9c22797ff6f28.png" alt-text="Microsoft Endpoint Manager portalı29" lightbox="images/6daa8d347c98fe94a0d9c22797ff6f28.png":::

8. **Test grubuna ata'yı > İleri'yi** seçin.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/45cefc8e4e474321b4d47b4626346597.png" alt-text="Microsoft Endpoint Manager portalı30" lightbox="images/45cefc8e4e474321b4d47b4626346597.png":::

9. **Gözden Geçir ve Oluştur > Oluştur'u** seçin.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/8ee0405f1a96c23d2eb6f737f11c1ae5.png" alt-text="Microsoft Endpoint Manager portalı31" lightbox="images/8ee0405f1a96c23d2eb6f737f11c1ae5.png":::

10. İlkeyi görüntüleyin.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/e74f6f6c150d017a286e6ed3dffb7757.png" alt-text="Microsoft Endpoint Manager portalı32" lightbox="images/e74f6f6c150d017a286e6ed3dffb7757.png":::

## <a name="validate-configuration-settings"></a>Yapılandırma ayarlarını doğrulama

### <a name="confirm-policies-have-been-applied"></a>İlkelerin uygulandığını onaylama

Yapılandırma ilkesi atandıktan sonra uygulanması biraz zaman alır.

Zamanlama hakkında bilgi için bkz. [Intune yapılandırma bilgileri](/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

Yapılandırma ilkesinin test cihazınıza uygulandığını onaylamak için her yapılandırma ilkesi için aşağıdaki işlemi izleyin.

1. MEM portalını açın ve yukarıdaki adımlarda gösterildiği gibi ilgili ilkeye gidin. Aşağıdaki örnekte yeni nesil koruma ayarları gösterilmektedir.

    > [!div class="mx-imgBorder"]
    > [![Microsoft Endpoint Manager portal33 görüntüsü.](images/43ab6aa74471ee2977e154a4a5ef2d39.png)](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox) 

2. İlke durumunu görüntülemek için **Yapılandırma İlkesi'ni** seçin.

    > [!div class="mx-imgBorder"]
    > [![Microsoft Endpoint Manager portalı34 görüntüsü.](images/55ecaca0e4a022f0e29d45aeed724e6c.png)](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)

3. Durumu görmek için  **Cihaz Durumu'nu** seçin.

    > [!div class="mx-imgBorder"]
    > [![Microsoft Endpoint Manager portalı35 görüntüsü.](images/18a50df62cc38749000dbfb48e9a4c9b.png)](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)

4. Durumu görmek için  **Kullanıcı Durumu'nu** seçin.

    > [!div class="mx-imgBorder"]
    > [![Microsoft Endpoint Manager portal36 görüntüsü.](images/4e965749ff71178af8873bc91f9fe525.png)](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)

5. Durumu görmek için  **Ayar başına durum'a** tıklayın.

    > [!TIP]
    > Bu görünüm, başka bir ilkeyle çakışan ayarları belirlemek için çok kullanışlıdır.

    > [!div class="mx-imgBorder"]
    > [![Microsoft Endpoint Manager portalı37 görüntüsü.](images/42acc69d0128ed09804010bdbdf0a43c.png)](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)

### <a name="confirm-endpoint-detection-and-response"></a>Uç nokta algılamayı ve yanıtı onaylama

1. Yapılandırmayı uygulamadan önce Endpoint Protection için Defender hizmeti başlatılmamalıdır.

    > [!div class="mx-imgBorder"]
    > [![Hizmetler paneli1 görüntüsü.](images/b418a232a12b3d0a65fc98248dbb0e31.png)](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)

2. Yapılandırma uygulandıktan sonra, Uç Nokta Koruma Hizmeti için Defender başlatılmalıdır.

    > [!div class="mx-imgBorder"]
    > [![Hizmetler paneli2'nin görüntüsü.](images/a621b699899f1b41db211170074ea59e.png)](images/a621b699899f1b41db211170074ea59e.png#lightbox)

3. Hizmetler cihazda çalıştırıldıktan sonra cihaz Microsoft 365 Defender portalında görünür.

    > [!div class="mx-imgBorder"]
    > [![Microsoft 365 Defender portalının görüntüsü.](images/df0c64001b9219cfbd10f8f81a273190.png)](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)

### <a name="confirm-next-generation-protection"></a>Yeni nesil korumayı onaylayın

1. İlkeyi test cihazına uygulamadan önce ayarları aşağıda gösterildiği gibi el ile yönetebilirsiniz.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/88efb4c3710493a53f2840c3eac3e3d3.png" alt-text="Ayarlar sayfası-1" lightbox="images/88efb4c3710493a53f2840c3eac3e3d3.png":::

2. İlke uygulandıktan sonra ayarları el ile yönetememelisiniz.

    > [!NOTE]
    > Aşağıdaki görüntüde **Bulut tabanlı korumayı aç** ve **Gerçek zamanlı korumayı aç** seçeneği yönetiliyor olarak gösteriliyor.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/9341428b2d3164ca63d7d4eaa5cff642.png" alt-text="Ayarlar sayfası-2" lightbox="images/9341428b2d3164ca63d7d4eaa5cff642.png":::

### <a name="confirm-attack-surface-reduction---attack-surface-reduction-rules"></a>Saldırı Yüzeyi Azaltmayı Onaylama - Saldırı yüzeyi azaltma kuralları

1. İlkeyi bir test cihazına uygulamadan önce bir PowerShell Penceresi yazın ve yazın `Get-MpPreference`.

2. Bu, içerik olmadan aşağıdaki satırlarla yanıt vermelidir:

    > AttackSurfaceReductionOnlyExclusions:
    >
    > AttackSurfaceReductionRules_Actions:
    >
    > AttackSurfaceReductionRules_Ids:

    :::image type="content" source="images/cb0260d4b2636814e37eee427211fe71.png" alt-text="Komut satırı-1" lightbox="images/cb0260d4b2636814e37eee427211fe71.png":::

3. İlkeyi bir test cihazına uyguladıktan sonra bir PowerShell Windows açın ve yazın `Get-MpPreference`.

4. Bu, aşağıda gösterildiği gibi içerik içeren aşağıdaki satırlarla yanıt vermelidir:

   :::image type="content" source="images/619fb877791b1fc8bc7dfae1a579043d.png" alt-text="Komut satırı-2" lightbox="images/619fb877791b1fc8bc7dfae1a579043d.png":::

### <a name="confirm-attack-surface-reduction---web-protection"></a>Saldırı Yüzeyini Azaltmayı Onaylama - Web Koruması

1. Test cihazında bir PowerShell Windows açın ve yazın  `(Get-MpPreference).EnableNetworkProtection`.

2. Bu, aşağıda gösterildiği gibi 0 ile yanıt vermelidir.

   :::image type="content" source="images/196a8e194ac99d84221f405d0f684f8c.png" alt-text="Komut satırı-3" lightbox="images/196a8e194ac99d84221f405d0f684f8c.png":::

3. İlkeyi uyguladıktan sonra bir PowerShell Windows açın ve yazın  `(Get-MpPreference).EnableNetworkProtection`.

4. Bu, aşağıda gösterildiği gibi bir 1 ile yanıt vermelidir.

   :::image type="content" source="images/c06fa3bbc2f70d59dfe1e106cd9a4683.png" alt-text="Komut satırı-4" lightbox="images/c06fa3bbc2f70d59dfe1e106cd9a4683.png":::
