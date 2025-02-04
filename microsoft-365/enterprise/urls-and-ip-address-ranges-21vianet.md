---
title: 21Vianet tarafından sağlanan Office 365 için URL'ler ve IP adresi aralıkları
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 07/28/2022
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Strat_O365_Enterprise
search.appverid:
- GMA150
- GPA150
- GEA150
ms.assetid: 5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
description: Bu makalede, Çin'de 21Vianet tarafından çalıştırıldığında Office 365 için URL'ler ve IP adresi aralıkları listelenir.
hideEdit: true
ms.openlocfilehash: 477b3918f7a4d86628efd1a23a45c97e80e10e74
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68199053"
---
# <a name="urls-and-ip-address-ranges-for-office-365-operated-by-21vianet"></a>21Vianet tarafından sağlanan Office 365 için URL'ler ve IP adresi aralıkları

 *Şunlar için geçerlidir: 21Vianet tarafından sağlanan Office 365 - Küçük İşletme Yönetici, 21Vianet tarafından sağlanan Office 365 - Yönetici*

**Özet**: Aşağıdaki uç noktalar (FQDN'ler, bağlantı noktaları, URL'ler, IPv4 ve IPv6 ön ekleri) 21 Vianet tarafından sağlanan Office 365 için geçerlidir ve yalnızca bu planları kullanan kuruluşlara üretkenlik hizmetleri sunmak üzere tasarlanmıştır.
  
 **Office 365 uç noktaları:** *21 Vianet* |  [Office 365 ABD Kamu DoD](microsoft-365-u-s-government-dod-endpoints.md) |  Office 365 ABD [Kamu GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) tarafından sağlanan [dünya çapında (GCC dahil)](urls-and-ip-address-ranges.md)  |  Office 365 |
  
**Son güncelleştirme:** 28.07.2022 - ![RSS.](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Günlük aboneliğini değiştir](https://endpoints.office.com/version/China?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)

**İndirin:** tüm gerekli ve isteğe bağlı hedeflerin [JSON olarak biçimlendirilmiş](https://endpoints.office.com/endpoints/China?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) bir listesi.

Bu verileri kullanarak ağ bağlantısını yönetmeye yönelik önerilerimizi anlamak için [Office 365 uç noktalarını yönetme](managing-office-365-endpoints.md) ile başlayın. Uç nokta verileri, etkin olmadan 30 gün önce yayınlanan yeni IP Adresleri ve URL'ler ile her ayın başında gerektiği gibi güncelleştirilir. Bu, henüz otomatik güncelleştirmelere sahip olmayan müşterilerin, yeni bağlantı gerekmeden önce işlemlerini tamamlamalarına olanak tanır. Destek artışlarını, güvenlik olaylarını veya diğer acil operasyonel gereksinimleri ele almak için gerekirse uç noktalar da ay boyunca güncelleştirilebilir. Aşağıdaki bu sayfada gösterilen verilerin tümü REST tabanlı web hizmetlerinden oluşturulmuştur. Bu verilere erişmek için bir betik veya bir ağ cihazı kullanıyorsanız, doğrudan [Web hizmetine](microsoft-365-ip-web-service.md) gitmelisiniz.

Aşağıdaki uç nokta verileri, kullanıcının makinesinden Office 365 bağlantı gereksinimlerini listeler. Microsoft'tan bir müşteri ağına giden ve bazen karma veya gelen ağ bağlantıları olarak adlandırılan ağ bağlantılarını içermez.

Uç noktalar dört hizmet alanında gruplandırılır. İlk üç hizmet alanı, bağlantı için bağımsız olarak seçilebilir. Dördüncü hizmet alanı ortak bir bağımlılıktır (Microsoft 365 Ortak ve Office olarak adlandırılır) ve her zaman ağ bağlantısı olmalıdır.

Gösterilen veri sütunları şunlardır:

- **Kimlik**: Uç nokta kümesi olarak da bilinen satırın kimlik numarası. Bu kimlik, uç nokta kümesi için web hizmeti tarafından döndürülen kimlikle aynıdır.

- **Kategori**: Uç nokta kümesinin "İyileştir", "İzin Ver" veya "Varsayılan" olarak kategorilere ayrılmış olup olmadığını gösterir. Bu kategoriler ve bunların yönetimine yönelik kılavuzlar hakkında bilgi edinmek için adresinden [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md)bilgi edinebilirsiniz. Bu sütun ayrıca ağ bağlantısına sahip olmak için hangi uç nokta kümelerinin gerekli olduğunu da listeler. Ağ bağlantısına sahip olması gerekmeyen uç nokta kümeleri için, uç nokta kümesi engellenirse hangi işlevlerin eksik olacağını belirtmek için bu alanda notlar sağlarız. Bir hizmet alanının tamamını hariç tutuyorsanız, gerekli olarak listelenen uç nokta kümeleri bağlantı gerektirmez.

- **HATA**: Uç nokta kümesi, Office 365 yol önekleriyle Azure ExpressRoute üzerinden destekleniyorsa bu **Evet**'tir. Gösterilen yol öneklerini içeren BGP topluluğu, listelenen hizmet alanıyla hizalanır. HATA **Hayır** olduğunda, ExpressRoute'un bu uç nokta kümesi için desteklenmediği anlamına gelir. Ancak, HATA’nın **Hayır** olduğu bir uç nokta kümesi için hiçbir yolun tanıtılmadığı varsayılmamalıdır.

- **Adresler**: Uç nokta kümesi için FQDN'leri veya joker alan adlarını ve IP Adresi aralıklarını listeler. IP Adresi aralığının CIDR biçiminde olduğunu ve belirtilen ağda birçok bağımsız IP Adresi içerebileceğini unutmayın.
 
- **Bağlantı Noktaları**: Ağ uç noktasını oluşturmak için Adreslerle birleştirilen TCP veya UDP bağlantı noktalarını listeler. Listelenen farklı bağlantı noktalarının bulunduğu IP Adresi aralıklarında bazı yinelemeler görebilirsiniz.

[!INCLUDE [Office 365 operated by 21Vianet endpoints](../includes/office-365-operated-by-21vianet-endpoints.md)]