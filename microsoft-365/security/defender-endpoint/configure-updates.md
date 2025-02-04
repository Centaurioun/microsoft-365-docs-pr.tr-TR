---
title: Microsoft Defender güncelleştirmeleri için özel bir aşamalı dağıtım işlemi oluşturma
description: Güncelleştirmeler için özel bir aşamalı dağıtım işlemi oluşturmak için desteklenen araçları kullanmayı öğrenin
keywords: güncelleştirme araçları, gpo, intune, mdm, microsoft endpoint manager, ilke, powershell
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
search.appverid: met150
ms.openlocfilehash: 85dbb5458aea474757a33b93e58a1c0b00f4c683
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68174896"
---
# <a name="create-a-custom-gradual-rollout-process-for-microsoft-defender-updates"></a>Microsoft Defender güncelleştirmeleri için özel bir aşamalı dağıtım işlemi oluşturma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

> [!NOTE]
> Bu işlev için virüsten koruma 4.18.2106.X veya daha yeni bir sürüm Microsoft Defender gerekir.

Defender güncelleştirmeleri için kendi özel aşamalı dağıtım işleminizi oluşturmak için grup ilkesi, Microsoft Endpoint Manager ve PowerShell'i kullanabilirsiniz.

Aşağıdaki tabloda, güncelleştirme kanallarını yapılandırmaya yönelik kullanılabilir grup ilkesi ayarları listelemektedir:

|Başlık ayarlama|Açıklama|Konum|
|---|---|---|
|Aşamalı Microsoft Defender aylık platform güncelleştirme dağıtım kanalını seçin|Aylık aşamalı dağıtım sırasında cihazların Microsoft Defender platform güncelleştirmelerini ne zaman alacağını belirtmek için bu ilkeyi etkinleştirin. <p> Beta Kanalı: Bu kanala ayarlanan cihazlar yeni güncelleştirmeleri ilk alan olacak. Sorunları tanımlama ve Microsoft'a raporlamaya katılmak için Beta Kanalı'na tıklayın. Windows Insider Programı'ndaki cihazlar varsayılan olarak bu kanala abonedir. Yalnızca (el ile) test ortamlarında ve sınırlı sayıda cihazda kullanım için. <p> Geçerli Kanal (Önizleme): Bu kanala ayarlanan cihazlara, aylık aşamalı sürüm döngüsü boyunca en erken güncelleştirmeler sunulacaktır. Ön üretim/doğrulama ortamları için önerilir. <p> Geçerli Kanal (Aşamalı): Aylık aşamalı sürüm döngüsünden sonra cihazlara güncelleştirmeler sunulacaktır. Üretim popülasyonunuzun küçük, temsili bir bölümüne (%10) başvurmanız önerilir. <p> Geçerli Kanal (Geniş): Cihazlara yalnızca aşamalı sürüm döngüsü tamamlandıktan sonra güncelleştirmeler sunulacaktır. Üretim popülasyonunuzda (~%10-100) geniş bir cihaz kümesine uygulanması önerilir. <p> Kritik- Zaman Gecikmesi: Cihazlara 48 saatlik gecikmeli güncelleştirmeler sunulacaktır. Yalnızca kritik ortamlar için önerilir. <p>Bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, cihaz aşamalı sürüm döngüsü sırasında otomatik olarak güncel kalır. Çoğu cihaz için uygundur.|Windows Components\Microsoft Defender Virüsten Koruma|
|Aylık Microsoft Defender aşamalı altyapı güncelleştirme dağıtım kanalını seçin|Aylık aşamalı dağıtım sırasında cihazların Microsoft Defender altyapısı güncelleştirmelerini ne zaman alacağını belirtmek için bu ilkeyi etkinleştirin. <p> Beta Kanalı: Bu kanala ayarlanan cihazlar yeni güncelleştirmeleri ilk alan olacak. Sorunları tanımlama ve Microsoft'a raporlamaya katılmak için Beta Kanalı'na tıklayın. Windows Insider Programı'ndaki cihazlar varsayılan olarak bu kanala abonedir. Yalnızca (el ile) test ortamlarında ve sınırlı sayıda cihazda kullanım için. <p> Geçerli Kanal (Önizleme): Bu kanala ayarlanan cihazlara, aylık aşamalı sürüm döngüsü boyunca en erken güncelleştirmeler sunulacaktır. Ön üretim/doğrulama ortamları için önerilir. <p> Geçerli Kanal (Aşamalı): Aylık aşamalı sürüm döngüsünden sonra cihazlara güncelleştirmeler sunulacaktır. Üretim popülasyonunuzun küçük, temsili bir bölümüne (%10) başvurmanız önerilir. <p> Geçerli Kanal (Geniş): Cihazlara yalnızca aşamalı sürüm döngüsü tamamlandıktan sonra güncelleştirmeler sunulacaktır. Üretim popülasyonunuzda (~%10-100) geniş bir cihaz kümesine uygulanması önerilir. <p> Kritik- Zaman Gecikmesi: Cihazlara 48 saatlik gecikmeli güncelleştirmeler sunulacaktır. Yalnızca kritik ortamlar için önerilir.<p> Bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, cihaz aşamalı sürüm döngüsü sırasında otomatik olarak güncel kalır. Çoğu cihaz için uygundur.|Windows Components\Microsoft Defender Virüsten Koruma|
|Aşamalı Microsoft Defender günlük güvenlik bilgileri güncelleştirmeleri dağıtım kanalını seçin|Günlük aşamalı dağıtım sırasında cihazların Microsoft Defender güvenlik bilgileri güncelleştirmelerini ne zaman alacağını belirtmek için bu ilkeyi etkinleştirin. <p> Geçerli Kanal (Aşamalı): Cihazlara sürüm döngüsünden sonra güncelleştirmeler sunulacaktır. Üretim popülasyonunun küçük, temsili bir bölümüne (%~10) uygulanması önerilir. <p> Geçerli Kanal (Geniş): Cihazlara yalnızca aşamalı sürüm döngüsü tamamlandıktan sonra güncelleştirmeler sunulacaktır. Üretim popülasyonunuzda (~%10-100) geniş bir cihaz kümesine uygulanması önerilir. <p>  Bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, cihaz günlük yayın döngüsü sırasında otomatik olarak güncel kalır. Çoğu cihaz için uygundur.|Windows Components\Microsoft Defender Virüsten Koruma|
|Microsoft Defender güncelleştirmelerinin aşamalı dağıtımını devre dışı bırakma|Defender güncelleştirmelerinin aşamalı dağıtımını devre dışı bırakmak için bu ilkeyi etkinleştirin. <p> Geçerli Kanal (Geniş): Bu kanala ayarlanan cihazlar, aşamalı sürüm döngüsü boyunca en son güncelleştirmeler sunulacaktır. Yalnızca sınırlı güncelleştirmeler alan veri merkezi makineleri için en iyi yöntemdir. <p> Not: Bu ayar hem aylık hem de günlük Defender güncelleştirmeleri için geçerlidir ve platform ve altyapı güncelleştirmeleri için önceden yapılandırılmış kanal seçimlerini geçersiz kılar. <p> Bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, platform ve altyapı güncelleştirmeleri için belirli kanallarda aksi belirtilmedikçe cihaz Geçerli Kanal'da (Varsayılan) kalır. Aşamalı yayın döngüsü sırasında otomatik olarak güncel kalın. Çoğu cihaz için uygundur.|Windows Components\Microsoft Defender Antivirus\MpEngine|
|

## <a name="group-policy"></a>Grup İlkesi

> [!NOTE]
> Güncelleştirilmiş bir Defender ADMX şablonu, Windows 10 21H2 sürümüyle birlikte yayımlanacaktır. Yerelleştirilmemiş bir sürüm adresinden https://github.com/microsoft/defender-updatecontrolsindirilebilir.

[grup ilkesi](/windows/win32/srvnodes/group-policy?redirectedfrom=MSDN) kullanarak uç noktalarınızda virüsten koruma Microsoft Defender yapılandırabilir ve yönetebilirsiniz.

Genel olarak, Virüsten Koruma grup ilkesi ayarlarını yapılandırmak veya değiştirmek Microsoft Defender aşağıdaki yordamı kullanabilirsiniz:

1. grup ilkesi yönetim makinenizde **grup ilkesi Yönetim Konsolu'nu** açın, yapılandırmak istediğiniz **grup ilkesi Nesnesine** (GPO) sağ tıklayın ve **Düzenle'ye** tıklayın.

2. grup ilkesi Yönetim Düzenleyicisi'ni kullanarak **Bilgisayar yapılandırması'na** gidin.

3. **Yönetim şablonları'nı** tıklatın.

4. Ağacı **Virüsten Koruma > Microsoft Defender Windows bileşenlerine** genişletin.

5. Yapılandırmak istediğiniz ayarı içeren bölümü (bu konudaki tabloda **Konum** olarak adlandırılır) genişletin, açmak için ayara çift tıklayın ve yapılandırma değişiklikleri yapın.

6. [Güncelleştirilmiş GPO'ları normalde yaptığınız gibi dağıtın](https://msdn.microsoft.com/library/ee663280(v=vs.85).aspx).

## <a name="intune"></a>Intune

Intune'da özel ilke oluşturmak için aşağıdaki bağlantıdaki yönergeleri izleyin:

[Microsoft Intune'da Windows 10 cihazlar için özel ayarlar ekleme - Azure \|Microsoft Docs](/mem/intune/configuration/custom-settings-windows-10)

Aşamalı dağıtım işlemi için kullanılan Defender CSP hakkında daha fazla bilgi için bkz. [Defender CSP](/windows/client-management/mdm/defender-csp).

## <a name="powershell"></a>PowerShell

Aşamalı güncelleştirmelerin dağıtımını `Set-MpPreference` yapılandırmak için cmdlet'ini kullanın.

Aşağıdaki parametreleri kullanın:

```powershell
Set-MpPreference
-PlatformUpdatesChannel Beta|Preview|Staged|Broad|Delayed|NotConfigured
-EngineUpdatesChannel Beta|Preview|Staged|Broad|Delayed|NotConfigured
-DisableGradualRelease 1|0
-SignaturesUpdatesChannel Staged|Broad|NotConfigured
```

Örneğin:

Platform güncelleştirmelerini Beta Kanalından gelecek şekilde yapılandırmak için kullanın `Set-MpPreference -PlatformUpdatesChannel Beta` .

Parametreler ve bunları yapılandırma hakkında daha fazla bilgi için bkz. [Set-MpPreference](/powershell/module/defender/set-mppreference) (Microsoft Defender Virüsten Koruma).

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)
