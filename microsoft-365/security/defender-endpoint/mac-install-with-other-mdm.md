---
title: Mac'te Uç Nokta için Microsoft Defender için farklı bir Mobil Cihaz Yönetimi (MDM) sistemiyle dağıtım
description: Mac'e diğer yönetim çözümlerine Uç Nokta için Microsoft Defender yükleyin.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, mac, installation, deploy, macos, catalina, mojave, high sierra
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 81947f0bfcb42ea3d3c803994c1144e92c856c87
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67704556"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-on-macos"></a>macOS'ta Uç Nokta için Microsoft Defender için farklı bir Mobil Cihaz Yönetimi (MDM) sistemiyle dağıtım

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a>Önkoşullar ve sistem gereksinimleri

Başlamadan önce, geçerli yazılım sürümü için önkoşulların ve sistem gereksinimlerinin açıklaması için [macOS'ta ana Uç Nokta için Microsoft Defender sayfasına](microsoft-defender-endpoint-mac.md) bakın.


## <a name="approach"></a>Yaklaşım

> [!CAUTION]

> Şu anda Microsoft, macOS üzerinde Uç Nokta için Microsoft Defender dağıtımı ve yönetimi için yalnızca Intune ve JAMF'yi resmi olarak desteklemektedir. Microsoft, aşağıda verilen bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

Kuruluşunuz resmi olarak desteklenmeyen bir Mobil Cihaz Yönetimi (MDM) çözümü kullanıyorsa bu, macOS üzerinde Uç Nokta için Microsoft Defender dağıtamadığınız veya çalıştıramadığınız anlamına gelmez.

macOS'ta Uç Nokta için Microsoft Defender satıcıya özgü özelliklere bağlı değildir. Aşağıdaki özellikleri destekleyen herhangi bir MDM çözümüyle kullanılabilir:

- Yönetilen cihazlara macOS .pkg dağıtın.
- Yönetilen cihazlara macOS sistem yapılandırma profillerini dağıtın.
- Yönetilen cihazlarda rastgele yönetici tarafından yapılandırılmış bir araç/betik çalıştırın.

Modern MDM çözümlerinin çoğu bu özellikleri içerir, ancak bunları farklı şekilde adlandırabilirler.

Ancak, uç nokta için Defender'ı önceki listeden son gereksinim olmadan dağıtabilirsiniz:

- Durumu merkezi bir şekilde toplayamazsınız.
- Uç Nokta için Defender'ı kaldırmaya karar verirseniz istemci cihazında yönetici olarak yerel olarak oturum açmanız gerekir.

## <a name="deployment"></a>Dağıtım

Çoğu MDM çözümü, benzer terminolojiye sahip macOS cihazlarını yönetmek için aynı modeli kullanır. [ŞABLON olarak JAMF tabanlı dağıtımı](mac-install-with-jamf.md) kullanın.

### <a name="package"></a>Paket

Yükleme paketi (wdav.pkg) [Microsoft 365 Defender portalından](mac-install-with-jamf.md) indirilmiş [olarak gerekli bir uygulama](mac-install-with-jamf.md) paketinin dağıtımını yapılandırın.

Paketi kuruluşunuza dağıtmak için MDM çözümünüzle ilişkili yönergeleri kullanın.

### <a name="license-settings"></a>Lisans ayarları

[Bir sistem yapılandırma profili](mac-install-with-jamf.md) ayarlayın. 

macOS'ta Uç Nokta için Microsoft Defender macOS'un bir parçası olmadığından MDM çözümünüz buna "Özel Ayarlar Profili" gibi bir ad verebilir.

[Microsoft 365 Defender portalından](mac-install-with-jamf.md) indirilen bir ekleme paketinden ayıklanabilen jamf/WindowsDefenderATPOnboarding.plist özellik listesini kullanın.
Sisteminiz XML biçiminde rastgele bir özellik listesini destekleyemeyebilir. Bu durumda jamf/WindowsDefenderATPOnboarding.plist dosyasını olduğu gibi karşıya yükleyebilirsiniz.
Alternatif olarak, önce özellik listesini farklı bir biçime dönüştürmeniz gerekebilir.

Genellikle özel profilinizin kimliği, adı veya etki alanı özniteliği vardır. Bu değer için tam olarak "com.microsoft.wdav.atp" kullanmanız gerekir.
MDM, ayarlar dosyasını bir istemci cihazında **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** dosyasına dağıtmak için kullanır ve Uç Nokta için Defender da ekleme bilgilerini yüklemek için bu dosyayı kullanır.

### <a name="kernel-extension-policy"></a>Çekirdek uzantısı ilkesi

KEXT veya çekirdek uzantısı ilkesi ayarlayın. Microsoft tarafından sağlanan çekirdek uzantılarına izin vermek için **UBF8T346G9** ekip tanımlayıcısını kullanın.

> [!CAUTION]
> Ortamınız Apple Silicon (M1) cihazlarından oluşuyorsa, bu makineler KEXT ilkelerine sahip yapılandırma profillerini almamalıdır.
> Apple bu makinelerde KEXT'yi desteklemez, bu tür bir profilin dağıtımı M1 makinelerinde başarısız olur.

### <a name="system-extension-policy"></a>Sistem uzantısı ilkesi

Bir sistem uzantısı ilkesi ayarlayın. **UBF8T346G9** takım tanımlayıcısını kullanın ve aşağıdaki paket tanımlayıcılarını onaylayın:

- com.microsoft.wdav.epsext
- com.microsoft.wdav.netext

### <a name="full-disk-access-policy"></a>Tam disk erişim ilkesi

Aşağıdaki bileşenlere Tam Disk Erişimi verin:

- Uç Nokta için Microsoft Defender
    - Tanımlayıcı: `com.microsoft.wdav`
    - Tanımlayıcı Türü: Paket Kimliği
    - Kod Gereksinimi: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

- Uç Nokta için Microsoft Defender Güvenlik Uzantısı
    - Tanımlayıcı: `com.microsoft.wdav.epsext`
    - Tanımlayıcı Türü: Paket Kimliği
    - Kod Gereksinimi: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

### <a name="network-extension-policy"></a>Ağ uzantısı ilkesi

Uç Nokta Algılama ve Yanıt özelliklerinin bir parçası olarak macOS'ta Uç Nokta için Microsoft Defender yuva trafiğini inceler ve bu bilgileri Microsoft 365 Defender portalına bildirir. Aşağıdaki ilke, ağ uzantısının bu işlevi gerçekleştirmesine izin verir.

- Filtre türü: Eklenti
- Eklenti paketi tanımlayıcısı: `com.microsoft.wdav`
- Filtre veri sağlayıcısı paket tanımlayıcısı: `com.microsoft.wdav.netext`
- Filtre veri sağlayıcısı belirlenmiş gereksinimi: `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
- Filtre yuvaları: `true`

## <a name="check-installation-status"></a>Yükleme durumunu denetleme

Ekleme durumunu denetlemek için bir istemci cihazında [Uç Nokta için Microsoft Defender](mac-install-with-jamf.md) çalıştırın.
