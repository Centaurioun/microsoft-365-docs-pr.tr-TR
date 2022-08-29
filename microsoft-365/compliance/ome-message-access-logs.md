---
title: Şifrelenmiş ileti portalı etkinlik günlüğü
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.date: 07/21/2022
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Erişim günlükleri, şifrelenmiş ileti portalı aracılığıyla alınan şifrelenmiş iletiler için kullanılabilir.
ms.openlocfilehash: fe45757eb6ca89f55a1b796d3752b1e3bcb1b89b
ms.sourcegitcommit: d7c51ab23de4b43bcc8eebebc5a2962831e9fd55
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/23/2022
ms.locfileid: "67420842"
---
# <a name="encrypted-message-portal-activity-log-by-microsoft-purview-advanced-message-encryption"></a>Microsoft Purview Gelişmiş İleti Şifrelemesi tarafından şifrelenmiş ileti portalı etkinlik günlüğü

Erişim günlükleri, kuruluşunuzun iletilerin ne zaman okunduğunu ve dış alıcılarınız tarafından iletileceğini belirlemesini sağlayan şifrelenmiş ileti portalı aracılığıyla şifrelenmiş iletiler için kullanılabilir. Günlüklerin tüm dış alıcılar için kullanılabilir olduğundan emin olmak için, kuruluşunuz tarafından portal deneyimini zorlayan dış alıcılara gönderilen korumalı e-postalara özel bir markalama şablonu uygulamanız gerekir. Bkz. [Şifrelenmiş iletilerinize kuruluşunuzun markasını ekleme](add-your-organization-brand-to-encrypted-messages.md).

## <a name="enabling-message-access-audit-logs-in-powershell"></a>PowerShell'de ileti erişimi denetim günlüklerini etkinleştirme

Erişim günlüğü [Exchange Online PowerShell V2 modülü](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) kullanılarak etkinleştirilebilir. *Set-IrmConfiguration'in -EnablePortalTrackingLogs* parametresi, şifrelenmiş ileti portalına erişim denetim günlüklerinin etkinleştirilip etkinleştirilmeymeyeceğini belirtir. Geçerli değerler şunlardır:

- $true: Denetim özelliğini açın.
- $false: Denetim özelliğini kapatma

Örnek: Set-IrmConfiguration -EnablePortalTrackingLogs $true

Daha fazla bilgi için bkz. [Set-IRMConfiguration (ExchangePowerShell)](/powershell/module/exchange/set-irmconfiguration).

## <a name="message-access-audit-information"></a>İleti erişimi denetim bilgileri

Erişim günlüğü, aşağıdaki etkinlik türleri için şifrelenmiş ileti portalından gönderilen iletilerin girdilerini içerir:

- Dış kullanıcı oturum açma zaman damgası ve kimlik doğrulama yöntemi
- Dış kullanıcı iletileri veya ekleri okuma
- Ek indirme
- posta yanıtları ve iletme

İleti erişim günlüğü şeması hakkında daha fazla bilgi için bkz. [Uyumluluk portalında denetim günlüğünde arama](search-the-audit-log-in-security-and-compliance.md#encrypted-message-portal-activities) yapma.

## <a name="search-for-events-in-the-message-access-logs"></a>İleti erişim günlüklerinde olayları arama

İleti erişim günlüklerinde yakalanan olayları görüntülemek için:

1. Microsoft Purview uyumluluk portalı **Çözümler'in** altında **Denetim'i** seçin.
1. **Arama'nın** altında **Etkinlikler** açılan menüsüne tıklayın ve şifreli ileti portalı etkinlikleri yazın.
1. Şifrelenmiş ileti portalı etkinlikleri altında, aramada kullanılacak olay türlerini seçin. Aramanın tarih aralığını ayarlayın (varsayılan olarak önceki haftadır), isteğe bağlı olarak arama için kuruluşunuza belirli bir kullanıcı ekleyebilirsiniz. Hazır olduğunuzda **Ara'yı** seçin.
1. Denetim özelliklerini görüntülemek için listeden bir olay seçin.
