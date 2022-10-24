---
title: Exchange Online izlemede eBulma azaltma için hizmet önerileri
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: ''
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- scotvorg
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- admindeeplinkMAC
- admindeeplinkEXCHANGE
f1.keywords:
- NOCSH
description: Exchange Online izlemede eKeşif azaltma için hizmet danışmanları hakkında bilgi edinin.
ms.openlocfilehash: 61bc8b59cce6ff74c6633b85d915309c4c2d388a
ms.sourcegitcommit: 0ca3ab2abe07810e9b2cc2d806e3c6b9f35b146c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2022
ms.locfileid: "68685369"
---
# <a name="service-advisories-for-ediscovery-throttling-in-exchange-online-monitoring"></a>Exchange Online izlemede eBulma azaltma için hizmet önerileri

eKeşif'in kısıtlandığını bildiren yeni bir Exchange Online hizmet önerisi yayımladık. Bu hizmet önerileri, kullanıcı azaltma nedeniyle Arama ve Dışarı Aktarma'yı gönderemediğinde örneklere görünürlük sağlar.

Bu hizmet önerileri Microsoft 365 yönetim merkezi görüntülenir. Bu hizmet önerilerini görüntülemek için **Sistem Durumu**  |  **[Hizmet durumu Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=842900)** |  bölümüne gidin. Aşağıda eBulma hizmeti danışmanlığı örneği verilmişti.

![eBulma hizmeti sistem durumu ekran görüntüsü](../media/ediscovery-service-health.jpg)

## <a name="what-does-this-service-advisory-indicate"></a>Bu hizmet önerisi neleri gösteriyor?

eBulma azaltma için hizmet önerileri, Microsoft tarafından ayarlanan sınırı aşan Arama ve Dışarı Aktarma işlerinin sayısı nedeniyle yöneticileri kiracılarının kısıtlandığı konusunda bilgilendirmektedir. [Microsoft Purview](/compliance/index.yml) uyumluluk portalında eBulma arama araçlarına çeşitli sınırlar uygulanır. Buna [İçerik Arama](/compliance/search-for-content) sayfasında çalıştırılacak aramalar ve eBulma [(Standart)](/compliance/get-started-core-ediscovery) sayfasında eBulma olayıyla ilişkili aramalar dahildir. Bu sınırlar, kuruluşlara sağlanan hizmetlerin durumunu ve kalitesini korumaya yardımcı olur. Bu öneriler, eBulma aramalarını ve dışarı aktarmalarını planlarken, çalıştırırken ve sorun giderirken bu sınırları dikkate alabilmeniz için farkındalık sağlar.

Microsoft Purview eKeşif (Standart) aracıyla ilgili sınırlar [için uyumluluk merkezindeki İçerik arama ve eBulma (Standart) sınırları bölümüne](/compliance/limits-for-content-search?viewFallbackFrom=o365-worldwide%20for%20service%20limits) bakın.

### <a name="how-often-will-i-see-these-service-advisories"></a>Bu hizmet önerilerini ne sıklıkta göreceğim?

Arama ve Dışarı Aktarma işlerinin tanımlı sınır içinde olduğu zamana kadar bu tür bir öneri görmeyi bekleyebilirsiniz.

## <a name="more-information"></a>Daha fazla bilgi

- eBulma uyumluluğu sorunlarını giderme ve çözme hakkında bilgi için bkz. [Microsoft Purview sorunlarını giderme](/troubleshoot/microsoft-365-compliance-welcome).
- Microsoft Purview hakkında bilgi için bkz. [Microsoft Purview nedir?](/purview/purview)
- Microsoft Purview eKeşif çözümleri hakkında daha fazla bilgi edinmek için bkz. [Microsoft Purview eKeşif çözümleri](/compliance/ediscovery)
