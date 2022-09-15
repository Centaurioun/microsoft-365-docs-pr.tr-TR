---
title: Multi-Geo Microsoft 365 eKeşif'i yapılandırma
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
ms.localizationpriority: medium
ms.collection: Strat_SP_gtc
description: eKeşif'i Microsoft 365 Multi-Geo'daki uydu konumlarında kullanmak üzere yapılandırmak için Region parametresini kullanmayı öğrenin.
ms.openlocfilehash: 640f5d4e6e8937e4dbcda1aaf2cfe48bf3d5ab22
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67698319"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a>Microsoft 365 Multi-Geo eBulma yapılandırması

[eBulma (Premium) özellikleri](../compliance/overview-ediscovery-20.md) , çok coğrafi bölgeli bir eBulma yöneticisinin "Bölge" güvenlik filtresi kullanmak zorunda kalmadan tüm coğrafi bölgeleri aramasına olanak sağlar. Veriler, çok coğrafi kiracının merkezi konumunun Azure örneğine aktarılır.

eBulma (Premium) özellikleri olmadan, çok coğrafi kiracılı bir eBulma yöneticisi veya yöneticisi eKeşif'i yalnızca bu kiracının merkezi konumunda gerçekleştirebilecektir. Uydu konumları için eBulma özelliğinin yürütülmesini desteklemek için PowerShell aracılığıyla "Region" adlı yeni bir uyumluluk güvenlik filtresi parametresi kullanılabilir. Bu parametre, merkezi konumu Kuzey Amerika, Avrupa veya Asya Pasifik'te olan kiracılar tarafından kullanılabilir. Merkezi konumu Kuzey Amerika, Avrupa veya Asya Pasifik'te olmayan ve uydu coğrafi konumlarında eBulma gerçekleştirmesi gereken kiracılar için eBulma (Premium) önerilir.

Microsoft 365 genel yöneticisi, başkalarının eBulma gerçekleştirmesine izin vermek için eBulma Yöneticisi izinleri atamalı ve eBulma işleminin uydu konumu olarak yürütüleceği bölgeyi belirtmek üzere ilgili Uyumluluk Güvenlik Filtrelerinde bir "Bölge" parametresi atamalıdır; aksi takdirde, uydu konumu için eBulma gerçekleştirilmeyecektir. Kullanıcı başına yalnızca bir "Bölge" güvenlik filtresi desteklenir.

eBulma Yöneticisi veya Yönetici rolü belirli bir uydu konumu için ayarlandığında, eBulma Yöneticisi veya Yöneticisi yalnızca bu uydu konumunda bulunan SharePoint sitelerine ve OneDrive sitelerine karşı eBulma arama eylemleri gerçekleştirebilir. Bir eBulma Yöneticisi veya Yönetici belirtilen uydu konumu dışındaki SharePoint veya OneDrive sitelerinde arama yapmaya çalışırsa, sonuç döndürülmeyecektir. Ayrıca, uydu konumunun eBulma Yöneticisi veya Yöneticisi dışarı aktarmayı tetiklediğinde veriler o bölgenin Azure örneğine aktarılır. Bu, içeriğin denetimli kenarlıklar arasında dışarı aktarılmasına izin vermeyerek kuruluşların uyumlu kalmasına yardımcı olur.

> [!NOTE]
> Bir eBulma Yöneticisi'nin birden çok SharePoint uydu konumunda arama gerçekleştirmesi gerekiyorsa, eBulma Yöneticisi için OneDrive veya SharePoint sitelerinin bulunduğu alternatif uydu konumunu belirten başka bir kullanıcı hesabı oluşturulması gerekir.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

Bir Bölge için Uyumluluk Güvenlik Filtresi'ni ayarlamak için:

1. [Microsoft 365 Güvenlik & Uyumluluğu PowerShell'e bağlanma](/powershell/exchange/connect-to-scc-powershell)

2. Aşağıdaki sözdizimini kullanın:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   Örneğin:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

Ek parametreler ve söz dizimi için [New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) makalesine bakın.
