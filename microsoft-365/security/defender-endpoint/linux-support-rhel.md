---
title: Linux RHEL6'da Uç Nokta için Microsoft Defender sorunlarını giderme
ms.reviewer: ''
description: Linux'ta Uç Nokta için Microsoft Defender için bulut bağlantısı sorunlarını giderme
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, linux, bulut, bağlantı, iletişim
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
ms.collection:
- m365-security
- tier3
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 739e4464a7c7a85d3a3ea75130e4e0a0bade000d
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68224854"
---
# <a name="troubleshoot-issues-for-microsoft-defender-for-endpoint-on-linux-rhel6"></a>Linux RHEL6'da Uç Nokta için Microsoft Defender sorunlarını giderme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Bu makalede, Red Hat Linux 6 (RHEL 6) veya üzeri sürümlerde Linux için Microsoft Defender karşılaşabileceğiniz sorunları giderme konusunda rehberlik sağlanmaktadır. 

Paket (mdatp_XXX.XX.XX.XX.x86_64.rpm) yüklendikten sonra, yüklemenin başarılı olduğunu doğrulamak için sağlanan eylemleri gerçekleştirin. 


## <a name="check-the-service-health"></a>Hizmet durumunu denetleme

Hizmet durumunu denetlemek için aşağıdaki komutu kullanın:

```bash
mdatp health 
```

## <a name="verify-that-the-service-is-running"></a>Hizmetin çalıştığını doğrulayın

Hizmetin çalıştığını doğrulamak için aşağıdaki komutu kullanın:

```bash
service mdatp status 
```

Beklenen çıkış: `mdatp start/running, process 4517`

## <a name="verify-the-distribution-and-kernel-version"></a>Dağıtım ve çekirdek sürümünü doğrulama
Dağıtım ve çekirdek sürümleri desteklenenler listesinde olmalıdır.

Dağıtım sürümünü almak için aşağıdaki komutu kullanın:

```bash
cat /etc/redhat-release (or /etc/system-release) 
```

Çekirdek sürümünü almak için aşağıdaki komutu kullanın:

```bash
uname -r
```
## <a name="check-if-mdatp-audisp-process-is-running"></a>mdatp audisp işleminin çalışıp çalışmadığını denetleyin 
Beklenen çıkış, işlemin çalışıyor olmasıdır.

Denetlemek için aşağıdaki komutu kullanın:

```bash
pidof mdatp_audisp_plugin 
```

## <a name="check-talpa-modules"></a>TALPA modüllerini denetleme
Dokuz modül yüklenmiş olmalıdır. 

Denetlemek için aşağıdaki komutu kullanın:

```bash
lsmod | grep talpa
```

Beklenen çıkış: Etkin

```bash
talpa_pedconnector       878  0 

talpa_pedevice          5189  2 talpa_pedconnector 

talpa_vfshook          32300  1 

talpa_vcdevice          4947  1 

talpa_syscall           9127  0 

talpa_core             90699  4 talpa_vfshook,talpa_vcdevice,talpa_syscall 

talpa_linux            29424  5 talpa_vfshook,talpa_vcdevice,talpa_syscall,talpa_core 

talpa_syscallhookprobe      882  0 

talpa_syscallhook      14987  2 talpa_vfshook,talpa_syscallhookprobe 
```


```bash
lsmod | grep talpa | wc -l 
```

Beklenen çıkış: 9

## <a name="check-talpa-status"></a>TALPA durumunu denetleme

```bash
cat /proc/sys/talpa/interceptors/VFSHookInterceptor/status 
```

Günlük dosyalarında hata ayıklama ('mdatp tanılama oluşturma' paketi dışında) 

```bash
/var/log/audit/audit.log 

/var/log/messages 

semanage fcontext -l > selinux.log 
```
 

Performans ve Bellek 

```bash
top -p <wdavdaemon pid>      

pmap -x <wdavdaemon pid> 
```

kullanılarak `pidof wdavdaemon`nerede `<wdavdaemon pid>` bulunabilir?

