---
title: Uç Nokta için Microsoft Defender Cihaz Denetimi Çıkarılabilir Depolama Birimi Koruması
description: Kullanıcının veya makinenin ya da her ikisinin de yetkisiz çıkarılabilir depolama medyası kullanmasını önlemeye yardımcı olan 'özellikleri anlama
keywords: çıkarılabilir depolama ortamı
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
ms.date: 08/01/2022
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 1add6ea29d38e784733b98646458f19c68fa6be1
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67524094"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Uç Nokta için Microsoft Defender Cihaz Denetimi Çıkarılabilir Depolama Birimi Koruması


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Uç Nokta için Microsoft Defender'de cihaz denetimi çıkarılabilir depolama koruması, kullanıcıların, uç noktaların veya her ikisinin de yetkisiz çıkarılabilir depolama medyası kullanmasını engeller.

## <a name="protection-policies"></a>Koruma ilkeleri

### <a name="removable-storage-access-control"></a>Çıkarılabilir depolama birimi erişim denetimi

**Yetenek -lerini**

- *Denetim* Dışlama ile veya hariç tutmadan çeşitli cihaz özelliklerine göre çıkarılabilir depolama birimine okuma veya yazma veya yürütme erişimi.
- *Önle* Okuma veya Yazma veya Dışlama olmadan erişim yürütme - Çeşitli cihaz özelliklerine göre belirli bir cihaza izin verin.

Dış depolamayı yönetmek için [cihaz yüklemesi](#device-installation) yerine çıkarılabilir depolama erişim denetimini kullanın.

**Windows 10 ve Windows 11 destek ayrıntıları**:

- Cihaz düzeyinde, kullanıcı düzeyinde uygulanır. veya her ikisini birden. Yalnızca belirli bir makinedeki belirli çıkarılabilir depolama birimine Okuma/Yazma/Yürütme erişimi gerçekleştiren belirli kişilere izin verin.
- MEM OMA-URI ve GPO desteği.
- Windows cihazları için bkz[. Çıkarılabilir depolama Access Control](device-control-removable-storage-access-control.md).

**Desteklenen Platform** - Windows 10, Windows 11

**macOS destek ayrıntıları**:

- Cihaz düzeyinde uygulanır: Aynı ilke, oturum açmış tüm kullanıcılar için de geçerlidir.
- macOS'a özgü bilgiler için bkz. [macOS için cihaz denetimi](mac-device-control-overview.md).

**Desteklenen platform** - macOS Catalina 10.15.4+ (sistem uzantıları etkin)


### <a name="device-installation"></a>Cihaz yüklemesi

**Özellikler** - Çeşitli cihaz özelliklerine göre dışlama ile veya dışlama olmadan yüklemeyi engelleyin.

**Windows 10 ve Windows 11 destek ayrıntıları**:

- Cihaz düzeyinde uygulanır: Aynı ilke, oturum açmış tüm kullanıcılar için de geçerlidir.
- Microsoft Endpoint Manager ve grup ilkesi Nesnelerini destekler.
- Windows hakkında daha fazla bilgi için bkz. [Uç Nokta için Microsoft Defender kullanarak USB cihazlarını ve diğer çıkarılabilir medyaları denetleme](control-usb-devices-using-intune.md).

**Desteklenen Platform** - Windows 10, Windows 11

**macOS destek ayrıntıları**:

- Cihaz düzeyinde uygulanır: Oturum açan tüm kullanıcılar için aynı ilke geçerlidir
- macOS'a özgü bilgiler için bkz. [macOS için cihaz denetimi](mac-device-control-overview.md).

**Desteklenen platform** - macOS Catalina 10.15.4+ (sistem uzantıları etkinleştirilmiş) veya üzeri

### <a name="endpoint-dlp-removable-storage"></a>Uç Nokta DLP Çıkarılabilir depolama alanı

**Özellikler** - Kullanıcının bir öğeyi veya bilgiyi çıkarılabilir medyaya veya USB cihazına kopyalamasını denetleyin, uyarın veya engelleyin.

**Açıklama** - Windows hakkında daha fazla bilgi için bkz [. Uç nokta veri kaybını önleme hakkında bilgi edinin](../../compliance/endpoint-dlp-learn-about.md).

**Desteklenen Platform** - Windows 10, Windows 11

### <a name="bitlocker"></a>Bitlocker

**Özellikler**:

- BitLocker korumalı olmayan çıkarılabilir sürücülere yazılacak verileri engelleyin.
- Kuruluşunuza ait bir bilgisayarda şifrelenmedikleri sürece çıkarılabilir sürücülere erişimi engelleme

**Açıklama** - Windows hakkında daha fazla bilgi için bkz. [BitLocker - Çıkarılabilir Sürücü Ayarları](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).

**Desteklenen Platform** - Windows 10, Windows 11
