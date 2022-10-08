---
title: Uç Nokta için Microsoft Defender güncelleştirmesini zamanlama (Linux)
description: Kuruluşunuzun varlıklarını daha iyi korumak için Uç Nokta için Microsoft Defender (Linux) güncelleştirmesini zamanlamayı öğrenin.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, linux, scans, virüsten koruma, uç nokta için microsoft defender (linux)
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
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: f1d0716f36e274ee5445304a73f3ab76f0686123
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68224876"
---
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a>Uç Nokta için Microsoft Defender (Linux) güncelleştirmelerini zamanlayın

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Linux'ta Uç Nokta için Microsoft Defender bir güncelleştirme çalıştırmak için bkz. [Linux'ta Uç Nokta için Microsoft Defender güncelleştirmelerini dağıtma](/microsoft-365/security/defender-endpoint/linux-updates).

Linux (ve Unix), zamanlanmış görevleri çalıştırabilmek için **crontab** (Görev Zamanlayıcı'ya benzer) adlı bir arağa sahiptir.

## <a name="pre-requisite"></a>Ön koşul

> [!NOTE]
> Tüm saat dilimlerinin listesini almak için aşağıdaki komutu çalıştırın: `timedatectl list-timezones`
>
> Saat dilimleri için örnekler:
>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>Cron işini ayarlamak için

Aşağıdaki komutları kullanın:

### <a name="backup-crontab-entries"></a>Crontab girdilerini yedekleme

```bash
sudo crontab -l > /var/tmp/cron_backup_201118.dat
```

> [!NOTE]
> Where 201118 == YYMMDD

> [!TIP]
> Düzenlemeden veya kaldırmadan önce bunu yapın.

Crontab'ı düzenlemek ve kök kullanıcı olarak yeni bir iş eklemek için:

```bash
sudo crontab -e
```

> [!NOTE]
> Varsayılan düzenleyici VIM'dir.

Şunu görebilirsiniz:

```output
0****/etc/opt/microsoft/mdatp/logrorate.sh
```

Ve

```output
02**sat /bin/mdatp scan quick>~/mdatp_cron_job.log
```

Bkz[. Uç Nokta için Microsoft Defender ile tarama zamanlama (Linux)](linux-schedule-scan-mde.md)

"Ekle" tuşuna basın

Aşağıdaki girdileri ekleyin:

```bash
CRON_TZ=America/Los_Angeles
```

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a>! RHEL ve varyantlar (CentOS ve Oracle Linux)
>
> ```bash
> 0 6 * * sun [ $(date +%d) -le 15 ] && sudo yum update mdatp -y >> ~/mdatp_cron_job.log
> ```

> #<a name="sles-and-variants"></a>! SLES ve çeşitlemeler
>
> ```bash
> 0 6 * * sun [ $(date +%d) -le 15 ] && sudo zypper update mdatp >> ~/mdatp_cron_job.log
> ```

> #<a name="ubuntu-and-debian-systems"></a>! Ubuntu ve Debian sistemleri
>
> ```bash
> 0 6 * * sun [ $(date +%d) -le 15 ] && sudo apt-get install --only-upgrade mdatp >> ~/mdatp_cron_job.log
> ```

> [!NOTE]
> Yukarıdaki örneklerde bunu 00 dakika, 06:00 (24 saat biçiminde saat), ayın herhangi bir günü, herhangi bir ay ve Pazar günleri olarak ayarlıyoruz. [$(date +\%d) -le 15] == 15. güne (3. hafta) eşit veya daha az değilse çalışmaz. Yani ayın her 3.Pazar günü (7) saat 06:00'da çalışacaktır. Pasifik (UTC -8).

"Esc" tuşuna basın

Çift tırnak işaretine "`:wq`" yazın.

> [!NOTE]
> w == write, q == quit

Cron işlerinizi görüntülemek için `sudo crontab -l`

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="Linux'ta Uç Nokta için Defender'a güncelleştirme.":::

Cron iş çalıştırmalarını incelemek için:

```bash
sudo grep mdatp /var/log/cron
```

mdatp_cron_job.log dosyasını incelemek için

```bash
sudo nano mdatp_cron_job.log
```

## <a name="for-those-who-use-ansible-chef-or-puppet"></a>Ansible, Chef veya Puppet kullananlar için

Aşağıdaki komutları kullanın:

### <a name="to-set-cron-jobs-in-ansible"></a>Ansible'da cron işleri ayarlamak için

```bash
cron - Manage cron.d and crontab entries
```

Daha fazla bilgi için bkz <https://docs.ansible.com/ansible/latest/modules/cron_module.html> .

### <a name="to-set-crontabs-in-chef"></a>Chef'te crontab'ları ayarlamak için

```bash
cron resource
```

Daha fazla bilgi için bkz <https://docs.chef.io/resources/cron/> .

### <a name="to-set-cron-jobs-in-puppet"></a>Puppet'da cron işleri ayarlamak için

Kaynak Türü: cron

Daha fazla bilgi için bkz <https://puppet.com/docs/puppet/5.5/types/cron.html> .

Puppet: Cron işleri ve zamanlanmış görevler ile otomatikleştirme

Daha fazla bilgi için bkz <https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/> .

## <a name="additional-information"></a>Ek bilgiler

### <a name="to-get-help-with-crontab"></a>Crontab ile ilgili yardım almak için

```bash
man crontab
```

### <a name="to-get-a-list-of-crontab-file-of-the-current-user"></a>Geçerli kullanıcının crontab dosyasının listesini almak için

```bash
crontab -l
```

### <a name="to-get-a-list-of-crontab-file-of-another-user"></a>Başka bir kullanıcının crontab dosyasının listesini almak için

```bash
crontab -u username -l
```

### <a name="to-backup-crontab-entries"></a>Crontab girdilerini yedeklemek için

```bash
crontab -l > /var/tmp/cron_backup.dat
```

> [!TIP]
> Düzenlemeden veya kaldırmadan önce bunu yapın.

### <a name="to-restore-crontab-entries"></a>Crontab girdilerini geri yüklemek için

```bash
crontab /var/tmp/cron_backup.dat
```

### <a name="to-edit-the-crontab-and-add-a-new-job-as-a-root-user"></a>Crontab'ı düzenlemek ve kök kullanıcı olarak yeni bir iş eklemek için

```bash
sudo crontab -e
```

### <a name="to-edit-the-crontab-and-add-a-new-job"></a>Crontab'ı düzenlemek ve yeni bir iş eklemek için

```bash
crontab -e
```

### <a name="to-edit-other-users-crontab-entries"></a>Diğer kullanıcının crontab girdilerini düzenlemek için

```bash
crontab -u username -e
```

### <a name="to-remove-all-crontab-entries"></a>Tüm crontab girdilerini kaldırmak için

```bash
crontab -r
```

### <a name="to-remove-other-users-crontab-entries"></a>Diğer kullanıcının crontab girdilerini kaldırmak için

```bash
crontab -u username -r
```

### <a name="explanation"></a>Açıklama

<pre>
+—————- minute (values: 0 - 59) (special characters: , - * /)  <br>
| +————- hour (values: 0 - 23) (special characters: , - * /) <br>
| | +———- day of month (values: 1 - 31) (special characters: , - * / L W C)  <br>
| | | +——- month (values: 1 - 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 - 6) (Sunday=0 or 7) (special characters: , - * / L W C) <br>
| | | | |*****command to be executed
</pre>
