---
title: Uç Nokta için Microsoft Defender için en düşük gereksinimler
description: Cihazları hizmete eklemeye yönelik lisanslama gereksinimlerini ve gereksinimlerini anlama
keywords: minimum gereksinimler, lisanslama, karşılaştırma tablosu
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: dd7ea89a3acb603398a261f0695e3e48f0193a15
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67700014"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender için en düşük gereksinimler

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-minreqs-abovefoldlink)

Cihazları hizmete eklemek için bazı minimum gereksinimler vardır. Cihazları hizmete eklemek için lisanslama, donanım ve yazılım gereksinimleri ve diğer yapılandırma ayarları hakkında bilgi edinin.

> [!TIP]
>
> - Bu makalede, Uç Nokta için Microsoft Defender Plan 2 için en düşük gereksinimler açıklanmaktadır. Uç Nokta Planı 1 için Defender hakkında bilgi arıyorsanız bkz. [Uç Nokta Planı 1 için Defender gereksinimleri](mde-p1-setup-configuration.md#review-the-requirements).
> - Uç Nokta için Defender: Uç Nokta [için Defender Teknoloji Topluluğu'ndaki](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced) en son geliştirmeler hakkında bilgi edinin.
> - Uç Nokta için Defender, son MITRE değerlendirmesinde sektör lideri optik ve algılama özelliklerini göstermiştir. Okuma: [MITRE ATT&CK tabanlı değerlendirmeden alınan içgörüler](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

## <a name="licensing-requirements"></a>Lisans gereksinimleri

[Uç Nokta Plan 1 ve Plan 2 için Defender'ın](defender-endpoint-plan-1-2.md) tek başına sürümleri sunucu lisanslarını içermez. Sunucuları bu planlara eklemek için Bulut için Defender teklifinin bir parçası olarak Sunucular için [Defender](/azure/defender-for-cloud/defender-for-cloud-introduction) Plan 1 veya Plan 2 gerekir. Daha fazla bilgi edinmek için bkz [. Sunucular için Microsoft Defender'a](/azure/defender-for-cloud/defender-for-servers-introduction) genel bakış.

Uç Nokta için Microsoft Defender için lisanslama gereksinimleri hakkında bilgi için bkz. [lisanslama bilgileri Uç Nokta için Microsoft Defender](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-defender-for-endpoint).

Ayrıntılı lisanslama bilgileri için [Ürün Koşulları sitesine](https://www.microsoft.com/licensing/terms/) bakın ve hüküm ve koşullar hakkında daha fazla bilgi edinmek için hesap ekibinizle birlikte çalışın.

Windows sürümlerindeki özellikler dizisi hakkında daha fazla bilgi için bkz. [Windows sürümlerini karşılaştırma](https://www.microsoft.com/windowsforbusiness/compare).
## <a name="browser-requirements"></a>Tarayıcı gereksinimleri

Uç Nokta için Defender'a erişim, aşağıdaki tarayıcıları destekleyen bir tarayıcı aracılığıyla yapılır:

- Microsoft Edge
- Google Chrome

> [!NOTE]
> Diğer tarayıcılar çalışabilir ancak desteklenen tarayıcılar söz konusu tarayıcılardır.

## <a name="hardware-and-software-requirements"></a>Donanım ve yazılım gereksinimleri

### <a name="supported-windows-versions"></a>Desteklenen Windows sürümleri

- Windows 11 Enterprise
- Windows 11 Education
- Windows 11 Pro
- Windows 11 Pro Education
- Windows 10 Enterprise
- [Windows 10 Enterprise LTSC 2016 (veya üzeri)](/windows/whats-new/ltsc/)
- Windows 10 Enterprise IoT

    >[!NOTE]
    >Windows 10 IoT Enterprise, Uç Nokta için Microsoft Defender'de desteklenen bir işletim sistemi olsa da ve OEM'lerin/ODM'lerin ürün veya çözümlerinin bir parçası olarak dağıtabilmelerini sağlarken, müşterilerin konak tabanlı yüklü yazılım ve desteklenebilirlik konusunda OEM/ODM'nin yönergelerini izlemesi gerekir.

- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows 8.1 Enterprise
- Windows 8.1 Pro
- Windows 7 SP1 Enterprise ([Destek için ESU gerekir](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)
- Windows 7 SP1 Pro ([Destek için ESU gerekir](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)
- Windows server
  - Windows Server 2008 R2 SP1 ([Destek için ESU gerekir](/windows-server/get-started/extended-security-updates-deploy))
  - Windows Server 2012 R2
  - Windows Server 2016
  - Windows Server, sürüm 1803 veya üzeri
  - Windows Server 2019
  - Windows Server 2022
- Windows Sanal Masaüstü
- Windows 365

Ağınızdaki cihazların bu sürümlerden birini çalıştırıyor olması gerekir.

Cihazlarda Uç Nokta için Defender'ın donanım gereksinimleri desteklenen sürümler için aynıdır.

> Çekirdekler: 2 minimum, 4 tercih edilen Bellek: 1 GB en az, 4 tercih edilir

Desteklenen Windows 10 sürümleri hakkında daha fazla bilgi için Windows 10 [sürüm bilgilerine](/windows/release-health/release-information) bakın.

> [!NOTE]
> - Windows'un mobil sürümlerini (Windows CE ve Windows 10 Mobile gibi) çalıştıran uç noktalar desteklenmez.
>
> - Windows 10 Enterprise 2016 LTSB çalıştıran Sanal Makineler, Microsoft dışı sanallaştırma platformlarında çalıştırılırsa performans sorunlarıyla karşılaşabilir.
>
> - Sanal ortamlar için Windows 10 Enterprise LTSC 2019 veya üzerini kullanmanızı öneririz.
>
> - [Uç Nokta Plan 1 ve Plan 2 için Defender'ın](defender-endpoint-plan-1-2.md) tek başına sürümleri sunucu lisanslarını içermez. Sunucuları bu planlara eklemek için Bulut için Defender teklifinin bir parçası olarak Sunucular için [Defender](/azure/defender-for-cloud/defender-for-cloud-introduction) Plan 1 veya Plan 2 gerekir. Daha fazla bilgi edinmek için. Bkz [. Sunucular için Microsoft Defender'a genel bakış](/azure/defender-for-cloud/defender-for-servers-introduction).

Bileşenler Microsoft Windows işletim sistemlerinde güncel olduğunda, Uç Nokta için Microsoft Defender destek ilgili işletim sisteminin yaşam döngüsünü izler. Daha fazla bilgi için bkz [. Yaşam Döngüsü SSS](/lifecycle/faq/general-lifecycle). Yeni özellikler veya özellikler genellikle yalnızca yaşam döngülerinin sonuna henüz ulaşmamış işletim sistemlerinde sağlanır. Güvenlik bilgileri güncelleştirmeleri (tanım ve altyapı güncelleştirmeleri) ve algılama mantığı en azından aşağıdakilere kadar sağlanmaya devam edecektir:

- [Destek sonu tarihi](/lifecycle/products/) (Genişletilmiş Güvenlik Güncelleştirmeler (ESU) programı olmayan işletim sistemleri için).
- [ESU sonu tarihi (ESU](/lifecycle/faq/extended-security-updates) programı olan işletim sistemleri için).

### <a name="other-supported-operating-systems"></a>Desteklenen diğer işletim sistemleri

- [Android](microsoft-defender-endpoint-android.md)
- [iOS](microsoft-defender-endpoint-ios.md)
- [Linux](microsoft-defender-endpoint-linux.md)
- [macOS](microsoft-defender-endpoint-mac.md)

> [!NOTE]
> Tümleştirmenin çalışması için Android, iOS ve macOS'un Linux dağıtımlarının ve sürümlerinin Uç Nokta için Defender ile uyumlu olduğunu onaylamanız gerekir.

### <a name="network-and-data-storage-and-configuration-requirements"></a>Ağ ve veri depolama ve yapılandırma gereksinimleri

Ekleme sihirbazını ilk kez çalıştırdığınızda, Uç Nokta için Microsoft Defender ile ilgili bilgilerinizin nerede depolandığını seçmeniz gerekir: Avrupa Birliği, Birleşik Krallık veya Birleşik Devletler veri merkezinde.

> [!NOTE]
>
> - İlk kurulumdan sonra veri depolama konumunuzu değiştiremezsiniz.
> - Microsoft'un verilerinizi nerede ve nasıl depoladığı hakkında daha fazla bilgi için [Uç Nokta için Microsoft Defender veri depolama ve gizlilik](data-storage-privacy.md) konularını gözden geçirin.

### <a name="diagnostic-data-settings"></a>Tanılama veri ayarları

> [!NOTE]
> Uç Nokta için Microsoft Defender etkin olduğu sürece belirli bir tanılama düzeyi gerektirmez.

Tanılama veri hizmetinin kuruluşunuzdaki tüm cihazlarda etkinleştirildiğinden emin olun.
Varsayılan olarak, bu hizmet etkindir. Algılayıcı verilerini onlardan aldığınızdan emin olmak için kontrol etmek iyi bir uygulamadır.

#### <a name="use-the-command-line-to-check-the-windows-diagnostic-data-service-startup-type"></a>Windows tanılama veri hizmeti başlangıç türünü denetlemek için komut satırını kullanın

1. Cihazda yükseltilmiş bir komut satırı istemi açın:
   1. **Başlangıç'a** gidin ve **cmd** yazın.
   2. **Komut istemi'ne** sağ tıklayın ve **Yönetici olarak çalıştır'ı** seçin.

2. Aşağıdaki komutu girin ve **Enter tuşuna** basın:

   ```console
   sc qc diagtrack
   ```

   Hizmet etkinse sonuç aşağıdaki ekran görüntüsüne benzer olmalıdır:

   :::image type="content" source="images/windefatp-sc-qc-diagtrack.png" alt-text="Diagtrack için sc sorgu komutunun sonucu" lightbox="images/windefatp-sc-qc-diagtrack.png":::

START_TYPE **AUTO_START** olarak ayarlı değilse hizmeti otomatik olarak başlatacak şekilde ayarlamanız gerekir.

#### <a name="use-the-command-line-to-set-the-windows-diagnostic-data-service-to-automatically-start"></a>Windows tanılama veri hizmetini otomatik olarak başlatacak şekilde ayarlamak için komut satırını kullanın

1. Uç noktada yükseltilmiş bir komut satırı istemi açın:
    1. **Başlangıç'a** gidin ve **cmd** yazın.
    2. **Komut istemi'ne** sağ tıklayın ve **Yönetici olarak çalıştır'ı** seçin.

2. Aşağıdaki komutu girin ve **Enter tuşuna** basın:

    ```console
    sc config diagtrack start=auto
    ```

3. Başarılı iletisi görüntülenir. Aşağıdaki komutu girerek değişikliği doğrulayın ve **Enter tuşuna** basın:

    ```console
    sc qc diagtrack
    ```

#### <a name="internet-connectivity"></a>İnternet bağlantısı

Cihazlarda İnternet bağlantısı doğrudan veya ara sunucu aracılığıyla gereklidir.

Uç Nokta için Defender algılayıcısı, Uç Nokta için Defender bulut hizmetiyle iletişim kurmak ve siber verileri raporlamak için günlük ortalama 5 MB bant genişliği kullanabilir. Dosya yüklemeleri ve araştırma paketi koleksiyonu gibi tek seferlik etkinlikler bu günlük ortalama bant genişliğine dahil değildir.

Ek ara sunucu yapılandırma ayarları hakkında daha fazla bilgi için bkz. [Cihaz ara sunucusu ve İnternet bağlantı ayarlarını yapılandırma](configure-proxy-internet.md).

Cihazları eklemeden önce tanılama veri hizmetinin etkinleştirilmesi gerekir. Hizmet, Windows 10 ve Windows 11'da varsayılan olarak etkindir.

## <a name="microsoft-defender-antivirus-configuration-requirement"></a>Microsoft Defender Virüsten Koruma yapılandırma gereksinimi

Uç Nokta için Defender aracısı, Microsoft Defender Virüsten Koruma'nın dosyaları tarayabilmesine ve bunlar hakkında bilgi sağlamasına bağlıdır.

Microsoft Defender Virüsten Koruma'nın etkin kötü amaçlı yazılımdan koruma yazılımı olup olmadığına bakılmaksızın Uç Nokta için Defender cihazlarında Güvenlik bilgileri güncelleştirmelerini yapılandırın. Daha fazla bilgi için bkz [. Microsoft Defender Virüsten Koruma güncelleştirmelerini yönetme ve temelleri uygulama](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).

Microsoft Defender Virüsten Koruma kuruluşunuzdaki etkin kötü amaçlı yazılımdan koruma yazılımı değilse ve Uç Nokta için Defender hizmetini kullandığınızda, Microsoft Defender Virüsten Koruma pasif moda geçer.

Kuruluşunuz Microsoft Defender Virüsten Koruma'yı grup ilkesi veya diğer yöntemler aracılığıyla kapattıysa, eklenen cihazlar bu grup ilkesi dışında tutulmalıdır.

Sunucuları ekliiyorsanız ve Microsoft Defender Virüsten Koruma sunucularınızdaki etkin kötü amaçlı yazılımdan koruma yazılımı değilse, Microsoft Defender Virüsten Koruma'nın pasif moda geçmek için yapılandırılması veya kaldırılması gerekir. Yapılandırma sunucu sürümüne bağlıdır. Daha fazla bilgi için bkz. [Microsoft Defender Virüsten Koruma uyumluluğu](microsoft-defender-antivirus-compatibility.md).

> [!NOTE]
> Normal grup ilkeniz Kurcalama Koruması için geçerli değildir ve Kurcalama Koruması açıkken Microsoft Defender Virüsten Koruma ayarlarında yapılan değişiklikler yoksayılır.

## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a>Microsoft Defender Virüsten Koruma Erken Başlatma Kötü Amaçlı Yazılımdan Koruma (ELAM) sürücüsü etkinleştirildi

Cihazlarınızda birincil kötü amaçlı yazılımdan koruma ürünü olarak Microsoft Defender Virüsten Koruma çalıştırıyorsanız, Uç Nokta için Defender aracısı başarıyla eklenecektir.

Üçüncü taraf kötü amaçlı yazılımdan koruma istemcisi çalıştırıyorsanız ve Mobil Cihaz Yönetimi çözümleri veya Microsoft Endpoint Manager (geçerli dal) kullanıyorsanız, Microsoft Defender Virüsten Koruma ELAM sürücüsünün etkinleştirildiğinden emin olmanız gerekir. Daha fazla bilgi için bkz. [Microsoft Defender Virüsten Koruma'nın ilke tarafından devre dışı bırakılmadığından emin olun](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).

## <a name="related-topics"></a>İlgili konular

- [Uç Nokta için Microsoft Defender dağıtımı ayarlama](production-deployment.md)
- [Cihazları ekleme](onboard-configure.md)
