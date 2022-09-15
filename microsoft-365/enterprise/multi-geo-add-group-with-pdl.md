---
title: Tercih edilen belirli bir veri konumuna sahip bir Microsoft 365 Grubu oluşturma
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
f1.keywords:
- NOCSH
ms.collection: Strat_SP_gtc
ms.localizationpriority: medium
description: Çok coğrafi bir ortamda belirli bir tercih edilen veri konumuna sahip bir Microsoft 365 grubu oluşturmayı öğrenin.
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
ms.openlocfilehash: ee2bc775f7274722ad2a59a253d8da8ce6795ce6
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705194"
---
# <a name="create-a-microsoft-365-group-with-a-specific-preferred-data-location"></a>Tercih edilen belirli bir veri konumuna sahip bir Microsoft 365 grubu oluşturma

Çok coğrafi bir ortamdaki kullanıcılar bir Microsoft 365 grubu oluşturduğunda, grubun tercih ettiği veri konumu (PDL) otomatik olarak kullanıcınınkine ayarlanır. Genel, SharePoint ve Exchange Yöneticileri seçtikleri herhangi bir bölgede grup oluşturabilir. 

Belirli bir PDL ile grup oluşturmanız gerekiyorsa, bunu <a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">SharePoint yönetim merkezinden</a> veya Exchange Online New-UnifiedGroup Microsoft PowerShell cmdlet'inden kullanarak yapabilirsiniz. Bunu yaptığınızda, hem grup posta kutusu hem de grupla ilişkilendirilmiş SharePoint sitesi belirtilen PDL'de sağlanır.

Belirttiğiniz PDL ile bir Microsoft 365 grubu oluşturmak için, grup sitesini oluşturmak istediğiniz coğrafi konumdaki <a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">SharePoint yönetim merkezine</a> gidin.

Örneğin:

Avustralya konumunuzda bir grup sitesi oluşturmak istiyorsanız `https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement`

1. **+ Oluştur'u** seçin.
2. Grup sitesi oluşturmak için işlemi izleyin.

Grup siteniz, site oluşturma isteğini başlattığınız SharePoint yönetim merkezine karşılık gelen coğrafi konumda sağlanır. 

Exchange PowerShell kullanma 

Exchange Online PowerShell'e bağlanın ve coğrafi konum koduyla *-MailBoxRegion* parametresini geçirin.

Örneğin: 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![Söz dizimi içeren New-UnifiedGroup PowerShell cmdlet'inin ekran görüntüsü.](../media/multi-geo-new-group-with-pdl-powershell.png)

> [!Note]
> SharePoint grup sitesi sağlama isteğe bağlıdır. Site, bir grup sahibi veya üyesi ilk kez erişmeye çalıştığında sağlanacaktır.

## <a name="geo-location-codes"></a>Coğrafi konum kodları

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a>İlgili konular

[Exchange Online PowerShell’e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell)

[Graph API kullanarak belirli bir tercih edilen veri konumuna sahip gruplar oluşturma](/graph/api/group-post-groups)
