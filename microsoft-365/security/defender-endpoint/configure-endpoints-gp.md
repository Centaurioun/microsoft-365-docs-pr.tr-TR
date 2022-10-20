---
title: windows cihazlarını grup ilkesi aracılığıyla Uç Nokta için Microsoft Defender ekleme
description: Yapılandırma paketini hizmete eklenmesi için Windows cihazlarına dağıtmak için grup ilkesi kullanın.
keywords: grup ilkesi kullanarak cihazları yapılandırma, cihaz yönetimi, Uç Nokta için Microsoft Defender cihazları yapılandırma, Uç Nokta için Microsoft Defender cihazları ekleme, grup ilkesi
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
ms.topic: conceptual
ms.date: 12/07/2021
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 32e9bda04c7abcee70af5d086255e905fab34170
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68632040"
---
# <a name="onboard-windows-devices-using-group-policy"></a>Windows araçlarını Grup İlkesi kullanarak ekleyin 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**Şunlar için geçerlidir:**

- Grup İlkesi
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)

> [!NOTE]
> Paketi dağıtmak için grup ilkesi (GP) güncelleştirmelerini kullanmak için Windows Server 2008 R2 veya sonraki bir sürümde olmanız gerekir.
>
> Windows Server 2019 ve Windows Server 2022 için, grup ilkesi tercihinin oluşturduğu XML dosyasının NT AUTHORITY\Well-Known-System-Account yerine NT AUTHORITY\SYSTEM kullanmanız gerekebilir.

> [!NOTE]
> Windows Server 2012 R2 ve 2016 için yeni, birleşik Uç Nokta için Microsoft Defender çözümünü kullanıyorsanız, doğru Uç Nokta için Microsoft Defender ilkesi seçeneklerine erişmek için lütfen merkezi deponuzdaki en son ADMX dosyalarını kullandığınızdan emin olun. Lütfen [Windows'da grup ilkesi Yönetim Şablonları için Merkezi Mağaza oluşturma ve yönetme](/troubleshoot/windows-client/group-policy/create-and-manage-central-store) makalesine başvurun ve **Windows 10 ile kullanmak üzere** en son dosyaları indirin.

Uç Nokta için Defender'ı dağıtma ile ilgili çeşitli yolları görmek için [PDF](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)  veya  [Visio'ya](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx) göz atın.

1. Hizmet ekleme sihirbazından indirdiğiniz GP yapılandırma paketi dosyasını (`WindowsDefenderATPOnboardingPackage.zip`) açın. Paketi <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalından</a> da alabilirsiniz:

    1. Gezinti bölmesinde **Ayarlar** > **Uç Noktaları** > **Cihaz yönetimi**  > **Ekleme'yi** seçin.

    1. İşletim sistemini seçin.

    1. **Dağıtım yöntemi** alanında **Grup ilkesi'ni** seçin.

    1. **Paketi indir'e** tıklayın ve .zip dosyasını kaydedin.

2. .zip dosyasının içeriğini, cihaz tarafından erişilebilen paylaşılan, salt okunur bir konuma ayıklayın. *OptionalParamsPolicy* adlı bir klasörünüz ve *WindowsDefenderATPOnboardingScript.cmd* dosyası olmalıdır.

3. Yeni bir GPO oluşturmak için [grup ilkesi Yönetim Konsolu'nu](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) açın, yapılandırmak istediğiniz **nesneler grup ilkesi** sağ tıklayın ve **Yeni'ye** tıklayın. Görüntülenen iletişim kutusuna yeni GPO'nun adını girin ve **Tamam'a** tıklayın.

4. [grup ilkesi Yönetim Konsolu'nu](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) açın, yapılandırmak istediğiniz grup ilkesi Nesnesine (GPO) sağ tıklayın ve **Düzenle'ye** tıklayın.

5. **grup ilkesi Yönetim Düzenleyicisi'nde** **Bilgisayar yapılandırması'na**, **Tercihler'e** ve ardından **Denetim masası ayarları'na** gidin.

6. **Zamanlanmış görevler'e** sağ tıklayın, **Yeni'nin** üzerine gelin ve **ardından Anında Görev 'e (En az Windows 7)** tıklayın.

7. Açılan **Görev** penceresinde **Genel** sekmesine gidin. **Güvenlik seçenekleri'nin** altında **Kullanıcıyı veya Grubu Değiştir'e** tıklayın ve SİSTEM yazın ve ardından **Adları Denetle'ye** ve ardından **Tamam'a** tıklayın. NT AUTHORITY\SYSTEM, görevin çalıştırılacağı kullanıcı hesabı olarak görünür.

8. **Kullanıcının oturum açıp açmadığını çalıştır'ı** seçin ve **En yüksek ayrıcalıklarla çalıştır** onay kutusunu işaretleyin.

9. Ad alanına zamanlanmış görev için uygun bir ad yazın (örneğin, Uç Nokta Dağıtımı için Defender).

10. **Eylemler** sekmesine gidin ve **Yeni...** öğesini seçin. **Eylem** alanında **Program başlat'ın** seçili olduğundan emin olun. Paylaşılan *WindowsDefenderATPOnboardingScript.cmd* dosyasının tam etki alanı adını (FQDN) kullanarak UNC yolunu girin.

11. **Tamam'ı** seçin ve açık GPMC pencerelerini kapatın.

12. GPO'yu Bir Kuruluş Birimine (OU) bağlamak için sağ tıklayın ve **Var olan bir GPO'yu bağla'ya** tıklayın. Görüntülenen iletişim kutusunda, bağlamak istediğiniz grup ilkesi Nesnesi'ni seçin. **Tamam**'a tıklayın.

> [!TIP]
> Cihazı ekledikten sonra, cihazın hizmete düzgün şekilde eklendiğini doğrulamak için bir algılama testi çalıştırmayı seçebilirsiniz. Daha fazla bilgi için bkz. [Yeni eklenen Uç Nokta için Defender cihazında algılama testi çalıştırma](run-detection-test.md).

## <a name="additional-defender-for-endpoint-configuration-settings"></a>Uç Nokta için Ek Defender yapılandırma ayarları

Her cihaz için, ayrıntılı analiz için bir dosya göndermek üzere Microsoft 365 Defender üzerinden bir istek yapıldığında cihazdan örneklerin toplanıp toplanamayacağını belirtebilirsiniz.

Derin analiz özelliğinde kullanılan örnek paylaşımının ayarları gibi ayarları yapılandırmak için grup ilkesi (GP) kullanabilirsiniz.

### <a name="configure-sample-collection-settings"></a>Örnek koleksiyon ayarlarını yapılandırma

1. GP yönetim cihazınızda, yapılandırma paketinden aşağıdaki dosyaları kopyalayın:

    - _AtpConfiguration.admx_ dosyasını _C:\\Windows\\PolicyDefinitions_ içine kopyalama

    - _AtpConfiguration.adml_ dosyasını _C:\\Windows\\PolicyDefinitions\\en-US_ içine kopyalayın

    [grup ilkesi Yönetim Şablonları için Merkezi Mağaza](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra) kullanıyorsanız, yapılandırma paketinden aşağıdaki dosyaları kopyalayın:

    - _AtpConfiguration.admx_ dosyasını _SysVol\\\<forest.root\>\\İlkeleri\\\\\\\<forest.root\>\\ İlkesiDefinitions_ içine kopyalama

    - _AtpConfiguration.adml_ dosyasını _SysVol\<forest.root\>\\\\İlkeleri\\\<forest.root\>\\\\\\ İlkesiDefinitions\\en-US_ içine kopyalama

2. [grup ilkesi Yönetim Konsolu'nu](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) açın, yapılandırmak istediğiniz GPO'ya sağ tıklayın ve **Düzenle'ye** tıklayın.

3. **grup ilkesi Yönetim Düzenleyicisi'nde** **Bilgisayar yapılandırması'na** gidin.

4. **İlkeler'e** ve ardından **Yönetim şablonları'nı** tıklatın.

5. **Windows bileşenleri'ne** tıklayın ve **ATP'yi Windows Defender**.

6. Cihazlarınızdan örnek paylaşımı etkinleştirmeyi veya devre dışı bırakmayı seçin.

> [!NOTE]
> Bir değer ayarlamazsanız, varsayılan değer örnek koleksiyonu etkinleştirmektir.

## <a name="other-recommended-configuration-settings"></a>Önerilen diğer yapılandırma ayarları

### <a name="update-endpoint-protection-configuration"></a>Uç nokta koruma yapılandırmasını güncelleştirme

Ekleme betiğini yapılandırdıktan sonra, uç nokta koruma yapılandırmaları eklemek için aynı grup ilkesini düzenlemeye devam edin. Tüm gerekli Microsoft Defender Virüsten Koruma özelliklerine sahip olduğunuzdan emin olmak için Windows 10 veya Server 2019, Windows 11 veya Windows Server 2022 çalıştıran bir sistemden grup ilkesi düzenlemeleri gerçekleştirin. Defender ATP yapılandırma ayarlarını kaydetmek için grup ilkesi nesnesini kapatıp yeniden açmanız gerekebilir.

Tüm ilkeler altında `Computer Configuration\Policies\Administrative Templates`bulunur.

**İlke konumu:** \Windows Components\Windows Defender ATP

Ilkesi|Ayar
---|---
Örnek koleksiyonu etkinleştir\devre dışı bırak|Etkin - "Makinelerde örnek koleksiyonu etkinleştir" işaretlendi

<br>

**İlke konumu:** \Windows Components\Microsoft Defender Virüsten Koruma

Ilkesi|Ayar
---|---
İstenmeyebilecek uygulamalar için algılamayı yapılandırma|Etkin, Engelle

<br>

**İlke konumu:** \Windows Components\Microsoft Defender Antivirus\MAPS

Ilkesi|Ayar
---|---
Microsoft MAPS'e katılma|Etkin, Gelişmiş MAPS
Daha fazla analiz gerektiğinde dosya örnekleri gönderme | Etkin, Güvenli örnekler gönderme

<br>

**İlke konumu:** \Windows Components\Microsoft Defender Antivirus\Gerçek Zamanlı Koruma

Ilkesi|Ayar
---|---
Gerçek zamanlı korumayı kapatma|Devre dışı
Davranış izlemeyi açma|Etkin
İndirilen tüm dosyaları ve ekleri tara|Etkin
Bilgisayarınızda dosya ve program etkinliğini izleme|Etkin

<br>

**İlke konumu:** \Windows Components\Microsoft Defender Antivirus\Scan

Bu ayarlar, uç noktanın düzenli taramalarını yapılandırıyor. Performansa izin verilen haftalık bir hızlı tarama gerçekleştirmenizi öneririz.

Ilkesi|Ayar
---|---
Zamanlanmış tarama çalıştırmadan önce en son virüs ve casus yazılım güvenlik bilgilerini denetleyin |Etkin

<br>

**İlke konumu:** \Windows Components\Microsoft Defender Antivirus\Microsoft Defender Exploit Guard\Attack Surface Reduction

Saldırı yüzeyi azaltma kuralları GUID'lerinin geçerli listesini [Saldırı yüzeyi azaltma kuralları dağıtımı 3. Adım: ASR kurallarını uygulama bölümünden](attack-surface-reduction-rules-deployment-implement.md) alın. Kural ayrıntılarına göre ek bilgi için bkz [. Saldırı yüzeyi azaltma kuralları başvurusu](attack-surface-reduction-rules-reference.md)

1. **Saldırı Yüzeyi Azaltmayı Yapılandır** ilkesini açın.

1. **Etkin**'i seçin.

1. **Göster** düğmesini seçin.

1. **Değer Adı** alanına her GUID'yi 2 değeriyle ekleyin.

   Bu, her bir ayarı yalnızca denetim için ayarlar.

   :::image type="content" source="images/asr-guid.png" alt-text="Saldırı yüzeyi azaltma yapılandırması" lightbox="images/asr-guid.png":::

Ilkesi|Konum|Ayar
---|---|---
Denetimli klasör erişimini yapılandırma| \Windows Components\Microsoft Defender Antivirus\Microsoft Defender Exploit Guard\Controlled Folder Access| Etkin, Denetim Modu

## <a name="run-a-detection-test-to-verify-onboarding"></a>Ekleme işlemini doğrulamak için algılama testi çalıştırma

Cihazı ekledikten sonra, bir cihazın hizmete düzgün şekilde eklendiğini doğrulamak için bir algılama testi çalıştırmayı seçebilirsiniz. Daha fazla bilgi için bkz. [Yeni eklenen Uç Nokta için Microsoft Defender cihazında algılama testi çalıştırma](run-detection-test.md).

## <a name="offboard-devices-using-group-policy"></a>grup ilkesi kullanarak cihazları çıkarma

Güvenlik nedeniyle, cihazları kullanıma almak için kullanılan paketin süresi, indirildiği tarihten 30 gün sonra dolar. Bir cihaza gönderilen süresi dolan çıkarma paketleri reddedilir. Bir çıkarma paketini indirirken paketlerin son kullanma tarihi size bildirilir ve paket adına da eklenir.

> [!NOTE]
> Ekleme ve çıkarma ilkeleri aynı cihazda aynı anda dağıtılmamalıdır, aksi takdirde bu öngörülemeyen çakışmalara neden olur.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalından</a> çıkarma paketini alın:

    1. Gezinti bölmesinde **Ayarlar** > **Uç Noktaları** > **Cihaz yönetimi** > **Çıkarma'yı** seçin.

    1. İşletim sistemini seçin.
    
    1. **Dağıtım yöntemi** alanında **Grup ilkesi'ni** seçin.

    1. **Paketi indir'e** tıklayın ve .zip dosyasını kaydedin.

2. .zip dosyasının içeriğini, cihaz tarafından erişilebilen paylaşılan, salt okunur bir konuma ayıklayın. *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* adlı bir dosyanız olmalıdır.

3. [grup ilkesi Yönetim Konsolu'nu](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) açın, yapılandırmak istediğiniz grup ilkesi Nesnesine (GPO) sağ tıklayın ve **Düzenle'ye** tıklayın.

4. **grup ilkesi Yönetim Düzenleyicisi'nde** **Bilgisayar yapılandırması'na,** **Tercihler'e** ve ardından **Denetim masası ayarları'na** gidin.

5. **Zamanlanmış görevler'e** sağ tıklayın, **Yeni'nin** üzerine gelin ve **hemen görev'e** tıklayın.

6. Açılan **Görev** penceresinde **Genel** sekmesine gidin. **Güvenlik seçenekleri'nin** altında yerel SYSTEM kullanıcı hesabını (BUILTIN\SYSTEM) seçin.

7. **Kullanıcının oturum açıp açmadığını çalıştır'ı** seçin ve **En yüksek ayrıcalıklarla çalıştır** onay kutusunu işaretleyin.

8. Ad alanına zamanlanmış görev için uygun bir ad yazın (örneğin, Uç Nokta Dağıtımı için Defender).

9. **Eylemler** sekmesine gidin ve **Yeni...** öğesini seçin. **Eylem** alanında **Program başlat'ın** seçili olduğundan emin olun. Paylaşılan *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* dosyasının dosya sunucusunun tam etki alanı adını (FQDN) kullanarak UNC yolunu girin.

10. **Tamam'ı** seçin ve açık GPMC pencerelerini kapatın.

> [!IMPORTANT]
> Kullanıma alma, cihazın portala algılayıcı verileri göndermeyi durdurmasına neden olur, ancak sahip olduğu uyarılara başvuru da dahil olmak üzere cihazdaki veriler 6 aya kadar saklanır.

## <a name="monitor-device-configuration"></a>Cihaz yapılandırmasını izleme

grup ilkesi ile cihazlarda ilkelerin dağıtımını izleme seçeneği yoktur. İzleme doğrudan portalda veya farklı dağıtım araçları kullanılarak yapılabilir.

## <a name="monitor-devices-using-the-portal"></a>Portalı kullanarak cihazları izleme

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalına</a> gidin.
2. **Cihaz envanteri'ne** tıklayın.
3. Cihazların görüntülendiğini doğrulayın.

> [!NOTE]
> Cihazların **Cihazlar listesinde** gösterilmeye başlaması birkaç gün sürebilir. Bu, ilkelerin cihaza dağıtılması için gereken süreyi, kullanıcının oturum açacağı süreyi ve uç noktanın raporlamaya başlaması için geçen süreyi içerir.

## <a name="setup-defender-av-policies"></a>Defender AV ilkelerini ayarlama

Yeni bir grup ilkesi oluşturun veya bu ayarları diğer ilkelerle birlikte gruplandırın. Bu, müşterinin ortamına ve farklı kuruluş birimlerini (OU) hedefleyerek hizmeti kullanıma sunma şekline bağlıdır.

1. GP'yi seçtikten veya yeni bir tane oluşturduktan sonra GP'yi düzenleyin.

2. **Bilgisayar Yapılandırma** > **İlkeleri** > **Yönetim Şablonları** > **Windows Bileşenleri** >  **Microsoft Defender Virüsten Koruma** > **Gerçek Zamanlı Koruma'ya** göz atın.

    :::image type="content" source="images/realtime-protect.png" alt-text="Gerçek zamanlı koruma" lightbox="images/realtime-protect.png":::

1. Karantina klasöründe, Karantina klasöründeki öğelerin kaldırılmasını yapılandırın.

    :::image type="content" source="images/removal-items-quarantine1.png" alt-text="Kaldırma öğeleri karantina klasörü" lightbox="images/removal-items-quarantine1.png":::

    :::image type="content" source="images/config-removal-items-quarantine2.png" alt-text="yapılandırma kaldırma karantinası" lightbox="images/config-removal-items-quarantine2.png":::

4. Tarama klasöründe tarama ayarlarını yapılandırın.

    :::image type="content" source="images/gpo-scans.png" alt-text="gpo taramaları" lightbox="images/gpo-scans.png":::

### <a name="monitor-all-files-in-real-time-protection"></a>Tüm dosyaları gerçek zamanlı korumada izleme

**Bilgisayar Yapılandırma** \> **İlkeleri** \> **Yönetim Şablonları** \> **Windows Bileşenleri** \> **Microsoft Defender Virüsten Koruma** \> **Gerçek Zamanlı Koruma'ya** göz atın.

:::image type="content" source="images/config-monitor-incoming-outgoing-file-act.png" alt-text="Gelen giden dosya etkinliği için izlemeyi yapılandırma" lightbox="images/config-monitor-incoming-outgoing-file-act.png":::

### <a name="configure-windows-defender-smartscreen-settings"></a>Windows Defender SmartScreen ayarlarını yapılandırma

1. **Bilgisayar Yapılandırma** \> **İlkeleri** \> **Yönetim Şablonları** \> **Windows Bileşenleri** \> **Windows Defender SmartScreen** \> **Gezgini'ne** gidin.

   :::image type="content" source="images/config-windows-def-smartscr-explorer.png" alt-text="Windows Defender akıllı ekran gezginini yapılandırma" lightbox="images/config-windows-def-smartscr-explorer.png":::
 
2. **Bilgisayar Yapılandırma** > **İlkeleri** > **Yönetim Şablonları** > **Windows Bileşenleri** >  **Windows Defender SmartScreen** > **Microsoft Edge'e** göz atın.

    :::image type="content" source="images/config-windows-def-smartscr-explorer.png" alt-text="Windows Defender akıllı ekran Edge'i yapılandırma" lightbox="images/config-windows-def-smartscr-explorer.png":::

### <a name="configure-potentially-unwanted-applications"></a>İstenmeyebilecek Uygulamaları Yapılandırma

**Bilgisayar Yapılandırma** \> **İlkeleri** \> **Yönetim Şablonları** \> **Windows Bileşenleri** \> **Microsoft Defender Virüsten Koruma'ya** göz atın.

:::image type="content" source="images/config-potential-unwanted-apps.png" alt-text="Olası istenmeyen uygulamayı yapılandırma" lightbox="images/config-potential-unwanted-apps.png":::

:::image type="content" source="images/config-potential-unwanted-apps2.png" alt-text="yapılandırma potansiyeli" lightbox="images/config-potential-unwanted-apps2.png":::

### <a name="configure-cloud-deliver-protection-and-send-samples-automatically"></a>Cloud Deliver Protection'ı yapılandırma ve örnekleri otomatik olarak gönderme

**Bilgisayar Yapılandırma** \> **İlkeleri** \> **Yönetim Şablonları** \> **Windows Bileşenleri** \> **Microsoft Defender Virüsten Koruma** \> **MAPS'e** göz atın.

:::image type="content" source="images/gpo-maps1.png" alt-text="Haritalar" lightbox="images/gpo-maps1.png":::

:::image type="content" source="images/gpo-maps-block-atfirst-sight.png" alt-text="İlk görüşte engelle" lightbox="images/gpo-maps-block-atfirst-sight.png":::

:::image type="content" source="images/gpo-maps-join-ms-maps.png" alt-text="Microsoft Haritalar'a katılma" lightbox="images/gpo-maps-join-ms-maps.png":::

:::image type="content" source="images/send-file-sample-further-analysis-require.png" alt-text="Daha fazla analiz gerektiğinde dosya örneği gönderme" lightbox="images/send-file-sample-further-analysis-require.png":::

> [!NOTE]
> **Tüm örnekleri gönder** seçeneği, güvenlik duruşunu artıran ikili dosyalar/betikler/belgeler için en fazla çözümlemeyi sağlar.
**Güvenli örnekler gönder** seçeneği analiz edilen ikili dosyaların/betiklerin/belgelerin türünü sınırlar ve güvenlik duruşunu azaltır. 

Daha fazla bilgi için bkz[. Microsoft Defender Virüsten Koruma'da bulut korumasını açma](enable-cloud-protection-microsoft-defender-antivirus.md) ve [Microsoft Defender Virüsten Koruma'da bulut koruması ve örnek gönderme.](cloud-protection-microsoft-antivirus-sample-submission.md)

### <a name="check-for-signature-update"></a>İmza güncelleştirmesini denetleme

Virüsten Koruma \> Güvenlik Bilgileri **Güncelleştirmeler Microsoft Defender** **Bilgisayar Yapılandırma** \> **İlkeleri** \> **Yönetim Şablonları** \> **Windows** **Bileşenleri'ne**\> göz atın.

:::image type="content" source="images/signature-update-1.png" alt-text="İmza güncelleştirmesi" lightbox="images/signature-update-1.png":::

:::image type="content" source="images/signature-update-2.png" alt-text="İmza tanımı güncelleştirmesi" lightbox="images/signature-update-2.png":::

### <a name="configure-cloud-deliver-timeout-and-protection-level"></a>Bulut teslimi zaman aşımı ve koruma düzeyini yapılandırma

**Bilgisayar Yapılandırma** \> **İlkeleri** \> **Yönetim Şablonları** \> **Windows Bileşenleri** \> **Microsoft Defender Virüsten Koruma** \> **MpEngine'e** göz atın.
Bulut koruma düzeyi ilkesini **Varsayılan Microsoft Defender Virüsten Koruma engelleme ilkesi** olarak yapılandırdığınızda, ilke devre dışı bırakılır. Koruma düzeyini windows varsayılanı olarak ayarlamak için gereken budur.

:::image type="content" source="images/config-extended-cloud-check.png" alt-text="yapılandırma genişletilmiş bulut denetimi" lightbox="images/config-extended-cloud-check.png":::

:::image type="content" source="images/cloud-protection-level.png" alt-text="bulut koruma düzeyini yapılandırma" lightbox="images/cloud-protection-level.png":::

## <a name="related-topics"></a>İlgili konular
- [Microsoft Endpoint Configuration Manager kullanarak Windows cihazlarını ekleyin](configure-endpoints-sccm.md)
- [Mobil Cihaz Yönetimi araçlarını kullanarak Windows cihazlarını ekleyin](configure-endpoints-mdm.md)
- [Windows araçlarını yerel betik kullanarak ekleyin](configure-endpoints-script.md)
- [Kalıcı olmayan sanal masaüstü altyapısı (VDI) cihazlarının katılımı](configure-endpoints-vdi.md)
- [Yeni eklenen Uç Nokta için Microsoft Defender cihazlarda algılama testi çalıştırma](run-detection-test.md)
- [Uç Nokta için Microsoft Defender ekleme sorunlarını giderme](troubleshoot-onboarding.md)
