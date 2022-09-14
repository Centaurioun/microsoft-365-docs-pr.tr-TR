---
title: Çok coğrafili ortamlarda SharePoint depolama kotaları
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
ms.localizationpriority: medium
description: Çok coğrafi ortamlardaki SharePoint depolama kotaları ve sharepoint online yöneticisi tarafından kotaların nasıl yönetilebileceği hakkında bilgi edinin.
ms.openlocfilehash: 78f57a13cc04e5f98189624a0c02f8f1b85cdea1
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67670233"
---
# <a name="sharepoint-storage-quotas-in-multi-geo-environments"></a>Çok coğrafili ortamlarda SharePoint depolama kotaları

Varsayılan olarak, çok coğrafi ortamın tüm coğrafi konumları kullanılabilir kiracı depolama kotasını paylaşır.

SharePoint coğrafi depolama kotası ayarıyla, her coğrafi konum için depolama kotasını yönetebilirsiniz. Bir coğrafi konum için depolama kotası ayırdığınızda, bu coğrafi konum için kullanılabilir en yüksek depolama miktarı olur ve kullanılabilir kiracı depolama kotasından düşülür. Kalan kullanılabilir kiracı depolama kotası daha sonra belirli bir depolama kotasının ayrılmadığı yapılandırılmış coğrafi konumlar arasında paylaşılır.

Herhangi bir coğrafi konum için SharePoint depolama kotası, Merkezi konuma bağlanarak SharePoint Online yöneticisi tarafından ayrılabilir. Uydu konumları için coğrafi yöneticiler depolama kotasını görüntüleyebilir ancak ayıramaz.

## <a name="configure-a-storage-quota-for-a-geo-location"></a>Coğrafi konum için depolama kotası yapılandırma

[Microsoft Office SharePoint Online Modülünü](https://www.microsoft.com/download/details.aspx?id=35588) kullanın ve coğrafi konum için depolama kotasını ayırmak üzere merkezi konuma bağlanın.

Bir konuma Depolama Kotası ayırmak için cmdlet'ini çalıştırın:

```powershell
Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB <value>
```

Geçerli coğrafi konumun Depolama Kotası'nı görüntülemek için şunu çalıştırın:

```powershell
Get-SPOGeoStorageQuota
```

![Get-SPOGeoStorageQuota cmdlet'ini gösteren PowerShell penceresinin ekran görüntüsü.](../media/multi-geo-storage-quota.png)

Tüm coğrafi konumların Depolama Kotasını görüntülemek için şunu çalıştırın:

```powershell
Get-SPOGeoStorageQuota -AllLocations
```

Coğrafi konum için ayrılan depolama kotasını kaldırmak için ayarlayın `StorageQuota value = 0`:

```powershell
Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB 0
```
