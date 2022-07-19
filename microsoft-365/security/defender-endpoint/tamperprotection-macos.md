---
title: MacOS güvenlik ayarlarını kurcalama koruması ile koruma
description: Kötü amaçlı uygulamaların önemli macOS güvenlik ayarlarını değiştirmesini önlemek için kurcalama koruması kullanın.
keywords: macos, kurcalama koruması, güvenlik ayarları, kötü amaçlı yazılım
ms.prod: m365-security
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 45a30d02992d3128ab1520c24927fb43c1180cf8
ms.sourcegitcommit: 1734c95ce72d9c8af695cb4b49b1e40d921a1fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/07/2022
ms.locfileid: "66862303"
---
# <a name="protect-macos-security-settings-with-tamper-protection"></a>MacOS güvenlik ayarlarını kurcalama koruması ile koruma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-rbac-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]


macOS'ta kurcalama koruması, güvenlik ayarlarında istenmeyen değişikliklerin yetkisiz kullanıcılar tarafından yapılmasını önlemeye yardımcı olur. Kurcalama koruması, macOS'ta Uç Nokta için Microsoft Defender yetkisiz olarak kaldırılmasını önlemeye yardımcı olur. Bu özellik ayrıca önemli güvenlik dosyalarının, işlemlerin ve yapılandırma ayarlarının değiştirilmesine yardımcı olur.

Kurcalama korumasını aşağıdaki modlarda ayarlayabilirsiniz:

|Konu|Açıklama|
|---|---|
|Devre dışı|Kurcalama koruması tamamen kapalıdır (yüklemeden sonra varsayılan mod budur)|
|Denetim|Kurcalama işlemleri günlüğe kaydedilir, ancak engellenmez|
|Engelle|Kurcalama koruması açık, kurcalama işlemleri engelleniyor|

Kurcalama koruması denetim veya blok moduna ayarlandığında aşağıdaki sonuçları bekleyebilirsiniz:

**Denetim modu**:

- Uç Nokta için Defender aracısını kaldırma eylemleri günlüğe kaydedilir (denetlendi)
- Uç Nokta için Defender dosyalarının düzenlenmesi/değiştirilmesi günlüğe kaydedilir (denetlendi)
- Uç Nokta için Defender konumu altında yeni dosyaların oluşturulması günlüğe kaydedilir (denetlendi)
- Uç Nokta için Defender dosyalarını silme işlemi günlüğe kaydedildi (denetlendi)
- Uç Nokta için Defender dosyalarının yeniden adlandırılması günlüğe kaydedilir (denetlendi)

**Blok modu**:

- Uç Nokta için Defender aracısını kaldırma eylemleri engellendi
- Uç Nokta için Defender dosyalarını düzenleme/değiştirme engellendi
- Uç Nokta için Defender konumu altında yeni dosyaların oluşturulması engellendi
- Uç Nokta için Defender dosyalarının silinmesi engellendi
- Uç Nokta için Defender dosyalarının yeniden adlandırılması engellendi
- Aracının başarısız olmasını durdurmak için komutlar

Engellenen eyleme yanıt olarak bir sistem iletisi örneği aşağıda verilmiştir:

![İşlemin engellenen görüntüsü](images/operation-blocked.png)

Mod adını zorlama düzeyi olarak sağlayarak kurcalama koruma modunu yapılandırabilirsiniz.

> [!NOTE]
>
> - Mod değişikliği hemen uygulanır.
> - İlk yapılandırma sırasında JAMF kullandıysanız, JAMF kullanarak yapılandırmayı da güncelleştirmeniz gerekir.

## <a name="before-you-begin"></a>Başlamadan önce

- Desteklenen macOS sürümleri: Monterey (12), Big Sur (11), Catalina (10.15+).
- Uç Nokta için Defender için gereken en düşük sürüm: 101.70.19.
- Kurcalama Koruması özelliği önizleme aşamasındayken Üretim dışı bir güncelleştirme kanalında ([Önizleme veya Beta](/deployoffice/office-insider/deploy/microsoft-autoupdate)) olmanız gerekir. Üretim kanalındaysanız, yapılandırılmış kurcalama koruma modu yoksayılır.

**Kesinlikle önerilen ayarlar:**

- Sistem Bütünlüğü Koruması (SIP) etkin. Daha fazla bilgi için bkz. [Sistem Bütünlüğü Korumasını Devre Dışı Bırakma ve Etkinleştirme](https://developer.apple.com/documentation/security/disabling_and_enabling_system_integrity_protection).
- Uç Nokta için Microsoft Defender yapılandırmak için Mobil cihaz yönetimi (MDM) aracını kullanın.

## <a name="configure-tamper-protection-on-macos-devices"></a>macOS cihazlarda kurcalama korumasını yapılandırma

Kurcalama korumasını yapılandırmanın birkaç yolu vardır:

- [El ile yapılandırma](#manual-configuration)
- [JAMF](#jamf)
- [Intune](#intune)

### <a name="before-you-begin"></a>Başlamadan önce

Durum değişikliğini gözlemlemek için "tamper_protection" öğesinin "devre dışı" veya "denetim" olarak ayarlandığını doğrulayın.
Ayrıca, "release_ring" öğesinin "Üretim" raporlamadığından emin olun.

```bash
mdatp health
```

```console
healthy                                     : true
health_issues                               : []
licensed                                    : true
engine_version                              : "1.1.19300.3"
app_version                                 : "101.70.19"
org_id                                      : "..."
log_level                                   : "info"
machine_guid                                : "..."
release_ring                                : "InsiderFast"
product_expiration                          : Dec 29, 2022 at 09:48:37 PM
cloud_enabled                               : true
cloud_automatic_sample_submission_consent   : "safe"
cloud_diagnostic_enabled                    : false
passive_mode_enabled                        : false
real_time_protection_enabled                : true
real_time_protection_available              : true
real_time_protection_subsystem              : "endpoint_security_extension"
network_events_subsystem                    : "network_filter_extension"
device_control_enforcement_level            : "audit"
tamper_protection                           : "audit"
automatic_definition_update_enabled         : true
definitions_updated                         : Jul 06, 2022 at 01:57:03 PM
definitions_updated_minutes_ago             : 5
definitions_version                         : "1.369.896.0"
definitions_status                          : "up_to_date"
edr_early_preview_enabled                   : "disabled"
edr_device_tags                             : []
edr_group_ids                               : ""
edr_configuration_version                   : "20.199999.main.2022.07.05.02-ac10b0623fd381e28133debe14b39bb2dc5b61af"
edr_machine_id                              : "..."
conflicting_applications                    : []
network_protection_status                   : "stopped"
data_loss_prevention_status                 : "disabled"
full_disk_access_enabled                    : true
```

### <a name="manual-configuration"></a>El ile yapılandırma

1. Aşağıdaki komutu kullanın:

   ```console
   sudo mdatp config tamper-protection enforcement-level --value block
   ```

   ![El ile yapılandırma komutunun görüntüsü](images/manual-config-cmd.png)

   > [!NOTE]
   > Kurcalama korumasını etkinleştirmek için el ile yapılandırma kullanıyorsanız, kurcalama korumasını istediğiniz zaman el ile de devre dışı bırakabilirsiniz. Örneğin, Sistem Tercihleri'nde Defender'dan Tam Disk Erişimini el ile iptal edebilirsiniz. Yerel yöneticinin bunu yapmasını önlemek için el ile yapılandırma yerine MDM kullanmalısınız.

2. Sonucu doğrulayın.

  ```bash
  mdatp health
  ```

  ```console
  healthy                                     : true
  health_issues                               : []
  licensed                                    : true
  engine_version                              : "1.1.19300.3"
  app_version                                 : "101.70.19"
  org_id                                      : "..."
  log_level                                   : "info"
  machine_guid                                : "..."
  release_ring                                : "InsiderFast"
  product_expiration                          : Dec 29, 2022 at 09:48:37 PM
  cloud_enabled                               : true
  cloud_automatic_sample_submission_consent   : "safe"
  cloud_diagnostic_enabled                    : false
  passive_mode_enabled                        : false
  real_time_protection_enabled                : true
  real_time_protection_available              : true
  real_time_protection_subsystem              : "endpoint_security_extension"
  network_events_subsystem                    : "network_filter_extension"
  device_control_enforcement_level            : "audit"
  tamper_protection                           : "block"
  automatic_definition_update_enabled         : true
  definitions_updated                         : Jul 06, 2022 at 01:57:03 PM
  definitions_updated_minutes_ago             : 5
  definitions_version                         : "1.369.896.0"
  definitions_status                          : "up_to_date"
  edr_early_preview_enabled                   : "disabled"
  edr_device_tags                             : []
  edr_group_ids                               : ""
  edr_configuration_version                   : "20.199999.main.2022.07.05.02-ac10b0623fd381e28133debe14b39bb2dc5b61af"
  edr_machine_id                              : "..."
  conflicting_applications                    : []
  network_protection_status                   : "stopped"
  data_loss_prevention_status                 : "disabled"
  full_disk_access_enabled                    : true
  ```

"tamper_protection" öğesinin artık "engelle" olarak ayarlandığına dikkat edin.

### <a name="jamf"></a>JAMF

Aşağıdaki ayarları ekleyerek Uç Nokta için Microsoft Defender [yapılandırma profilinde](mac-jamfpro-policies.md) kurcalama koruma modunu yapılandırın:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
  <dict>
    <key>tamperProtection</key>
    <dict>
      <key>enforcementLevel</key>
      <string>block</string>
    </dict>
  </dict>
</plist>
```

> [!NOTE]
> Uç Nokta için Microsoft Defender için zaten bir yapılandırma profiliniz varsa, buna ayarlar *eklemeniz* gerekir. İkinci bir yapılandırma profili oluşturmanız gerekmez.

### <a name="intune"></a>Intune

Intune aracılığıyla kurcalama korumasını yapılandırmak için belgelenmiş Intune profil örneğini izleyin. Daha fazla bilgi için bkz. [macOS'ta Uç Nokta için Microsoft Defender için tercihleri ayarlama](mac-preferences.md).

Intune profilinize aşağıdaki yapılandırmayı ekleyin:

> [!NOTE]
> Intune yapılandırması için, Kurcalama koruma yapılandırmasını eklemek için yeni bir profil yapılandırma dosyası oluşturabilir veya bu parametreleri mevcut yapılandırmaya ekleyebilirsiniz.

```xml
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>tamperProtection</key>
                <dict>
                             <key>enforcementLevel</key>
                             <string>block</string>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

Aşağıdaki komutu çalıştırarak kurcalama koruma durumunu denetleyin:

`mdatp health --field tamper_protection`

Kurcalama koruması açıksa sonuç "engelle" ifadesini gösterir:

![Blok modunda kurcalama koruması görüntüsü](images/tp-block-mode.png)

Ayrıca tam `mdatp health` olarak çalıştırabilir ve çıkışta "tamper_protection" öğesini arayabilirsiniz

## <a name="verify-tamper-protection-preventive-capabilities"></a>Kurcalama koruması önleyici özelliklerini doğrulama

Kurcalama korumasının açık olduğunu çeşitli yollarla doğrulayabilirsiniz.

### <a name="verify-block-mode"></a>Blok modunu doğrulama

Microsoft 365 Defender portalında kurcalama uyarısı oluşturulur

![Microsoft 365 Defender portalında tetiklenen kurcalama uyarısının görüntüsü](images/tampering-sensor-portal.png)

### <a name="verify-block-mode-and-audit-modes"></a>Blok modunu ve denetim modlarını doğrulama

- Gelişmiş avcılık'ı kullanarak, kurcalama uyarılarının göründüğünü görürsünüz
- Kurcalama olayları yerel cihaz günlüklerinde bulunabilir: `sudo grep -F '[{tamperProtection}]' /Library/Logs/Microsoft/mdatp/microsoft_defender_core.log`

![Kurcalama koruma günlüğünün görüntüsü](images/tamper-protection-log.png)

### <a name="diy-scenarios"></a>DIY senaryoları

- Kurcalama koruması "engelle" olarak ayarlandığında Uç Nokta için Defender'ı kaldırmak için farklı yöntemler deneme. Örneğin, uygulama kutucuğunu çöp kutusuna sürükleyin veya komut satırını kullanarak kurcalama korumasını kaldırın.
- Uç Nokta için Defender işlemini (sonlandırma) durdurmayı deneyin.
- Uç Nokta için Defender dosyalarını silmeyi, yeniden adlandırmayı, değiştirmeyi, taşımayı deneyin (kötü amaçlı bir kullanıcının yapacağına benzer şekilde): Örneğin:

  - /Applications/Microsoft Defender ATP.app/
  - /Library/LaunchDaemons/com.microsoft.fresno.plist
  - /Library/LaunchDaemons/com.microsoft.fresno.uninstall.plist
  - /Library/LaunchAgents/com.microsoft.wdav.tray.plist
  - /Library/Yönetilen Tercihler/com.microsoft.wdav.ext.plist
  - /Library/Yönetilen Tercihler/mdatp_managed.json
  - /Library/Yönetilen Tercihler/com.microsoft.wdav.atp.plist
  - /Library/Yönetilen Tercihler/com.microsoft.wdav.atp.offboarding.plist
  - /usr/local/bin/mdatp

## <a name="turning-off-tamper-protection"></a>Kurcalama korumasını kapatma

Aşağıdaki yöntemlerden herhangi birini kullanarak kurcalama korumasını kapatabilirsiniz.

### <a name="manual-configuration"></a>El ile yapılandırma

Aşağıdaki komutu kullanın:

```console
sudo mdatp config tamper-protection enforcement-level - -value disabled
```

## <a name="jamf"></a>JAMF
`enforcementLevel` Yapılandırma profilinizde değeri "devre dışı" olarak değiştirin ve makineye gönderin:

```console
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
  <dict>
    <key>tamperProtection</key>
    <dict>
      <key>enforcementLevel</key>
      <string>disabled</string>
    </dict>
  </dict>
</plist>

```

### <a name="intune"></a>Intune
Intune profilinize aşağıdaki yapılandırmayı ekleyin:

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>tamperProtection</key>
                <dict>
                             <key>enforcementLevel</key>
                             <string>disabled</string>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="troubleshooting-configuration-issues"></a>Yapılandırma sorunlarını giderme

### <a name="issue-tamper-protection-is-reported-as-disabled"></a>Sorun: Kurcalama koruması devre dışı olarak bildiriliyor

Komut `mdatp health` çalıştırılıyorsa, siz etkinleştirmiş olsanız ve eklemeden bu yana bir saatten fazla zaman geçmiş olsa bile, kurcalama korumasının devre dışı bırakıldığını bildirirse, aşağıdaki komutu çalıştırarak doğru yapılandırmaya sahip olup olmadığınızı de kontrol edebilirsiniz:

```console
$ sudo grep -F '\[{tamperProtection}\]: Feature state:' /Library/Logs/Microsoft/mdatp/microsoft_defender_core.log | tail -n 1


```

Mod "engelle" (veya "denetim") olmalıdır. Değilse, kurcalama koruma modunu komut veya Intune aracılığıyla `mdatp config` ayarlamadınız demektir.
