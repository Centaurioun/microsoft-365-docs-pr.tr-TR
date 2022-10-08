---
title: Windows araçlarını yerel betik kullanarak ekleyin
description: Cihazların hizmete eklenmesine olanak tanımak için yapılandırma paketini cihazlara dağıtmak için yerel bir betik kullanın.
keywords: yerel betik kullanarak cihazları yapılandırma, cihaz yönetimi, Uç Nokta için Microsoft Defender cihazları yapılandırma
search.appverid: met150
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
- tier1
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 43ed97b37acde59a44dc17c1ee051ea00c151fec
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68180307"
---
# <a name="onboard-windows-devices-using-a-local-script"></a>Windows araçlarını yerel betik kullanarak ekleyin

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

Ayrıca tek tek cihazları Uç Nokta için Defender'a el ile de ekleyebilirsiniz. Ağınızdaki tüm cihazları eklemeyi taahhüt etmeden önce hizmeti test ederken bunu yapmak isteyebilirsiniz.

> [!IMPORTANT]
> Bu betik, on adede kadar cihazda kullanılmak üzere iyileştirilmiştir.
> Yerel betik, Uç Nokta için Microsoft Defender değerlendirmek için özel bir ekleme yöntemidir.
> Veri raporlama sıklığı, yerel betik kullanılarak eklenirken diğer ekleme yöntemlerine göre daha yüksek ayarlanır.
> Bu ayar değerlendirme amaçlıdır ve normalde üretim dağıtımlarında kullanılmaz. Bu nedenle, çevresel etkiyle ilgili endişeler vardır, bu nedenle yerel betikleri kullanan dağıtım sayısını on ile sınırlamanızı öneririz.
> Daha önce açıklandığı gibi bir üretim ortamına dağıtıyorsanız, grup ilkesi veya Microsoft Endpoint Configuration Manager gibi [diğer dağıtım seçeneklerini](configure-endpoints.md) kullanın.

Uç Nokta için Defender'ı dağıtma ile ilgili çeşitli yolları görmek için [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  veya  [Visio'ya](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) göz atın. 

## <a name="onboard-devices"></a>Cihazları ekleme 

1.  Hizmet ekleme sihirbazından indirdiğiniz GP yapılandırma paketini .zip dosyasını (*WindowsDefenderATPOnboardingPackage.zip*) açın. Paketi <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalından</a> da alabilirsiniz:

    1. Gezinti bölmesinde **Ayarlar** > **Uç Noktaları** > **Cihaz yönetimi** > **Ekleme'yi** seçin.


Uç Nokta için Defender'ı dağıtma ile ilgili çeşitli yolları görmek için [PDF](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)  veya  [Visio'ya](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx) göz atın.

1. Hizmet ekleme sihirbazından indirdiğiniz GP yapılandırma paketini .zip dosyasını (*WindowsDefenderATPOnboardingPackage.zip*) açın. Paketi <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalından</a> da alabilirsiniz:
    1. Gezinti bölmesinde **Ayarlar** \> **Uç Noktaları** \> **Cihaz yönetimi** \> **Ekleme'yi** seçin.
    2. İşletim sistemi olarak Windows 10 veya Windows 11 seçin.
    3. **Dağıtım yöntemi** alanında **Yerel Betik'i** seçin.
    4. **Paketi indir'e** tıklayın ve .zip dosyasını kaydedin.

2. Yapılandırma paketinin içeriğini eklemek istediğiniz cihazdaki bir konuma (örneğin, Masaüstü) ayıklayın. *WindowsDefenderATPLocalOnboardingScript.cmd* adlı bir dosyanız olmalıdır.

3. Cihazda yükseltilmiş bir komut satırı istemi açın ve betiği çalıştırın:
   1. **Başlangıç'a** gidin ve **cmd** yazın.
   2. **Komut istemi'ne** sağ tıklayın ve **Yönetici olarak çalıştır'ı** seçin.

    :::image type="content" source="images/run-as-admin.png" alt-text="Yönetici olarak çalıştır'ı işaret eden Pencere Başlat menüsü" lightbox="images/run-as-admin.png":::

4.  Betik dosyasının konumunu yazın. Dosyayı masaüstüne kopyaladıysanız şunu yazın: *%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd*

5.  **Enter** tuşuna basın veya **Tamam'a** tıklayın.

Cihazın uyumlu olduğunu el ile nasıl doğrulayabileceğiniz ve algılayıcı verilerini doğru şekilde bildirebileceğiniz hakkında bilgi için bkz. [Ekleme sorunlarını Uç Nokta için Microsoft Defender giderme](troubleshoot-onboarding.md).

> [!TIP]
> Cihazı ekledikten sonra, bir cihazın hizmete düzgün şekilde eklendiğini doğrulamak için bir algılama testi çalıştırmayı seçebilirsiniz. Daha fazla bilgi için bkz. [Yeni eklenen Uç Nokta için Microsoft Defender uç noktasında algılama testi çalıştırma](run-detection-test.md).

## <a name="configure-sample-collection-settings"></a>Örnek koleksiyon ayarlarını yapılandırma

Her cihaz için, ayrıntılı analiz için bir dosya göndermek üzere Microsoft 365 Defender aracılığıyla bir istek yapıldığında cihazdan örneklerin toplanıp toplanmayacağını belirtmek için bir yapılandırma değeri ayarlayabilirsiniz.

*Regedit* kullanarak veya *bir .reg* dosyası oluşturup çalıştırarak cihazdaki örnek paylaşım ayarını el ile yapılandırabilirsiniz.

Yapılandırma aşağıdaki kayıt defteri anahtarı girdisi aracılığıyla ayarlanır:

```console
Path: "HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection"
Name: "AllowSampleCollection"
Value: 0 or 1
```

Burada Ad türü bir D-WORD'dür. Olası değerler şunlardır:

- 0 - bu cihazdan örnek paylaşımına izin vermez
- 1 - Bu cihazdan tüm dosya türlerinin paylaşılmasına izin verir

Kayıt defteri anahtarının mevcut olmaması durumunda varsayılan değer 1'dir.

## <a name="run-a-detection-test-to-verify-onboarding"></a>Ekleme işlemini doğrulamak için algılama testi çalıştırma

Cihazı ekledikten sonra, bir cihazın hizmete düzgün şekilde eklendiğini doğrulamak için bir algılama testi çalıştırmayı seçebilirsiniz. Daha fazla bilgi için bkz. [Yeni eklenen Uç Nokta için Microsoft Defender cihazında algılama testi çalıştırma](run-detection-test.md).

## <a name="offboard-devices-using-a-local-script"></a>Yerel betik kullanarak cihazları çıkarma

Güvenlik nedeniyle, cihazları kullanıma almak için kullanılan paketin süresi, indirildiği tarihten 30 gün sonra dolar. Bir cihaza gönderilen süresi dolan çıkarma paketleri reddedilir. Bir çıkarma paketini indirirken paketlerin son kullanma tarihi size bildirilir ve paket adına da eklenir.

> [!NOTE]
> Ekleme ve çıkarma ilkeleri aynı cihazda aynı anda dağıtılmamalıdır, aksi takdirde bu öngörülemeyen çakışmalara neden olur.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalından</a> çıkarma paketini alın:
    1. Gezinti bölmesinde **Ayarlar** \> **Uç Noktaları** \> **Cihaz yönetimi** \> **Çıkarma'yı** seçin.
    2. İşletim sistemi olarak Windows 10 veya Windows 11 seçin.
    3. **Dağıtım yöntemi** alanında **Yerel Betik'i** seçin.
    4. **Paketi indir'e** tıklayın ve .zip dosyasını kaydedin.

2. .zip dosyasının içeriğini cihazlar tarafından erişilebilen paylaşılan, salt okunur bir konuma ayıklayın. *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* adlı bir dosyanız olmalıdır.

3. Cihazda yükseltilmiş bir komut satırı istemi açın ve betiği çalıştırın:
   1. **Başlangıç'a** gidin ve **cmd** yazın.
   2. **Komut istemi'ne** sağ tıklayın ve **Yönetici olarak çalıştır'ı** seçin.

      :::image type="content" source="images/run-as-admin.png" alt-text="Yönetici olarak çalıştır seçeneğini işaret eden Windows Başlat menüsü" lightbox="images/run-as-admin.png":::

4. Betik dosyasının konumunu yazın. Dosyayı masaüstüne kopyaladıysanız şunu yazın: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*

5. **Enter** tuşuna basın veya **Tamam'a** tıklayın.

> [!IMPORTANT]
> Kullanıma alma, cihazın portala algılayıcı verileri göndermeyi durdurmasına neden olur, ancak sahip olduğu uyarılara başvuru da dahil olmak üzere cihazdaki veriler 6 aya kadar saklanır.

## <a name="monitor-device-configuration"></a>Cihaz yapılandırmasını izleme

Betiğin başarıyla tamamlandığını ve aracının çalıştığını doğrulamak için [Ekleme sorunlarını giderme](troubleshoot-onboarding.md) sayfasındaki farklı doğrulama adımlarını izleyebilirsiniz.

İzleme doğrudan portalda veya farklı dağıtım araçları kullanılarak da yapılabilir.

### <a name="monitor-devices-using-the-portal"></a>Portalı kullanarak cihazları izleme

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalına</a> gidin.
2. **Cihaz envanteri'ne** tıklayın.
3. Cihazların görüntülendiğini doğrulayın.

## <a name="related-topics"></a>İlgili konular
- [Windows araçlarını Grup İlkesi kullanarak ekleyin](configure-endpoints-gp.md)
- [Microsoft Endpoint Configuration Manager kullanarak Windows cihazlarını ekleyin](configure-endpoints-sccm.md)
- [Mobil Cihaz Yönetimi araçlarını kullanarak Windows cihazlarını ekleyin](configure-endpoints-mdm.md)
- [Kalıcı olmayan sanal masaüstü altyapısı (VDI) cihazlarının katılımı](configure-endpoints-vdi.md)
- [Yeni eklenen bir Uç Nokta için Microsoft Defender cihazında algılama testi çalıştırma](run-detection-test.md)
- [Uç Nokta için Microsoft Defender ekleme sorunlarını giderme](troubleshoot-onboarding.md)
