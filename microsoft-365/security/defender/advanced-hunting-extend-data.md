---
title: Doğru ayarlarla gelişmiş avcılık kapsamını genişletme
description: Gelişmiş tehdit avcılığında en kapsamlı verileri aldığınızdan emin olmak için Windows cihazlarında denetim ayarlarını ve diğer ayarları denetleyin
keywords: gelişmiş tehdit avcılığı, olay, özet, varlık, denetim ayarları, kullanıcı hesabı yönetimi, güvenlik grubu yönetimi, tehdit avcılığı, siber tehdit avcılığı, arama, sorgulama, telemetri, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.openlocfilehash: 1c2e0ef6b07f746ba88e190807ef914a9948b8f8
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68625423"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Doğru ayarlarla gelişmiş avcılık kapsamını genişletme

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender
- Uç Nokta için Microsoft Defender

[Gelişmiş avcılık](advanced-hunting-overview.md); cihazlarınız, Office 365 çalışma alanlarınız, Azure AD ve Kimlik için Microsoft Defender dahil olmak üzere çeşitli kaynaklardan gelen verilere dayanır. Mümkün olan en kapsamlı verileri almak için ilgili veri kaynaklarında doğru ayarlara sahip olduğunuzdan emin olun.

## <a name="advanced-security-auditing-on-windows-devices"></a>Windows cihazlarında gelişmiş güvenlik denetimi
Yerel hesap yönetimi, yerel güvenlik grubu yönetimi ve hizmet oluşturma gibi cihazlarınızdaki etkinlikler hakkında veri aldığınızdan emin olmak için bu gelişmiş denetim ayarlarını açın.

| Veri | Açıklama | Şema tablosu | Yapılandırma |
| --- | --- | --- | --- |
| Hesap yönetimi | Yerel hesap oluşturma, silme ve hesapla ilgili diğer etkinlikleri gösteren çeşitli `ActionType` değerler olarak yakalanan olaylar | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Gelişmiş güvenlik denetim ilkesi dağıtma: [Kullanıcı Hesabı Yönetimini Denetleme](/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Gelişmiş güvenlik denetimi ilkeleri hakkında bilgi edinin](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Güvenlik grubu yönetimi | Yerel güvenlik grubu oluşturmayı ve diğer yerel grup yönetimi etkinliklerini gösteren çeşitli `ActionType` değerler olarak yakalanan olaylar | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Gelişmiş güvenlik denetim ilkesi dağıtma: [Güvenlik Grubu Yönetimini Denetleme](/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Gelişmiş güvenlik denetimi ilkeleri hakkında bilgi edinin](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Hizmet yüklemesi | değeriyle `ActionType` `ServiceInstalled`yakalanan ve bir hizmetin oluşturulduğunu belirten olaylar | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Gelişmiş güvenlik denetim ilkesi dağıtma: [Güvenlik Sistemi Uzantısını Denetleme](/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Gelişmiş güvenlik denetimi ilkeleri hakkında bilgi edinin](/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>Etki alanı denetleyicisinde Kimlik için Microsoft Defender algılayıcısı
Active Directory'yi şirket içinde çalıştırıyorsanız, Kimlik için Microsoft Defender verilerini almak için Kimlik için Microsoft Defender algılayıcısını etki alanı denetleyicisine yüklemeniz gerekir. Yüklendiğinde ve düzgün yapılandırıldığında, bu veriler Kimlik için Microsoft Defender aracılığıyla gelişmiş avlanmaya da geçer ve ağınızdaki kimlik bilgilerinin ve olayların daha bütünsel bir resmini sağlar. Bu veriler Kimlik için Microsoft Defender gelişmiş avcılık kapsamındaki ilgili uyarılar oluşturma özelliğini de geliştirir. 

| Veri | Açıklama | Şema tablosu | Yapılandırma |
| --- | --- | --- | --- |
| Etki alanı denetleyicisi | Kimlik için Microsoft Defender gönderilen şirket içi Active Directory verileri, hesap ayrıntıları, oturum açma etkinliği ve Active Directory sorguları gibi kimlikle ilgili bilgileri zenginleştirir | [IdentityInfo](advanced-hunting-identityinfo-table.md), [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) ve [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) gibi birden çok tablo  | - [Kimlik için Microsoft Defender algılayıcısını yükleme](/azure-advanced-threat-protection/install-atp-step4)<br>- [İlgili Windows Olaylarını açma](/azure-advanced-threat-protection/configure-event-collection) |

>[!NOTE]
>Bu makaledeki bazı tablolar Uç Nokta için Microsoft Defender'de kullanılamayabilir. Daha fazla veri kaynağı kullanarak tehditleri avlamak için [Microsoft 365 Defender açın](m365d-enable.md). Gelişmiş avcılık sorgularını Uç Nokta için Microsoft Defender'den geçirme bölümünde yer alan adımları izleyerek [gelişmiş avcılık iş akışlarınızı Uç Nokta için Microsoft Defender'den Microsoft 365 Defender](advanced-hunting-migrate-from-mde.md) taşıyabilirsiniz.

## <a name="related-topics"></a>İlgili konular
- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)