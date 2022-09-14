---
title: Linux kaynaklarında Uç Nokta için Microsoft Defender
ms.reviewer: ''
description: Linux'ta Uç Nokta için Microsoft Defender nasıl kaldırıldığı, tanılama günlüklerinin nasıl toplandığı, CLI komutları ve ürünle ilgili bilinen sorunlar gibi kaynakları açıklar.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 881e13cf1381c7f26d7c16920728e6e8829d638d
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67690171"
---
# <a name="resources"></a>Kaynaklar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a>Tanılama bilgilerini toplama

Bir sorunu yeniden oluşturabiliyorsanız, önce günlüğe kaydetme düzeyini artırın, sistemi bir süre çalıştırın ve ardından günlük düzeyini varsayılana geri yükleyin.

1. Günlük düzeyini artırın:

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. Sorunu yeniden oluşturun.

3. Uç Nokta için Defender günlüklerini yedeklemek için aşağıdaki komutu çalıştırın. Dosyalar bir .zip arşivinde depolanır.

   ```bash
   sudo mdatp diagnostic create
   ```

    Bu komut, işlem başarılı olduktan sonra yedeklemenin dosya yolunu da yazdırır:

   ```Output
   Diagnostic file created: <path to file>
   ```

4. Günlük düzeyini geri yükleme:

   ```bash
   mdatp log level set --level info
   ```

   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a>Günlük yükleme sorunları

Yükleme sırasında bir hata oluşursa, yükleyici yalnızca genel bir hata bildirir.

Ayrıntılı günlük öğesine `/var/log/microsoft/mdatp/install.log`kaydedilir.
Yükleme sırasında sorunlarla karşılaşırsanız, nedenini tanılamamıza yardımcı olabilmemiz için bu dosyayı bize gönderin.

## <a name="uninstall"></a>Kaldır

Linux'ta Uç Nokta için Defender'ı kaldırmanın çeşitli yolları vardır. Puppet gibi bir yapılandırma aracı kullanıyorsanız yapılandırma aracının paket kaldırma yönergelerini izleyin.

### <a name="manual-uninstallation"></a>El ile kaldırma

- `sudo yum remove mdatp` RHEL ve varyantlar için (CentOS ve Oracle Linux).
- `sudo zypper remove mdatp` SLES ve varyantlar için.
- `sudo apt-get purge mdatp` Ubuntu ve Debian sistemleri için.

## <a name="configure-from-the-command-line"></a>Komut satırından yapılandırma

Ürün ayarlarını denetleme ve isteğe bağlı taramaları tetikleme gibi önemli görevler komut satırından gerçekleştirilebilir.

### <a name="global-options"></a>Genel seçenekler

Varsayılan olarak, komut satırı aracı sonucu insan tarafından okunabilir biçimde döndürür. Ayrıca araç, otomasyon senaryoları için yararlı olan sonucuN JSON olarak çıkışını da destekler. Çıktıyı JSON olarak değiştirmek için aşağıdaki komutlardan herhangi birine geçirin `--output json` .

### <a name="supported-commands"></a>Desteklenen komutlar

Aşağıdaki tabloda, en yaygın senaryolardan bazılarına yönelik komutlar listelemektedir. Desteklenen komutların tam listesini görüntülemek için Terminal'den komutunu çalıştırın `mdatp help` .

<br>

****

|Grup|Senaryo|Komut|
|---|---|---|
|Yapılandırma|Gerçek zamanlı korumayı açma/kapatma|`mdatp config real-time-protection --value [enabled\|disabled]`|
|Yapılandırma|Davranış izlemeyi açma/kapatma|`mdatp config behavior-monitoring --value [enabled\|disabled]`
|Yapılandırma|Bulut korumasını açma/kapatma|`mdatp config cloud --value [enabled\|disabled]`|
|Yapılandırma|Ürün tanılamasını açma/kapatma|`mdatp config cloud-diagnostic --value [enabled\|disabled]`|
|Yapılandırma|Otomatik örnek göndermeyi açma/kapatma|`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`|
|Yapılandırma|AV pasif modunu açma/kapatma|`mdatp config passive-mode --value [enabled\|disabled]`|
|Yapılandırma|Dosya uzantısı için virüsten koruma dışlaması ekleme/kaldırma|`mdatp exclusion extension [add\|remove] --name [extension]`|
|Yapılandırma|Dosya için virüsten koruma dışlaması ekleme/kaldırma|`mdatp exclusion file [add\|remove] --path [path-to-file]`|
|Yapılandırma|Dizin için virüsten koruma dışlaması ekleme/kaldırma|`mdatp exclusion folder [add\|remove] --path [path-to-directory]`|
|Yapılandırma|Bir işlem için virüsten koruma dışlaması ekleme/kaldırma|`mdatp exclusion process [add\|remove] --path [path-to-process]` <p> `mdatp exclusion process [add\|remove] --name [process-name]`|
|Yapılandırma|Tüm virüsten koruma dışlamalarını listeleme|`mdatp exclusion list`|
|Yapılandırma|İzin verilenler listesine tehdit adı ekleme|`mdatp threat allowed add --name [threat-name]`|
|Yapılandırma|İzin verilenler listesinden bir tehdit adını kaldırma|`mdatp threat allowed remove --name [threat-name]`|
|Yapılandırma|İzin verilen tüm tehdit adlarını listeleme|`mdatp threat allowed list`|
|Yapılandırma|PUA korumasını açma|`mdatp threat policy set --type potentially_unwanted_application --action block`|
|Yapılandırma|PUA korumasını kapatma|`mdatp threat policy set --type potentially_unwanted_application --action off`|
|Yapılandırma|PUA koruması için denetim modunu açma|`mdatp threat policy set --type potentially_unwanted_application --action audit`|
|Yapılandırma|İsteğe bağlı taramalar için paralellik derecesini yapılandırma|`mdatp config maximum-on-demand-scan-threads --value [numerical-value-between-1-and-64]`|
|Yapılandırma|Güvenlik bilgileri güncelleştirmelerinden sonra taramaları açma/kapatma|`mdatp config scan-after-definition-update --value [enabled/disabled]`|
|Yapılandırma|Arşiv taramasını açma/kapatma (yalnızca isteğe bağlı taramalar)|`mdatp config scan-archives --value [enabled/disabled]`|
|Yapılandırma|Dosya karması hesaplamasını açma/kapatma|`mdatp config enable-file-hash-computation --value [enabled/disabled]`|
|Tanılama|Günlük düzeyini değiştirme|`mdatp log level set --level verbose [error|warning|info|verbose]`|
|Tanılama|Tanılama günlükleri oluşturma|`mdatp diagnostic create --path [directory]`|
|Hizmet Durumu|Ürünün durumunu kontrol edin|`mdatp health`|
|Koruma|Yolu tarama|`mdatp scan custom --path [path] [--ignore-exclusions]`|
|Koruma|Hızlı tarama yapma|`mdatp scan quick`|
|Koruma|Tam tarama yapma|`mdatp scan full`|
|Koruma|Devam eden isteğe bağlı taramayı iptal etme|`mdatp scan cancel`|
|Koruma|Güvenlik bilgileri güncelleştirmesi isteme|`mdatp definitions update`|
|Koruma geçmişi|Tam koruma geçmişini yazdırma|`mdatp threat list`|
|Koruma geçmişi|Tehdit ayrıntılarını alma|`mdatp threat get --id [threat-id]`|
|Karantina yönetimi|Karantinaya alınan tüm dosyaları listeleme|`mdatp threat quarantine list`|
|Karantina yönetimi|Tüm dosyaları karantinadan kaldırma|`mdatp threat quarantine remove-all`|
|Karantina yönetimi|Karantinaya tehdit olarak algılanan bir dosya ekleme|`mdatp threat quarantine add --id [threat-id]`|
|Karantina yönetimi|Tehdit olarak algılanan bir dosyayı karantinadan kaldırma|`mdatp threat quarantine remove --id [threat-id]`|
|Karantina yönetimi|Dosyayı karantinadan geri yükleme|`mdatp threat quarantine restore --id [threat-id] --path [destination-folder]`|
|Uç Nokta Algılama ve Yanıt|Erken önizlemeyi ayarlama (kullanılmayan)|`mdatp edr early-preview [enable|disable]`|
|Uç Nokta Algılama ve Yanıt|Grup kimliğini ayarlama|`mdatp edr group-ids --group-id [group-id]`|
|Uç Nokta Algılama ve Yanıt|Etiketi ayarlama /kaldırma, yalnızca `GROUP` desteklenir|`mdatp edr tag set --name GROUP --value [tag]`|
|Uç Nokta Algılama ve Yanıt|Dışlamaları listeleme (kök)|`mdatp edr exclusion list [processes|paths|extensions|all]`|
|
