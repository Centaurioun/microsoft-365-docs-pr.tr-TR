---
title: Mac'te Uç Nokta için Microsoft Defender kaynakları
description: Mac'te Uç Nokta için Microsoft Defender kaldırma, tanılama günlüklerini toplama, CLI komutları ve ürünle ilgili bilinen sorunlar gibi kaynaklar.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: fe4ff18bcc82aa46b1af023bace98608422aa2cc
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67690039"
---
# <a name="resources-for-microsoft-defender-for-endpoint-on-macos"></a>macOS'ta Uç Nokta için Microsoft Defender kaynakları

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a>Tanılama bilgilerini toplama

Bir sorunu yeniden oluşturabiliyorsanız günlük düzeyini artırın, sistemi bir süre çalıştırın ve günlük düzeyini varsayılana geri yükleyin.

1. Günlük düzeyini artırın:

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. Sorunu yeniden oluşturma

3. Uç Nokta için Microsoft Defender günlüklerini yedeklemek için komutunu çalıştırın`sudo mdatp diagnostic create`. Dosyalar bir .zip arşivinde depolanır. Bu komut, işlem başarılı olduktan sonra yedeklemenin dosya yolunu da yazdırır.

   > [!TIP]
   > Varsayılan olarak, tanılama günlükleri öğesine `/Library/Application Support/Microsoft/Defender/wdavdiag/`kaydedilir. Tanılama günlüklerinin kaydedildiği dizini değiştirmek için aşağıdaki komuta geçin `--path [directory]` ve değerini istenen dizinle değiştirin `[directory]` .

   ```bash
   sudo mdatp diagnostic create
   ```

   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. Günlük düzeyini geri yükleme:

   ```bash
   mdatp log level set --level info
   ```

   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a>Yükleme sorunlarını günlüğe kaydetme

Yükleme sırasında bir hata oluşursa, yükleyici yalnızca genel bir hata bildirir.

Ayrıntılı günlük öğesine `/Library/Logs/Microsoft/mdatp/install.log`kaydedilir. Yükleme sırasında sorunlarla karşılaşırsanız, nedenini tanılamamıza yardımcı olabilmemiz için bu dosyayı bize gönderin.

## <a name="uninstalling"></a>Kaldırma

macOS'ta Uç Nokta için Microsoft Defender kaldırmanın birkaç yolu vardır. Merkezi olarak yönetilen kaldırma JAMF'de kullanılabilse de Microsoft Intune için henüz kullanılamadığını unutmayın.

### <a name="interactive-uninstallation"></a>Etkileşimli kaldırma

- **Bulucu > Uygulamaları'yı** açın. **Uç Nokta için Microsoft Defender > Çöp Kutusuna Taşı'ya** sağ tıklayın.

### <a name="supported-output-types"></a>Desteklenen çıkış türleri

Tablo ve JSON biçimi çıkış türlerini destekler. Her komut için varsayılan bir çıkış davranışı vardır. Aşağıdaki komutları kullanarak tercih ettiğiniz çıkış biçimindeki çıkışı değiştirebilirsiniz:

`-output json`

`-output table`

### <a name="from-the-command-line"></a>Komut satırından

- `sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'`

## <a name="configuring-from-the-command-line"></a>Komut satırından yapılandırma

Ürün ayarlarını denetleme ve isteğe bağlı taramaları tetikleme gibi önemli görevler komut satırından yapılabilir:

|Grup|Senaryo|Komut|
|---|---|---|
|Yapılandırma|Gerçek zamanlı korumayı açma/kapatma|`mdatp config real-time-protection --value [enabled/disabled]`|
|Yapılandırma|Bulut korumasını açma/kapatma|`mdatp config cloud --value [enabled/disabled]`|
|Yapılandırma|Ürün tanılamasını açma/kapatma|`mdatp config cloud-diagnostic --value [enabled/disabled]`|
|Yapılandırma|Otomatik örnek göndermeyi açma/kapatma|`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`|
|Yapılandırma|İzin verilenler listesine tehdit adı ekleme|`mdatp threat allowed add --name [threat-name]`|
|Yapılandırma|İzin verilenler listesinden bir tehdit adını kaldırma|`mdatp threat allowed remove --name [threat-name]`|
|Yapılandırma|İzin verilen tüm tehdit adlarını listeleme|`mdatp threat allowed list`|
|Yapılandırma|PUA korumasını açma|`mdatp threat policy set --type potentially_unwanted_application -- action block`|
|Yapılandırma|PUA korumasını kapatma|`mdatp threat policy set --type potentially_unwanted_application -- action off`|
|Yapılandırma|PUA koruması için denetim modunu açma|`mdatp threat policy set --type potentially_unwanted_application -- action audit`|
|Yapılandırma|Virüsten koruma pasif modunu açma/kapatma|`mdatp config passive-mode --value [enabled/disabled]`|
|Yapılandırma|İsteğe bağlı taramalar için paralellik derecesini yapılandırma|`mdatp config maximum-on-demand-scan-threads --value [numerical-value-between-1-and-64]`|
|Yapılandırma|Güvenlik bilgileri güncelleştirmelerinden sonra taramaları açma/kapatma|`mdatp config scan-after-definition-update --value [enabled/disabled]`|
|Yapılandırma|Arşiv taramasını açma/kapatma (yalnızca isteğe bağlı taramalar)|`mdatp config scan-archives --value [enabled/disabled]`|
|Yapılandırma|Dosya karması hesaplamasını açma/kapatma|`mdatp config enable-file-hash-computation --value [enabled/disabled]`|
|Yapılandırma|data_loss_prevention açma/kapatma|`mdatp config data_loss_prevention --value [enabled/disabled]`|
|Tanılama|Günlük düzeyini değiştirme|`mdatp log level set --level [error/warning/info/verbose]`|
|Tanılama|Tanılama günlükleri oluşturma|`mdatp diagnostic create --path [directory]`|
|Hizmet Durumu|Ürünün durumunu kontrol edin|`mdatp health`|
|Hizmet Durumu|Spefic ürün özniteliğini denetleme|`mdatp health --field [attribute: healthy/licensed/engine_version...]`|
|Koruma|Yolu tarama|`mdatp scan custom --path [path] [--ignore-exclusions]`|
|Koruma|Hızlı tarama yapma|`mdatp scan quick`|
|Koruma|Tam tarama yapma|`mdatp scan full`|
|Koruma|Devam eden isteğe bağlı taramayı iptal etme|`mdatp scan cancel`|
|Koruma|Güvenlik bilgileri güncelleştirmesi isteme|`mdatp definitions update`|
|Edr|Etiketi ayarla/kaldır, yalnızca GROUP desteklenir|`mdatp edr tag set --name GROUP --value [name]`|
|Edr|Cihazdan grup etiketini kaldırma|`mdatp edr tag remove --tag-name [name]`|
|Edr|Grup Kimliği Ekle|`mdatp edr group-ids --group-id [group]`|

### <a name="how-to-enable-autocompletion"></a>Otomatik tamamlama nasıl etkinleştirilir?

Bash'te otomatik tamamlama özelliğini etkinleştirmek için aşağıdaki komutu çalıştırın ve Terminal oturumunu yeniden başlatın:

```bash
echo "source /Applications/Microsoft\ Defender.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

Zsh'de otomatik tamamlama özelliğini etkinleştirmek için:

- Cihazınızda otomatik tamamlamanın etkinleştirilip etkinleştirilmediğini denetleyin:

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- Yukarıdaki komut herhangi bir çıkış üretmezse, aşağıdaki komutu kullanarak otomatik tamamlama özelliğini etkinleştirebilirsiniz:

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- macOS'ta Uç Nokta için Microsoft Defender için otomatik tamamlamayı etkinleştirmek ve Terminal oturumunu yeniden başlatmak için aşağıdaki komutları çalıştırın:

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions

   sudo ln -svf "/Applications/Microsoft Defender.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a>İstemci Uç Nokta için Microsoft Defender karantina dizini

`/Library/Application Support/Microsoft/Defender/quarantine/` tarafından `mdatp`karantinaya alınan dosyaları içerir. Dosyalar tehdit izleme kimliğinden sonra adlandırılır. Geçerli trackingId'ler ile `mdatp threat list`gösterilir.

## <a name="microsoft-defender-for-endpoint-portal-information"></a>portal bilgilerini Uç Nokta için Microsoft Defender

[macOS için EDR özellikleri artık geldi](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801), Uç Nokta için Microsoft Defender blogunda Uç Nokta için Microsoft Defender Güvenlik Merkezi'nde neler bekleyebileceğinize ilişkin ayrıntılı yönergeler sağlanmaktadır.
