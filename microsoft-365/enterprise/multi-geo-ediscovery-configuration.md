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
ms.openlocfilehash: f46699221c257319dbe9bba356c9487e74d0dd2a
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68804402"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a>Microsoft 365 Multi-Geo eBulma yapılandırması

[eBulma (Premium) özellikleri](../compliance/overview-ediscovery-20.md) , Multi-Geo eBulma yöneticisinin bir "Bölge" güvenlik filtresi kullanmak zorunda kalmadan tüm _Coğrafyalarda_ arama gerçekleştirmesine olanak sağlar. Veriler, çok coğrafi _kiracılı kiracının_ _Birincil Sağlanan Coğrafya_ konumunun Azure örneğine aktarılır.

eBulma (Premium) özellikleri olmadan, Bir Multi-Geo _Kiracısının_ eBulma yöneticisi veya yöneticisi eBulma'yı yalnızca bu _Kiracının_ _Birincil Sağlanan Coğrafya_ konumunda gerçekleştirebilecektir. _Uydu Coğrafya_ konumları için eBulma özelliğinin yürütülmesini desteklemek için PowerShell aracılığıyla "Region" adlı yeni bir uyumluluk güvenlik filtresi parametresi kullanılabilir. Bu parametre _, Birincil Sağlanan Coğrafya_ konumu Kuzey Amerika, Avrupa veya Asya Pasifik'te olan _Kiracılar_ tarafından kullanılabilir. _Birincil Sağlanan Coğrafya_ konumu Kuzey Amerika, Avrupa veya Asya Pasifik'te olmayan ve _Uydu Coğrafya_ konumlarında eBulma gerçekleştirmesi gereken _Kiracılar_ için eBulma (Premium) önerilir.

Microsoft 365 genel yöneticisinin, başkalarının eBulma gerçekleştirmesine izin vermek için eBulma Yöneticisi izinleri ataması ve eBulma'yı _Uydu Coğrafya_ konumu olarak yürütmek için _Coğrafyayı_ belirtmek üzere geçerli Uyumluluk Güvenlik Filtresinde bir "Bölge" parametresi ataması gerekir; aksi takdirde _, Uydu Coğrafya_ konumu için eBulma işlemi gerçekleştirilmeyecektir. Kullanıcı başına yalnızca bir "Bölge" güvenlik filtresi desteklenir.

eBulma Yöneticisi veya Yönetici rolü belirli bir _Uydu Coğrafya_ konumu için ayarlandığında, eBulma Yöneticisi veya Yöneticisi yalnızca o _Uydu Coğrafya_ konumunda bulunan SharePoint sitelerine ve OneDrive sitelerine karşı eBulma arama eylemleri gerçekleştirebilir. Bir eBulma Yöneticisi veya Yönetici belirtilen _Uydu Coğrafya_ konumu dışındaki SharePoint veya OneDrive sitelerinde arama yapmaya çalışırsa hiçbir sonuç döndürülmeyecektir. Ayrıca, _uydu coğrafya_ konumunun eBulma Yöneticisi veya Yöneticisi dışarı aktarma işlemini tetiklediğinde veriler o bölgenin Azure örneğine aktarılır. Bu, içeriğin denetimli kenarlıklar arasında dışarı aktarılmasına izin vermeyerek kuruluşların uyumlu kalmasına yardımcı olur.

> [!NOTE]
> Bir eBulma Yöneticisinin birden çok SharePoint _Uydu Coğrafyası_ konumunda arama gerçekleştirmesi gerekiyorsa, eBulma Yöneticisi için OneDrive veya SharePoint sitelerinin bulunduğu alternatif _Uydu Coğrafya_ konumunu belirten başka bir kullanıcı hesabı oluşturulması gerekir.

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
