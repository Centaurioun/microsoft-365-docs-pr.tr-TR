---
title: Windows sunucularını Uç Nokta için Microsoft Defender hizmetine ekleme
description: Algılayıcı verilerini Uç Nokta için Microsoft Defender algılayıcıya gönderebilmeleri için Windows sunucularını ekleme.
keywords: sunucu ekleme, sunucu, 2012r2, 2016, 2019, sunucu ekleme, cihaz yönetimi, Uç Nokta için Microsoft Defender sunucuları yapılandırma, Uç Nokta için Microsoft Defender sunucuları ekleme, ekleme Uç Nokta için Microsoft Defender Sunucu
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
ms.localizationpriority: medium
ms.date: 09/22/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 5a29b372aaa2cddb4d1c7c541e0070e900188d90
ms.sourcegitcommit: 2ff545246fec060ea7829da5afbc1cdc698d51ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68362043"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a>Windows sunucularını Uç Nokta için Microsoft Defender hizmetine ekleme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- Windows Server 2012 R2
- Windows Server 2016
- Windows Server Semi-Annual Enterprise Channel
- Windows Server 2019 ve üzeri
- Windows Server 2019 core edition
- Windows Server 2022
- [Uç Nokta için Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configserver-abovefoldlink)

Uç Nokta için Defender, Windows Server işletim sistemini de içerecek şekilde desteği genişletir. Bu destek, Microsoft 365 Defender konsolu aracılığıyla sorunsuz bir şekilde gelişmiş saldırı algılama ve araştırma özellikleri sağlar. Windows Server desteği sunucu etkinlikleri, çekirdek ve bellek saldırısı algılama kapsamı hakkında daha ayrıntılı içgörüler sağlar ve yanıt eylemlerini etkinleştirir.

Bu makalede, belirli Windows sunucularının Uç Nokta için Microsoft Defender ekleme işlemi açıklanır.

Windows sunucuları için Windows Güvenliği Taban Çizgilerini indirme ve kullanma hakkında yönergeler için bkz. [Windows Güvenliği Temeller](/windows/device-security/windows-security-baselines).

## <a name="windows-server-onboarding-overview"></a>Windows Server eklemeye genel bakış

Sunucuları başarıyla eklemek için aşağıdaki genel adımları tamamlamanız gerekir.

:::image type="content" source="images/server-onboarding-tools-methods.png" alt-text="Windows Sunucuları ve Windows 10 cihazları için ekleme akışının çizimi" lightbox="images/server-onboarding-tools-methods.png":::

>[!NOTE]
> Windows Hyper-V Server sürümleri desteklenmez.

**Sunucular için Microsoft Defender ile tümleştirme**:

Uç Nokta için Microsoft Defender, Sunucular için Microsoft Defender ile sorunsuz bir şekilde tümleşir. Sunucuları otomatik olarak ekleyebilir, Bulut için Microsoft Defender tarafından izlenen sunucuların Uç Nokta için Defender'da görünmesini sağlayabilir ve Bulut müşterisi için bir Microsoft Defender olarak ayrıntılı araştırmalar gerçekleştirebilirsiniz. Daha fazla bilgi [için lütfen Uç noktalarınızı Bulut için Defender'ın tümleşik EDR çözümüyle koruma: Uç Nokta için Microsoft Defender](/azure/defender-for-cloud/integration-defender-for-endpoint?tabs=windows)

> [!NOTE]
> Windows Server 2012 R2 ve 2016 için, bu makinelere modern, birleşik çözümü el ile yükleyebilir/yükseltebilir ya da sunucu planı için ilgili Microsoft Defender kapsamındaki sunucuları otomatik olarak dağıtmak veya yükseltmek için tümleştirmeyi kullanabilirsiniz. [Bulut için Defender'ın tümleşik EDR çözümüyle uç noktalarınızı koruma: Uç Nokta için Microsoft Defender](/azure/defender-for-cloud/integration-defender-for-endpoint?tabs=windows#enable-the-integration) bölümünde geçiş yapma hakkında daha fazla bilgi.
> - Sunucuları izlemek için Bulut için Microsoft Defender kullandığınızda, otomatik olarak bir Uç Nokta için Defender kiracısı oluşturulur (ABD kullanıcıları için ABD'de, Avrupa kullanıcıları için AB'de ve Birleşik Krallık kullanıcıları için İngiltere'de).
Uç Nokta için Defender tarafından toplanan veriler, sağlama sırasında tanımlandığı gibi kiracının coğrafi konumunda depolanır.
> - Bulut için Microsoft Defender kullanmadan önce Uç Nokta için Defender kullanıyorsanız, daha sonra Bulut için Microsoft Defender ile tümleştirseniz bile verileriniz kiracınızı oluştururken belirttiğiniz konumda depolanır.
> - Yapılandırıldıktan sonra, verilerinizin depolandığı konumu değiştiremezsiniz. Verilerinizi başka bir konuma taşımanız gerekiyorsa, kiracıyı sıfırlamak için Microsoft Desteği'a başvurmanız gerekir.
> - Bu tümleştirmeyi kullanan sunucu uç noktası izlemesi, Office 365 GCC müşterileri için devre dışı bırakıldı.
> - Bulut için Microsoft Defender aracılığıyla eklenen Linux sunucularının ilk yapılandırmaları Defender Virüsten Koruma'yı [pasif modda](/defender-endpoint/microsoft-defender-antivirus-compatibility#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions) çalıştıracak şekilde ayarlanacaktır.

**R2 ve Windows Server 2016 Windows Server 2012**:

- Yükleme ve ekleme paketlerini indirme
- Yükleme paketini uygulama
- İlgili araç için ekleme adımlarını izleyin

**Windows Server Semi-Annual Enterprise Channel ve Windows Server 2019**:

- Ekleme paketini indirme
- İlgili araç için ekleme adımlarını izleyin

>[!IMPORTANT]
>Uç Nokta için Microsoft Defender Server SKU'su satın almaya uygun olmak için, aşağıdakilerden herhangi birini(Windows E5/A5, Microsoft 365 E5/A5 veya Microsoft 365 E5 Güvenlik abonelik lisanslarından en az birini) zaten satın almış olmanız gerekir.  Lisanslama hakkında daha fazla bilgi için bkz. [Ürün Koşulları](https://www.microsoft.com/licensing/terms/productoffering/MicrosoftDefenderforEndpointServer/all).

## <a name="windows-server-2012-r2-and-windows-server-2016"></a>R2 ve Windows Server 2016 Windows Server 2012

### <a name="new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution"></a>Modern birleşik çözümde yeni Windows Server 2012 R2 ve 2016 işlevleri

R2 ve Windows Server 2012 Windows Server 2016 ekleme işleminin önceki uygulaması (Nisan 2022'nin öncesinde) Microsoft Monitoring Agent (MMA) kullanımını gerektiriyordu.

Yeni birleşik çözüm paketi, bağımlılıkları ve yükleme adımlarını kaldırarak sunucuları eklemeyi kolaylaştırır. Ayrıca çok genişletilmiş bir özellik kümesi sağlar. Daha fazla bilgi için lütfen [R2 ve 2016 Windows Server 2012 Savunma](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/defending-windows-server-2012-r2-and-2016/ba-p/2783292) bölümüne bakın.

Eklediğiniz sunucuya bağlı olarak, birleşik çözüm Virüsten Koruma'yı ve/veya EDR algılayıcısını Microsoft Defender yükler. Aşağıdaki tabloda hangi bileşenin yüklü olduğu ve varsayılan olarak nelerin yerleşik olduğu gösterilir.

|Sunucu sürümü|Av|Edr|
|----|----|----|
|Windows Server 2012 R2 SP1|![Evet.](images/svg/check-yes.svg)|![Evet.](images/svg/check-yes.svg)|
|Windows Server 2016|Yerleşik|![Evet.](images/svg/check-yes.svg)|
|Windows Server 2019 veya üzeri|Yerleşik|Yerleşik|

Sunucularınızı daha önce MMA kullanarak ekleme yaptıysanız, yeni çözüme geçiş yapmak için [Sunucu geçişi](server-migration.md) bölümünde sağlanan yönergeleri izleyin.

> [!IMPORTANT]
> Ekleme işlemine devam etmeden önce, [Windows Server 2012 R2 ve 2016 için yeni, birleşik çözüm paketinde bilinen sorunlar ve sınırlamalar](#known-issues-and-limitations-in-the-new-unified-solution-package-for-windows-server-2012-r2-and-2016) bölümüne bakın.

### <a name="prerequisites"></a>Önkoşullar

#### <a name="prerequisites-for-windows-server-2012-r2"></a>Windows Server 2012 R2 için önkoşullar

Makinelerinizi en son [aylık toplama](https://support.microsoft.com/topic/windows-8-1-and-windows-server-2012-r2-update-history-47d81dd2-6804-b6ae-4112-20089467c7a6) paketiyle tamamen güncelleştirdiyseniz, başka bir önkoşul **yoktur** ve aşağıdaki gereksinimler zaten doldurulur.

Yükleyici paketi, başarılı bir yükleme için en düşük gereksinimlerin karşılanmış olup olmadığını değerlendirmek üzere bir güncelleştirme aracılığıyla aşağıdaki bileşenlerin zaten yüklenip yüklenmediğini denetler:

- [Müşteri deneyimi ve tanılama telemetrisi için güncelleştirme](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)
- [Windows'ta Evrensel C Çalışma Zamanı Güncelleştirmesi](https://support.microsoft.com/topic/update-for-universal-c-runtime-in-windows-c0514201-7fe6-95a3-b0a5-287930f3560c)
- [Windows Server 2012 R2 için Güvenlik Güncelleştirmesi (KB3045999)](https://support.microsoft.com/en-us/topic/ms15-038-description-of-the-security-update-for-windows-april-14-2015-99265f07-6926-d6d2-5203-3b32b214a9c3)

#### <a name="prerequisites-for-windows-server-2016"></a>Windows Server 2016 önkoşulları

- 14 Eylül 2021 veya sonraki sürümlerden hizmet yığını güncelleştirmesi (SSU) yüklenmelidir.
- 20 Eylül 2018 veya sonraki sürümlerden en son Toplu Güncelleştirme (LCU) yüklenmelidir.  Sunucuya en son kullanılabilir SSU ve LCU'nun yüklenmesi önerilir.
- Microsoft Defender Virüsten Koruma özelliğini etkinleştirin ve güncel olduğundan emin olun. Windows Server'da Defender Virüsten Koruma'yı etkinleştirme hakkında daha fazla bilgi için bkz. [Devre dışı bırakıldıysa Windows Server'da Defender Virüsten Koruma'yı](enable-update-mdav-to-latest-ws.md#re-enable-microsoft-defender-antivirus-on-windows-server-if-it-was-disabled) [yeniden etkinleştirme ve kaldırılmışsa Windows Server'da Defender Virüsten Koruma'yı yeniden etkinleştirme](enable-update-mdav-to-latest-ws.md#re-enable-microsoft-defender-antivirus-on-windows-server-if-it-was-uninstalled).
- Windows Update kullanarak en son platform sürümünü indirin ve yükleyin. Alternatif olarak, güncelleştirme paketini [Microsoft Update Kataloğu'ndan](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4052623) veya [MMPC'den](https://go.microsoft.com/fwlink/?linkid=870379&arch=x64) el ile indirin.

#### <a name="prerequisites-for-running-with-third-party-security-solutions"></a>Üçüncü taraf güvenlik çözümleriyle çalışmak için önkoşullar

Üçüncü taraf kötü amaçlı yazılımdan koruma çözümü kullanmayı planlıyorsanız Microsoft Defender Virüsten Koruma'yı pasif modda çalıştırmanız gerekir. Yükleme ve ekleme işlemi sırasında pasif moda ayarlamayı unutmayın. 

> [!NOTE]
> McAfee Endpoint Security (ENS) veya VirusScan Enterprise (VSE) bulunan sunuculara Uç Nokta için Microsoft Defender yüklüyorsanız, Microsoft Defender Virüsten Koruma'nın kaldırılmadığından veya devre dışı bırakılmadığından emin olmak için McAfee platformunun sürümünün güncelleştirilmesi gerekebilir. Gereken sürüm numaraları dahil olmak üzere daha fazla bilgi için [McAfee Bilgi Merkezi makalesine bakın](https://kcm.trellix.com/corporate/index?page=content&id=KB88214).

#### <a name="update-packages-for-microsoft-defender-for-endpoint-on-windows-server-2012-r2-and-2016"></a>Windows Server 2012 R2 ve 2016'da Uç Nokta için Microsoft Defender paketlerini güncelleştirme

EDR Algılayıcısı bileşenine yönelik düzenli ürün iyileştirmeleri ve düzeltmeleri almak için [KB5005292](https://go.microsoft.com/fwlink/?linkid=2168277) Windows Update uygulandığından veya onay aldığından emin olun. Ayrıca koruma bileşenlerini güncel tutmak için bkz[. Virüsten koruma güncelleştirmelerini yönetme ve temelleri uygulama Microsoft Defender](/microsoft-365/security/defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions).

Windows Server Update Services (WSUS) ve/veya Microsoft Endpoint Configuration Manager kullanıyorsanız, bu yeni "EDR Algılayıcısı için Uç Nokta için Microsoft Defender güncelleştirmesi" "Uç Nokta için Microsoft Defender" kategorisi altında kullanılabilir.

### <a name="onboarding-steps-summary"></a>Ekleme adımları özeti

- ADIM 1: [Yükleme ve ekleme paketlerini indirme](#step-1-download-installation-and-onboarding-packages)
- ADIM 2: [Yükleme ve ekleme paketini uygulama](#step-2-apply-the-installation-and-onboarding-package)
- 3. ADIM: [Ekleme adımlarını tamamlayın](#step-3-complete-the-onboarding-steps)

### <a name="step-1-download-installation-and-onboarding-packages"></a>ADIM 1: Yükleme ve ekleme paketlerini indirme

Portaldan hem **yükleme** hem de **ekleme** paketlerini indirmeniz gerekir.

> [!NOTE]
> Yükleme paketi aylık olarak güncelleştirilir. Kullanımdan önce en son paketi indirdiğinizden emin olun.
> Yüklemeden sonra güncelleştirmek için yükleyici paketini yeniden çalıştırmanız gerekmez. Bunu yaparsanız, kaldırma gereksinimi olduğundan yükleyici ilk olarak sizden çıkarmanızı ister. Bkz[. Windows Server 2012 R2 ve 2016'da Uç Nokta için Microsoft Defender paketlerini güncelleştirme](#update-packages-for-microsoft-defender-for-endpoint-on-windows-server-2012-r2-and-2016).

> [!div class="mx-imgBorder"]
> ![Ekleme panosunun resmi](images/install-agent-onboard.png)

   > [!NOTE]
   > Windows Server 2012R2'de, Microsoft Defender Virüsten Koruma yükleme paketi tarafından yüklenir ve pasif moda ayarlamadığınız sürece etkin olur. Windows Server 2016'da, Microsoft Defender Virüsten Koruma'nın bir özellik olarak yüklenmesi gerekir (bkz. [MDE'ye geçme](/microsoft-365/security/defender-endpoint/switch-to-mde-phase-2#re-enable-microsoft-defender-antivirus-on-windows-server-2016)) ve yüklemeye devam etmeden önce tam olarak güncelleştirilmelidir.
   >
   > Microsoft dışı bir kötü amaçlı yazılımdan koruma çözümü çalıştırıyorsanız, yüklemeden önce Microsoft dışı çözüme Microsoft Defender Virüsten Koruma ([Defender İşlemleri sekmesindeki Microsoft Defender İşlemler listesinden](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)) için dışlamalar eklediğinizden emin olun.  Defender Virüsten Koruma dışlama listesine Microsoft dışı güvenlik çözümleri eklenmesi de önerilir.

**Yükleme paketi**, Uç Nokta için Microsoft Defender aracısını yükleyen bir MSI dosyası içerir.

**Ekleme paketi** aşağıdaki dosyaları içerir:

- `OptionalParamsPolicy` - örnek toplamayı etkinleştiren ayarı içerir
- `WindowsDefenderATPOnboardingScript.cmd` - ekleme betiğini içerir

Paketleri indirmek için şu adımları izleyin:

1. Microsoft 365 Defender'da **Ayarlar > Cihaz Yönetimi > Ekleme'ye** gidin.

2. **R2 ve 2016 Windows Server 2012** seçin.

3. **Yükleme paketini indir'i** seçin ve .msi dosyasını kaydedin.

4. **Ekleme paketini indir'i** seçin ve .zip dosyasını kaydedin.

5. Microsoft Defender Virüsten Koruma'Microsoft Defender yükleme seçeneklerinden birini kullanarak yükleme paketini yükleyin. Yükleme için yönetici izinleri gerekir.

### <a name="step-2-apply-the-installation-and-onboarding-package"></a>ADIM 2: Yükleme ve ekleme paketini uygulama

Bu adımda, makineyi eklemeye hazırlamak için cihazınızı Uç Nokta için Microsoft Defender bulut ortamına eklemeden önce gerekli önleme ve algılama bileşenlerini yükleyeceksiniz. Tüm [önkoşulların](#prerequisites) karşılandığından emin olun.

   > [!NOTE]
   > Microsoft Defender Virüsten Koruma yüklenir ve pasif moda ayarlamadığınız sürece etkin olur.

#### <a name="options-to-install-the-microsoft-defender-for-endpoint-packages"></a>Uç Nokta için Microsoft Defender paketlerini yükleme seçenekleri

Önceki bölümde bir yükleme paketi indirdiyseniz. Yükleme paketi, tüm Uç Nokta için Microsoft Defender bileşenleri için yükleyiciyi içerir.

Aracıyı yüklemek için aşağıdaki seçeneklerden herhangi birini kullanabilirsiniz:

- [Komut satırını kullanarak yükleme](#install-microsoft-defender-for-endpoint-using-the-command-line)
- [Betik kullanarak yükleme](#install-microsoft-defender-for-endpoint-using-a-script)
- [grup ilkesi kullanarak yükleme ve ekleme paketlerini uygulama](#apply-the-microsoft-defender-for-endpoint-installation-and-onboarding-packages-using-group-policy)

##### <a name="install-microsoft-defender-for-endpoint-using-the-command-line"></a>Komut satırını kullanarak Uç Nokta için Microsoft Defender yükleme

Uç Nokta için Microsoft Defender yüklemek için önceki adımdaki yükleme paketini kullanın.

Uç Nokta için Microsoft Defender yüklemek için aşağıdaki komutu çalıştırın:

```console
Msiexec /i md4ws.msi /quiet
```

Kaldırmak için, uygun çıkarma betiğini kullanarak önce makinenin çıkarıldığından emin olun. Ardından kaldırmayı gerçekleştirmek için programlar \> ve özellikler Denetim Masası \> kullanın.

Alternatif olarak, Uç Nokta için Microsoft Defender kaldırmak için aşağıdaki kaldırma komutunu çalıştırın:

```console
Msiexec /x md4ws.msi /quiet
```

Yukarıdaki komutun başarılı olması için yükleme için kullandığınız paketi kullanmanız gerekir.

Anahtar `/quiet` tüm bildirimleri gizler.

> [!NOTE]
> Microsoft Defender Virüsten Koruma otomatik olarak pasif moda geçmiyor. Microsoft dışı bir virüsten koruma/kötü amaçlı yazılımdan koruma çözümü çalıştırıyorsanız Microsoft Defender Virüsten Koruma'yı pasif modda çalışacak şekilde ayarlayabilirsiniz. Komut satırı yüklemeleri için isteğe bağlı`FORCEPASSIVEMODE=1`, müdahaleyi önlemek için Microsoft Defender Virüsten Koruma bileşenini hemen Pasif moda ayarlar. Ardından, EDR Block gibi özellikleri desteklemek üzere eklendikten sonra Defender Virüsten Koruma'nın pasif modda kalmasını sağlamak için "ForceDefenderPassiveMode" kayıt defteri anahtarını ayarlayın.

Windows Server desteği sunucu etkinlikleri, çekirdek ve bellek saldırısı algılama kapsamı hakkında daha ayrıntılı içgörüler sağlar ve yanıt eylemlerini etkinleştirir.

##### <a name="install-microsoft-defender-for-endpoint-using-a-script"></a>Betik kullanarak Uç Nokta için Microsoft Defender yükleme

Yükleme, kaldırma ve ekleme işlemini otomatikleştirmeye yardımcı olması için [yükleyici yardımcı betiğini](server-migration.md#installer-script) kullanabilirsiniz. 
> [!NOTE]
> Yükleme betiği imzalandı. Betikte yapılan değişiklikler imzayı geçersiz kılacak. Betiği GitHub'dan indirdiğinizde, yanlışlıkla değiştirilmesini önlemek için önerilen yaklaşım, kaynak dosyaları zip arşivi olarak indirmek ve ardından install.ps1 dosyasını almak için ayıklamaktır (ana Kod sayfasında Kod açılan menüsüne tıklayın ve "ZIP'i İndir"i seçin).

Bu betik, [önceki MMA tabanlı Uç Nokta için Microsoft Defender çözümünden sunucu geçişi senaryolarında açıklanan senaryolar](/microsoft-365/security/defender-endpoint/server-migration) ve aşağıda açıklandığı gibi grup ilkesi kullanılarak dağıtım için de dahil olmak üzere çeşitli senaryolarda kullanılabilir.

##### <a name="apply-the-microsoft-defender-for-endpoint-installation-and-onboarding-packages-using-group-policy"></a>Grup ilkesini kullanarak Uç Nokta için Microsoft Defender yükleme ve ekleme paketlerini uygulama

1. Grup ilkesi oluşturma: <br> [grup ilkesi Yönetim Konsolu'nu](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) açın, yapılandırmak istediğiniz **nesneler grup ilkesi** sağ tıklayın ve **Yeni'yi** seçin. Görüntülenen iletişim kutusuna yeni GPO'nun adını girin ve **Tamam'ı** seçin.

2. [grup ilkesi Yönetim Konsolu'nu](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) açın, yapılandırmak istediğiniz grup ilkesi Nesnesine (GPO) sağ tıklayın ve **Düzenle'yi** seçin.

3. **grup ilkesi Yönetim Düzenleyicisi'nde** **Bilgisayar yapılandırması'na**, **Tercihler'e** ve ardından **Denetim masası ayarları'na** gidin.

4. **Zamanlanmış görevler'e** sağ tıklayın, **Yeni'nin** üzerine gelin ve **ardından Anında Görev 'e (En az Windows 7)** tıklayın.

5. Açılan **Görev** penceresinde **Genel** sekmesine gidin. **Güvenlik seçenekleri'nin** altında **Kullanıcıyı veya Grubu Değiştir'i** seçin ve SİSTEM yazıp **Adları Denetle'yi** ve ardından **Tamam'ı** seçin. NT AUTHORITY\SYSTEM, görevin çalıştırılacağı kullanıcı hesabı olarak görünür.

6. **Kullanıcının oturum açıp açmadığını çalıştır'ı** seçin ve **En yüksek ayrıcalıklarla çalıştır** onay kutusunu işaretleyin.

7. Ad alanına zamanlanmış görev için uygun bir ad yazın (örneğin, Uç Nokta Dağıtımı için Defender).

8. **Eylemler** sekmesine gidin ve **Yeni...** öğesini seçin. **Eylem** alanında **Program başlat'ın** seçili olduğundan emin olun. [Yükleyici betiği](server-migration.md#installer-script) yüklemeyi işler ve yükleme tamamlandıktan hemen sonra ekleme adımını gerçekleştirir. *C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'ı* seçin ve bağımsız değişkenleri sağlayın:

    ```console
     -ExecutionPolicy RemoteSigned \\servername-or-dfs-space\share-name\install.ps1 -OnboardingScript \\servername-or-dfs-space\share-name\windowsdefenderatponboardingscript.cmd
    ```

    > [!NOTE]

    > Önerilen yürütme ilkesi ayarıdır `Allsigned`. Betik uç noktada SYSTEM olarak çalışıyorsa bu, betiğin imzalama sertifikasının Yerel Bilgisayar Güvenilen Yayımcılar deposuna aktarılmasını gerektirir.

    paylaşılan *install.ps1* dosyasının tam etki alanı adını (FQDN) kullanarak sunucuadı-veya-dfs-space\share-name yerine UNC yolunu yazın\\. Yükleyici paketi md4ws.msi aynı dizine yerleştirilmelidir.  UNC yolunun izinlerinin, günlük dosyalarının oluşturulmasını desteklemek için paketi yükleyen bilgisayar hesabına yazma erişimine izin verdiğinden emin olun. Günlük dosyalarının oluşturulmasını devre dışı bırakmak istiyorsanız (önerilmez), -noETL -noMSILog parametrelerini kullanabilirsiniz.

    Microsoft Defender Virüsten Koruma'nın Microsoft dışı kötü amaçlı yazılımdan koruma çözümleriyle birlikte var olmasını istediğiniz senaryolar için yükleme sırasında pasif modu ayarlamak için $Passive parametresini ekleyin.

9. **Tamam'ı** seçin ve açık GPMC pencerelerini kapatın.

10. GPO'yu Bir Kuruluş Birimine (OU) bağlamak için sağ tıklayın ve **Var olan bir GPO'yu bağla'ya** tıklayın. Görüntülenen iletişim kutusunda, bağlamak istediğiniz grup ilkesi Nesnesi'ni seçin. **Tamam**'ı seçin.

Daha fazla yapılandırma ayarı için bkz [. Örnek koleksiyon ayarlarını](configure-endpoints-gp.md#configure-sample-collection-settings) yapılandırma ve [Diğer önerilen yapılandırma ayarları](configure-endpoints-gp.md#other-recommended-configuration-settings).

### <a name="step-3-complete-the-onboarding-steps"></a>3. ADIM: Ekleme adımlarını tamamlayın

Aşağıdaki adımlar yalnızca üçüncü taraf kötü amaçlı yazılımdan koruma çözümü kullanıyorsanız geçerlidir. Aşağıdaki Microsoft Defender Virüsten koruma pasif modu ayarını uygulamanız gerekir. Doğru yapılandırıldığını doğrulayın:

1. Aşağıdaki kayıt defteri girdisini ayarlayın:
    - Yolu: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
    - Ad: `ForceDefenderPassiveMode`
    - Türü: `REG_DWORD`
    - Değer: `1`

   :::image type="content" source="images/atp-verify-passive-mode.png" alt-text="Pasif mod doğrulama sonucu" lightbox="images/atp-verify-passive-mode.png":::

> [!IMPORTANT]
>
> - Yerel betik kavram kanıtı için uygundur ancak üretim dağıtımı için kullanılmamalıdır. Üretim dağıtımı için grup ilkesi veya Microsoft Endpoint Configuration Manager kullanmanızı öneririz.

#### <a name="known-issues-and-limitations-in-the-new-unified-solution-package-for-windows-server-2012-r2-and-2016"></a>Windows Server 2012 R2 ve 2016 için yeni, birleşik çözüm paketindeki bilinen sorunlar ve sınırlamalar

Yeni bir yükleme gerçekleştirmeden önce her zaman en son yükleyici paketini indirin. Yüklemeden sonra, [Windows Server 2012 R2 ve 2016'da Uç Nokta için Microsoft Defender için paketleri güncelleştirme](#update-packages-for-microsoft-defender-for-endpoint-on-windows-server-2012-r2-and-2016) bölümünde açıklanan bileşen güncelleştirmelerini kullanarak düzenli olarak güncelleştirin. Aşağıdaki ayrıntılar Windows Server 2012 R2 ve 2016 için yeni birleşik çözüm paketi için geçerlidir:

- İşletim sistemi güncelleştirmesi, hizmet yüklemesinde zaman aşımı nedeniyle diskleri yavaş olan makinelerde yükleme sorununa neden olabilir. Yükleme "c:\program files\windows defender\mpasdesc.dll bulunamadı, - 310 WinDefend" iletisiyle başarısız oluyor. Gerekirse başarısız yüklemeyi temizlemeye yardımcı olmak için en son yükleme paketini ve en son [install.ps1](https://github.com/microsoft/mdefordownlevelserver) betiğini kullanın.
- [Proxy sunucusundaki Uç Nokta için Microsoft Defender hizmet URL'lerine erişimi etkinleştirme](/microsoft-365/security/defender-endpoint/configure-proxy-internet?enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server) bölümünde belirtildiği gibi bağlantı gereksinimlerinin karşılandığından emin olun. Bunlar, Windows Server 2019 için bu gereksinimlere eşdeğerdir.
- Statik TelemetryProxyServer kullanıldığında **ve** sertifika iptal listesi (CRL) URL'lerine SYSTEM hesabı bağlamından ulaşılamadığında buluta Windows Server 2012 R2 bağlantısıyla ilgili bir sorun tespit ettik. Hemen azaltma, bu tür bir bağlantı sağlayan alternatif bir proxy seçeneği ("sistem genelinde") kullanmak veya SYSTEM hesabı bağlamında WinInet ayarı aracılığıyla aynı proxy'yi yapılandırmaktır.
Alternatif olarak, geçici bir çözüm olarak sertifika yüklemek [için bağlantısı kesilmiş makinelerde TelemetryProxyServer ile ilgili bilinen bir sorun için Geçici Çözüm'de](#workaround-for-a-known-issue-with-telemetryproxyserver-on-disconnected-machines) sağlanan yönergeleri kullanın.
- Daha önce, OMS/Log Analytics ağ geçidinin Defender bulut hizmetlerine bağlantı sağlaması için Windows Server 2016 ve altında Microsoft Monitoring Agent'ın (MMA) kullanılmasına izin veriliyor. Windows Server 2019, Windows Server 2022 ve Windows 10'da Uç Nokta için Microsoft Defender gibi yeni çözüm bu ağ geçidini desteklemez.
- Windows Server 2016 Microsoft Defender Virüsten Koruma'nın yüklü olduğunu ve etkin ve güncel olduğunu doğrulayın. Windows Update kullanarak en son platform sürümünü indirip yükleyebilirsiniz. Alternatif olarak, güncelleştirme paketini [Microsoft Update Kataloğu'ndan](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4052623) veya [MMPC'den](https://go.microsoft.com/fwlink/?linkid=870379&arch=x64) el ile indirin.
- Windows Server 2012 R2'de Microsoft Defender Virüsten Koruma için kullanıcı arabirimi yoktur. Ayrıca, Windows Server 2016 üzerindeki kullanıcı arabirimi yalnızca temel işlemlere izin verir. Bir cihazda yerel olarak işlem gerçekleştirmek için Bkz. [PowerShell, WMI ve MPCmdRun.exeile Uç Nokta için Microsoft Defender yönetme](/microsoft-365/security/defender-endpoint/manage-mde-post-migration-other-tools). Sonuç olarak, özellikle kullanıcı etkileşimini kullanan, kullanıcının bir karar vermesinin veya belirli bir görevi gerçekleştirmesinin istendiği yer gibi özellikler beklendiği gibi çalışmayabilir. Kullanıcı arabirimini devre dışı bırakması veya etkinleştirmemesi veya herhangi bir yönetilen sunucuda kullanıcı etkileşimi gerektirmesi önerilir çünkü koruma özelliğini etkileyebilir.
- Tüm Saldırı Yüzeyi Azaltma kuralları tüm işletim sistemlerinde kullanılamaz. Bkz [. Saldırı Yüzeyi Azaltma (ASR) kuralları](/microsoft-365/security/defender-endpoint/attack-surface-reduction-rules).
- [Ağ Koruması'nı](/microsoft-365/security/defender-endpoint/network-protection) etkinleştirmek için daha fazla yapılandırma gerekir:
  - `Set-MpPreference -EnableNetworkProtection Enabled`
  - `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`
  - `Set-MpPreference -AllowNetworkProtectionDownLevel 1`
  - `Set-MpPreference -AllowDatagramProcessingOnWinServer 1`

  Ayrıca, yüksek hacimli ağ trafiğine sahip makinelerde, bu özelliği geniş bir şekilde etkinleştirmeden önce ortamınızda performans testi önerilir. Ek kaynak tüketimini hesaba eklemeniz gerekebilir.
- İşletim sistemi yükseltmeleri desteklenmez. Ardından yükseltmeden önce kaldırın.
- **Sunucu rolleri** için otomatik dışlamalar Windows Server 2012 R2'de desteklenmez; ancak işletim sistemi dosyaları için yerleşik dışlamalar desteklenir. Dışlama ekleme hakkında daha fazla bilgi için bkz. [Şu anda desteklenen Windows sürümlerini çalıştıran Kurumsal bilgisayarlar için virüs tarama önerileri](https://support.microsoft.com/topic/virus-scanning-recommendations-for-enterprise-computers-that-are-running-currently-supported-versions-of-windows-kb822158-c067a732-f24a-9079-d240-3733e39b40bc).
- Önceki MMA tabanlı çözümden yükseltilen makinelerde ve EDR algılayıcısı 10.8047.22439.1056'dan eski bir (önizleme) sürümüdür. MMA tabanlı çözümün kaldırılması ve geri döndürülmesi kilitlenmelere neden olabilir. Böyle bir önizleme sürümü kullanıyorsanız KB5005292 kullanarak güncelleştirin.
- 2107 ve 2203 sürümlerinde Microsoft Endpoint Configuration Manager (MECM) kullanarak yeni çözümü dağıtmak ve eklemek için bir paket oluşturulması gerekir. Configuration Manager'da program ve betik dağıtma hakkında daha fazla bilgi için bkz. [Configuration Manager'de paketler ve programlar](/configmgr/apps/deploy-use/packages-and-programs). MMA tabanlı sürümden geçiş yapmak için MECM 2107, 2203'i de kullanabilirsiniz. Daha fazla bilgi için bkz. [Sunucuları Microsoft Monitoring Agent'tan birleşik çözüme geçirme](application-deployment-via-mecm.md).
- Endpoint Protection düğümünü kullanarak ilke yapılandırma yönetimini desteklemek için düzeltme paketi veya üzerini içeren MECM 2107 gereklidir. 
- Microsoft Endpoint Configuration Manager 2207 veya üzeri [otomatik yüklemeyi ve eklemeyi](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#bkmk_2207) destekler

#### <a name="workaround-for-a-known-issue-with-telemetryproxyserver-on-disconnected-machines"></a>Bağlantısı kesilmiş makinelerde TelemetryProxyServer ile ilgili bilinen bir sorun için geçici çözüm

Sorun açıklaması: Sertifika İptal Listesi (CRL) URL'sine erişmek için başka bir yolu olmayan makinelerde, Uç Nokta için Microsoft Defender EDR bileşeni tarafından kullanılacak bir ara sunucu belirtmek için TelemetryProxyServer ayarını kullanırken, eksik bir ara sertifika EDR algılayıcısının bulut hizmetine başarıyla bağlanmamasına neden olur.

Etkilenen senaryo: Windows Server 2012 R2 üzerinde çalışan Akıllı sürüm numarası 10.8048.22439.1065 veya önceki önizleme sürümleriyle -Uç Nokta için Microsoft Defender -TelemetryProxyServer proxy yapılandırmasını kullanma; diğer yöntemler etkilenmez

Geçi -ci çözüm:
1. Ekleme sayfasında bulunan en son paketi kullanarak veya KB5005292 uygulayarak makinenin Akıllı sürüm 10.8048.22439.1065 veya üzerini çalıştırdığından emin olun.
2. Sertifikayı indirme ve sıkıştırmasını açma https://github.com/microsoft/mdefordownlevelserver/blob/main/InterCA.zip
3. Sertifikayı Yerel Bilgisayar güvenilen "Ara Sertifika Yetkilileri" deposuna aktarın.
PowerShell komutunu kullanabilirsiniz: Import-Certificate -FilePath .\InterCA.cer -CertStoreLocation Cert:\LocalMachine\Ca

## <a name="windows-server-semi-annual-enterprise-channel-sac-windows-server-2019-and-windows-server-2022"></a>Windows Server Semi-Annual Enterprise Channel (SAC), Windows Server 2019 ve Windows Server 2022

### <a name="download-package"></a>Paketi indirme

1. Microsoft 365 Defender'da **Ayarlar > Cihaz Yönetimi > Ekleme'ye** gidin.

2. **Windows Server 1803 ve 2019'ı** seçin.

3. **Paketi indir'i** seçin. WindowsDefenderATPOnboardingPackage.zip olarak kaydedin.

4. Ekleme adımlarını tamamlama bölümünde sağlanan [adımları](#step-3-complete-the-onboarding-steps) izleyin.

## <a name="verify-the-onboarding-and-installation"></a>Ekleme ve yüklemeyi doğrulama

virüsten koruma ve Uç Nokta için Microsoft Defender Microsoft Defender çalıştığını doğrulayın.

## <a name="run-a-detection-test-to-verify-onboarding"></a>Ekleme işlemini doğrulamak için algılama testi çalıştırma

Cihazı ekledikten sonra, bir cihazın hizmete düzgün şekilde eklendiğini doğrulamak için bir algılama testi çalıştırmayı seçebilirsiniz. Daha fazla bilgi için bkz. [Yeni eklenen Uç Nokta için Microsoft Defender cihazında algılama testi çalıştırma](run-detection-test.md).

> [!NOTE]
> Microsoft Defender Virüsten Koruma'nın çalıştırılması gerekmez, ancak önerilir. Birincil uç nokta koruma çözümü başka bir virüsten koruma satıcısı ürünüyse Defender Virüsten Koruma'yı Pasif modda çalıştırabilirsiniz. Pasif modun açık olduğunu yalnızca Uç Nokta için Microsoft Defender algılayıcının (SENSE) çalıştığını doğruladıktan sonra onaylayabilirsiniz.

1. Microsoft Defender Virüsten Koruma'nın yüklü olduğunu doğrulamak için aşağıdaki komutu çalıştırın:

    > [!NOTE]
    > Bu doğrulama adımı yalnızca etkin kötü amaçlı yazılımdan koruma çözümünüz olarak Microsoft Defender Virüsten Koruma kullanıyorsanız gereklidir.

    ```DOS
    sc.exe query Windefend
    ```

    Sonuç 'Belirtilen hizmet yüklü bir hizmet olarak yok' ise virüsten koruma Microsoft Defender yüklemeniz gerekir.

    Windows sunucularınızda Microsoft Defender Virüsten Koruma'yı yapılandırmak ve yönetmek için grup ilkesi kullanma hakkında bilgi için bkz. [Microsoft Defender Virüsten Koruma'yı yapılandırmak ve yönetmek için grup ilkesi ayarlarını kullanma](use-group-policy-microsoft-defender-antivirus.md).

2. Uç Nokta için Microsoft Defender çalıştığını doğrulamak için aşağıdaki komutu çalıştırın:

    ```DOS
    sc.exe query sense
    ```

    Sonuç, çalıştığını göstermelidir. Ekleme ile ilgili sorunlarla karşılaşırsanız bkz. [Ekleme sorunlarını giderme](troubleshoot-onboarding.md).

## <a name="run-a-detection-test"></a>Algılama testi çalıştırma

Sunucunun Uç Nokta hizmeti için Defender'a rapor ettiğini doğrulamak için [Yeni eklenen bir cihazda algılama testi çalıştırma](run-detection-test.md) bölümündeki adımları izleyin.

## <a name="next-steps"></a>Sonraki adımlar

Cihazları hizmete başarıyla ekledikten sonra, Uç Nokta için Microsoft Defender bileşenlerini tek tek yapılandırmanız gerekir. Çeşitli bileşenleri etkinleştirme konusunda rehberlik almak için [Benimseme sırasını](prepare-deployment.md#adoption-order) izleyin.

## <a name="offboard-windows-servers"></a>Windows sunucularını çıkarma

R2, Windows Server 2016, Windows Server (SAC), Windows Server 2019 ve Windows Server 2019 Core sürümünü Windows Server 2012 Windows 10 istemci cihazları için kullanılabilen yöntemle kullanıma sunabilirsiniz.

- [grup ilkesi kullanarak cihazları çıkarma](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [Configuration Manager kullanarak cihazları çıkarma](configure-endpoints-sccm.md#offboard-devices-using-configuration-manager)
- [Mobil Cihaz Yönetimi araçlarını kullanarak cihazları çıkarma](configure-endpoints-mdm.md#offboard-devices-using-mobile-device-management-tools)
- [Yerel betik kullanarak cihazları çıkarma](configure-endpoints-script.md#offboard-devices-using-a-local-script)

Çıkarma sonrasında, Windows Server 2012 R2 ve Windows Server 2016'da birleşik çözüm paketini kaldırmaya devam edebilirsiniz.

Diğer Windows sunucu sürümleri için, Hizmetten Windows sunucularını çıkarmak için iki seçeneğiniz vardır:

- MMA aracısını kaldırma
- Uç Nokta için Defender çalışma alanı yapılandırmasını kaldırma

> [!NOTE]
> Diğer Windows server sürümleri için bu çıkarma yönergeleri, MMA gerektiren Windows Server 2016 ve Windows Server 2012 R2 için önceki Uç Nokta için Microsoft Defender çalıştırıyorsanız da geçerlidir. Yeni birleştirilmiş çözüme geçiş yönergeleri[, Uç Nokta için Microsoft Defender'daki Sunucu geçiş senaryolarında yer alır](/microsoft-365/security/defender-endpoint/server-migration).

## <a name="related-articles"></a>İlgili makaleler

- [Windows'un önceki sürümlerini ekleyin](onboard-downlevel.md)
- [Windows 10 cihazları ekleme](configure-endpoints.md)
- [Windows dışı diğer cihazları ekleyin](configure-endpoints-non-windows.md)
- [Ara sunucu ve internet bağlantısı ayarlarını yapılandırın](configure-proxy-internet.md)
- [Yeni eklenen Uç Nokta için Defender cihazında algılama testi çalıştırma](run-detection-test.md)
- [Uç Nokta için Microsoft Defender ekleme sorunlarını giderme](troubleshoot-onboarding.md)
