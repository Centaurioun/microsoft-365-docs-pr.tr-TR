---
title: SharePoint site içeriğini coğrafi bir konumla kısıtlama
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
ms.collection: Strat_SP_gtc
ms.localizationpriority: medium
description: Bu makalede, SharePoint sitelerini çok coğrafi ortamda belirtilen bir coğrafi konumla kısıtlamayı öğrenin.
ms.openlocfilehash: dd7048ea6eba4c8de7a0566c67d6588f395004c6
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68803671"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a>SharePoint site içeriğini coğrafi bir konumla kısıtlama

Belirli durumlarda, sitenin taşınmasını engelleyerek veya sitenin dosya içeriğinin başka bir _Coğrafya_ konumunda önbelleğe alınmasını engelleyerek sitenin ve dosya içeriğinin sitenin oluşturulduğu _Coğrafya_ konumunda kalmasını zorunlu kılmayı seçebilirsiniz.

Bu görevi **, RestrictedToGeo** parametresiyle [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) cmdlet'ini kullanarak yapabilirsiniz. Bu parametrenin varsayılan değeri NULL'dır, ancak bunu aşağıdaki kısıtlamalardan biriyle değiştirebilirsiniz:

|Kısıtlama|Açıklama|
|:----------|:----------|
|NoRestriction|Site başka bir _Coğrafya_ konumuna taşınabilir.|
|BlockMoveOnly|Site başka bir _Coğrafya_ konumuna taşınamaz, ancak site içeriği diğer _Coğrafya_ konumlarında önbelleğe alınabiliyor.|
|BlockFull|Site başka bir _Coğrafya_ konumuna taşınamaz ve tam dosya içeriği diğer _Coğrafya_ konumlarında önbelleğe alınmaz. Dosyaların başlığı (içerikten toplanır), dosya adı ve dosyanın diğer özellikleri diğer _Coğrafya_ konumlarında önbelleğe alınmaya devam edebilir.<br>Sitede depolanan içerik BlockFull olarak yapılandırılmadan önce diğer _Coğrafya_ konumlarında önbelleğe alınmaya devam edebilir.|

Aşağıdaki sözdizimini kullanın:

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

Örneğin:

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`
