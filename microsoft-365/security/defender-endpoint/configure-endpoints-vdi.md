---
title: Kalıcı olmayan sanal masaüstü altyapısı (VDI) cihazlarının katılımı
description: Yapılandırma paketini sanal masaüstü altyapısı (VDI) cihazına dağıtarak Uç Nokta için Microsoft Defender hizmetine eklenmelerini sağlayın.
keywords: sanal masaüstü altyapısını yapılandırma (VDI) cihazı, vdi, cihaz yönetimi, Uç Nokta için Microsoft Defender yapılandırma, uç noktalar
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.date: 04/15/2022
ms.subservice: mde
ms.openlocfilehash: ca5e4ac05df410f15c12acc8254c782cdda4f042
ms.sourcegitcommit: 95ac076310ab9006ed92c69938f7ae771cd10826
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67850424"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-in-microsoft-365-defender"></a>Microsoft 365 Defender kalıcı olmayan sanal masaüstü altyapısı (VDI) cihazlarını ekleme

Sanal masaüstü altyapısı (VDI), son kullanıcıların neredeyse tüm cihazlardan (kişisel bilgisayarınız, akıllı telefonunuz veya tabletiniz gibi) kurumsal sanal masaüstleri örneklerine erişmesini sağlayan ve kuruluşa fiziksel makineler sağlama gereksinimini ortadan kaldıran bir BT altyapısı kavramıdır. BT departmanları artık fiziksel uç noktaları yönetmek, onarmak ve değiştirmekle sorumlu olmadığından VDI cihazlarının kullanılması maliyeti düşürür. Yetkili kullanıcılar, güvenli bir masaüstü istemcisi veya tarayıcısı aracılığıyla onaylanan herhangi bir cihazdan aynı şirket sunucularına, dosyalarına, uygulamalarına ve hizmetlerine erişebilir.

Bt ortamındaki diğer sistemlerde olduğu gibi, bunların da gelişmiş tehditlere ve saldırılara karşı koruma sağlamak için bir Uç Nokta Algılama ve Yanıt (EDR) ve Virüsten Koruma çözümü olmalıdır.


[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Sanal masaüstü altyapısı (VDI) cihazları
- Windows 10, Windows 11, Windows Server 2019, Windows Server 2022, Windows Server 2008R2/2012R2/2016


> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configvdi-abovefoldlink)

 > [!NOTE]
  > **Kalıcı VDI'ler** - Kalıcı bir VDI makinesini Uç Nokta için Microsoft Defender ekleme işlemi, masaüstü veya dizüstü bilgisayar gibi fiziksel bir makineyi eklediğiniz şekilde işlenir. Kalıcı bir makine eklemek için grup ilkesi, Microsoft Endpoint Manager ve diğer yöntemler kullanılabilir. Microsoft 365 Defender portalında (https://security.microsoft.com) ekleme altında tercih ettiğiniz ekleme yöntemini seçin ve bu tür için yönergeleri izleyin. Daha fazla bilgi için bkz [. Windows istemcisini ekleme](onboard-windows-client.md).

## <a name="onboarding-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Kalıcı olmayan sanal masaüstü altyapısı (VDI) cihazlarını ekleme

Uç Nokta için Defender kalıcı olmayan VDI oturumu eklemeyi destekler.

VDI örneklerini eklerken ilgili zorluklar olabilir. Bu senaryo için tipik zorluklar şunlardır:

- Gerçek sağlamadan önce Uç Nokta için Defender'a eklenmesi gereken kısa süreli bir oturumun anında erken eklemesi.
- Cihaz adı genellikle yeni oturumlar için yeniden kullanılır.

VDI ortamında, VDI örneklerinin ömrü kısa olabilir. VDI cihazları Uç Nokta için Defender portalında şu şekilde görünebilir:


- Her VDI örneği için tek portal girişi. VDI örneği zaten Uç Nokta için Microsoft Defender eklendiyse ve bir noktada silindikten sonra aynı ana bilgisayar adıyla yeniden oluşturulduysa, portalda bu VDI örneğini temsil eden yeni bir nesne OLUŞTURULMAZ. 

  > [!NOTE]
  > Bu durumda, oturum oluşturulduğunda *,* örneğin katılımsız yanıt dosyası kullanılarak aynı cihaz adı yapılandırılmalıdır.

- Her cihaz için birden çok giriş - her VDI örneği için bir giriş.

Aşağıdaki adımlar VDI cihazlarını ekleme konusunda size yol gösterir ve tek ve birden çok giriş için adımları vurgular.

> [!WARNING]
> Düşük kaynak yapılandırmalarının olduğu ortamlarda, VDI önyükleme yordamı Uç Nokta için Defender algılayıcısı ekleme işlemini yavaşlatabilir.

### <a name="onboarding-steps"></a>Ekleme adımları

> [!NOTE]
> Windows Server 2016 ve Windows Server 2012 R2'nin, bu özelliğin çalışması için [Windows sunucularını ekleme](/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2012-r2-and-windows-server-2016) yönergeleri kullanılarak yükleme paketinin uygulanmasıyla hazırlanması gerekir.

1.  Hizmet ekleme sihirbazından indirdiğiniz VDI yapılandırma paketini .zip dosyasını (*WindowsDefenderATPOnboardingPackage.zip*) açın. Paketi <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalından</a> da alabilirsiniz:

    1. Gezinti bölmesinde **Ayarlar** > **Uç Noktaları** > **Cihaz yönetimi** > **Ekleme'yi** seçin.

    1. İşletim sistemini seçin.

    1.  **Dağıtım yöntemi** alanında **, kalıcı olmayan uç noktalar için VDI ekleme betikleri'ni** seçin.

    1. **Paketi indir'e** tıklayın ve .zip dosyasını kaydedin.

2. .zip dosyasından ayıklanan WindowsDefenderATPOnboardingPackage klasöründeki dosyaları yolunun `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`altındaki altın/ana görüntüye kopyalayın.
    1. Her cihaz için birden çok girdi uyguluyorsanız ( her oturum için bir tane), WindowsDefenderATPOnboardingScript.cmd dosyasını kopyalayın.
    2. Her cihaz için tek bir giriş uyguluyorsanız hem Onboard-NonPersistentMachine.ps1 hem de WindowsDefenderATPOnboardingScript.cmd dosyasını kopyalayın.

    > [!NOTE]
    > Klasörü görmüyorsanız `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` , gizli olabilir. Dosya Gezgini **Gizli dosya ve klasörleri göster** seçeneğini belirlemeniz gerekir.

3. Yerel grup ilkesi Düzenleyicisi penceresini açın ve **Bilgisayar Yapılandırması** \> **Windows Ayarları** \> **Betikleri** \> **Başlatma'ya** gidin.

   > [!NOTE]
   > Etki alanı grup ilkesi, kalıcı olmayan VDI cihazlarının eklenmesi için de kullanılabilir.

4. Uygulamak istediğiniz yönteme bağlı olarak uygun adımları izleyin:
    - Her cihaz için tek giriş için:

         **PowerShell Betikleri** sekmesini seçin ve **Ekle'ye** tıklayın (Windows Gezgini, ekleme betiğini daha önce kopyaladığınız yolda doğrudan açılır). PowerShell betiğini `Onboard-NonPersistentMachine.ps1`ekleme bölümüne gidin. Otomatik olarak tetiklendiğinden, diğer dosyayı belirtmeniz gerekmez.

    - Her cihaz için birden çok giriş için:

         **Betikler** sekmesini seçin, ardından **Ekle'ye** tıklayın (Windows Gezgini, ekleme betiğini daha önce kopyaladığınız yolda doğrudan açılır). Ekleme bash betiğine `WindowsDefenderATPOnboardingScript.cmd`gidin.

5. Çözümünüzü test edin:
   1. Tek bir cihazla havuz oluşturun.
   2. Cihazda oturum açın.
   3. Cihazdan oturumu kapatın.
   4. Cihazda başka bir kullanıcıyla oturum açın.
   5. Uygulamak istediğiniz yönteme bağlı olarak uygun adımları izleyin:
      - Her cihaz için tek giriş için: Microsoft 365 Defender portalında yalnızca bir girişi denetleyin.
      - Her cihaz için birden çok giriş için: Microsoft 365 Defender portalında birden çok girişi denetleyin.

6. Gezinti bölmesinde **Cihazlar listesi'ne** tıklayın.

7. Cihaz adını girerek arama işlevini kullanın ve arama türü olarak **Cihaz'ı** seçin.

## <a name="for-downlevel-skus-windows-server-2008-r2"></a>Alt düzey SKU'lar için (Windows Server 2008 R2)

> [!NOTE]
> Diğer Windows sunucu sürümleri için bu yönergeler, MMA gerektiren Windows Server 2016 ve Windows Server 2012 R2 için önceki Uç Nokta için Microsoft Defender çalıştırıyorsanız da geçerlidir. Yeni birleştirilmiş çözüme geçiş yönergeleri[, Uç Nokta için Microsoft Defender'daki Sunucu geçiş senaryolarında yer alır](/microsoft-365/security/defender-endpoint/server-migration).

> [!NOTE]
> Aşağıdaki kayıt defteri yalnızca amaç 'Her cihaz için tek bir giriş' elde etmek olduğunda geçerlidir.

1. Kayıt defteri değerini şu şekilde ayarlayın:

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    veya komut satırını kullanarak:

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. [Sunucu ekleme işlemini](configure-server-endpoints.md) izleyin. 

## <a name="updating-virtual-desktop-infrastructure-vdi-images-persistent-or-non-persistent"></a>Sanal masaüstü altyapısı (VDI) görüntülerini güncelleştirme (kalıcı veya kalıcı olmayan)

Güncelleştirmeleri VDI'lerde çalışan VM'lere kolayca dağıtabilme özelliği sayesinde, makinelerinizde güncelleştirmeleri hızlı ve kolay bir şekilde nasıl edinebileceğinize odaklanmak için bu kılavuzu kısaltdık. Güncelleştirmeler konak sunucusundaki bileşen bitlerine genişletildiğinden ve açıldığında doğrudan VM'ye indirildiğinden, artık düzenli aralıklarla altın renkli görüntüler oluşturmanız ve mühürlemeniz gerekmez.

Daha fazla bilgi [için, Sanal Masaüstü Altyapısı (VDI) ortamında Microsoft Defender Virüsten Koruma için dağıtım kılavuzundaki yönergeleri](/microsoft-365/security/defender-endpoint/deployment-vdi-microsoft-defender-antivirus) izleyin.

   > [!NOTE]
   > VDI ortamınızın ana görüntüsünü (SENSE hizmeti çalışıyor) dahil ettiyseniz, görüntüyü üretime geri döndürmeden önce bazı verileri çıkarmanız ve temizlemeniz gerekir.
   > 1. Aşağıdaki komutu bir CMD penceresinde çalıştırarak algılayıcının durdurulduğunu doğrulayın:
   >  ```console
   >  sc query sense
   >  ```
   > 2. PsExec.exe kullanarak aşağıdaki komutları çalıştırın (buradan indirilebilir) https://download.sysinternals.com/files/PSTools.zip)
   >
   >  ```console
   >  PsExec.exe -s cmd.exe
   >  cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
   >  del *.* /f /s /q
   >  REG DELETE "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
   >  exit
   >  ```

## <a name="other-recommended-configuration-settings"></a>Önerilen diğer yapılandırma ayarları

Cihazları hizmete ekledikten sonra, aşağıdaki önerilen yapılandırma ayarlarıyla etkinleştirerek dahil edilen tehdit koruması özelliklerinden yararlanmak önemlidir.

### <a name="next-generation-protection-configuration"></a>Yeni nesil koruma yapılandırması

Aşağıdaki yapılandırma ayarları önerilir:

#### <a name="cloud-protection-service"></a>Bulut Koruma Hizmeti

- Bulut tabanlı korumayı açma: Evet
- Bulut tabanlı koruma düzeyi: Yapılandırılmadı
- Saniyeler içinde Defender Bulut Genişletilmiş Zaman Aşımı: 20

#### <a name="exclusions"></a>Dışlamalar
- Yerel yönetici birleştirmeyi devre dışı bırakma: Yapılandırılmadı
- Hariç tutulacak Defender işlemleri:
  - `%Programfiles%\FSLogix\Apps\frxccd.exe`
  - `%Programfiles%\FSLogix\Apps\frxccds.exe`
  - `%Programfiles%\FSLogix\Apps\frxsvc.exe`

- Taramaların ve gerçek zamanlı korumanın dışında tutulacak dosya uzantıları:
  -  `%Programfiles%\FSLogix\Apps\frxccd.sys`
  - `%Programfiles%\FSLogix\Apps\frxdrv.sys`
  - `%Programfiles%\FSLogix\Apps\frxdrvvt.sys`
  - `%TEMP%*.VHD`
  - `%TEMP%*.VHDX`
  - `%Windir%\TEMP*.VHD`
  - `%Windir%\TEMP*.VHDX`
  - `\\storageaccount.file.core.windows.net\share**.VHD`
  -  `\\storageaccount.file.core.windows.net\share**.VHDX`

#### <a name="real-time-protection"></a>Gerçek Zamanlı Koruma

- Tüm ayarları açın ve tüm dosyaları izleyecek şekilde ayarlayın

#### <a name="remediation"></a>Düzeltme
- Karantinaya alınan kötü amaçlı yazılımların tutulacak gün sayısı: 30
- Örnek onayı gönderme: Tüm örnekleri otomatik olarak gönderme
- İstenmeyebilecek uygulamalarda gerçekleştirmeniz gereken eylem: Etkinleştir
- Algılanan tehditler için eylemler:
  - Düşük tehdit: Temiz
  - Orta tehdit, Yüksek tehdit, Ciddi tehdit: Karantina

#### <a name="scan"></a>Tarama

- Arşivlenen dosyaları tara: Evet
- Zamanlanmış taramalar için düşük CPU önceliği kullanma: Yapılandırılmadı
- Yakalama tam taramayı devre dışı bırakma: Yapılandırılmadı
- Yakalama hızlı taramayı devre dışı bırakma: Yapılandırılmadı
- Tarama başına CPU kullanım sınırı: 50
- Tam tarama sırasında eşlenen netoword sürücülerini tarama: Yapılandırılmadı
- Günlük hızlı taramayı şu saatte çalıştır: 23:00
- Tarama türü: Yapılandırılmadı
- Zamanlanmış taramanın çalıştırıldığı haftanın günü: Yapılandırılmadı
- Zamanlanmış taramanın çalıştırıldığı günün saati: Yapılandırılmadı
- Taramayı çalıştırmadan önce imza güncelleştirmelerini denetleyin: Evet

#### <a name="updates"></a>Güncelleştirmeler
- Güvenlik bilgileri güncelleştirmelerinin ne sıklıkta denetleneceklerini girin: 8
- Diğer ayarları varsayılan durumda bırakın

#### <a name="user-experience"></a>Kullanıcı deneyimi
- Microsoft Defender uygulamasına kullanıcı erişimine izin ver: Yapılandırılmadı

#### <a name="enable-tamper-protection"></a>Kurcalama korumasını etkinleştirme
- Microsoft Defender'ın devre dışı bırakılmasını önlemek için kurcalama korumasını etkinleştirme: Etkinleştir

#### <a name="attack-surface-reduction"></a>Saldırı yüzeyini azaltma

- Ağ korumasını etkinleştirme: Denetim modu
- Microsoft Edge için SmartScreen gerektir: Evet
- Kötü amaçlı site erişimini engelle: Evet
- Doğrulanmamış dosya indirmeyi engelle: Evet

#### <a name="attack-surface-reduction-rules"></a>Saldırı yüzeyini azaltma kuralları
- Denetim için tüm kullanılabilir kuralları yapılandırın.

> [!NOTE]
> Bu etkinliklerin engellenmesi meşru iş süreçlerini kesintiye uğratabilir. En iyi yaklaşım, her şeyi denetime ayarlamak, hangilerinin güvenli olduğunu belirlemek ve ardından hatalı pozitif algılamaları olmayan uç noktalarda bu ayarları etkinleştirmektir.

## <a name="related-topics"></a>İlgili konular
- [Windows araçlarını Grup İlkesi kullanarak ekleyin](configure-endpoints-gp.md)
- [Microsoft Endpoint Configuration Manager kullanarak Windows cihazlarını ekleyin](configure-endpoints-sccm.md)
- [Mobil Cihaz Yönetimi araçlarını kullanarak Windows cihazlarını ekleyin](configure-endpoints-mdm.md)
- [Windows araçlarını yerel betik kullanarak ekleyin](configure-endpoints-script.md)
- [Uç Nokta için Microsoft Defender ekleme sorunlarını giderme](troubleshoot-onboarding.md)
