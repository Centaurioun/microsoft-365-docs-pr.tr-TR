---
title: Tam veri eşleşme etkinlikleri için bildirimler oluşturma
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Tam veri eşleştirme etkinlikleri için nasıl bildirim oluşturacağınızı öğrenin.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 09bb41de09b6f44a9f556446c5a566322b44ad0d
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66949139"
---
# <a name="create-notifications-for-exact-data-match-activities"></a>Tam veri eşleşme etkinlikleri için bildirimler oluşturma

[Tam veri eşleşmesi (EDM) ile özel hassas bilgi türleri](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types) oluşturduğunuzda, [denetim günlüğünde](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log) oluşturulan bir dizi etkinlik vardır. Bu etkinlikler gerçekleştiğinde sizi bilgilendiren bildirimler oluşturmak için [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) PowerShell cmdlet'ini kullanabilirsiniz:

- `CreateSchema`
- `EditSchema`
- `RemoveSchema`
- `UploadDataFailed`
- `UploadDataCompleted`

> [!NOTE]
 EDM etkinlikleri için bildirim oluşturma özelliği yalnızca World Wide ve GCC bulutlarında kullanılabilir.

## <a name="pre-requisites"></a>Önkoşullar

Kullandığınız hesap aşağıdakilerden biri olmalıdır:

- Genel yönetici
- Uyumluluk yöneticisi
- Exchange Online yöneticisi

DLP izinleri hakkında daha fazla bilgi edinmek için bkz. [İzinler](data-loss-prevention-policies.md#permissions).

EDM tabanlı sınıflandırma şu aboneliklere dahildir:

- Office 365 E5
- Microsoft 365 E5
- Microsoft 365 E5 Uyumluluk
- Microsoft E5/A5 Information Protection ve İdare

DLP lisansı hakkında daha fazla bilgi edinmek için bkz. [Güvenlik & uyumluluğu için Microsoft 365 lisanslama kılavuzu](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

## <a name="configure-notifications-for-edm-activities"></a>EDM etkinlikleri için bildirimleri yapılandırma

1. [Güvenlik & Uyumluluğu PowerShell'e bağlanın](/powershell/exchange/connect-to-scc-powershell).

2. Bildirimi oluşturmak `New-ProtectionAlert` istediğiniz etkinliği kullanarak cmdlet'ini çalıştırın.  Örneğin, eylem gerçekleştiğinde `UploadDataCompleted` bildirim almak istiyorsanız şunu çalıştırın:

    ```powershell
    New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <address to send notification to> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
    ```
    
    `UploadDataFailed` için şunu çalıştırabilirsiniz:
    
    ```powershell
    New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <SMTP address to send notification to> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
    ```

## <a name="related-articles"></a>İlgili makaleler

- [Tam veri eşleşmesine dayalı hassas bilgi türleri hakkında daha fazla bilgi edinme](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert)
