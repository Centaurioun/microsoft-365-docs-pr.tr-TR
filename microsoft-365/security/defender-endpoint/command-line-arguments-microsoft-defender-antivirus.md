---
title: Microsoft Defender Virüsten Koruma'yi yönetmek için komut satırını kullanma
description: Microsoft Defender Virüsten Koruma taramalarını çalıştırın ve ayrılmış bir komut satırı yardımcı programıyla yeni nesil korumayı yapılandırın.
keywords: windows defender taraması çalıştırma, komut satırından virüsten koruma taraması çalıştırma, komut satırından Windows Defender taraması çalıştırma, mpcmdrun, defender
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 05/24/2021
ms.subservice: mde
ms.topic: how-to
ms.collection: M365-security-compliance
search.appverid: met150
ms.openlocfilehash: c8855237c4864e58d53591e4ae88e84a67495c9d
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67702368"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>microsoft defender virüsten korumayı mpcmdrun.exe komut satırı aracıyla yapılandırma ve yönetme

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma 

**Platform**
- Windows

mpcmdrun.exeayrılmış komut **satırı aracını kullanarak** Microsoft Defender Virüsten Koruma'da çeşitli işlevler gerçekleştirebilirsiniz. Bu yardımcı program, Microsoft Defender Virüsten Koruma görevlerini otomatikleştirmek istediğinizde kullanışlıdır. yardımcı programını içinde `%ProgramFiles%\Windows Defender\MpCmdRun.exe`bulabilirsiniz. Komut isteminden çalıştırın.

> [!TIP]
> Komut isteminin yönetici düzeyinde bir sürümünü açmanız gerekebilir. Başlat menüsünde **Komut İstemi'ni** aradığınızda **Yönetici olarak çalıştır'ı** seçin. Güncelleştirilmiş bir Microsoft Defender kötü amaçlı yazılımdan koruma platformu sürümü çalıştırıyorsanız şu konumdan komutunu çalıştırın `MpCmdRun` : `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>`. Kötü amaçlı yazılımdan koruma platformu hakkında daha fazla bilgi için bkz. [Microsoft Defender Virüsten Koruma güncelleştirmeleri ve temelleri](manage-updates-baselines-microsoft-defender-antivirus.md).

MpCmdRun yardımcı programı aşağıdaki söz dizimini kullanır:

```console
MpCmdRun.exe [command] [-options]
```

İşte bir örnek:

```console
MpCmdRun.exe -Scan -ScanType 2
```

Örneğimizde, MpCmdRun yardımcı programı cihazda tam bir virüsten koruma taraması başlatır.

## <a name="commands"></a>Komut

|Komut|Açıklama|
|---|---|
|`-?`**Veya** `-h`|MpCmdRun aracı için tüm kullanılabilir seçenekleri görüntüler|
|`-Scan [-ScanType [<value>]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]`|Kötü amaçlı yazılımları tarar. **ScanType** değerleri şunlardır:<p>**0** Yapılandırmanıza göre varsayılan<p>**1** Hızlı tarama<p>**2** Tam tarama<p>**3** Dosya ve dizin özel taraması.<p>CpuThrottling, ilke yapılandırmalarına göre çalışır|
|`-Trace [-Grouping #] [-Level #]`|Tanılama izlemeyi başlatır|
|`-GetFiles [-SupportLogLocation <path>]`|Destek bilgilerini toplar. Bkz. "[Tanılama verileri toplama](collect-diagnostic-data.md)"|
|`-GetFilesDiagTrack`|ile `-GetFiles`aynıdır, ancak geçici DiagTrack klasörüne çıkış sağlar|
|`-RemoveDefinitions [-All]`|Yüklü Güvenlik zekasını önceki bir yedek kopyaya veya özgün varsayılan kümeye geri yükler|
|`-RemoveDefinitions [-DynamicSignatures]`|Yalnızca dinamik olarak indirilen Güvenlik zekasını kaldırır|
|`-RemoveDefinitions [-Engine]`|Önceki yüklü altyapıyı geri yükler|
|`-SignatureUpdate [-UNC \|-MMPC]`|Yeni Güvenlik bilgileri güncelleştirmelerini denetler|
|`-Restore  [-ListAll \|[[-Name <name>] [-All] \|[-FilePath <filePath>]] [-Path <path>]]`|Karantinaya alınan öğeleri geri yükler veya listeler|
|`-AddDynamicSignature [-Path]`|Dinamik Güvenlik zekası yükler|
|`-ListAllDynamicSignatures`|Yüklenen dinamik Güvenlik zekasını listeler|
|`-RemoveDynamicSignature [-SignatureSetID]`|Dinamik Güvenlik zekasını kaldırır|
|`-CheckExclusion -path <path>`|Yolun dışlanıp dışlanmadığını denetler|
|`-ValidateMapsConnection`|Ağınızın Microsoft Defender Virüsten Koruma bulut hizmetiyle iletişim kurabildiğini doğrular. Bu komut yalnızca Windows 10, sürüm 1703 veya sonraki sürümlerde çalışır.|

## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>komutları mpcmdrun.exe aracılığıyla çalıştırmayla ilgili yaygın hatalar

Aşağıdaki tabloda, MpCmdRun aracı kullanılırken oluşabilecek yaygın hatalar listelenir.

|Hata iletisi|Olası neden|
|---|---|
|**ValidateMapsConnection başarısız oldu (800106BA)** veya **0x800106BA**|Microsoft Defender Virüsten Koruma hizmeti devre dışı bırakıldı. Hizmeti etkinleştirin ve yeniden deneyin. Microsoft Defender Virüsten Koruma'yı yeniden etkinleştirme konusunda yardıma ihtiyacınız varsa bkz. [Uç noktalarınızda Microsoft Defender Virüsten Koruma'yı yeniden yükleme/etkinleştirme](switch-to-mde-phase-2.md#reinstallenable-microsoft-defender-antivirus-on-your-endpoints).<p> **İpucu**: Windows 10 1909 veya daha eski ve Windows Server 2019 veya daha eski sürümlerinde, hizmet daha önce *Windows Defender Virüsten Koruma* olarak adlandırılıyordu.|
|**0x80070667**|Komutunu 1607 veya daha eski Windows 10 ya da Windows Server 2016 veya daha eski bir bilgisayardan çalıştırıyorsunuz`-ValidateMapsConnection`. Komutu, sürüm 1703 veya daha yeni Windows 10 ya da Windows Server 2019 veya daha yeni bir makineden çalıştırın.|
|**MpCmdRun iç veya dış komut, çalıştırılabilir program veya toplu iş dosyası olarak tanınmaz.**|Araç veya `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` konumundan çalıştırılmalıdır ( `2012.4-0` Platform güncelleştirmeleri Mart ayı dışında aylık olduğundan farklı olabilir)|
|**ValidateMapsConnection MAPS ile bağlantı kuramadı (hr=80070005 httpcode=450)**|Komut yetersiz ayrıcalıklar kullanılarak denendi. Yönetici olarak komut istemini (cmd.exe) kullanın.|
|**ValidateMapsConnection MAPS ile bağlantı kuramadı (hr=80070006 httpcode=451)**|Güvenlik duvarı bağlantıyı engelliyor veya SSL denetimi gerçekleştiriyor.|
|**ValidateMapsConnection MAPS ile bağlantı kuramadı (hr=80004005 httpcode=450)**|Ad çözümleme sorunları gibi ağ ile ilgili olası sorunlar|
|**ValidateMapsConnection MAPS ile bağlantı kuramadı (hr=0x80508015**|Güvenlik duvarı bağlantıyı engelliyor veya SSL denetimi gerçekleştiriyor.|
|**ValidateMapsConnection MAPS ile bağlantı kuramadı (hr=800722F0D**|Güvenlik duvarı bağlantıyı engelliyor veya SSL denetimi gerçekleştiriyor.|
|**ValidateMapsConnection MAPS ile bağlantı kuramadı (hr=80072EE7 httpcode=451)**|Güvenlik duvarı bağlantıyı engelliyor veya SSL denetimi gerçekleştiriyor.|

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Microsoft Defender Virüsten Koruma özelliklerini yapılandırın](configure-microsoft-defender-antivirus-features.md)
- [Microsoft Defender Virüsten Koruma ağ bağlantılarını yapılandırın ve doğrulayın](configure-network-connections-microsoft-defender-antivirus.md)
- [Yönetim ve yapılandırma araçları için başvuru konuları](configuration-management-reference-microsoft-defender-antivirus.md)
