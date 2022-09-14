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
ms.openlocfilehash: 03e1738b88d10717892152655a9e4f3de7a2d847
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67673051"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a>SharePoint site içeriğini coğrafi bir konumla kısıtlama

Belirli durumlarda, sitenin taşınmasını engelleyerek veya sitenin dosya içeriğinin başka bir coğrafi konumda önbelleğe alınmasını önleyerek sitenin ve dosya içeriğinin sitenin oluşturulduğu coğrafi konumda kalmasını zorunlu kılmayı seçebilirsiniz.

Bu görevi **, RestrictedToGeo** parametresiyle [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) cmdlet'ini kullanarak yapabilirsiniz. Bu parametrenin varsayılan değeri NULL'dır, ancak bunu aşağıdaki kısıtlamalardan biriyle değiştirebilirsiniz:

|Kısıtlama|Açıklama|
|:----------|:----------|
|NoRestriction|Site başka bir coğrafi konuma taşınabilir.|
|BlockMoveOnly|Site başka bir coğrafi konuma taşınamaz, ancak site içeriği diğer coğrafi konumlarda önbelleğe alınabilir.|
|BlockFull|Site başka bir coğrafi konuma taşınamaz ve tam dosya içeriği diğer coğrafi konumlarda önbelleğe alınmaz. Dosyaların başlığı (içerikten toplanır), dosya adı ve dosyanın diğer özellikleri diğer coğrafi konumlarda önbelleğe alınmaya devam edebilir.<br>Sitede depolanan içerik BlockFull olarak yapılandırılmadan önce diğer coğrafi konumlarda önbelleğe alınmaya devam edebilir.|

Aşağıdaki sözdizimini kullanın:

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

Örneğin:

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`
