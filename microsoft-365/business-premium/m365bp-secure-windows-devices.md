---
title: Windows cihazlarının güvenliğini sağlama
f1.keywords:
- CSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: microsoft-365-business
ms.subservice: business-premium
ms.localizationpriority: high
ms.date: 08/16/2022
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
description: Yerleşik ayarları kullanarak şirketinizin Windows cihazlarının güvenliğini sağlamayı öğrenin.
ms.openlocfilehash: 32632b416b79ae6f1c58b91fbed2035b44690694
ms.sourcegitcommit: db89873e22a12705ed313964c1bc2fa19d4fe719
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67878001"
---
# <a name="secure-windows-devices"></a>Windows cihazlarının güvenliğini sağlama

Buradaki amaç, Windows 10 veya 11 için varsayılan cihaz ilkesinin parçası olan ayarları yapılandırmaktır. Mobil cihazlar ve bilgisayarlar da dahil olmak üzere bir Windows cihazını iş hesaplarıyla oturum açarak bağlayan tüm kullanıcılar bu ayarları otomatik olarak alır. Kurulum sırasında varsayılan ilkeyi kabul etmenizi ve daha sonra belirli kullanıcı gruplarını hedef alan ilkeler eklemenizi öneririz.

## <a name="before-you-begin"></a>Başlamadan önce

windows cihazlarını Microsoft 365 İş Ekstra kullanıcılar için ayarlamadan önce tüm Windows cihazlarının Windows 10 Pro çalıştığından emin olun.

Windows 10 Pro, Windows 10 Pro ve Windows 11 Pro tamamlayan ve merkezi yönetim ve güvenlik denetimlerini etkinleştiren bir dizi bulut hizmeti ve cihaz yönetimi özelliği olan Windows 10 Business dağıtımı için önkoşuldur Microsoft 365 İş Ekstra.

[Microsoft 365 İş Ekstra gereksinimleri hakkında daha fazla bilgi edinin](https://www.microsoft.com/microsoft-365/business/microsoft-365-business-premium?activetab=pivot:techspecstab).

## <a name="windows-10-pro"></a>Windows 10 Pro

Windows 7 Pro, Windows 8 Pro veya Windows 8.1 Pro gibi Windows'un önceki sürümlerini çalıştıran Windows cihazlarınız varsa, Microsoft 365 İş Ekstra aboneliğiniz bu cihazları Windows 10 Pro veya Windows 11 Pro.
  
Windows cihazlarını yükseltme hakkında daha fazla bilgi için bkz[. Windows cihazlarını Windows 10 Pro yükseltme](m365bp-upgrade-windows-10-pro.md).

## <a name="secure-your-windows-10-and-11-devices"></a>Windows 10 ve 11 cihazlarınızın güvenliğini sağlama

Varsayılan olarak tüm ayarlar **Açık** durumdadır. Aşağıdaki ayarlar kullanılabilir:

|Ayar |Açıklama |
|:-----|:-----|
|Microsoft Defender Virüsten Koruma kullanarak bilgisayarların virüslerden ve diğer tehditlerden korunmasına yardımcı olun  |Bilgisayarları İnternet'e bağlı olmanın tehlikelerinden korumak için Microsoft Defender Virüsten Koruma'nın açık olmasını gerektirir.   |
|Microsoft Edge'de bilgisayarların web tabanlı tehditlerden korunmasına yardımcı olun   |Edge'de, kullanıcıları kötü amaçlı sitelerden ve indirmelerden korumaya yardımcı olan ayarları açar.  |
|BitLocker ile bilgisayarlardaki dosya ve klasörleri yetkisiz erişime karşı korumaya yardımcı olun  |BitLocker, bilgisayar sabit sürücülerini şifreleyerek verileri korur ve bir bilgisayar kaybolur veya çalınırsa verilerin açığa çıkarmasını önler. Daha fazla bilgi için bkz. [BitLocker SSS](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions).  |
|Cihaz şu kadar süre boşta kaldığında ekranı kapat  |Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.  |

## <a name="next-objective"></a>Sonraki hedef

[Windows cihazları yönetme](m365bp-manage-windows-devices.md)
