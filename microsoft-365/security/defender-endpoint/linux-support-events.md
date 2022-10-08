---
title: Linux'ta Uç Nokta için Microsoft Defender için eksik olayları veya uyarı sorunlarını giderme
description: Linux'ta Uç Nokta için Microsoft Defender eksik olayları veya uyarı sorunlarını giderme.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, linux, events
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
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 58cb9f836c2751743149eebd6b776ee8f879aa51
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68222082"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Linux'ta Uç Nokta için Microsoft Defender için eksik olayları veya uyarı sorunlarını giderme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Bu makalede, <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalında</a> eksik olayları veya uyarıları azaltmak için bazı genel adımlar sağlanır.

**Uç Nokta için Microsoft Defender** bir cihaza düzgün bir şekilde yüklendikten sonra portalda bir _cihaz sayfası_ oluşturulur. Kaydedilen tüm olayları cihaz sayfasındaki zaman çizelgesi sekmesinde veya gelişmiş tehdit avcılığı sayfasında gözden geçirebilirsiniz. Bu bölümde beklenen olayların bazılarının veya tümünün eksik olması durumunda sorun giderilir.
Örneğin, tüm _CreatedFile_ olayları eksikse.

## <a name="missing-network-and-login-events"></a>Ağ ve oturum açma olayları eksik

Uç Nokta için Microsoft Defender ağ ve oturum açma etkinliğini izlemek için Linux'tan çerçeve kullanılmıştır`audit`.

1. Denetim çerçevesinin çalıştığından emin olun.

    ```bash
    service auditd status
    ```

    beklenen çıkış:

    ```output
    ● auditd.service - Security Auditing Service
    Loaded: loaded (/usr/lib/systemd/system/auditd.service; enabled; vendor preset: enabled)
    Active: active (running) since Mon 2020-12-21 10:48:02 IST; 2 weeks 0 days ago
        Docs: man:auditd(8)
            https://github.com/linux-audit/audit-documentation
    Process: 16689 ExecStartPost=/sbin/augenrules --load (code=exited, status=1/FAILURE)
    Process: 16665 ExecStart=/sbin/auditd (code=exited, status=0/SUCCESS)
    Main PID: 16666 (auditd)
        Tasks: 25
    CGroup: /system.slice/auditd.service
            ├─16666 /sbin/auditd
            ├─16668 /sbin/audispd
            ├─16670 /usr/sbin/sedispatch
            └─16671 /opt/microsoft/mdatp/sbin/mdatp_audisp_plugin -d
    ```

2. Durduruldu olarak işaretlenmişse `auditd` başlatın.

    ```bash
    service auditd start
    ```

**SLES** sistemlerinde, içinde `auditd` SYSCALL denetimi varsayılan olarak devre dışı bırakılmış olabilir ve eksik olaylar için hesaba eklenebilir.

1. SYSCALL denetiminin devre dışı bırakılmadığını doğrulamak için geçerli denetim kurallarını listeleyin:

    ```bash
    sudo auditctl -l
    ```

    Aşağıdaki satır varsa, Uç Nokta için Microsoft Defender belirli SYSCALL'leri izlemesini sağlamak için satırı kaldırın veya düzenleyin.

    ```output
    -a task, never
    ```

    denetim kuralları konumunda `/etc/audit/rules.d/audit.rules`bulunur.

## <a name="missing-file-events"></a>Eksik dosya olayları

Dosya olayları çerçeve ile `fanotify` toplanır. Bazı veya tüm dosya olaylarının eksik olması durumunda cihazda etkinleştirildiğinden ve dosya sisteminin [desteklendiğinden](microsoft-defender-endpoint-linux.md#system-requirements) emin olun`fanotify`.

Makinedeki dosya sistemlerini şu şekilde listeleyin:

```bash
df -Th
```
