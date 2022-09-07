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
ms.sourcegitcommit: 651610ca73bfd1d008d97311b59782790df664fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2022
ms.locfileid: "67613812"
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
|Microsoft Defender Virüsten Koruma kullanarak bilgisayarların virüslerden ve diğer tehditlerden korunmasına yardımcı olun  |Bilgisayarları internete bağlı olmanın tehlikelerinden korumak için Microsoft Defender Virüsten Koruma'nın açık olmasını gerektirir.   |
|Microsoft Edge'de bilgisayarların web tabanlı tehditlerden korunmasına yardımcı olun   |Edge'de, kullanıcıları kötü amaçlı sitelerden ve indirmelerden korumaya yardımcı olan ayarları açar.  |
|BitLocker ile bilgisayarlardaki dosya ve klasörleri yetkisiz erişime karşı korumaya yardımcı olun  |BitLocker, bilgisayar sabit sürücülerini şifreleyerek verileri korur ve bir bilgisayar kaybolur veya çalınırsa verilerin açığa çıkarmasını önler. Daha fazla bilgi için bkz. [BitLocker SSS](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions).  |
|Cihaz şu kadar süre boşta kaldığında ekranı kapat  |Kullanıcı cihaz başında olmadığında şirket verilerinin korunmasını sağlar. Kullanıcı bir kafe gibi herkese açık bir konumda çalışıyorken kısa süreliğine uzaklaşabilir veya başka bir şeyle ilgilenebilir ve bu sırada diğer kişiler cihazdaki bilgilere bakabilir. Bu ayar sayesinde, ekran kapanmadan önce kullanıcının ne kadar süre boşta olabileceğini denetleyebilirsiniz.  |

## <a name="next-objective"></a>Sonraki hedef

[Windows cihazları yönetme](m365bp-manage-windows-devices.md)
